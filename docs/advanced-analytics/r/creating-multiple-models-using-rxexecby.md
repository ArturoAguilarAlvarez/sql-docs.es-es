---
title: Creación de varios modelos mediante rxExecBy (SQL Server Machine Learning) | Microsoft Docs
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: b83abad65689e3e12310251d09199f5aa0e7c3cb
ms.sourcegitcommit: 0d6e4cafbb5d746e7d00fdacf8f3ce16f3023306
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49085131"
---
# <a name="creating-multiple-models-using-rxexecby"></a>Crear varios modelos mediante rxExecBy
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

SQL Server 2017 CTP 2.0 incluye una nueva función, **rxExecBy**, que admite el procesamiento paralelo de varios modelos relacionados. En lugar de "Train" una gran modelo según los datos de varias entidades similar, los científicos de datos pueden crear rápidamente varios modelos relacionados, cada uno con los datos específicos de una sola entidad.

Por ejemplo, supongamos que está supervisando los errores de dispositivo y captura de datos para muchos tipos diferentes de los equipos. Mediante el uso de rxExecBy, puede proporcionar un único conjunto de datos grande como entrada, especificar una columna en la que se va a estratificar el conjunto de datos, como el tipo de dispositivo y, a continuación, crear varios modelos de dispositivos individuales.

Este proceso ha se denomina procesamiento "pleasingly paralelo", porque toma una tarea que era un poco onerosos para los científicos de datos o en el mejor tedioso y hace que una operación rápida y sencilla.

Las aplicaciones típicas de este enfoque incluyen la previsión de los medidores inteligentes domésticos individuales, creación de las proyecciones de ingresos para las líneas de producto independiente o modelos para las aprobaciones de préstamo que se adaptan a las ramas de banco individuales.

## <a name="how-rxexec-works"></a>Cómo funciona rxExec

La función rxExecBy en RevoScaleR está diseñada para grandes volúmenes de procesamiento a través de un gran número de conjuntos de datos pequeños en paralelo.

1. Llame a la función rxExecBy como parte del código de R y pasar un conjunto de datos de los datos no ordenados.
2. Especificar la partición por la que deberían agruparse y ordenarse los datos.
3. Definir una transformación o función que se debe aplicar a cada partición de datos de modelado
4. Cuando se ejecuta la función, se procesan las consultas de datos en paralelo si su entorno lo admite. Además, las tareas de modelado o transformación se distribuyen entre núcleos individuales y a ejecutar en paralelo. Contexto de proceso admitidos para las tres operaciones incluyen RxSpark y RxInSQLServer.
5. Se devuelven varios resultados.

## <a name="rxexecby-syntax-and-examples"></a>rxExecBy sintaxis y ejemplos

**rxExecBy** toma cuatro entradas, una de las entradas que se va a un objeto de origen de datos o conjunto de datos que se puede crear particiones en un determinado **clave** columna. La función devuelve una salida para cada partición. El formato de la salida depende de la función que se pasa como argumento, por ejemplo, si se pasa una función de modelado como rxLinMod, podría devolver un modelo entrenado independiente para cada partición del conjunto de datos.

### <a name="supported-functions"></a>Funciones admitidas

Modelado: `rxLinMod`, `rxLogit`, `rxGlm`, `rxDtree`

Puntuación: `rxPredict`,

Transformación o análisis: `rxCovCor`

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo crear varios modelos utilizando el conjunto de datos de líneas aéreas, que se crean particiones en la columna [DayOfWeek]. La función definida por el usuario, `delayFunc`, se aplica a cada una de las particiones mediante rxExecBy que realiza la llamada. La función crea modelos independientes para los lunes, el martes, y así sucesivamente.

```SQL
EXEC sp_execute_external_script
@language = N'R'
, @script = N'
delayFunc <- function(key, data, params) { 
    df <- rxImport(inData = airlineData) 
    rxLinMod(ArrDelay ~ CRSDepTime, data = df) 
} 
OutputDataSet <- rxExecBy(airlineData, c("DayOfWeek"), delayFunc)
'
, @input_data_1 = N'select ArrDelay, DayOfWeek, CRSDepTime from AirlineDemoSmall]'
, @input_data_1_name = N'airlineData'

```

Si se produce un error, `varsToPartition is invalid`, compruebe si el nombre de la columna de clave o columnas se ha escrito correctamente. El lenguaje R distingue mayúsculas de minúsculas.

Tenga en cuenta que este ejemplo no está optimizado para SQL Server y en muchos casos podría lograr un mejor rendimiento con SQL para agrupar los datos. Sin embargo, mediante rxExecBy, puede crear trabajos paralelos de R.

El ejemplo siguiente ilustra el proceso en R con SQL Server como contexto de proceso:

```R
sqlServerConnString <- "SERVER=hostname;DATABASE=TestDB;UID=DBUser;PWD=Password;"
inTable <- paste("airlinedemosmall")
sqlServerDataDS <- RxSqlServerData(table = inTable, connectionString = sqlServerConnString)

# user function
".Count" <- function(keys, data, params)
{
  myDF <- rxImport(inData = data)
  return (nrow(myDF))
}

# Set SQL Server compute context with level of parallelism = 2
sqlServerCC <- RxInSqlServer(connectionString = sqlServerConnString, numTasks = 4)
rxSetComputeContext(sqlServerCC)

# Execute rxExecBy in SQL Server compute context
sqlServerCCResults <- rxExecBy(inData = sqlServerDataDS, keys = c("DayOfWeek"), func = .Count)
```


