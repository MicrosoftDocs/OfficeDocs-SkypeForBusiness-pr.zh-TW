---
title: 管理應用程式中的應用程式設定Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在組織中Microsoft Teams應用程式設定策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059197"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>管理應用程式中的應用程式設定Microsoft Teams

做為系統管理員，您可以使用應用程式設定策略執行下列工作：

- 自訂 Teams 以強調對使用者而言最重要的應用程式。 您可以選擇要釘選的應用程式，並設定其顯示順序。 釘上應用程式可讓您展示貴組織中使用者所需的應用程式，包括由協力廠商或貴組織的開發人員所建立的應用程式。
- 控制使用者是否可以將應用程式釘選到 Teams。
- 代表使用者安裝應用程式。 您可以選擇使用者啟動應用程式時，預設會安裝Teams。 請記住，如果指派給使用者的應用程式許可權政策允許，使用者仍可[](teams-app-permission-policies.md)自行安裝 App。

> [!Note]
> 對於系統管理員安裝的 App，使用者無法卸載這些應用程式。

應用程式會釘到應用程式欄，即 Teams 桌面用戶端側邊以及 Teams 行動用戶端 (iOS 和 Android) 。

|Teams桌面用戶端  |Teams 行動用戶端 |
|---------|---------|
|![桌面Teams用戶端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![手機Teams用戶端](media/mobile-app-ui.png)      |

若要查看系統管理員安裝的應用程式，請在應用程式欄中選取 **...在桌面** 和 web 用戶端Teams更多應用程式，然後向上滑動到行動用戶端。

您可以在系統管理中心管理Microsoft Teams設定政策。 使用全域 (整個組織的預設) ，或建立及指派自訂策略。  除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

您可以編輯全域原則中的設定，以包含您想要的應用程式。 若要自訂Teams組織中不同使用者群組的使用者，請建立並指派一或多個自訂策略。

![應用程式設定政策頁面](media/app-setup-policies.png)

> [!NOTE]
> 如果您有Teams，您必須知道全域原則中的作業應用程式預設為釘點，即使目前未在全域原則中列出。 它會是用戶端上釘上應用程式清單中的第四Teams App。

## <a name="create-a-custom-app-setup-policy"></a>建立自訂應用程式設定策略

您可以使用系統管理Microsoft Teams建立自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **政策**。

2. 選取 [新增 **]**。

   ![新增應用程式設定政策頁面](media/app-setup-policies-add.png)

3. 輸入原則的名稱和描述。

4. 視您是否要讓使用者上傳 **自訂** Upload，開啟或關閉自訂應用程式Teams。 如果全組織 App 設定中已關閉 **允許第** 三方應用程式， [則無法變更此設定](manage-apps.md#manage-org-wide-app-settings)。

5. 開啟或關閉 **允許使用者釘點**，取決於您是否要讓使用者將應用程式釘到 App 欄來個人化其 App 欄。

   > [!NOTE]
   > **Microsoft 365 政府社群雲端 (GCC) 、 (GCC** GCC高和 DoD Teams系統管理中心提供允許使用者釘) 設定，但目前沒有作用。

6. 若要為使用者安裝應用程式，請執行下列工作：

    1. 在 **安裝的應用程式下**，選取 新增 **應用程式**。

    2. 在新增 **已安裝的應用程式窗格中**，搜尋使用者啟動應用程式時要自動安裝Teams。 您也可以根據應用程式權限原則篩選應用程式。 當您選擇您的應用程式清單時，請選取 **新增**。

       ![新增已安裝的應用程式窗格](media/app-setup-policies-add-installed-apps.png)

7. 若要釘上應用程式，請執行下列步驟：

    1. 在 **已釘選的 App** 下，選取 新增 **應用程式**。

    2. 在新增 **釘選的應用程式窗格中** ，搜尋您想要新增的應用程式，然後選取 **新增**。 您也可以根據應用程式權限原則篩選應用程式。 當您選擇要釘選的應用程式清單時， **請選取** 新增 。

       ![新增釘上應用程式窗格](media/app-setup-policies-add-apps.png)

    3. 以您希望 App 在應用程式中顯示的順序排列Teams，然後選取 **儲存**。

       ![釘上應用程式區段](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>編輯應用程式設定策略

您可以使用系統管理Microsoft Teams編輯策略，包括您 (全組織的預設) 策略和自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **政策**。

2. 按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。

3. 從此處，進行您需要的變更。

4. 選取 [儲存 **]**。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>指派自訂應用程式設定策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>常見問題集

### <a name="working-with-app-setup-policies"></a>使用應用程式設定策略

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>系統管理中心內建的應用程式設定Microsoft Teams政策

- **全域 (全組織的預設) ：** 除非您指派其他原則，否則此預設原則會適用于貴組織中的所有使用者。 編輯全域原則以釘上使用者最重要的應用程式。

- **FrontlineWorker：** 此政策適用于前線員工。 您可以將它指派給貴組織的前線工作人員。 您必須知道，就像您建立自訂策略一樣，您必須將策略指派給使用者，讓設定保持有效。 For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我在新增釘上的應用程式窗格中找不到應用程式

並非所有應用程式都可以透過應用程式設定Teams釘釘至其他應用程式。 某些應用程式可能不支援此功能。 若要尋找可釘上的應用程式，請搜尋在新增釘上 App 窗格中 **的應用程式** 。 具有個人範圍 (靜態) 和 bot 的定位點可以釘釘到 Teams 桌面用戶端，這些應用程式可在新增釘上的應用程式窗格中 **使用**。

請記住，應用程式Teams會列出所有Teams應用程式。 新增 **釘上應用程式窗格** 僅包含可透過Teams釘釘至應用程式。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是教育Teams管理員。我需要知道教育用應用程式中的應用程式設定Teams政策

教育用應用程式無法Teams通話應用程式。 當您建立新的自訂應用程式設定策略時，通話應用程式會顯示在應用程式清單中。 不過，應用程式不會釘Teams用戶端，Teams使用者不會在 Teams 中看到通話應用程式。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>可新增多少個釘點應用程式至策略

在 iOS 和 Android 手機上，Teams至少 (兩個 app) 。 如果策略少於兩個 App，行動用戶端不會反映該策略設定，而是會繼續使用現有的設定。

您可以新增到策略的釘點 App 數量沒有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>政策變更生效需要多久時間

編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

### <a name="user-experience"></a>使用者體驗

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>使用者如何在應用程式中查看所有已釘Teams

若要查看已釘住使用者的所有 App，使用者可能需要根據已安裝的應用程式數量及其用戶端視窗Teams執行下列操作。

|Teams桌面用戶端 |Teams 行動用戶端 |
|---------|---------|
|在應用程式欄的 Teams中，選取 **...更多應用程式**。| 在靠近應用程式底部的應用程式Teams向上滑動。|
|![桌面用戶端Teams更多應用程式](media/app-setup-policies-desktop-more-apps.png)<br>   |![行動用戶端中的Teams應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>我需要知道行動Teams體驗

iOS Teams Android (的手機用戶端) 靜態選項卡支援個人 App。 固定到桌面Teams的應用程式會顯示在Teams用戶端中。 個人 Bot 會顯示在行動用戶端上的聊天中。

協力廠商應用程式 (可從 Store Teams下載) ，才能在行動版上顯示。 如果系統管理員釘釘了未經 Microsoft for Mobile Teams的應用程式，它會顯示在桌上出版上，但不會顯示在行動版上。 請參閱 [行動用戶端](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 以瞭解更多資訊。

有了Teams用戶端，使用者會看到核心 Teams 應用程式，例如活動、聊天和 Teams，而且您可以釘上 Microsoft 的一些第一方應用程式，例如 Shifts。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>使用者可以變更透過策略釘上的應用程式順序嗎？

如果使用者開啟了允許使用者釘選選項，Teams桌面和行動用戶端上的釘選應用程式順序。  使用者無法變更在 Web 用戶端上釘Teams的順序。

#### <a name="does-user-pinning-take-precedence"></a>使用者釘點是否優先

系統管理圖釘永遠優先。 如果開啟 **了允許使用者釘選** 選項，使用者就會在系統管理員釘選的 App 下方保留已釘選的應用程式。 如果 **關閉允許使用者** 釘選選項，則使用者將失去其預先存在的圖釘，且只有系統管理員釘選的應用程式會存在於應用程式欄中。

### <a name="custom-teams-apps"></a>自訂Teams應用程式

我的組織已建立自訂 Teams 應用程式，併發布至 AppSource 或租使用者應用程式目錄，但是當應用程式釘釘到 Teams 中的應用程式欄時，應用程式圖示不會如預期顯示。 如何修正此問題

提交應用程式之前，請務必遵循標誌指導方針。 若要深入瞭解，請參閱賣方 [儀表板提交檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>相關主題

[在 Teams 中管理應用程式的設定](admin-settings.md)

[在 Teams 中將原則指派給使用者](assign-policies.md)
