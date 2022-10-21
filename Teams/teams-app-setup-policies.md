---
title: 在 Microsoft Teams 中管理應用程式設定原則
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何建立、編輯及管理應用程式設定原則，以釘選應用程式、安裝應用程式，以及允許使用者上傳自訂應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: c741bb8a1b6ab7e27ec064dc0f22226f69bc6e10
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655889"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理應用程式設定原則

身為系統管理員，您會使用應用程式設定原則來安裝和釘選應用程式，以及允許使用者上傳自訂應用程式。 釘選可協助促進組織中相關應用程式的採用。

* **釘選應用程式：** 應用程式設定原則可讓您選擇要釘選的應用程式、設定應用程式在 Teams 應用程式列或撰寫訊息區域中對使用者顯示的順序。 系統管理員也可以控制使用者是否可以釘選其自己的應用程式。 請參閱[釘選應用程式](#pin-apps)。
* **安裝應用程式：** 應用程式設定原則可讓您在使用者啟動 Teams 時和會議期間代表使用者安裝允許的應用程式。 如需詳細資訊，請參閱[安裝應用程式](#install-apps)。
* **上傳自訂應用程式：** 應用程式設定原則可讓您允許使用者將自訂應用程式上傳至 Teams。 如需詳細資訊，請參閱[上傳自訂應用程式](teams-custom-app-policies-and-settings.md)。

Microsoft Teams 系統管理中心預設提供下列內建應用程式設定原則：

* **全域 (全組織預設值)**：除非您指派另一個原則，否則此預設原則會套用至組織中的所有使用者。 編輯全域原則以釘選對使用者最重要的應用程式。

* **FirstlineWorker**：此原則適用於前線員工。 無法自訂此原則。 您可以將它指派給組織的前線員工。

## <a name="pin-apps"></a>釘選應用程式

釘選應用程式可讓您突顯組織中使用者最需要的應用程式。 釘選適用于 Teams 中的所有應用程式類型—核心應用程式、Microsoft 提供的應用程式、協力廠商應用程式，以及您組織內開發的自訂應用程式。 透過應用程式設定原則釘選應用程式也會安裝它，前提是若允許使用者使用該應用程式。 使用應用程式設定原則，您可以執行下列工作：

* 自訂使用者的 Microsoft Teams，以突顯對他們來說最重要的應用程式。 您可以選擇要釘選的應用程式，以及應用程式顯示的順序。
* 控制使用者是否可以釘選應用程式。

應用程式會釘選到 Teams 桌面用戶端左邊和 Teams 行動用戶端底部的應用程式列。

|Teams 桌面用戶端  |Teams 行動用戶端 |
|---------|---------|
|![顯示 Teams 桌面用戶端中應用程式行的螢幕擷取畫面。](media/app-setup-policies-desktop-app-bar.png).  |   ![顯示 Teams 行動用戶端中應用程式行的螢幕擷取畫面。](media/mobile-app-ui.png)      |

撰寫郵件區域底部提供訊息延伸模組。

若要使用應用程式設定原則釘選應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 [Teams 應用程式 **]**  >  **[[設定原則]](https://admin.teams.microsoft.com/policies/app-setup)**。

1. 選取 [新增 **]**。

1. 輸入原則的名稱和描述。

1. 開啟 [使用者釘選 **]**。

   > [!NOTE]
   > Microsoft 365 政府社群雲端 (GCC) 環境 (GCC、GCC High 和 DoD) 中的 Teams 系統管理中心提供 [使用者釘選 **]** 設定，但沒有作用。

1. 在 [釘選的應用程式 **]** 底下，選取 [新增應用程式 **]**。

1. 在 **[新增釘選的應用程式]** 窗格中，搜尋您要新增的應用程式，然後選取 **[新增]**。 您也可以依應用程式權限原則篩選應用程式。

1. 選取 [新增 **]**。

1. 在 [應用程式列 **]** 或 [訊息延伸模組 **]** 下，以您希望應用程式在 Teams 中顯示的順序排列應用程式。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="設定原則中釘選的應用程式和釘選的訊息延伸模組的螢幕擷取畫面。":::

1. 選取 [儲存 **]**。

> [!NOTE]
> 在 Teams 教育版中，預設會在全域原則中釘選作業應用程式，即使您未在全域原則中看見它列出亦然。

> [!NOTE]
> 針對組織的前線員工，建議您使用量身打造的前線應用程式體驗。 此功能會針對擁有 [F 授權](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)的使用者，在 Teams 中釘選最相關的應用程式。 若要深入了解，請參閱 [為您的前線員工量身打造 Teams 應用程式](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

## <a name="install-apps"></a>安裝應用程式

使用應用程式設定原則，系統管理員可以完成下列工作：

* 為使用者在其個人 Teams 環境中安裝應用程式。
* 為使用者安裝應用程式做為[訊息延伸模組](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)。

如果 [應用程式](teams-app-permission-policies.md) 許可權原則允許使用者且 Teams 系統管理員允許該應用程式，使用者就可以自行安裝應用程式。相反地，如果某個使用者或組織已封鎖應用程式，使用者就可以 [要求系統管理員核准](user-requests-approve-apps.md)。

若要使用應用程式設定原則安裝應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 [Teams 應用程式 **]**  >  **[[設定原則]](https://admin.teams.microsoft.com/policies/app-setup)**。
1. 選取 [新增 **]**。
1. 提供原則的名稱和描述。
1. 在 [安裝的應用程式 **]** 區段中，選取 [新增應用程式 **]**。
1. 在 [新增已安裝的應用程式 **]** 窗格中，搜尋您想要為使用者安裝的應用程式。 您也可以依應用程式權限原則篩選應用程式。
1. 選取 [新增 **]**。

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="透過應用程式原則安裝應用程式的螢幕擷取畫面。":::

## <a name="manage-app-setup-policies"></a>管理應用程式設定原則

您會在 Microsoft Teams 系統管理中心管理應用程式設定原則。 使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 使用者會取得全域原則。 如果您建立自訂原則，則會覆寫全域原則。 全域系統管理員或 Teams 服務系統管理員可以管理這些原則。

您會編輯全域原則中的設定，以包括您需要的應用程式。 若要針對組織中的不同使用者群組自訂 Teams，請建立並指派一或多個自訂原則。

:::image type="content" source="media/app-setup-policies-update.png" alt-text="顯示應用程式設定原則頁面的螢幕擷取畫面，其中包含管理原則或新增原則的選項。":::

### <a name="edit-an-app-setup-policy"></a>編輯應用程式設定原則

您可以使用 Microsoft Teams 系統管理中心來編輯原則，包括您建立的全域 (全組織預設) 原則和自訂原則。 編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

1. 登入 Teams 系統管理中心並存取 [Teams 應用程式 **]**  >  **[[設定原則]](https://admin.teams.microsoft.com/policies/app-setup)**。
1. 選擇您想要編輯的原則，然後選取 [編輯 **]**。

1. 進行您想要的變更。

1. 選取 [儲存 **]**。

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>在應用程式設定原則中指派自訂原則給使用者和群組

若要了解如何將原則指派給使用者和群組，請參閱[如何將原則指派給使用者和群組](assign-policies-users-and-groups.md)。

## <a name="considerations-and-limitations"></a>考量與限制

* 您無法使用應用程式設定原則來安裝具有可設定索引標籤的自訂應用程式。
* 使用者無法解除安裝系統管理員安裝的應用程式。
* 透過應用程式設定原則釘選的應用程式可以由使用者取消釘選 (如果在設定原則中允許使用者釘選)。
* 在 Teams 教育版中，預設會在全域原則中釘選作業應用程式，即使您未在全域原則中看見它列出亦然。
* 您可以新增至一個原則的釘選應用程式數目沒有上限。 不過，至少必須將兩個應用程式釘選到 Teams 行動用戶端 (iOS 和 Android)。 如果一個原則的應用程式少於兩個，行動用戶端將不會反映該原則設定，而是將繼續使用現有的設定。
* 編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

## <a name="faqs"></a>常見問題集

### <a name="working-with-app-setup-policies"></a>使用應用程式設定原則

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我在 [新增釘選的應用程式] 窗格中找不到某個應用程式

並非所有應用程式都可以透過應用程式設定原則釘選到 Teams。 某些應用程式可能不支援此功能。 若要尋找可釘選的應用程式，請在 [新增釘選的應用程式 **]** 窗格中搜尋應用程式。 具有個人範圍 (靜態索引標籤) 和 Bot 的索引標籤可以釘選到 Teams 桌面用戶端，而這些應用程式可在 [新增釘選的應用程式 **]** 窗格中取得。

請記住，Teams 應用程式市集會列出所有 Teams 應用程式。 [新增釘選的應用程式 **]** 窗格僅包含可透過原則釘選到 Teams 的應用程式。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是 Teams 教育版系統管理員。關於 Teams 教育版中的應用程式設定原則，我需要知道哪些資訊

通話應用程式在 Teams 教育版中無法使用。 當您在應用程式設定原則中建立新的自訂原則時，通話應用程式會顯示在應用程式清單中。 不過，該應用程式不會釘選到 Teams 用戶端，因此 Teams 教育版使用者不會在 Teams 中看見通話應用程式。

### <a name="user-experience"></a>使用者體驗

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>使用者如何在 Teams 中查看其所有釘選的應用程式

若要檢視為使用者釘選的所有應用程式，使用者可能必須執行下列動作，視已安裝的應用程式數目及其 Teams 用戶端視窗的大小而定。

|Teams 桌面用戶端 |Teams 行動用戶端 |
|---------|---------|
|在 Teams 側邊的應用程式列中，選取 [... 更多應用程式 **]**。| 在 Teams 底部附近的應用程式列中，向上撥動。|
|![顯示 Teams 桌面用戶端中已釘選更多應用程式的螢幕擷取畫面。](media/app-setup-policies-desktop-more-apps.png)   |![顯示 Teams 行動用戶端中已釘選更多應用程式的螢幕擷取畫面](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>關於 Teams 行動體驗，我需要知道哪些資訊

Teams 行動用戶端 (iOS 和 Android) 支援具有靜態索引標籤的個人應用程式。 釘選到 Teams 桌面用戶端的應用程式會出現在 Teams 行動用戶端中。 個人 Bot 會出現在行動用戶端上的聊天中。

第三方應用程式 (可從 Teams 市集下載) 必須先經過核准，才會在行動裝置上顯示。 如果系統管理員釘選應用程式，但其未經 Microsoft for Mobile 核准，它將會顯示在 Teams 桌面上，但不會顯示在行動裝置上。 如需詳細資訊，請參閱[行動用戶端](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients)。

透過 Teams 行動用戶端，使用者會看到核心 Teams 應用程式，例如活動、聊天和 Teams，而且您可以釘選一些 Microsoft 提供的應用程式。

#### <a name="order-of-apps-pinned-through-a-policy"></a>透過原則釘選的應用程式順序

如果已開啟 [使用者釘選 **]** 選項，則使用者可以變更 Teams 桌面和行動用戶端上其釘選應用程式的順序。 使用者無法變更 Teams Web 用戶端上其釘選應用程式的順序。

#### <a name="does-user-pinning-take-precedence"></a>使用者釘選是否優先

系統管理員釘選一律優先。 如果 [ **使用者釘選** ] 選項已開啟，則由使用者釘選的應用程式會顯示在系統管理員釘選的應用程式下方。 如果 [ **使用者釘選** ] 選項已關閉，則使用者會遺失現有的 PIN 碼，而且應用程式行中只會提供由系統管理員釘選的應用程式。

### <a name="custom-teams-apps"></a>自訂 Teams 應用程式

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的組織已建立自訂 Teams 應用程式，並將其發佈至 AppSource 或租用戶應用程式目錄，但是當應用程式釘選到 Teams 中的應用程式列時，應用程式圖示未如預期顯示。 如何修正？

提交應用程式之前，請確定您遵循標誌指導方針。 若要深入了解，請參閱[賣方儀表板提交的檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-articles"></a>相關文章

* [在 Teams 中管理應用程式的設定](admin-settings.md)
* [在 Teams 中將原則指派給使用者](assign-policies-users-and-groups.md)
