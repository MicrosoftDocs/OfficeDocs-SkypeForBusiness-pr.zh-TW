---
title: 取得使用者設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：瞭解 [取得使用者設定] 作業，該作業是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992630"
---
# <a name="get-user-settings"></a>取得使用者設定
 
**摘要：** 瞭解 [取得使用者設定] 作業，該作業是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得使用者設定] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的 [使用者設定] 服務的一部分。
  
## <a name="get-user-settings"></a>取得使用者設定

[取得使用者設定] 會傳回指定使用者的設定清單。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**
  
- *有效*-選用。 這個參數只有在使用特殊的使用者識別碼預設值時才適用。 在其他情況下，它會被忽略。 `True`傳回有效的使用者設定`false`並只傳回使用者設定（預設）。
    
  **要求標頭**-沒有其他標頭。
  
  **要求主體**-無。
  
  **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
  **狀態碼**-成功的操作會傳回狀態碼200（確定）。
  
  **回應標題**-沒有其他標頭。
  
  **回應主體**-以下是 JSON 中的回應載荷範例。
  
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
