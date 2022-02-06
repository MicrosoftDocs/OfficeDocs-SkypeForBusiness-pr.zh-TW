---
title: 取得使用者設定
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '摘要：瞭解 [取得使用者設定] 作業，這是使用者設定服務的一部分。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。'
---

# <a name="get-user-setting"></a>取得使用者設定
 
**總結：** 深入瞭解使用者設定作業，這是使用者設定服務的一部分。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
「取得使用者設定」作業是「儲存庫 API 的呼叫品質」儀表板中使用者設定服務的一部分。
  
## <a name="get-user-setting"></a>取得使用者設定

取得使用者設定會傳回單一使用者設定。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  -使用者的識別碼。
  
 索引 *鍵* 的設定。
  
 *值*  -設定值。
  

