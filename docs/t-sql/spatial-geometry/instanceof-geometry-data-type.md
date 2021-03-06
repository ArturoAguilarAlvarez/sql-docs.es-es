---
title: InstanceOf (tipo de datos geometry) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- InstanceOf
- InstanceOf_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- InstanceOf (geometry Data Type)
ms.assetid: fdea1248-29a4-4bab-a60d-a1b359b5e109
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3f517a0a991d36fb0371a7f2eee5e3fb4a0dacc2
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47715961"
---
# <a name="instanceof-geometry-data-type"></a>InstanceOf (tipo de datos geometry)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Este método comprueba si la instancia de **geometry** es la misma que la del tipo especificado. Devuelve 1 si el tipo de una instancia de **geometry** coincide con el tipo especificado, o si el tipo especificado es un antecesor del tipo de la instancia; en caso contrario, devuelve 0.
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
.InstanceOf (geometry_type )  
```  
  
## <a name="arguments"></a>Argumentos  
 *geometry_type*  
 Es una cadena **nvarchar(4000)** en la que se especifica uno de los 15 tipos expuestos en la jerarquía de tipos de **geometry**.  
  
## <a name="return-types"></a>Tipos devueltos  
 Tipo de valor devuelto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **bit**  
  
 Tipo de valor devuelto de CLR: **SqlBoolean**  
  
## <a name="remarks"></a>Notas  
 La entrada del método debe ser una de las siguientes: **Geometry**, **Point**, **Curve**, **LineString**, **CircularString**, **CompoundCurve**, **Surface**, **Polygon**, **CurvePolygon**, **GeometryCollection**, **MultiSurface**, **MultiPolygon**, **MultiCurve**, **MultiLineString** o **MultiPoint**. Este método produce una excepción **ArgumentException** si se usa cualquier otra cadena como entrada.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se crea una instancia de `MultiPoint` y se utiliza `InstanceOf()` para ver si la instancia es de tipo `GeometryCollection`.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT(0 0, 13.5 2, 7 19)', 0);  
SELECT @g.InstanceOf('GEOMETRYCOLLECTION');  
```  
  
## <a name="see-also"></a>Ver también  
 [Métodos extendidos en instancias de geometry](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)  
  
  

