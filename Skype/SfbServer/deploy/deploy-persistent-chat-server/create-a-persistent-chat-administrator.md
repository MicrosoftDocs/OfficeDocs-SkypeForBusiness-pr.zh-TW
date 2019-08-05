---
title: 建立常設聊天室管理員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '摘要: 請閱讀本主題, 瞭解如何建立持久聊天伺服器系統管理員角色, 以便在商務用 Skype Server 2015 中開始設定及管理持續聊天服務。'
ms.openlocfilehash: b0edd3e1f10bf040be18242bfa600bb694169257
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193997"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>建立常設聊天室管理員
 
**摘要:** 請閱讀本主題, 瞭解如何建立持久聊天伺服器系統管理員角色, 以便在商務用 Skype Server 2015 中開始設定及管理永久性聊天服務。
  
在商務用 Skype Server 中, 執行特定工作的使用者必須指派為一或多個特定群組的成員。 角色式存取控制 (RBAC) 是用來將使用者指派至預先定義的商務用 Skype Server 系統管理角色, 以授與許可權。 這些角色會與 Active Directory 網域服務中的通用安全性群組相對應。 永久聊天系統管理員安全性群組的成員 (CsPersistentChatAdministrator) 會獲授與永久聊天伺服器 Cmdlet 的存取權, 可以使用商務用 Skype Server 管理命令介面或商務用 Skype 來執行。伺服器 [控制台]。
  
在設定及管理持續性聊天伺服器之前, 請確定適當的使用者權利和許可權已就緒, 且任何將充當永久聊天系統管理員的使用者, 都會新增到 [永久聊天管理員] 安全性群組。
  
> [!NOTE] 
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。

## <a name="create-a-persistent-chat-administrator"></a>建立常設聊天室管理員

若要將使用者新增至持續聊天系統管理員安全性群組, 請 CsPersistentChatAdministrator, 執行下列步驟:
  
1. 使用有權修改 Active Directory 群組成員資格的帳戶, 登入已安裝 Active Directory 使用者和電腦的電腦。
    
2. 按一下 [開始], 按一下 [所有程式], 按一下 [系統管理工具], 然後按一下 [Active Directory 使用者和電腦]。
    
3. 在 [Active Directory 使用者和電腦] 中, 展開您網域的名稱, 然後按一下 [使用者] 容器。
    
4. 以滑鼠右鍵按一下安全性群組 CsPersistentChatAdministrator, 然後按一下 [屬性]。
    
5. 在 [屬性] 對話方塊的 [成員] 索引標籤上, 按一下 [新增]。
    
6. 在 [選取使用者、電腦、連絡人或群組] 對話方塊中, 于 [輸入要選取的物件名稱] 方塊中, 輸入要新增到群組的使用者名稱或 [顯示名稱], 然後按一下 [確定]。
    
7. 按一下 [屬性] 對話方塊中的 [確定]。
    

