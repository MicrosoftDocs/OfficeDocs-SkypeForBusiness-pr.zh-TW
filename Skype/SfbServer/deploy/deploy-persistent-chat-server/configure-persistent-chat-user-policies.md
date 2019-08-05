---
title: 設定常設聊天室使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中建立持續聊天伺服器的初始使用者原則。 持續聊天的使用者原則會判斷是否允許使用者存取聊天室。'
ms.openlocfilehash: 3f2a55f3a411fc3020ebe9af57d456f00dd74ef4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193998"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>設定常設聊天室使用者原則
 
**摘要:** 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 中建立持續聊天伺服器的初始使用者原則。 持續聊天的使用者原則會判斷是否允許使用者存取聊天室。
  
您可以在下列層面管理持續性聊天伺服器使用者原則: 全域、網站或使用者。 首先, 您要設定全域原則, 為您部署中的所有使用者啟用持續聊天設定, 然後建立其他使用者和網站原則, 以控制是否針對特定的使用者和網站開啟持續聊天功能。
  
本主題包含下列各節:
  
- 設定全域原則
    
- 建立網站原則
    
- 建立使用者原則
    
- 將原則套用到使用者或使用者群組
    
> [!NOTE] 
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。

## <a name="configure-the-global-policy"></a>設定全域原則

若要設定全域原則:
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。
    
3. 在商務用 Skype Server 的 [控制台] 中, 按一下 [**持續聊天**], 然後按一下 [**永久聊天原則**]。
    
4. 按一下原則清單中的 [全域]****，按一下 [編輯]****，然後按一下 [顯示詳細資料]****。
    
5. 在 [編輯常設聊天室原則 - 全域] **** 中，執行下列動作： 
    
   - 如果不想要使用全域的預設設定，請在 [名稱] **** 中指定全域原則的新名稱。
    
   - 在 [**描述**] 中, 提供使用者原則的詳細資料 (例如, _centralSiteName_的全域原則)。
    
   - 若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的持續聊天, 請選取或清除 [**啟用持續聊天**] 核取方塊。
    
6. 按一下 [認可]****。
    
## <a name="create-a-site-policy"></a>建立網站原則

針對您已部署的每個網站, 您可以建立特定于網站的持久聊天原則。 網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。 若要建立網站原則:
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。
    
4. 按一下 [新增]****，然後按一下 [站台原則]****。
    
5. 在 [選取站台] **** 中，按一下要套用原則的網站。
    
6. 在 [新增常設聊天室原則] **** 中，執行下列動作：
    
   - 在 [名稱]**** 中，指定新網站原則的名稱 (例如，Redmond)。
    
   - 在 [描述]**** 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。
    
   - 若要控制未特別透過網站原則控制之所有網站的常設聊天室，請選取或清除 [啟用常設聊天室]**** 核取方塊。
    
7. 按一下 [認可]****。
    
## <a name="create-a-user-policy"></a>建立使用者原則

您可以建立使用者專用的原則來覆寫全域原則, 以及使用者所屬的任何網站原則。 若要建立使用者原則:
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。
    
4. 依序按一下 [新增]**** 和 [使用者原則]****。
    
5. 在 [新增常設聊天室原則] **** 中，執行下列動作：
    
   - 在 [名稱] **** 中，指定新使用者原則的名稱。
    
   - 在 [**描述**] 中, 提供使用者原則的詳細資料 (例如, 針對特定使用者的持續聊天原則)。
    
   - 若要控制未透過使用者原則明確控制之所有使用者的持續聊天, 請選取或清除 [**啟用持續聊天**] 核取方塊。
    
6. 按一下 [認可]****。
    
## <a name="apply-a-policy-to-a-user-account"></a>將原則套用到使用者帳戶

建立原則之後, 您可以將它們套用至使用者帳戶, 如下所示:
  
1. 使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。
    
3. 在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。
    
4. 在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。
    
5. 在 [**永久聊天原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中, 選取您要套用的持久聊天使用者原則。
    
    > [!NOTE]
    > [ ** \<自動\> **設定] 會套用預設的有效原則。 伺服器會自動套用這些設定。
  
6. 按一下 [認可]****。
    

