---
title: Establecer un tamaño máximo de tabla para una tabla de seguimiento (SQL Server Profiler) | Microsoft Docs
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
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
caps.latest.revision: 22
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 530e6bd70bc40fc85ac5a2071a3983b0933f6f31
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36201721"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a>Establecer un tamaño máximo de tabla para una tabla de seguimiento (SQL Server Profiler)
  En este tema se describe cómo establecer un tamaño máximo de tabla para tablas de seguimiento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a>Para establecer un tamaño máximo de tabla para una tabla de seguimiento  
  
1.  En el menú **Archivo** , haga clic en **Nuevo seguimiento**y, a continuación, conéctese a una instancia de SQL Server.  
  
     Aparece el cuadro de diálogo **Propiedades de seguimiento**.  
  
    > [!NOTE]  
    >  Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento. Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .  
  
2.  En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.  
  
3.  En el cuadro **Nombre de plantilla**.  
  
4.  Active la casilla **Guardar en la tabla**.  
  
5.  Conéctese al servidor en el que desee que se almacene el seguimiento.  
  
     Aparecerá el cuadro de diálogo **Tabla de destino** .  
  
6.  En la lista **Base de datos** , seleccione una base de datos para el seguimiento.  
  
7.  En el cuadro **Tabla** , escriba o seleccione un nombre de tabla.  
  
8.  Active la casilla **Establecer número máximo de filas (en miles)** y especifique un número máximo de filas para la tabla de seguimiento.  
  
    > [!NOTE]  
    >  Cuando el número de filas de la tabla supere el máximo especificado, dejarán de registrarse los eventos de seguimiento. No obstante, la traza continuará.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server Profiler](sql-server-profiler.md)   
 [SQL Server Profiler](sql-server-profiler.md)  
  
  