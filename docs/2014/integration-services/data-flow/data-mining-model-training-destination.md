---
title: Destino de Entrenamiento del modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: fdef0e0ed6de3bf527a5b87bc05a12e1bc6ace5f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48068965"
---
# <a name="data-mining-model-training-destination"></a>entrenamiento del modelo de minería de datos, destino
  El destino de Entrenamiento del modelo de minería de datos entrena los modelos de minería de datos pasando los datos que recibe el destino por los algoritmos de modelos de minería de datos. Un destino puede entrenar varios modelos de minería de datos si los modelos se generan sobre la misma estructura de minería de datos. Para obtener más información, consulte [Mining Structure Columns](../../analysis-services/data-mining/mining-structure-columns.md) y [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md).  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a>Configuración del destino de entrenamiento del modelo de minería de datos  
 Si una columna de nivel de caso de la estructura de destino y los modelos generados en la estructura tiene el tipo de contenido KEY TIME o KEY SEQUENCE, los datos de entrada se deben ordenar en esa columna. Por ejemplo, los modelos generados con el algoritmo de serie temporal de Microsoft usan el tipo de contenido KEY TIME. Si no se ordenan los datos de entrada, el procesamiento del modelo puede producir un error. Si los datos requieren que se ordenen, puede usar la transformación Ordenar en una etapa anterior del flujo de datos para ordenar los datos. Este requisito no se aplica a las columnas con el tipo de contenido KEY. Para obtener más información, vea [Tipos de contenido &#40;minería de datos&#41;](../../analysis-services/data-mining/content-types-data-mining.md) y [Transformación Ordenar](transformations/sort-transformation.md).  
  
> [!NOTE]  
>  La entrada del destino de Entrenamiento del modelo de minería de datos se debe ordenar. Para ordenar los datos, puede incluir un destino de Ordenar en dirección ascendente desde el destino de Entrenamiento del modelo de minería de datos en el flujo de datos. Para más información, consulte [Sort Transformation](transformations/sort-transformation.md).  
  
 Este destino tiene una entrada y ninguna salida.  
  
 El destino de Entrenamiento del modelo de minería de datos usa un administrador de conexiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectarse al proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene la estructura y los modelos de minería de datos que entrena el destino. Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).  
  
 Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.  
  
 Para obtener más información sobre las propiedades que se pueden establecer en el cuadro de diálogo **Editor de entrenamiento de modelos de minería de datos** , haga clic en uno de los siguientes temas:  
  
-   [Editor de entrenamiento de modelos de minería de datos &#40;ficha conexión&#41;](../data-mining-model-training-editor-connection-tab.md)  
  
-   [Editor de entrenamiento de modelos de minería de datos &#40;pestaña columnas&#41;](../data-mining-model-training-editor-columns-tab.md)  
  
 El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación. Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:  
  
-   [Common Properties](../common-properties.md)  
  
-   [Propiedades personalizadas del destino de entrenamiento del modelo de minería de datos](data-mining-model-training-destination-custom-properties.md)  
  
 Para obtener más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).  
  
  
