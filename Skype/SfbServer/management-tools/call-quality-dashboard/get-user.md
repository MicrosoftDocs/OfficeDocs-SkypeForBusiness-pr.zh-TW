---
title: 取得使用者
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：瞭解使用者服務中的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: adcb832d03d97eee978e3eb4c0f9027bd44ac7ce
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768671"
---
# <a name="get-user"></a>取得使用者
 
**摘要：** 深入瞭解 User Service 的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
「取得使用者」作業是「用於通話品質」儀表板之存放庫 API 中使用者服務的一部分。
  
## <a name="get-user"></a>取得使用者

[取得] 使用者從存放庫傳回使用者記錄。
  
|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。 如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  -使用者的識別碼。
  
 *loginName*  -一般使用者的外部使用者識別。 如果使用 Windows 驗證來驗證使用者，則這可能是使用者的 FQDN。
  
 *defaultItemId*  -此使用者之預設專案的識別碼。 預設專案是與使用者相關聯的最上層專案。 您可以從預設專案流覽此使用者擁有的所有其他專案。
  
> [!NOTE]
> 提供  `defaultItemId` 值以取得專案作業，以取得預設專案的詳細資料。
  

