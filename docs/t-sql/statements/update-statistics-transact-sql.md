---
title: "Actualizar estadísticas (Transact-SQL) | Documentos de Microsoft"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- UPDATE STATISTICS
- UPDATE_STATISTICS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- updating statistics
- query optimization statistics [SQL Server], updating
- UPDATE STATISTICS statement
- statistical information [SQL Server], updating
ms.assetid: 919158f2-38d0-4f68-82ab-e1633bd0d308
caps.latest.revision: 74
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5a1b053ddc09876717f0fbf34b2d7c294988162f
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="update-statistics-transact-sql"></a>UPDATE STATISTICS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Actualiza las estadísticas de optimización de consulta para una tabla o vista indizada. De forma predeterminada, el optimizador de consultas ya actualiza las estadísticas como requisito para mejorar el plan de consulta; en algunos casos puede mejorar el rendimiento de las consultas utilizando UPDATE STATISTICS o el procedimiento almacenado [sp_updatestats](../../relational-databases/system-stored-procedures/sp-updatestats-transact-sql.md) para actualizar las estadísticas con más frecuencia que las actualizaciones de forma predeterminada.  
  
 La actualización de las estadísticas asegura que las consultas se compilan con estadísticas actualizadas. Sin embargo, la actualización de las estadísticas hace que las consultas se vuelvan a compilar. Recomendamos no actualizar las estadísticas con demasiada frecuencia, porque hay que elegir el punto válido entre la mejora de los planes de consulta y el tiempo empleado en volver a compilar las consultas. Las compensaciones específicas dependen de su aplicación. UPDATE STATISTICS puede usar tempdb para ordenar la muestra de filas con fines de creación de estadísticas.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
UPDATE STATISTICS table_or_indexed_view_name   
    [   
        {   
            { index_or_statistics__name }  
          | ( { index_or_statistics_name } [ ,...n ] )   
                }  
    ]   
    [    WITH   
        [  
            FULLSCAN   
              [ [ , ] PERSIST_SAMPLE_PERCENT = { ON | OFF } ]    
            | SAMPLE number { PERCENT | ROWS }   
              [ [ , ] PERSIST_SAMPLE_PERCENT = { ON | OFF } ]    
            | RESAMPLE   
              [ ON PARTITIONS ( { <partition_number> | <range> } [, …n] ) ]  
            | <update_stats_stream_option> [ ,...n ]  
        ]   
        [ [ , ] [ ALL | COLUMNS | INDEX ]   
        [ [ , ] NORECOMPUTE ]   
        [ [ , ] INCREMENTAL = { ON | OFF } ]  
    ] ;  
  
<update_stats_stream_option> ::=  
    [ STATS_STREAM = stats_stream ]  
    [ ROWCOUNT = numeric_constant ]  
    [ PAGECOUNT = numeric_contant ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
UPDATE STATISTICS schema_name . ] table_name   
    [ ( { statistics_name | index_name } ) ]  
    [ WITH   
       {  
              FULLSCAN   
            | SAMPLE number PERCENT   
            | RESAMPLE   
        }  
    ]  
[;]  
```  
  
## <a name="arguments"></a>Argumentos  
 *table_or_indexed_view_name*  
 Es el nombre de la tabla o vista indizada que contiene el objeto de estadísticas.  
  
 *index_or_statistics_name*  
 Es el nombre del índice cuyas estadísticas se van a actualizar o el nombre de las estadísticas que actualizar. Si *index_or_statistics_name* no se especifica, el optimizador de consultas actualiza todas las estadísticas de la tabla o vista indizada. Esto incluye las estadísticas creadas usando la instrucción CREATE STATISTICS en las columnas, las estadísticas de columna única creadas cuando se usa AUTO_CREATE_STATISTICS y las estadísticas creadas para los índices.  
  
 Para obtener más información acerca de AUTO_CREATE_STATISTICS, vea [ALTER DATABASE SET Options &#40; Transact-SQL &#41; ](../../t-sql/statements/alter-database-transact-sql-set-options.md). Para ver todos los índices de una tabla o vista, puede usar [sp_helpindex](../../relational-databases/system-stored-procedures/sp-helpindex-transact-sql.md).  
  
 FULLSCAN  
 Para calcular las estadísticas, examine todas las filas de la tabla o la vista indizada. FULLSCAN y SAMPLE 100 PERCENT tienen los mismos resultados. FULLSCAN no se puede utilizar con la opción SAMPLE.  
  
 EJEMPLO *número* {% | FILAS}  
 Especifique el porcentaje aproximado o número de filas de la tabla o vista indizada que el optimizador de consultas usará al actualizar las estadísticas. En PERCENT, *número* puede estar comprendido entre 0 y 100 y para las filas, *número* puede oscilar entre 0 y el número total de filas. El porcentaje o número de filas real de los ejemplos del optimizador de consultas podría no coincidir con el porcentaje o el número especificado. Por ejemplo, el optimizador de consultas examina todas las filas en una página de datos.  
  
 SAMPLE es útil para casos especiales en el que el plan de consulta, basado en el muestreo predeterminado, no es óptimo. En la mayoría de las situaciones, no es necesario especificar SAMPLE porque el optimizador de consultas utiliza el muestreo y determina el tamaño de muestra estadísticamente significativo de forma predeterminada, tal y como se exige para crear planes de consulta de alta calidad. 
 
A partir de [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)], muestreo de datos para generar estadísticas se realiza en paralelo, cuando se usa el nivel de compatibilidad 130, para mejorar el rendimiento de recopilación de estadísticas. El optimizador de consultas usará las estadísticas de ejemplo paralelas, cada vez que un tamaño de la tabla supera un cierto umbral. 
   
 SAMPLE no se puede utilizar con la opción FULLSCAN. Cuando no se especifica SAMPLE ni FULLSCAN, el optimizador de consultas utiliza los datos muestreados y calcula el tamaño de la muestra de forma predeterminada.  
  
 Recomendamos no especificar 0 PERCENT ni 0 ROWS. Cuando se especifican 0 PERCENT o ROWS, el objeto de estadísticas se actualiza pero no contiene datos de estadísticas.  
  
 Para la mayoría de las cargas de trabajo, no se requiere un examen completo y muestreo predeterminado es el adecuado.  
Sin embargo, ciertas cargas de trabajo que son sensibles a muy diferentes distribuciones de datos pueden requerir un tamaño de muestra mayor, o incluso un examen completo.  
Para obtener más información, consulte el [blog de CSS SQL Escalation Services](http://blogs.msdn.com/b/psssql/archive/2010/07/09/sampling-can-produce-less-accurate-statistics-if-the-data-is-not-evenly-distributed.aspx).  
  
 RESAMPLE  
 Se actualiza cada estadística utilizando su velocidad de muestra más reciente.  
  
 El uso de RESAMPLE puede producir un recorrido de tabla completo. Por ejemplo, las estadísticas de los índices utilizan un recorrido de tabla completo como su velocidad de muestra. Cuando no se especifica ninguna de las opciones de muestreo (SAMPLE, FULLSCAN ni RESAMPLE), el optimizador de consultas muestrea los datos y calcula el tamaño de la muestra de forma predeterminada.  

PERSIST_SAMPLE_PERCENT = {ON | {OFF}  
Cuando **ON**, las estadísticas conservará el porcentaje de muestreo de conjunto para las actualizaciones posteriores que no especifican explícitamente un porcentaje de muestreo. Cuando **OFF**, porcentaje de muestreo de las estadísticas se restablecería a muestreo predeterminado en actualizaciones posteriores que no especifican explícitamente un porcentaje de muestreo. El valor predeterminado es **OFF**. 
 
 > [!NOTE]
 > Si se ejecuta AUTO_UPDATE_STATISTICS, utiliza el porcentaje de muestreo persistente si está disponible, o usar el porcentaje de muestreo predeterminado si no.
 > Volver a MUESTREAR comportamiento no se ve afectado por esta opción.
 
 > [!TIP] 
 > [DBCC SHOW_STATISTICS](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md) y [sys.dm_db_stats_properties](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-properties-transact-sql.md) exponer el valor de porcentaje de ejemplo persistente para la estadística seleccionada.
 
 **Se aplica a**: [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] SP1 CU4.  
 
 EN las particiones ({ \<número_de_partición > | \<intervalo >} [,... n]) ] Fuerza las estadísticas de nivel de hoja que abarcan las particiones especificadas en la cláusula ON PARTITIONS se vuelven a calcular y, a continuación, se combinen para generar las estadísticas globales. WITH RESAMPLE es necesario porque no se pueden combinar estadísticas de partición generadas con distintas frecuencias de muestreo.  
  
**Se aplica a**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] a través de[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]
  
 ALL | COLUMNS | INDEX  
 Actualice todas las estadísticas existentes, las estadísticas creadas en una o más columnas, o las estadísticas creadas para los índices. Si no se especifica ninguna de las opciones, la instrucción UPDATE STATISTICS actualiza todas las estadísticas en la tabla o vista indizada.  
  
 NORECOMPUTE  
 Deshabilite la opción automática de actualización de las estadísticas, AUTO_UPDATE_STATISTICS, para las estadísticas especificadas. Si se especifica esta opción, el optimizador de consultas completa esta actualización de estadísticas y deshabilita las actualizaciones futuras.  
  
 Para volver a habilitar el comportamiento de la opción AUTO_UPDATE_STATISTICS, vuelva a ejecutar UPDATE STATISTICS sin la opción NORECOMPUTE o ejecute **sp_autostats**.  
  
> [!WARNING]  
>  Utilizar esta opción puede producir planes de consulta poco óptimos. Se recomienda usar esta opción con moderación y que lo haga únicamente un administrador de sistemas cualificado.  
  
 Para obtener más información acerca de la opción AUTO_UPDATE_STATISTICS, consulte [ALTER DATABASE SET Options &#40; Transact-SQL &#41; ](../../t-sql/statements/alter-database-transact-sql-set-options.md).  
  
 INCREMENTAL = { ON | OFF }  
 Cuando **ON**, las estadísticas se vuelven a crear como estadísticas por partición. Cuando **OFF**, se quita el árbol de estadísticas y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vuelve a calcular las estadísticas. El valor predeterminado es **OFF**.  
  
 Si no se admiten las estadísticas por partición, se genera un error. Las estadísticas incrementales no se admiten para los siguientes tipos de estadísticas:  
  
-   Estadísticas creadas con índices que no están alineados por partición con la tabla base.  
  
-   Estadísticas creadas sobre bases de datos secundarias legibles AlwaysOn.  
  
-   Estadísticas creadas sobre bases de datos de solo lectura.  
  
-   Estadísticas creadas sobre índices filtrados.  
  
-   Estadísticas creadas sobre vistas.  
  
-   Estadísticas creadas sobre tablas internas.  
  
-   Estadísticas creadas con índices espaciales o índices XML.  
  
**Se aplica a**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] a través de[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]
  
 \<update_stats_stream_option >[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="when-to-use-update-statistics"></a>Cuándo utilizar UPDATE STATISTICS  
 Para obtener más información acerca de cuándo utilizar UPDATE STATISTICS, vea [estadísticas](../../relational-databases/statistics/statistics.md).  
  
## <a name="updating-all-statistics-with-spupdatestats"></a>Actualizar todas las estadísticas con sp_updatestats  
 Para obtener más información sobre cómo actualizar las estadísticas para todas las tablas internas y definidas por el usuario de la base de datos, vea el procedimiento almacenado [sp_updatestats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-updatestats-transact-sql.md). Por ejemplo, el comando siguiente llama a sp_updatestats para actualizar todas las estadísticas de la base de datos.  
  
```t-sql  
EXEC sp_updatestats;  
```  
  
## <a name="determining-the-last-statistics-update"></a>Determinar la actualización de estadísticas más reciente  
 Para saber cuándo se actualizaron las estadísticas por última vez, use la función [STATS_DATE](../../t-sql/functions/stats-date-transact-sql.md) .  
  
## <a name="pdw--sql-data-warehouse"></a>PDW / almacenamiento de datos SQL  
 La siguiente sintaxis no es compatible con PDW / almacenamiento de datos SQL  
  
```t-sql  
update statistics t1 (a,b);   
```  
  
```t-sql  
update statistics t1 (a) with sample 10 rows;  
```  
  
```t-sql  
update statistics t1 (a) with NORECOMPUTE;  
```  
  
```t-sql  
update statistics t1 (a) with INCREMENTAL=ON;  
```  
  
```t-sql  
update statistics t1 (a) with stats_stream = 0x01;  
```  
  
## <a name="permissions"></a>Permissions  
 Requiere el permiso ALTER en la tabla o la vista.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-update-all-statistics-on-a-table"></a>A. Actualizar todas las estadísticas en una tabla  
 En el ejemplo siguiente se actualiza las estadísticas de todos los índices de la `SalesOrderDetail` tabla.  
  
```t-sql  
USE AdventureWorks2012;  
GO  
UPDATE STATISTICS Sales.SalesOrderDetail;  
GO  
```  
  
### <a name="b-update-the-statistics-for-an-index"></a>B. Actualizar las estadísticas para un índice  
 En este ejemplo se actualizan las estadísticas del índice `AK_SalesOrderDetail_rowguid` de la tabla `SalesOrderDetail`.  
  
```t-sql  
USE AdventureWorks2012;  
GO  
UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;  
GO  
```  
  
### <a name="c-update-statistics-by-using-50-percent-sampling"></a>C. Actualizar las estadísticas con un muestreo del 50 %  
 En este ejemplo se crean y, después, se actualizan las estadísticas de las columnas `Name` y `ProductNumber` de la tabla `Product`.  
  
```t-sql  
USE AdventureWorks2012;  
GO  
CREATE STATISTICS Products  
    ON Production.Product ([Name], ProductNumber)  
    WITH SAMPLE 50 PERCENT  
-- Time passes. The UPDATE STATISTICS statement is then executed.  
UPDATE STATISTICS Production.Product(Products)   
    WITH SAMPLE 50 PERCENT;  
```  
  
### <a name="d-update-statistics-by-using-fullscan-and-norecompute"></a>D. Actualizar estadísticas utilizando FULLSCAN y NORECOMPUTE  
 En este ejemplo se actualizan las estadísticas de `Products` de la tabla `Product`, se exige un examen completo de todas las filas de la tabla `Product` y se desactivan las estadísticas automáticas para las estadísticas de `Products`.  
  
```t-sql  
USE AdventureWorks2012;  
GO  
UPDATE STATISTICS Production.Product(Products)  
    WITH FULLSCAN, NORECOMPUTE;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Ejemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] y[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-update-statistics-on-a-table"></a>E. Actualizar las estadísticas en una tabla  
 El siguiente ejemplo se actualiza el `CustomerStats1` estadísticas sobre la `Customer` tabla.  
  
```t-sql  
UPDATE STATISTICS Customer ( CustomerStats1 );  
```  
  
### <a name="f-update-statistics-by-using-a-full-scan"></a>F. Actualizar estadísticas mediante un examen completo  
 El siguiente ejemplo se actualiza el `CustomerStats1` estadísticas, en función de examen de todas las filas en el `Customer` tabla.  
  
```t-sql  
UPDATE STATISTICS Customer (CustomerStats1) WITH FULLSCAN;  
```  
  
### <a name="g-update-all-statistics-on-a-table"></a>G. Actualizar todas las estadísticas en una tabla  
 En el ejemplo siguiente se actualiza todas las estadísticas en el `Customer` tabla.  
  
```t-sql  
UPDATE STATISTICS Customer;  
```  
  
## <a name="see-also"></a>Vea también  
 [Estadísticas](../../relational-databases/statistics/statistics.md)   
 [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [CREATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/create-statistics-transact-sql.md)   
 [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md)   
 [DROP STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/drop-statistics-transact-sql.md)   
 [sp_autostats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md)   
 [sp_updatestats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-updatestats-transact-sql.md)   
 [STATS_DATE &#40; Transact-SQL &#41;](../../t-sql/functions/stats-date-transact-sql.md)  
 [Sys.dm_db_stats_properties &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-properties-transact-sql.md)
  
  



