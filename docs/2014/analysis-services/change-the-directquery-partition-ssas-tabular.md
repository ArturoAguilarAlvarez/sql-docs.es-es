---
title: Cambiar la partición de DirectQuery (SSAS Tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b247bd63087003b1c9205719a6d1cb0563390cc3
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48161551"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a>Cambiar la partición DirectQuery (SSAS Tabular)
  Dado que únicamente se puede designar una partición de una tabla como la partición DirectQuery, Analysis Services utiliza de forma predeterminada la primera partición que se creó en la tabla. Durante la creación del proyecto de modelos, puede cambiar la partición DirectQuery utilizando el cuadro de diálogo Administrador de particiones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Para los modelos implementados, puede cambiar la partición DirectQuery utilizando [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a>Cambiar la partición de DirectQuery para un proyecto de modelos tabular  
  
1.  En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el diseñador de modelos, haga clic en la tabla (pestaña) que contiene la tabla con particiones.  
  
2.  Haga clic en el menú **Tabla** y en **Particiones**.  
  
3.  En el **Administrador de particiones**, la partición asignada como la partición DirectQuery actual incluye el prefijo **(DirectQuery)** en el nombre de partición.  
  
     Seleccione otra partición en la lista **Particiones** y haga clic en **Establecer como DirectQuery**. El botón **Establecer como DirectQuery** no está habilitado si está seleccionada la partición DirectQuery actual, y no está visible si el modelo no se ha habilitado para el modo de consulta directa.  
  
4.  Si es necesario, cambie las opciones de procesamiento y, a continuación, haga clic en **Aceptar**.  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a>Cambiar la partición de DirectQuery para un modelo tabular implementado  
  
1.  En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], abra la base de datos del modelo en el Explorador de objetos.  
  
2.  Expanda el nodo **Tablas** , haga clic con el botón derecho en la tabla con particiones y, después, seleccione **Particiones**.  
  
     La partición designada para su uso con el modo DirectQuery tiene el prefijo (DirectQuery) en el nombre de partición.  
  
3.  Para cambiar a una partición diferente, haga clic en el icono **Consulta directa** de la barra de herramientas para abrir el cuadro de diálogo **Establecer partición DirectQuery** . El icono de la barra de herramientas de DirectQuery no está disponible en los modelos no habilitados para la consulta directa.  
  
4.  Elija una partición diferente en la lista desplegable **Nombre de partición** y, a continuación, cambie las opciones de procesamiento de la partición si es necesario.  
  
## <a name="see-also"></a>Vea también  
 [Las particiones &#40;Tabular de SSAS&#41;](tabular-models/partitions-ssas-tabular.md)  
  
  
