---
title: Crear un atributo basado en dominio (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 1c1dc3110f35d79d0e100ac90b52b303b0e750fb
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48158345"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a>Crear un atributo basado en dominio (complemento MDS para Excel)
  En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], los administradores pueden crear un atributo basado en dominio si quieren restringir los valores de una columna a un conjunto específico de valores.  
  
 Los valores pueden estar ya en la hoja de cálculo o pueden proceder de una entidad existente.  
  
> [!NOTE]  
>  Si los usuarios escriben un valor en la columna restringida, en lugar de seleccionarlo de la lista, se muestran errores en la columna **$InputStatus$** al publicar.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento:  
  
-   Debe disponer del permiso para tener acceso a las áreas funcionales del **Explorador** y de **Administración del sistema** .  
  
-   Debe ser administrador de modelo. Para obtener más información, vea [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).  
  
-   El modelo y la entidad deben existir.  
  
### <a name="to-perform-this-procedure"></a>Para realizar este procedimiento:  
  
1.  En Excel, cargue la entidad que contenga la columna (atributo) que vaya a restringir. Para obtener más información, consulte [cargar datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).  
  
2.  Haga clic en cualquier celda en la columna que vaya a restringir.  
  
3.  En el grupo **Compilar modelo** , haga clic en **Propiedades de atributo**.  
  
4.  En el cuadro de diálogo **Propiedades de atributo** , en la lista **Tipo de atributo** , elija **Lista restringida (basada en dominio)**.  
  
5.  En la lista **Rellenar el atributo con valores de** :  
  
    -   Para usar valores de la hoja de cálculo, elija **la columna seleccionada**. Se creará una nueva entidad y una tabla de ensayo con los valores de la columna seleccionada.  
  
    -   Para usar valores de una entidad existente, elija el nombre de la entidad.  
  
6.  Si elige **la columna seleccionada** en el paso anterior, en el cuadro **Nuevo nombre de entidad** , escriba un nombre para la nueva entidad. Puede ser el mismo que el nombre de la columna (atributo).  
  
7.  Haga clic en **Aceptar**. Cada celda de la columna tiene ahora una lista de valores para que los usuarios elijan.  
  
## <a name="next-steps"></a>Pasos siguientes  
  
-   Para agregar y eliminar los valores en la lista restringida, cargue la entidad en la que el atributo se basa. Para obtener más información sobre la carga de entidades, vea [cargar datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Atributos basados en dominio &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md)   
 [Crear una entidad &#40;Complemento MDS para Excel&#41;](create-an-entity-mds-add-in-for-excel.md)   
 [Generar un modelo &#40;complemento MDS para Excel&#41;](building-a-model-mds-add-in-for-excel.md)  
  
  
