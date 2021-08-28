---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat 使用者原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中建立 Persistent Chat Server 的初始使用者原則。 Persistent Chat 使用者原則決定使用者是否可以存取聊天室。
ms.openlocfilehash: 0cf0bb4f241e6186dcf63c3678e36e11e65b0956
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624395"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定 Persistent Chat 使用者原則
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中建立 Persistent Chat Server 的初始使用者原則。 Persistent Chat 使用者原則決定使用者是否可以存取聊天室。
  
您可以在下列層級管理 Persistent Chat Server 使用者原則：全域、網站或使用者。 起初，您會設定全域原則，為部署中的所有使用者啟用 Persistent Chat 設定，然後建立其他使用者和網站原則，以控制是否開啟特定使用者和網站的持續性聊天功能。
  
本主題包含下列各節：
  
- 設定全域原則
    
- 建立網站原則
    
- 建立使用者原則
    
- 將原則套用至使用者或使用者群組
    
> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。

## <a name="configure-the-global-policy"></a>設定全域原則

若要設定全域原則：
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在商務用 Skype Server 控制台] 中，按一下 [ **persistent chat**]，然後按一下 [ **persistent chat Policy**]。
    
4. 依序按一下原則清單中的 [全域]、[編輯] 及 [顯示詳細資料]。
    
5. 在 [編輯常設聊天室原則 - 全域] 中，執行下列動作： 
    
   - 如果您不想要使用預設值 [全域]，請在 [名稱] 中指定全域原則的新名稱。
    
   - 在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如  _CentralSiteName_) 的全域原則）。
    
   - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="create-a-site-policy"></a>建立網站原則

您可以針對已部署的每個網站，建立網站特定的持久聊天原則。 網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。 若要建立網站原則：
  
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
    
## <a name="create-a-user-policy"></a>建立使用者原則

您可以建立使用者特有的原則，以覆寫全域原則和使用者所屬的任何網站原則。 若要建立使用者原則：
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。
    
4. 按一下 [新增]，然後按一下 [使用者原則]。
    
5. 在 [新增常設聊天室原則] 中，執行下列動作：
    
   - 在 [名稱] 中，指定新使用者原則的名稱。
    
   - 在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如，特定使用者) 的持續性聊天原則）。
    
   - 若要控制未特別透過使用者原則控制之所有使用者的持續聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="apply-a-policy-to-a-user-account"></a>將原則套用至使用者帳戶

建立原則之後，您可以將原則套用至使用者帳戶，如下所示：
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。
    
4. 在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。
    
5. 在 [ **persistent chat 原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的 [持久聊天] 使用者原則。
    
    > [!NOTE]
    > **\<Automatic\>** 設定將套用預設的有效原則。 伺服器會自動套用這些設定。
  
6. 按一下 **[認可]**。
    

