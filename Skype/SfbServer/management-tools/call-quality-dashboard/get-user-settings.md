---
title: 取得使用者設定
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：瞭解 User 設定 Service 的「取得使用者設定」作業。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: b7be08df46aa63287d931a566d26671bfecfc3b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778173"
---
# <a name="get-user-settings"></a>取得使用者設定
 
**摘要：** 深入瞭解 user 設定 Service 的「取得使用者設定」作業。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
[取得使用者設定] 作業是「儲存庫 API 的呼叫品質」儀表板中使用者設定服務的一部分。
  
## <a name="get-user-settings"></a>取得使用者設定

取得使用者設定會傳回指定使用者的設定清單。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**
  
- *有效*  -選用。 只有在使用特殊使用者識別碼預設值時，此參數才適用。 在其他情況下，它會被忽略。 `True` 會傳回有效的使用者設定，並 `false` 只傳回使用者設定 (預設) 。
    
  **要求標頭** -沒有其他標頭。
  
  **要求正文** -無。
  
  **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
  **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
  **回應標頭** -沒有其他標頭。
  
  **回應** 內文-以下是 JSON 中的範例回應負載。
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
