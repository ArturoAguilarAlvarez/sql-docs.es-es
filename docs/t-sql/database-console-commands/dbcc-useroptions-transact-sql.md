---
title: DBCC USEROPTIONS (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC USEROPTIONS
- DBCC_USEROPTIONS_TSQL
- USEROPTIONS_TSQL
- USEROPTIONS
dev_langs:
- TSQL
helpviewer_keywords:
- DBCC USEROPTIONS statement
- active SET options
- SET statement, active SET options
ms.assetid: 565ab112-7af1-4c18-a579-07cdb332f539
caps.latest.revision: 41
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a94a29317bef21f784d2b0b927577627434ce7d9
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-useroptions-transact-sql"></a>DBCC USEROPTIONS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Devuelve las opciones SET activas (establecidas) para la conexión actual.
  
![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxis  
  
```sql
DBCC USEROPTIONS  
[ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>Argumentos  
NO_INFOMSGS  
Suprime todos los mensajes informativos con niveles de gravedad entre 0 y 10.
  
## <a name="result-sets"></a>Conjuntos de resultados  
DBCC USEROPTIONS devuelve una columna para el nombre de la opción SET y una columna para el valor de la opción (los valores y las entradas pueden variar):

```sql

| `Set Option                   Value`  
 `---------------------------- ---------------------------`  
 `textsize                     64512`  
 `language                     us_english`  
 `dateformat                   mdy`  
 `datefirst                    7`  
 `lock_timeout                 -1`  
 `quoted_identifier            SET`  
 `arithabort                   SET`  
 `ansi_null_dflt_on            SET`  
 `ansi_warnings                SET`  
 `ansi_padding                 SET`  
 `ansi_nulls                   SET`  
 `concat_null_yields_null      SET`  
 `isolation level              read committed`  
 `(13 row(s) affected)`  
 `DBCC execution completed. If DBCC printed error messages, contact your system administrator.`
 ```  
  
## <a name="remarks"></a>Comentarios  
Si la opción de base de datos READ_COMMITTED_SNAPSHOT está establecida en ON y el nivel de aislamiento de transacción está establecido en 'read committed', DBCC USEROPTIONS notifica un nivel de aislamiento de transacción 'read committed snapshot'. El nivel de aislamiento real es read committed.
  
## <a name="permissions"></a>Permissions  
Debe pertenecer al rol **public** .
  
## <a name="examples"></a>Ejemplos  
En el ejemplo siguiente se devuelven las opciones SET activas de la conexión actual.
  
```sql  
DBCC USEROPTIONS;  
```  
  
## <a name="see-also"></a>Vea también  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[Instrucciones SET &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
[SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md)
  
  
