---
title: Filtrado para actualiza registros | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- filtering for updated records [ADO]
ms.assetid: 4a798921-d7bb-47c9-a252-550fd9463ec9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 74ea4a208cad079933b27a7305a5ce0462e08515
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47639203"
---
# <a name="filtering-for-updated-records"></a>Filtrar registros actualizados
Antes de llamar a UpdateBatch, puede usar la propiedad de filtro de conjunto de registros para ver solo aquellos registros que han cambiado desde que se abrió el conjunto de registros o la última llamada al método UpdateBatch. Para ello, establezca Filter en adFilterPendingRecords para determinar cuántos registros se actualizarán, como se muestra en el ejemplo de código en la sección siguiente.  
  
## <a name="remarks"></a>Comentarios  
 Este ejemplo amplía el ejemplo UpdateBatch anterior filtrando el conjunto de registros justo antes de llamar el UpdateBatch, que muestra al usuario qué registros cambiará y lo que permite a cancelar la actualización (mediante el método CancelBatch).  
  
```  
'BeginFilterPend  
    '...  
    objRs1.Open strSQL, strConn, adOpenStatic, adLockBatchOptimistic, adCmdText  
  
    ' Change value of Phone field for first record in Recordset, saving value  
    ' for later restoration.  
    intId = objRs1("ShipperId")  
    sPhone = objRs1("Phone")  
  
    objRs1("Phone") = "(111) 555-1111"  
  
    'Add two new records  
    For i = 0 To 1  
        objRs1.AddNew  
        objRs1(1) = "New Shipper #" & CStr((i + 1))  
        objRs1(2) = "(nnn) 555-" & i & i & i & i  
    Next i  
  
    objRs1.Filter = adFilterPendingRecords  
  
    MsgBox "There are " & objRs1.RecordCount & " records pending.", _  
            , "Filter Pending"  
  
    ' Cancel the updates  
    objRs1.CancelBatch  
'EndFilterPend  
```  
  
## <a name="see-also"></a>Vea también  
 [Modo por lotes](../../../ado/guide/data/batch-mode.md)
