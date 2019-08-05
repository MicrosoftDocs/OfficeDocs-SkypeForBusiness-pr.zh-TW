---
title: CQD 的使用者服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '摘要: 瞭解使用者服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193942"
---
# <a name="user-service-for-cqd"></a>CQD 的使用者服務
 
**摘要:** 瞭解使用者服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。
  
## <a name="user-service"></a>使用者服務

[知識庫 API] 提供簡化的使用者管理模型, 使用者的提供 (建立新的使用者帳戶) 是自動及隱式的。 當使用者第一次針對知識庫 API 提出要求時, 知識庫會建立新的使用者記錄。 
  
[通話品質儀表板] 也會自動為新使用者建立使用者專用專案。 新的使用者專用專案是系統使用者專案的完整克隆。 如此一來, 使用者就能立即開始自訂其自己的報表和查詢複本。 
  
> [!NOTE]
> 使用者可以使用 [通話品質儀表板] 隨時重設他們的專用專案。 
  
 **特殊的使用者識別碼**
  
[知識庫 API] 包含需要整數值來指定特定使用者的 REST API Uri。 範例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。 在這裡, {userId} 應該由整數值 (例如0、1等) 取代。
  
此外, 知識庫 API 將會在 Uri 中的 {userId} 接受兩個特殊的使用者識別碼。
  
-  *預設值*-代表目前與 API 互動的使用者。 這可讓應用程式存取目前使用者的內容, 而不需追蹤實際的 [使用者識別碼] 值。 範例: `https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system* -代表系統使用者。 這可讓應用程式無需知道實際的 [使用者識別碼] 值即可存取系統使用者的內容。 範例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另有說明, 否則可以在 Uri 中 {userId} 使用特殊的使用者識別碼。 
  
其餘的作業包括在下表中。
  
|**一道**|**說明**|
|:-----|:-----|
|[取得使用者](get-users.md) <br/> |傳回文件庫中的使用者清單。  <br/> |
|[取得使用者](get-user.md) <br/> |傳回使用者記錄。  <br/> |
   

