---
title: Prácticas recomendadas para la administración de excepciones de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 7dad2ba27f67423ae84d9b63c52f479a5ffca278
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48144535"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a>Prácticas recomendadas para la administración de excepciones de Reporting Services
  Al desarrollar aplicaciones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], hay varias metodologías disponibles para eliminar o reducir la aparición de excepciones. Cuando se producen excepciones, proporcione mensajes de error claros y concisos al usuario, y agregue una administración de excepciones adecuada para evitar que las aplicaciones finalicen inesperadamente.  
  
 Una aplicación que envía solicitudes al servicio web del servidor de informes debería:  
  
-   Evitar producir excepciones impidiendo tantas solicitudes no válidas como sea posible.  
  
-   Detectar las excepciones y, siempre que sea posible, proporcionar código de administración de errores específico.  
  
-   Tratar los casos de error que no inician excepciones.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Prevención de solicitudes no válidas](preventing-invalid-requests.md)|Describe las técnicas para evitar que las solicitudes que no sean válidas se envíen al servidor de informes.|  
|[Uso de los bloques Try/Catch](using-try-and-catch-blocks.md)|Describe cómo mejorar más la confiabilidad de una aplicación con bloques try/catch.|  
|[Administración de advertencias y casos que no producen excepciones](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|Explica cómo controlar los errores que no producen ninguna excepción que se inicie a través de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|[Uso de la propiedad Detail para administrar errores concretos](using-the-detail-property-to-handle-specific-errors.md)|Explica cómo administrar mediante programación errores concretos mediante la propiedad **Detail** del objeto **SoapException**.|  
  
## <a name="see-also"></a>Vea también  
 [Propiedad Detail](../soapexception-class/detail-property.md)   
 [Introducción a la administración de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md)   
 [Clase SoapException de Reporting Services](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
