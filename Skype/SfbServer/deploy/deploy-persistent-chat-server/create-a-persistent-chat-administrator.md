---
title: 在商務用 Skype Server 2015 中建立持續性聊天系統管理員
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要：閱讀此主題以瞭解如何建立 persistent chat Server 系統管理員角色，以在商務用 Skype Server 2015 中啟用 persistent 聊天服務的初始設定和管理。
---

# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中建立持續性聊天系統管理員
 
**總結：** 閱讀此主題以瞭解如何建立 persistent chat Server 系統管理員角色，以在商務用 Skype Server 2015 中啟用 persistent 聊天服務的初始設定和管理。
  
在商務用 Skype Server 中，執行特定工作的使用者必須指派為一或多個特定群組的成員。 Role-Based 存取控制 (RBAC) 是用來授與許可權的方式，方法是指派使用者至預先定義的商務用 Skype Server 系統管理角色。 這些角色會對應至 Active Directory 網域服務中的通用安全性群組。 可使用商務用 Skype Server 管理命令介面或商務用 Skype Server 控制台，將 persistent chat Server Cmdlet 的存取權授與 CsPersistentChatAdministrator，以取得 persistent chat Server Cmdlet 的成員。
  
在設定及管理 Persistent Chat Server 之前，請確定適當的使用者權限及許可權已存在，而且將充當 Persistent Chat 系統管理員的任何使用者都已新增至 Persistent Chat Administrator 安全性群組。
  
> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。

## <a name="create-a-persistent-chat-administrator"></a>建立常設聊天室系統管理員

若要將使用者新增至 [Persistent Chat Administrator] 安全性群組，請 CsPersistentChatAdministrator，執行下列步驟：
  
1. 使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。
    
2. 依序按一下 [開始]、[所有程式]、[系統管理工具] 及 [Active Directory 使用者及電腦]。
    
3. 在 [Active Directory 使用者及電腦] 中，展開您的網功能變數名稱稱，然後按一下 [使用者] 容器。
    
4. 以滑鼠右鍵按一下安全性群組 CsPersistentChatAdministrator，然後按一下 [屬性]。
    
5. 在 [屬性] 對話方塊的 [成員] 索引標籤上，按一下 [新增]。
    
6. 在 [選取使用者、電腦、連絡人或群組] 對話方塊的 [輸入物件名稱來選取] 方塊中，輸入要新增至群組的使用者名稱或顯示名稱，然後按一下 [確定]。
    
7. 在 [內容] 對話方塊中，按一下 [確定]。
    

