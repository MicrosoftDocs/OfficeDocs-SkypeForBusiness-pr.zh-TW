---
title: 取得子項目
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：瞭解 Sub-Items 作業，也就是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: a1e439b9bfdfddf7009babbeb39a8175adc2a569
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851907"
---
# <a name="get-sub-items"></a>取得子項目
 
**摘要：** 深入瞭解 Sub-Items 作業，也就是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
Get Sub-Items 作業是用於通話品質儀表板之存放庫 API 中的專案服務的一部分。
  
## <a name="get-sub-items"></a>取得子項目

Get Sub-Items 會傳回特定專案的子專案。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。 如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
> [!NOTE]
> 會傳回 Item 物件的陣列。 
  
```json
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

Sub-Items 作業所傳回的 Item 物件只包含下列三個欄位。 
  
 *itemId*  -專案的識別碼。
  
 *userId*  -擁有此專案之使用者的識別碼。
  
 *type*  -內容類型。 此欄位是由應用程式所設定。
  
> [!NOTE]
>  `Content` 和 `subItems` 欄位不會包含在回應中，以減少透過網路傳輸的資料量。
  

