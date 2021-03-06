---
title: Métodos de representación y ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: e3d21be1658d6f638ef8af9abd1f1241c2f459ae
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48104155"
---
# <a name="rendering-and-execution-methods"></a>Métodos de representación y ejecución
  Puede utilizar estos métodos para administrar la ejecución de elementos, el almacenamiento en memoria caché y la representación de informes.  
  
|Método|Acción|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|Invalida la memoria caché para un elemento.|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|Devuelve la configuración de la memoria caché para un elemento y la configuración que describe cuándo expira la copia del elemento en la memoria caché.|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|Devuelve la opción de ejecución y los valores asociados para un elemento individual.|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|Devuelve una lista de valores de ejecución admitidos.|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|Procesa el informe especificado y lo representa en un formato especificado.|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|Configura un elemento para el almacenamiento en memoria caché y proporciona la configuración que especifica cuándo expira la copia del elemento en la memoria caché.|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|Establece las opciones de ejecución y las propiedades de ejecución asociadas para un elemento especificado.|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|Genera una instantánea de ejecución de elemento para un elemento especificado.|  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Servicio web del servidor de informes](../report-server-web-service.md)   
 [Métodos del servicio web del servidor de informes](report-server-web-service-methods.md)   
 [Referencia técnica &#40;SSRS&#41;](../../technical-reference-ssrs.md)  
  
  
