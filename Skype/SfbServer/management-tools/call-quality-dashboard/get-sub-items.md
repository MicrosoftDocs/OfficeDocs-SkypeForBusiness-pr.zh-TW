---
title: 取得子專案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '摘要: 瞭解 [取得子專案] 作業, 該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186910"
---
# <a name="get-sub-items"></a>取得子專案
 
**摘要:** 瞭解 [取得子專案] 作業, 該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得子專案] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。
  
## <a name="get-sub-items"></a>取得子專案

[取得子專案] 會傳回特定專案的子專案。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼 200 (確定)。 如果找不到指定的使用者識別碼, 則會傳回狀態碼 404 (找不到)。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是 JSON 中的回應載荷範例。
  
> [!NOTE]
> 傳回 Item 物件的陣列。 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

子專案操作所傳回的專案物件只包含下列三個欄位。 
  
 *itemId* -專案識別碼。
  
 *userId* -擁有此專案的使用者識別碼。
  
 *類型*-內容的類型。 這個欄位是由應用程式所設定。
  
> [!NOTE]
>  `Content`而且`subItems`欄位不會包含在回應中, 以減少網路上傳輸的資料量。
  

