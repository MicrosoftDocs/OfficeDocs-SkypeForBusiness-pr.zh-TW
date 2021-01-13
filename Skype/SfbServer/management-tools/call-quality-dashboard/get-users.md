---
title: 取得使用者
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要：瞭解「使用者服務」的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832423"
---
# <a name="get-users"></a>取得使用者
 
**摘要：** 深入瞭解 User Service 的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
  
「取得使用者」作業是「用於通話品質」儀表板之存放庫 API 中使用者服務的一部分。
  
## <a name="get-users"></a>取得使用者

取得使用者會傳回存放庫中的使用者清單。
  
|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
> [!NOTE]
> 傳回使用者物件的陣列。 如需使用者物件的詳細資訊，請參閱 Get User。 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


