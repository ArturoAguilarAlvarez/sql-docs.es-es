---
title: Conexión al servidor (Oracle) y propiedades de conexión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f675a41138121a017096c1025698d34529468f49
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48180095"
---
# <a name="connect-to-server-oracle-connection-properties"></a>Conectar al servidor (Oracle), Propiedades de conexión
  Utilice la pestaña **Propiedades de conexión** del cuadro de diálogo **Conectar al servidor** para especificar una opción de publicación de **Puerta de enlace** o **Completo**. Después de identificar un publicador, esta opción no se puede cambiar sin quitar y volver a configurar el publicador. Para obtener más información, vea [Configurar un publicador de Oracle](non-sql/configure-an-oracle-publisher.md).  
  
## <a name="options"></a>Opciones  
 **Tipo de publicador**  
 Seleccione **Puerta de enlace** o **Completo**. La opción **Completo** está diseñada para proporcionar publicaciones de instantáneas y transaccionales con todas las características compatibles con la publicación de Oracle. La opción **Puerta de enlace** proporciona optimizaciones de diseño específicas para mejorar el rendimiento en casos en los que la replicación sirva como puerta de enlace entre sistemas. La opción **Puerta de enlace** no se puede utilizar si tiene previsto publicar la misma tabla en varias publicaciones transaccionales. Una tabla puede aparecer como máximo en una publicación transaccional y en cualquier número de publicaciones de instantáneas si selecciona **Puerta de enlace**.  
  
 **Tiempos de espera**  
 Especifique el tiempo durante el que el distribuidor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe intentar conectarse con el publicador de Oracle antes de que se genere un error de tiempo de espera.  
  
## <a name="see-also"></a>Vea también  
 [Glosario de términos de publicaciones de Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md)   
 [Performance Tuning for Oracle Publishers](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
