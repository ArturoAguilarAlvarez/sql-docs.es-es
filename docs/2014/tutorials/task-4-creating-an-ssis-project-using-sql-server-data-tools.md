---
title: 'Tarea 4: Crear un proyecto de SSIS con SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 584ba08e49efaf0dc3a8de2a1fa8fd34ac20bfe3
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48113286"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a>Tarea 4: crear un proyecto de SSIS con SQL Server Data Tools
  En esta tarea, creará un proyecto de SSIS usando **SQL Server Data Tools** para automatizar la limpieza y la búsqueda de coincidencias de los datos de proveedor.  
  
1.  Inicie **SQL Server Data Tools**. Haga clic en Inicio, seleccione **Todos los programas**, expanda **Microsoft SQL Server 2012**y, a continuación, haga clic en **SQL Server Data Tools**.  
  
2.  En el menú **Archivo** , elija **Nuevo**y, a continuación, haga clic en **Proyecto**.  
  
3.  Expanda **Business Intelligence** en el panel **Plantillas instaladas** y seleccione **Integration Services**.  
  
     ![Visual Studio - cuadro de diálogo nuevo proyecto](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - cuadro de diálogo nuevo proyecto")  
  
4.  Seleccione **Proyecto de Integration Services** en la **lista de tipos de proyecto**.  
  
5.  Escriba **CleanseAndCurateSuppliers** en **Nombre** y haga clic en **Aceptar**.  
  
6.  En la ventana **Explorador de soluciones** , haga clic con el botón secundario en **Package.dtsx** y seleccione **Cambiar nombre**. Si no ve la ventana **Explorador de soluciones** , haga clic en **Ver** en la barra de menús y, a continuación, haga clic en **Explorador de soluciones**.  
  
     ![Package.dtsx - menú renombrar](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - menú renombrar")  
  
7.  Escriba **CleanseAndCurate.dtsx** y presione **ENTRAR**. Asegúrese de que la **extensión** siga siendo **.dtsx**.  
  
## <a name="next-step"></a>Paso siguiente  
 [Tarea 5: Agregar una tarea Flujo de datos](task-5-adding-data-flow-task.md)  
  
  
