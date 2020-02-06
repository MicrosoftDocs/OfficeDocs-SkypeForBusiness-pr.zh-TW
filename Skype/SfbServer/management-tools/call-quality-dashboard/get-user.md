---
title: 取得使用者
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：瞭解 [取得使用者] 作業（這是使用者服務的一部分）。 使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816732"
---
# <a name="get-user"></a>取得使用者
 
**摘要：** 瞭解 [取得使用者] 作業，該操作是使用者服務的一部分。 使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得使用者] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的使用者服務的一部分。
  
## <a name="get-user"></a>取得使用者

[取得使用者] 會從儲存庫傳回使用者記錄。
  
|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。 如果找不到指定的使用者識別碼，則會傳回狀態碼404（找不到）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是 JSON 中的回應載荷範例。
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* -使用者識別碼。
  
 *loginName* -一般使用者的外部使用者識別。 如果使用 Windows 驗證來驗證使用者，則這可能是使用者的 FQDN。
  
 *defaultItemId* -此使用者的預設專案識別碼。 預設專案是與使用者相關聯的最上方專案。 此使用者擁有的所有其他專案都可以從預設專案中流覽。
  
> [!NOTE]
> 提供`defaultItemId`值以取得專案操作，以取得預設專案的詳細資料。
  

