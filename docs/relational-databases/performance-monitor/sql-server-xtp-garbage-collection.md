---
title: Recolección de elementos no utilizados de XTP de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
s.technology: performance
ms.topic: conceptual
ms.assetid: 64ae91e5-b420-44b4-af1a-f8bca83d7f41
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 61df3bf16815b5a053caf2a04ff87483350094c4
ms.sourcegitcommit: ca038f1ef180e4e1b27910bbc5d87822cd1ed176
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2018
ms.locfileid: "52158763"
---
# <a name="sql-server-xtp-garbage-collection"></a>Recolección de elementos no utilizados de XTP de SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  El objeto de rendimiento Recolección de elementos no utilizados de XTP de SQL Server contiene contadores relacionados con el recolector de elementos no utilizados del motor OLTP en memoria.  
  
 En esta tabla se describen los contadores de **Recolección de elementos no utilizados de XTP de SQL Server** .  
  
|Contador|Descripción|  
|-------------|-----------------|  
|**Reintentos de recorrido de esquinas sucias/s (emitidos por GC)**|Número de reintentos de recorrido debido a conflictos de escritura durante los rastreos de esquinas sucias emitidos por el recolector de elementos no utilizados (en promedio), por segundo. Es un contador de nivel muy bajo, no está pensado para uso de los clientes.|  
|**Elementos de trabajo principales de GC/s**|Número de elementos de trabajo procesados por el subproceso principal de GC.|  
|**Elemento de trabajo paralelo de GC/s**|Número de veces que un subproceso paralelo ha ejecutado un elemento de trabajo de GC.|  
|**Filas procesadas/s**|Número de filas procesadas por el recolector de elementos no utilizados (en promedio), por segundo.|  
|**Filas procesadas/s (primero en el cubo y quitadas)**|Número de filas procesadas por el recolector de elementos no utilizados que estaban primero en el depósito de hash correspondiente, y que se pudieron quitar inmediatamente (en promedio), por segundo.|  
|**Filas procesadas/s (primero en el cubo)**|Número de filas procesadas por el recolector de elementos no utilizados que estaban primero en el depósito de hash correspondiente (en promedio), por segundo.|  
|**Filas procesadas/s (marcadas para desvincular)**|Número de filas procesadas por el recolector de elementos no utilizados que ya estaban marcadas para desvincular (en promedio), por segundo.|  
|**Filas procesadas/s (no se necesita ningún rastreo)**|Número de filas procesadas por el recolector de elementos no utilizados que no necesitarán un rastreo de esquinas sucias (en promedio), por segundo.|  
|**Rastreo de filas expiradas quitadas/s**|Número de filas expiradas quitadas durante los rastreos de esquinas sucias (en promedio), por segundo.|  
|**Rastreo de filas expiradas tocadas/s**|Número de filas expiradas tocadas durante los rastreos de esquinas sucias (en promedio), por segundo.|  
|**Rastreo de filas que van a expirar tocadas/s**|Número de filas que van a expirar tocadas durante los rastreos de esquinas sucias (en promedio), por segundo.|  
|**Rastreo de filas tocadas/s**|Número de filas tocadas durante los rastreos de esquinas sucias (en promedio), por segundo.|  
|**Rastreo de recorridos iniciados/s**|Número de recorridos de rastreo de esquinas sucias iniciados (en promedio), por segundo.|  
  
## <a name="see-also"></a>Ver también  
 [Contadores de rendimiento de XTP &#40;OLTP en memoria&#41;](../../relational-databases/performance-monitor/sql-server-xtp-in-memory-oltp-performance-counters.md)  
  
  
