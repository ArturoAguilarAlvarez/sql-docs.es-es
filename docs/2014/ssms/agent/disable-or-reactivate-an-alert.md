---
title: Deshabilitar o volver a activar una alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
caps.latest.revision: 26
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15bf7a49e966ff691c135001a1588d6d3465937b
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36103240"
---
# <a name="disable-or-reactivate-an-alert"></a>Deshabilitar o volver a activar una alerta
  En este tema se describe cómo deshabilitar o volver a activar una alerta del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Seguridad](#Security)  
  
-   **Para deshabilitar o volver a activar una alerta, utilizando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permissions  
 De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden editar la información de una alerta. A otros usuarios debe concederse el rol fijo de base de datos **SQLAgentOperatorRole** en la base de datos **msdb** .  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### <a name="to-disable-or-reactivate-an-alert"></a>Para deshabilitar o volver a activar una alerta  
  
1.  En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la alerta que desea deshabilitar o volver a activar.  
  
2.  Haga clic en el signo más para expandir **Agente SQL Server**.  
  
3.  Haga clic en el signo más para expandir la carpeta **Alertas** .  
  
4.  Haga clic con el botón derecho en la alerta que desea habilitar y seleccione **Habilitar** . Para deshabilitar una alerta, haga clic con el botón derecho en la alerta que desea deshabilitar y seleccione **Deshabilitar**.  
  
5.  Aparece el cuadro de diálogo **Deshabilitar la alerta** o **Habilitar la alerta** con el estado del proceso. Cuando termine, haga clic en **Cerrar**.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
  
#### <a name="to-disable-or-reactivate-an-alert"></a>Para deshabilitar o volver a activar una alerta  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 Para obtener más información, consulte [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).  
  
  