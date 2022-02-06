---
title: CQD 的使用者服務
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：瞭解使用者服務，它是「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
---

# <a name="user-service-for-cqd"></a>CQD 的使用者服務
 
**總結：** 深入瞭解使用者服務，此服務是「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。
  
## <a name="user-service"></a>使用者服務

存放庫 API 提供簡化的使用者管理模型，其中使用者布建 (建立新的使用者帳戶) 為自動和隱含。 當使用者第一次對存放庫 API 提出要求時，存放庫便會建立新的使用者記錄。 
  
通話品質儀表板也會自動為新使用者建立使用者專用專案。 新的使用者專用專案是系統使用者之專案的完整克隆。 如此一來，使用者可以立即開始自訂的報表和查詢副本開始進行自訂。 
  
> [!NOTE]
> 使用 [通話品質] 儀表板，使用者可以隨時重設他們的專屬專案。 
  
 **特殊使用者 IDs**
  
存放庫 API 包括 REST API URIs，需要整數值來指定特定的使用者。 範例：  `https://<portal>/QoERepositoryService/repository/user/{userId}` 。 在這裡，{userId} 應該以整數值取代，例如0，1，etc。
  
此外，知識庫 API 會在 URIs 中接受兩個特殊使用者 IDs {userId}。
  
-  *default*  -代表目前與 API 互動的使用者。 這可讓應用程式存取目前使用者的內容，而不需要追蹤實際的使用者識別碼值。 範例： `https://<portal>/QoERepositoryService/repository/user/default` 。
    
-  *system*  -代表系統使用者。 這可讓應用程式在不知道實際使用者識別碼值的情況下，存取系統使用者的內容。 範例： `https://<portal>/QoERepositoryService/repository/user/system` 。
    
除非另有說明，否則可以在 URIs {userId} 中使用特殊使用者 IDs。 
  
其餘的作業包含在下表中。
  
|**作業**|**描述**|
|:-----|:-----|
|[取得使用者](get-users.md) <br/> |傳回存放庫中的使用者清單。  <br/> |
|[取得使用者](get-user.md) <br/> |傳回使用者記錄。  <br/> |
   

