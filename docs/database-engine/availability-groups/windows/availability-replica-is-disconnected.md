---
title: Réplica de disponibilidad desconectada | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4d070f183fbe5b09016af950cfad9e6da60e90c6
ms.sourcegitcommit: 63b4f62c13ccdc2c097570fe8ed07263b4dc4df0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51605745"
---
# <a name="availability-replica-is-disconnected"></a>Réplica de disponibilidad desconectada
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Introducción  
  
|||  
|-|-|  
|**Nombre de directiva**|Estado de conexión de la réplica de disponibilidad|  
|**Problema**|La réplica de disponibilidad está desconectada.|  
|**Categoría**|**Crítico**|  
|**Faceta**|Réplica de disponibilidad|  
  
## <a name="description"></a>Descripción  
 Esta directiva comprueba el estado de conexión entre las réplicas de disponibilidad. La directiva está en mal estado cuando el estado de conexión de la réplica de disponibilidad es DISCONNECTED. De lo contrario, la directiva está en un estado correcto.  
  
> [!NOTE]  
>  Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Réplica de disponibilidad desconectada](https://go.microsoft.com/fwlink/p/?LinkId=220857) en TechNet Wiki.  
  
## <a name="possible-causes"></a>Posibles causas  
 La réplica secundaria no está conectada a la réplica principal. El estado de conexión es DISCONNECTED. Este problema puede deberse a lo siguiente:  
  
-   El puerto de conexión puede estar en conflicto con otra aplicación.  
  
-   El tipo de cifrado o el algoritmo no coinciden.  
  
-   Se ha eliminado o no se ha iniciado el extremo de la conexión.  
  
-   El transporte está desconectado.  
  
## <a name="possible-solutions"></a>Soluciones posibles  
 Las siguientes son posibles soluciones para este problema:  
  
-   Compruebe la configuración del extremo de creación de reflejo de la base de datos para las instancias de la réplica principal y secundaria, y actualice la configuración que no coincide.  
  
-   Compruebe si el puerto está en conflicto y, si en ese caso, cambie el número de puerto.  
  
## <a name="see-also"></a>Ver también  
 [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
