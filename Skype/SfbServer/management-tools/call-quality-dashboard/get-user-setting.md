---
title: 取得使用者設定
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：瞭解 [建立使用者] 設定作業，這是使用者設定服務的一部分。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832483"
---
# <a name="get-user-setting"></a>取得使用者設定
 
**摘要：** 深入瞭解 [使用者設定] 服務的 [取得] 使用者設定作業。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
  
「取得使用者設定」作業是「用於通話品質」儀表板的 [儲存庫 API] 中的 [使用者設定] 服務的一部分。
  
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
  

