---
title: 管理 Microsoft 團隊中的 app 許可權原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的 app 許可權原則，以及如何使用它們來控制貴組織中的使用者可以使用哪些應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 83a06357402b44c5c15932211e562e488c2a2d5a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938472"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的 app 許可權原則

身為系統管理員，您可以使用應用程式權限原則來控制組織中 Microsoft Teams 使用者可使用的應用程式。 您可以允許或封鎖由 Microsoft、協力廠商及貴組織發佈的所有 app 或特定應用程式。 當您封鎖應用程式時，擁有原則的使用者將無法從 Teams 應用程式商店安裝該應用程式。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

您可以在 Microsoft 團隊系統管理中心管理 app 許可權原則。 您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 在您編輯或指派原則之後，可能需要幾個小時的時間，變更才會生效。

![App 許可權原則的螢幕擷取畫面](media/app-permission-policies.png)

> [!NOTE]
> 整個組織內的應用程式設定會覆寫全域原則和您建立並指派給使用者的任何自訂原則。

如果您的組織已在團隊中，您在 Microsoft 365 系統管理中心的 [整個租使用者]**設定**中所設定的應用程式設定會反映在 [[管理應用程式](manage-apps.md)] 頁面上的 [組織內應用程式設定] 中。 如果您是團隊新手，且剛開始使用，則預設會允許全域原則中的所有 app。 這包含由 Microsoft、協力廠商及貴組織發佈的應用程式。

例如，您想要封鎖所有協力廠商應用程式，並允許 Microsoft 針對貴組織中的人力資源小組特定應用程式。 首先，您會移至 [[管理應用程式](manage-apps.md)] 頁面，並確認您想要在人力資源團隊中允許的應用程式可在組織層級使用。 接著，建立名為 HR App 許可權原則的自訂原則，將它設定為 [封鎖] 並允許您想要的 app，然後將它指派給 HR 小組的使用者。

> [!NOTE]
> 如果您已在 Microsoft 365 政府版的環境中部署團隊，請參閱適用于[gcc 的 App 許可權原則](#app-permission-policies-for-gcc)，以深入瞭解適用于 GCC 的協力廠商應用程式設定。

## <a name="create-a-custom-app-permission-policy"></a>建立自訂應用程式許可權原則

如果您想要控制貴組織中不同群組使用者的可用應用程式，請建立並指派一或多個自訂應用程式許可權原則。 您可以根據 Microsoft、協力廠商或您的組織發佈的應用程式，建立並指派個別的自訂原則。 您必須知道，在您建立自訂原則之後，如果已停用組織內應用程式設定中的協力廠商應用程式，就無法變更它。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**]  >  **許可權原則**。
2. 按一下 [**新增**]。 <br>
    ![新應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-new-policy.png)
3. 輸入原則的名稱和描述。
4. 在 [ **Microsoft app**]、[**協力廠商應用**程式] 和 [**自訂應用程式**] 底下，選取下列其中一項：

    - **允許所有 app**
    - **允許特定的 app 和封鎖所有人**
    - **封鎖特定應用程式並允許所有其他 app**
    - **封鎖所有 app**

5. 如果您已選取 [**允許特定應用程式並封鎖其他 app**]，請新增您想要允許的應用程式：

    1. 選取 [**允許應用程式**]。
    1. 搜尋您要允許的應用程式，然後按一下 [**新增**]。 搜尋結果會篩選到應用程式發行者（**Microsoft**app、**協力廠商應用程式**或**自訂應用程式**）。
    1. 當您選取 app 清單後，請按一下 [**允許**]。 

6. 同樣地，如果您已選取 [**封鎖特定應用程式並允許所有人**]，請搜尋並新增您想要封鎖的應用程式，然後按一下 [**封鎖**]。
7. 按一下 [儲存]****。

## <a name="edit-an-app-permission-policy"></a>編輯應用程式許可權原則

您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括您建立的全域原則和自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**]  >  **許可權原則**。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 您可以從這裡進行所要的變更。 您可以根據應用程式發行者管理設定，然後根據 [允許/封鎖] 設定新增及移除應用程式。
4. 按一下 [儲存]****。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>將自訂應用程式許可權原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="app-permission-policies-for-gcc"></a>適用于 GCC 的 App 許可權原則

在 Microsoft 365 政府版的團隊部署中，請務必瞭解下列關於適用于 GCC 的協力廠商應用程式設定。

在 GCC 中，預設會封鎖所有協力廠商應用程式。 此外，您會在 Microsoft 團隊系統管理中心的 [應用程式許可權原則] 頁面上，看到有關管理協力廠商應用程式的相關資訊。

![在 GCC 中應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-gcc.png)

若要為您組織中的使用者或一組使用者啟用協力廠商應用程式，請執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]，然後在應用程式清單中，確認您要允許一組使用者使用的協力廠商應用程式已設定為 [在組織層級**封鎖**]。

2. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **許可權原則**]，然後編輯全域原則來封鎖協力廠商應用程式。 若要執行此動作：
    1. 在 [應用程式許可權原則] 頁面上，按一下 [**全域（組織範圍預設值）**]，然後按一下 [**編輯**]。
    2. 在 [**協力廠商應用程式**] 底下，選取 [**封鎖特定的 app 並允許所有其他**app]，新增應用程式，然後按一下 [**儲存**]。

    > [!NOTE]
    > 在您移至下一個步驟之前，請務必先執行此動作，才能允許組織層級的 app。 這是因為如果協力廠商應用程式未封鎖在全域應用程式許可權原則中，則全域原則適用的所有使用者，都可以在組織階層時存取協力廠商 app。

3. 允許組織階層的協力廠商應用程式。 若要執行此動作，請在左側導覽中，移至 [**團隊 app**  >  **管理應用程式**]。 在應用程式清單中，按一下應用程式名稱的左邊以選取 app，然後選取 [**允許**]。
4. [建立自訂應用程式許可權原則](#create-a-custom-app-permission-policy)以允許 app，然後[將原則指派](#assign-a-custom-app-permission-policy-to-users)給您想要的使用者。

## <a name="faq"></a>常見問題集

### <a name="working-with-app-permission-policies"></a>使用應用程式許可權原則

#### <a name="what-app-interactions-do-permission-policies-affect"></a>許可權原則會影響哪些 app 互動？
許可權原則可控制使用者的安裝、探索及互動，以控制應用程式的使用狀況。 無論指派的許可權原則為何，管理員仍可管理 Microsoft 團隊系統管理中心中的 app。

#### <a name="can-i-control-line-of-business-lob-apps"></a>我可以控制商務用線（LOB）應用程式嗎？
是的，您可以使用應用程式許可權原則來控制自訂（LOB）應用程式的推出與發佈。 您可以建立自訂原則或編輯全域原則，以根據貴組織的需求來允許或封鎖自訂應用程式。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>App 許可權原則如何與釘選的 app 和 app 設定原則相關？

您可以將應用程式設定原則與 app 許可權原則搭配使用。 已從使用者的已啟用應用程式集中選取預先固定的 app。 此外，如果使用者有應用程式許可權原則，而該策略封鎖 app 設定原則中的 app，該 app 就不會出現在小組中。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>我可以使用應用程式許可權原則來限制上傳自訂應用程式嗎？

您可以在 [**管理**app] 頁面上使用整個組織的設定，或按一下 [應用程式設定原則]，限制您的組織上傳自訂應用程式。  

若要限制特定使用者上傳自訂應用程式，請使用自訂 app 原則。 若要深入瞭解，請參閱[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>封鎖應用程式適用于團隊行動用戶端嗎？

是的，當您封鎖應用程式時，該應用程式會在所有團隊用戶端間封鎖。  

### <a name="user-experience"></a>使用者體驗

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>當應用程式遭到封鎖時，使用者有何體驗？

使用者無法與封鎖的 app 或其功能（例如 bot、索引標籤和訊息延伸）互動。 在共用的內容（例如小組或群組聊天）中，機器人仍可以傳送訊息給該內容的所有參與者。 小組會在應用程式遭到封鎖時向使用者顯示。

例如，當應用程式遭到封鎖時，使用者就不能執行下列任何一項動作：

- 將 app 新增至個人或加入聊天或團隊
- 傳送訊息給應用程式的 bot
- 執行傳送資訊回到應用程式的按鈕動作，例如可操作的訊息  
- [查看] 應用程式的索引標籤
- 設定連接器接收通知
- 使用應用程式的訊息延伸

舊版入口網站允許您在組織階層控制應用程式，這表示當應用程式遭到封鎖時，系統會封鎖組織中的所有使用者。 封鎖 [[管理應用程式](manage-apps.md)] 頁面上的應用程式的運作方式與此完全相同。

針對指派給特定使用者的 app 許可權原則，如果允許並封鎖具有機器人或連接器功能的應用程式，而且如果只允許共用內容中的部分使用者使用該應用程式，則群組聊天或頻道的成員不具備該應用程式的許可權，就能看到由 bot 或連接器張貼的訊息歷程記錄和訊息。，但無法與它互動。

## <a name="related-topics"></a>相關主題

[在 Teams 中的應用程式系統管理設定](admin-settings.md)

[指派策略給小組中的使用者](assign-policies.md)
