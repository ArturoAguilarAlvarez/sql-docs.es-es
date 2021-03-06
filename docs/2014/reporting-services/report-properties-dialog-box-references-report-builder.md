---
title: Informe de cuadro de diálogo de propiedades, las referencias (generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 6222a5bfb1efe52e2b35345e7bd6364676936b2b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48104585"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>Propiedades del informe (cuadro de diálogo), Referencias (Generador de informes)
  Seleccione **Referencias** en el cuadro de diálogo **Propiedades del informe** para agregar o quitar referencias a ensamblados personalizados u otros ensamblados externos, así como instancias de clases personalizadas que las expresiones usarán en la definición de informe. Los ensamblados personalizados no se admiten en el modo local en el Generador de informes. Para crear informes que usan los ensamblados personalizados, use el Diseñador de informes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
## <a name="options"></a>Opciones  
 **Agregar o quitar ensamblados**  
 Muestra los ensamblados a los que el informe hace referencia. El ensamblado debe estar disponible en el equipo donde está instalada la herramienta que está usando para diseñar el informe y en el servidor de informes. El nombre de la referencia debe coincidir con el contenido de  **\<CodeModule >** exactamente las etiquetas en el archivo de lenguaje de definición de informe (.rdl).  
  
 **Agregar**  
 Haga clic en esta opción para agregar un ensamblado. Haga clic en el botón del signo de puntos suspensivos (…) para abrir el cuadro de diálogo **Abrir** y seleccionar los ensamblados necesarios para completar el procesamiento del informe y la evaluación de las expresiones.  
  
 **Quitar**  
 Para quitar una referencia de ensamblado de la lista, seleccione el nombre del ensamblado y haga clic en el botón **Quitar** .  
  
 **Agregar o quitar clases**  
 Muestra las instancias de clases que se utilizan en el informe. Solo los miembros basados en instancias, no los miembros estáticos, utilizan la lista de clases.  
  
 **Agregar**  
 Haga clic en esta opción para agregar una referencia de clase. Haga clic en el botón del signo de puntos suspensivos (…) para abrir el cuadro de diálogo **Abrir** y seleccionar las clases necesarias para completar el procesamiento del informe y la evaluación de las expresiones.  
  
 **Quitar**  
 Para eliminar la instancia de clase, selecciónela y haga clic en el botón **Quitar** .  
  
 **Subir**  
 Para las clases que tienen dependencias, puede mover esta referencia hacia arriba en la lista.  
  
 **Bajar**  
 Para las clases que tienen dependencias, puede mover esta referencia hacia abajo en la lista.  
  
## <a name="see-also"></a>Vea también  
 [Ayuda del Generador de informes para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)  
  
  
