---
title: PDOStatement::getAttribute | Microsoft Docs
ms.custom: ''
ms.date: 07/13/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 41d0cca3-8556-4573-bb90-8e9402d9379f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0e9f9a4e6af61eb507fa58f70b0aeb9060a16940
ms.sourcegitcommit: 63b4f62c13ccdc2c097570fe8ed07263b4dc4df0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51605085"
---
# <a name="pdostatementgetattribute"></a>PDOStatement::getAttribute
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Recupera el valor de un atributo de controlador personalizado o un atributo PDOStatement predefinido.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
mixed PDOStatement::getAttribute( $attribute );  
```  
  
#### <a name="parameters"></a>Parámetros  
$*attribute*: entero; una de las constantes PDO::ATTR_* o PDO::SQLSRV_ATTR_\*. Los atributos compatibles son los atributos que se pueden establecer con [pdostatement:: setAttribute](../../connect/php/pdostatement-setattribute.md), PDO:: sqlsrv_attr_direct_query (para obtener más información, consulte [Direct Statement Execution and Prepared Statement Execution en el controlador PDO_SQLSRV](../../connect/php/direct-statement-execution-prepared-statement-execution-pdo-sqlsrv-driver.md)), PDO:: attr_cursor y PDO:: sqlsrv_attr_cursor_scroll_type (para obtener más información, consulte [tipos de Cursor (controlador PDO_SQLSRV)](../../connect/php/cursor-types-pdo-sqlsrv-driver.md)).  
  
## <a name="return-value"></a>Valor devuelto  
Si se ejecuta correctamente, devuelve un valor (mixto) para un atributo PDO predefinido o el atributo de controlador personalizado. En caso de error, se devuelve Null.  
  
## <a name="remarks"></a>Notas  
Para obtener un ejemplo, consulte [PDOStatement::setAttribute](../../connect/php/pdostatement-setattribute.md) .  
  
En la versión 2.0 de los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)], se agregó compatibilidad con PDO.  
  
## <a name="see-also"></a>Ver también  
[Clase PDOStatement](../../connect/php/pdostatement-class.md)

[PDO](https://php.net/manual/book.pdo.php)  
  
