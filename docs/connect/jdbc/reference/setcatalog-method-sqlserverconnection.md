---
title: Método setCatalog (SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.setCatalog
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 553c0603-c07d-436a-86eb-3ba6b51bd696
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a123f6d8a51bdb20f5a90bec39eb4b44b19f110e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47622773"
---
# <a name="setcatalog-method-sqlserverconnection"></a>Método setCatalog (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el nombre de catálogo determinado para seleccionar un subespacio de la base de datos de este objeto [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) donde pueda funcionar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setCatalog(java.lang.String catalog)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *catalog*  
  
 Objeto **String** que contiene el nombre del catálogo.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notas  
 Este método setCatalog especificado por el método setCatalog en la interfaz java.sql.Connection.  
  
 El *catálogo* argumento elude la [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] automáticamente. Al utilizar este método, se establece la propiedad de catálogo para el objeto Connection. No se establece implícitamente de cualquier otra manera.  
  
## <a name="see-also"></a>Ver también  
 [Miembros SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Clase SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
