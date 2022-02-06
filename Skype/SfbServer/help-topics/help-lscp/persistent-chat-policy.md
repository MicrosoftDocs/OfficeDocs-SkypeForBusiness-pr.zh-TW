---
title: 常設聊天室原則
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 您可以使用 Persistent 聊天群組的持續聊天原則頁面，管理全域、集區、網站或使用者層級的原則，包括設定預設全域原則，以及為您的部署建立一或多個額外的使用者和網站原則。 如果使用者依原則為使用者啟用 Persistent Chat Server，則 Persistent Chat Server 環境會出現在其用戶端中。
---

# <a name="persistent-chat-policy"></a>常設聊天室原則
 
您可以使用 **Persistent 聊天** 群組的 **持續聊天原則** 頁面，管理全域、集區、網站或使用者層級的原則，包括設定預設全域原則，以及為您的部署建立一或多個額外的使用者和網站原則。 如果使用者依原則為使用者啟用 Persistent Chat Server，則 Persistent Chat Server 環境會出現在其用戶端中。
  
當您部署 Persistent Chat Server 時，會自動建立全域原則，而且可以設定，但不能刪除。 因為全域原則會套用至所有使用者，所以不需要為每個使用者設定。
  
您可以建立及設定多個網站和使用者原則，以及全域原則，讓使用者能夠使用 Persistent Chat Server。 Pool 和 site Persistent Chat Server policy 會覆寫全域 Persistent Chat Server policy，但僅限於該網站的使用者。 對於獲指派指使用原則的使用者，使用者原則會優先於其全域、集區和網站原則。
  
> [!NOTE]
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。 
  
## <a name="tasks-that-you-can-perform"></a>您可以執行的工作

您可以在 **Persistent Chat Policy** 頁面上執行下列工作：啟用 Persistent chat Server Policy;manage Persistent Chat Server policy。
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>設定持久聊天的全域原則

1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在商務用 Skype Server 控制台] 中，按一下 [ **persistent chat**]，然後按一下 [ **persistent chat Policy**]。
    
4. 依序按一下原則清單中的 [全域]、[編輯] 及 [顯示詳細資料]。
    
5. 在 [編輯常設聊天室原則 - 全域] 中，執行下列動作：
    
   - 如果您不想要使用預設值 [全域]，請在 [名稱] 中指定全域原則的新名稱。
    
   - 在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如  _CentralSiteName_) 的全域原則）。
    
   - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>若要建立網站的持續聊天原則

您可以針對已部署的每個網站，建立網站特定的持久聊天原則。
  
網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。
    
4. 按一下 [新增]，然後按一下 [站台原則]。
    
5. 在 [選取站台] 中，按一下要套用該原則的網站。
    
6. 在 [新增常設聊天室原則] 中，執行下列動作：
    
   - 在 [名稱] 中，指定新網站原則的名稱 (例如，Redmond)。
    
   - 在 [描述] 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。
    
   - 若要控制未特別透過網站原則控制之所有網站的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。
    
7. 按一下 **[認可]**。
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>若要建立持久聊天的使用者原則

在 [商務用 Skype Server 控制台] 中，您可以定義可指派 **給使用者使用者** 的使用者原則。
  
使用者原則會覆寫全域與網站原則，但僅限於指派?特定使用者的使用者原則。
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。
    
4. 按一下 [新增]，然後按一下 [使用者原則]。
    
5. 在 [新增常設聊天室原則] 中，執行下列動作：
    
   - 在 [名稱] 中，指定新使用者原則的名稱。
    
   - 在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如，特定使用者) 的持續性聊天原則）。
    
   - 若要控制未特別透過使用者原則控制之所有使用者的持續聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>將 Persistent Chat 使用者原則套用至使用者帳戶

如果使用者已啟用商務用 Skype Server，您可以將適當的原則套用至特定使用者，以便為 Persistent Chat Server 啟用或停用。
  
使用本主題中的程式，將先前建立的 Persistent Chat 使用者原則套用至一或多個使用者帳戶或使用者群組。
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。
    
4. 在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。
    
5. 在 [ **Persistent chat 原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的 [持久聊天] 使用者原則。
    
    > [!NOTE]
    > **\<Automatic\>** 設定將套用預設的有效原則。 伺服器會自動套用這些設定。
  
6. 按一下 **[認可]**。
    

