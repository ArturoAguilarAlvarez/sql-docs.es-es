---
title: Propiedades de Configuración de SQL Server Native Client (pestaña Marcas) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
manager: craigg
ms.openlocfilehash: 68bcc2c6a0077a8d3a9440e9c41ea069be3ba2c6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47644553"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a>Propiedades de Configuración de SQL Server Native Client (pestaña Marcas)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de este equipo se comunican con los servidores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante los protocolos suministrados en el archivo de biblioteca de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client. En esta página se configura el equipo cliente para solicitar una conexión cifrada mediante Capa de sockets seguros (SSL). Si no es posible establecer una conexión cifrada, la conexión no se establecerá.  
  
 El proceso de inicio de sesión siempre está cifrado. Las opciones que se facilitan a continuación solo se aplican al cifrado de datos. Para más información sobre cómo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cifra la comunicación e instrucciones sobre cómo configurar el cliente para que confíe en la entidad de certificación raíz del certificado de servidor, vea "Cifrar conexiones a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" y "Cómo habilitar conexiones cifradas en el [!INCLUDE[ssDE](../../includes/ssde-md.md)] (Administrador de configuración de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] )" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="options"></a>Opciones  
 **ForceEncryption**  
 Solicita una conexión con SSL.  
  
 **TrustServerCertificate**  
 Cuando se establece en **No**, el proceso de cliente intenta validar el certificado de servidor. El cliente y el servidor deben tener cada uno un certificado emitido por una entidad de certificación pública. Si el certificado no está presente en el equipo cliente o no se puede validar, la conexión finalizará.  
  
 Si se establece en **Yes**, el cliente no validará el certificado de servidor, por lo que se habilitará el uso de un certificado autofirmado.  
  
 **Confiar en certificado de servidor** solo está disponible si **Forzar cifrado de protocolos** se ha establecido en **Sí**.  
  
  
