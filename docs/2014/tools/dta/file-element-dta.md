---
title: Archivo de elemento (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1d74a576ea8d966d5c1a2c802eb42049c33a94b2
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48097715"
---
# <a name="file-element-dta"></a>File (DTA, elemento)
  Especifica el archivo de carga de trabajo. Una carga de trabajo es un conjunto de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecuta en una o varias bases de datos que se desean optimizar. Los archivos de carga de trabajo pueden ser scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] (.sql) o archivos de seguimiento (.trc). Para más información, consulte [Iniciar y utilizar el Asistente para la optimización de motor de base de datos](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|**Tipo y longitud de los datos**|Utilice el tipo de datos `string` para especificar la ruta de acceso del directorio al archivo de carga de trabajo. Por ejemplo:<br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> El servidor aplica el límite de longitud.|  
|**Valor predeterminado**|Ninguno.|  
|**Repetición**|Una obligatoria si no se especifica ningún otro tipo de carga de trabajo. Es necesario especificar un elemento secundario **EventString**, **File**o **Database** para el elemento primario **Workload** , aunque solo se puede utilizar un tipo. Por ejemplo, si se especifica una carga de trabajo con el elemento **File** , no se puede especificar una carga de trabajo con el elemento **Database** en el mismo archivo de entrada XML.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elementos|  
|------------------|--------------|  
|**Elemento primario**|[Elemento de la carga de trabajo &#40;DTA&#41;](workload-element-dta.md)|  
|**Elementos secundarios**|Ninguno.|  
  
## <a name="example"></a>Ejemplo  
 Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
