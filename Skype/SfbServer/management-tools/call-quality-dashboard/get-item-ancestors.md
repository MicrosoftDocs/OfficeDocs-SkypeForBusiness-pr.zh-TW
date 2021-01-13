---
title: 取得項目上階
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：瞭解屬於專案服務的「取得專案祖先」作業。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832573"
---
# <a name="get-item-ancestors"></a>取得項目上階
 
**摘要：** 瞭解 [取得專案] 上級作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
  
「取得專案祖先」作業是存放庫 API for a Call Quality 儀表板的專案服務的一部分。
  
## <a name="get-item-ancestors"></a>取得項目上階

取得專案祖先會傳回存放庫中的特定專案祖先。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。 如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  -專案的識別碼。
  
 *Item2*  -深度是指從專案的距離。 0是直接父項。
  
 *Item3*  -專案的標題。
  

