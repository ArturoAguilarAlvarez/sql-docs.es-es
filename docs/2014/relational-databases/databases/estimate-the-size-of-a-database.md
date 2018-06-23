---
title: Estimar el tamaño de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
caps.latest.revision: 19
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 12013bd903a6ce0343e67ab500b7c3c2356f5e55
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36201390"
---
# <a name="estimate-the-size-of-a-database"></a>Estimar el tamaño de una base de datos
  Cuando diseña una base de datos, puede que necesite realizar una estimación del tamaño que tendrá la base de datos cuando esté llena. Esta estimación puede ayudarle a determinar la configuración de hardware que necesitará para realizar lo siguiente:  
  
-   Conseguir el rendimiento que necesitan las aplicaciones.  
  
-   Asegurar la cantidad física adecuada de espacio en disco necesario para almacenar los datos y los índices.  
  
 Asimismo, la estimación del tamaño de la base de datos puede ayudarle a determinar si el diseño de su base de datos necesita reajustes. Por ejemplo, puede determinar que el tamaño estimado de la base de datos es demasiado grande para una implementación en su organización, y que se necesita un mayor grado de normalización. Por el contrario, el tamaño estimado puede inferior al esperado, con lo que podrá reducir la normalización de la base de datos para mejorar el rendimiento de las consultas.  
  
 Para realizar una estimación del tamaño de una base de datos, efectúe una estimación del tamaño de cada tabla por separado y sume los valores obtenidos. El tamaño de una tabla depende de si tiene índices y, si los tiene, del tipo de índices.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Calcular el tamaño de una tabla](estimate-the-size-of-a-table.md)|Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en una tabla y en los índices asociados.|  
|[Estimar el tamaño de un montón](estimate-the-size-of-a-heap.md)|Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un montón. Un montón es una tabla que no contiene un índice clúster.|  
|[Estimar el tamaño de un índice clúster](estimate-the-size-of-a-clustered-index.md)|Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un índice clúster.|  
|[Estimar el tamaño de un índice no clúster](estimate-the-size-of-a-nonclustered-index.md)|Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un índice no clúster.|  
  
  