---
title: 取得項目
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：瞭解 [取得專案] 作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 3a9dda3850a86cffbb9fcbbb5c078512a04d0375
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619719"
---
# <a name="get-item"></a>取得項目
 
**摘要：** 瞭解 [取得專案] 作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
[取得專案] 作業是「用於通話品質」儀表板之 [存放庫 API] 中專案服務的一部分。
  
## <a name="get-item"></a>取得項目

取得專案會傳回存放庫中的特定專案。
  
|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。 如果找不到指定的專案識別碼，它會傳回狀態碼 404 (找不到) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  -專案的識別碼。
  
 *userId*  -擁有此專案之使用者的識別碼。
  
 *content*  -應用程式特定的內容。
  
 *type*  -內容類型。 此欄位是由應用程式所設定。
  
 *subItemIds*  -子專案的 IDs （如果有的話）。 這是用來儲存通話的「取得 Sub-Items 運作的短路。 應用程式也可以使用 [取得 Sub-Items] 作業取得相同的資訊。
  

