---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: c3c2c479d23c85ccf66b7fbbf9575c5576b0ea10
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48202545"
---
# <a name="mssqleng014157"></a>MSSQL_ENG014157
    
## <a name="message-details"></a>Detalles del mensaje  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|14157|  
|Origen del evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nombre simbólico||  
|Texto del mensaje|La suscripción creada por el suscriptor '%1!s!' a la publicación '%2!s!' expiró y ha sido eliminada.|  
  
## <a name="explanation"></a>Explicación  
 Un suscriptor debe sincronizarse con el publicador en el tiempo especificado en el período de conservación de la publicación. Si un suscriptor no se sincroniza en este período, la suscripción expira. Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).  
  
## <a name="user-action"></a>Acción del usuario  
 La suscripción se debe volver a crear e inicializar para que el suscriptor pueda empezar a recibir cambios de datos de nuevo:  
  
-   Para obtener información sobre la creación de suscripciones, vea [Suscribirse a publicaciones](subscribe-to-publications.md).  
  
-   Para obtener información sobre la inicialización de suscripciones, vea [Initialize a Subscription](initialize-a-subscription.md) (Inicializar una suscripción).  
  
 Si la base de datos de suscripciones contiene varios cambios que no se han sincronizado con el publicador, puede usar la [tablediff Utility](../../tools/tablediff-utility.md) para determinar qué filas de las bases de datos de publicaciones y suscripciones son diferentes.  
  
 Puede aumentar el período de conservación de la publicación para evitar tener suscripciones expiradas. Tenga cuidado al establecer un valor alto porque puede provocar que se almacenen más datos y metadatos, lo que afectaría al rendimiento. Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md)  
  
  
