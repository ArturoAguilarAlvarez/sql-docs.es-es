---
title: MSSQL_ENG021330 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 05a2b45668efdd1bcef6b30e009d8248cb96e2be
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47620981"
---
# <a name="mssqleng021330"></a>MSSQL_ENG021330
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="message-details"></a>Detalles del mensaje  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|21330|  
|Origen del evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nombre simbólico||  
|Texto del mensaje|No se pudo crear un subdirectorio bajo el directorio de trabajo de replicación.(%1!)|  
  
## <a name="explanation"></a>Explicación  
 Este error se puede producir cuando una suscripción se inicializa manualmente y hay un problema para crear el directorio en el que se almacenan los scripts de replicación. Este error puede deberse a un problema de permisos: cuando se inicializa una suscripción sin utilizar una instantánea, la cuenta con la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el publicador debe tener permisos de escritura para la carpeta de la instantánea en el distribuidor.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe que se ha especificado la ruta de acceso correcta para la carpeta de instantáneas y que la cuenta con la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el publicador dispone de permisos suficientes.  
  
## <a name="see-also"></a>Ver también  
 [Specify the Default Snapshot Location &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/specify-the-default-snapshot-location-sql-server-management-studio.md)  (Especificar la ubicación predeterminada de instantáneas [SQL Server Management Studio])  
 [Referencia de errores y eventos &#40;replicación&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)   
 [Initialize a Transactional Subscription Without a Snapshot](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md) (Inicializar una suscripción transaccional sin una instantánea)  
  
  
