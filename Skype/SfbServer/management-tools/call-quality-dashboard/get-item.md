---
title: 取得項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：瞭解 [取得專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816792"
---
# <a name="get-item"></a>取得項目
 
**摘要：** 瞭解 [取得專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得專案] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。
  
## <a name="get-item"></a>取得項目

[取得專案] 會傳回文件庫中的特定專案。
  
|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。 如果找不到指定的專案識別碼，則會傳回狀態碼404（找不到）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是 JSON 中的回應載荷範例。
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* -專案識別碼。
  
 *userId* -擁有此專案的使用者識別碼。
  
 *內容*-應用程式特定的內容。
  
 *類型*-內容的類型。 這個欄位是由應用程式所設定。
  
 *subItemIds* -子專案的識別碼（如果有的話）。 這是 [取得子專案] 作業的短路，以儲存通話。 應用程式也可以使用 [取得子專案] 作業來取得相同的資訊。
  

