---
title: Opciones de artículos para la replicación transaccional | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7e003ab7a1928c98e2e4e004d53d71fc001227d7
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48190725"
---
# <a name="article-options-for-transactional-replication"></a>Opciones de artículos para la replicación transaccional
  Existen varias opciones para artículos en las publicaciones transaccionales. Con la replicación transaccional puede hacer lo siguiente:  
  
-   Especificar cómo se propagan los cambios desde el publicador a los suscriptores. Para más información, vea [Especificar cómo se propagan los cambios para los artículos transaccionales](transactional-articles-specify-how-changes-are-propagated.md).  
  
-   Especificar que se replique la ejecución de un procedimiento almacenado. Esto resulta de utilidad al replicar los resultados de los procedimientos almacenados orientados al mantenimiento que afectan a grandes cantidades de datos. Para más información, vea [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).  
  
-   Especificar opciones de esquema, por ejemplo si las restricciones y los desencadenadores se copian en el suscriptor. Para obtener más información, vea [Especificar opciones de esquema](../publish/specify-schema-options.md).  
  
-   Utilizar filtros de fila y columna. Filtrar artículos de tabla permite crear particiones de los datos que se van a publicar. Para obtener más información, vea [Filtrar datos publicados](../publish/filter-published-data.md).  
  
## <a name="see-also"></a>Vea también  
 [Publicar datos y objetos de base de datos](../publish/publish-data-and-database-objects.md)  
  
  
