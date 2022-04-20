---
title: 管理 Microsoft Teams 中的應用程式設定原則
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在Microsoft Teams中使用和管理貴組織使用者的應用程式設定原則。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 328f2676ccec6cd1450166d7032877e176d5f1cd
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910819"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>管理 Microsoft Teams 中的應用程式設定原則

身為系統管理員，您可以使用應用程式設定原則來安裝和釘選應用程式以宣傳貴組織中最常使用的應用程式，以及決定是否要讓使用者將自訂應用程式上傳至Teams。

- **釘選應用程式：** 應用程式設定原則可讓您選擇要釘選的應用程式、設定使用者在Teams應用程式行或撰寫訊息區域中的顯示順序，以及控制使用者是否可以釘選自己的應用程式。 如需詳細資訊，請參閱 [釘選應用程式](#pin-apps)。
- **安裝應用程式：** 應用程式設定原則可讓您在使用者啟動Teams和會議期間代表使用者安裝應用程式。 如需詳細資訊，請參閱 [安裝應用程式](#install-apps)。
- **Upload自訂應用程式：** 應用程式設定原則可讓使用者上傳自訂應用程式以Teams。 如需詳細資訊，請[參閱Upload自訂應用程式。](#upload-custom-apps)

## <a name="pin-apps"></a>釘選應用程式

> [!NOTE]
> 我們建議貴組織的第一線員工使用量身打造的第一線應用程式體驗。 這項功能會為擁有[F 授權](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)的使用者釘選Teams中最相關的應用程式。 若要深入瞭解，請參閱[為前線員工量身Teams應用程式](pin-teams-apps-based-on-license.md)。

釘選應用程式可讓您展示組織中使用者需要的應用程式，包括協力廠商或貴組織開發人員所建置的應用程式。

使用應用程式設定原則，您可以執行下列工作：

- 自訂 Teams 以強調對使用者而言最重要的應用程式。 您選擇要釘選的應用程式，並設定它們的顯示順序。
- 控制使用者是否可以將應用程式釘選到 Teams。

應用程式會釘選到應用程式行，也就是Teams桌面用戶端左側和 iOS 和 Android) Teams行動 (用戶端底部的列。

|Teams 桌面用戶端  |Teams 行動用戶端 |
|---------|---------|
|![Teams桌面用戶端。](media/app-setup-policies-desktop-app-bar.png).  |   ![Teams行動用戶端](media/mobile-app-ui.png)      |

訊息延伸模組位於撰寫郵件區域的底部。

> [!NOTE]
> 如果您有Teams 教育版，請務必瞭解[作業] 應用程式預設會釘選到全域原則中，即使目前未在全域原則中顯示。

若要建立應用程式設定原則來釘選應用程式，請執行下列步驟：

1. 登入[Microsoft Teams系統管理中心](https://admin.teams.microsoft.com)。

1. 在左窗格中，移至 **Teams應用程式**  >  **設定原則**。

1. 選取 [新增 **]**。

1. 輸入原則的名稱和描述。

1. 開啟 **[使用者釘選]**。

   > [!NOTE]
   > **使用者釘選** 設定可在Teams環境 (GCC GCC高和 DoD) 的 Microsoft 365 政府社群雲端 (GCC) 系統管理中心使用，但目前沒有作用。

1. 在 **[釘選的應用程式] 底** 下，選取 **[新增應用程式]**。

1. 在 [ **新增釘選的應用程式** ] 窗格中，搜尋您要新增的應用程式，然後選取 [ **新增]**。 您也可以依應用程式許可權原則篩選應用程式。

1. 選取 [新增 **]**。

1. 在 **[應用程式行**] 或 [**訊息中心] 延伸** 模組底下，依照您希望應用程式在 Teams 中顯示的順序排列這些應用程式。

   ![[釘選的應用程式] 區段。](media/pin-messaging-extensions.png)

1. 選取 [儲存 **]**。

## <a name="install-apps"></a>安裝應用程式

您可以選擇使用者在其個人Teams環境中預設要安裝哪些應用程式、將應用程式安裝為[訊息延伸](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)模組，以及指定要在會議中安裝的應用程式。

使用應用程式設定原則，您可以執行下列工作：

- 在使用者的個人Teams環境中安裝應用程式
- 為使用者安裝應用程式做為訊息延伸模組
- 在會議召集人會議中安裝應用程式

> [!NOTE]
> 如果指派給他們的 [應用程式許可權原則](teams-app-permission-policies.md) 允許，使用者仍然可以自行安裝應用程式。

若要建立應用程式設定原則來安裝應用程式，請執行下列步驟：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **Teams應用程式**  >  **設定原則**。

2. 選取 [新增 **]**。

3. 輸入原則的名稱和描述。

4. 在 **[已安裝的應用程式] 底** 下，選取 **[新增應用程式]**。

5. 在 [ **新增已安裝的應用程式** ] 窗格中，搜尋您要為使用者自動安裝的應用程式。 您也可以依應用程式許可權原則篩選應用程式。

6. 選取 [新增 **]**。

![安裝應用程式原則。](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> 使用者無法卸載系統管理員所安裝的應用程式。

## <a name="upload-custom-apps"></a>Upload自訂應用程式

您可以使用Microsoft Teams系統管理中心建立自訂原則，讓使用者上傳自訂應用程式以Teams。

若要建立應用程式設定原則以允許使用者將自訂應用程式上傳至Teams，請執行下列步驟：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **Teams應用程式**  >  **設定原則**。

2. 選取 [新增 **]**。

3. 輸入原則的名稱和描述。

4. 根據您是否要讓使用者上傳 **自訂應用程式以Teams**，開啟或關閉自訂應用程式Upload。

> [!NOTE]
> 如果在 [全組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)中關閉 **協力廠商應用程式**，您就無法變更此設定。

## <a name="manage-app-setup-policies"></a>管理應用程式設定原則

您可以在Microsoft Teams系統管理中心管理應用程式設定原則。 使用全域 (組織的預設) 原則或建立及指派自訂原則。  除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

您可以編輯全域原則中的設定，以包含您要的應用程式。 若要自訂群組織中不同使用者群組的Teams，請建立並指派一或多個自訂原則。

![[應用程式設定原則] 頁面。](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>編輯應用程式設定原則

您可以使用Microsoft Teams系統管理中心來編輯原則，包括全域 (組織的預設) 原則和您建立的自訂原則。

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **Teams應用程式**  >  **設定原則**。

2. 選擇您要編輯的原則，然後選取 [ **編輯]**。

3. 進行所要的變更。

4. 選取 [儲存 **]**。

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>指派自訂應用程式設定原則給使用者和群組

如需指派原則給使用者和群組的詳細資訊，請參閱 [指派原則給使用者和群組](assign-policies-users-and-groups.md)。

## <a name="faq"></a>常見問題集

### <a name="working-with-app-setup-policies"></a>使用應用程式設定原則

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams系統管理中心包含哪些內建應用程式設定原則

- **全域 (組織預設)**：此預設原則會套用至貴組織中的所有使用者，除非您指派其他原則。 編輯全域原則以釘選對使用者最重要的應用程式。

- **第一線工作人員**：這項原則適用于第一線工作人員。 您可以將它指派給組織中的一線工作人員。 請務必瞭解，就像您建立的自訂原則一樣，您必須將原則指派給使用者，讓設定為使用中。 For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users-and-groups) section of this article.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我在 [新增釘選的應用程式] 窗格中找不到應用程式

並非所有應用程式都可以透過應用程式設定原則釘選到Teams。 某些應用程式可能不支援此功能。 若要尋找可以釘選的應用程式，請在 [ **新增釘選的應用程式** ] 窗格中搜尋應用程式。 個人範圍 (靜態索引標籤) 和 Bot 的索引標籤可以釘選到Teams桌面用戶端，這些應用程式可在 [**新增釘選的應用程式**] 窗格中使用。

請記住，Teams App Store 會列出所有Teams應用程式。 **[新增釘選的應用程式**] 窗格僅包含可透過原則釘選到Teams的應用程式。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是系統管理員Teams 教育版。在 Teams 教育版 中的應用程式設定原則須知事項

Teams 教育版 中無法使用通話應用程式。 當您建立新的自訂應用程式設定原則時，通話應用程式會顯示在應用程式清單中。 不過，應用程式並未釘選到Teams用戶端，Teams 教育版使用者也不會在 Teams 中看到 [通話] 應用程式。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>有多少釘選的應用程式可以新增至原則

 (iOS 和 Android) ，至少必須將兩個應用程式釘選到Teams行動用戶端。 如果原則的應用程式少於兩個，行動用戶端將不會反映原則設定，而是會繼續使用現有的設定。

您可以新增至原則的釘選應用程式數量沒有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>原則變更需要多久時間才會生效

編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

### <a name="user-experience"></a>使用者體驗

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>使用者如何在 Teams 中查看所有已釘選的應用程式

若要檢視所有釘選給使用者的應用程式，使用者可能必須根據已安裝的應用程式數量及其Teams用戶端視窗的大小執行下列動作。

|Teams 桌面用戶端 |Teams 行動用戶端 |
|---------|---------|
|在 Teams 側邊的應用程式行中，選取 **...[更多應用程式]**。| 在靠近Teams底部的應用程式行中，向上撥動。|
|![Teams桌面用戶端中的更多應用程式。](media/app-setup-policies-desktop-more-apps.png)   |![Teams行動用戶端中的更多應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>行動Teams體驗須知事項

iOS 和 Android (Teams行動用戶端) 支援具有靜態索引標籤的個人應用程式。 釘選到Teams桌面用戶端的應用程式會顯示在Teams行動用戶端中。 個人機器人會出現在行動用戶端的聊天中。

協力廠商應用程式 (可從 Teams Store 下載) 必須在行動裝置上顯示之前獲得核准。 如果系統管理員釘選 Microsoft 行動裝置版未核准的應用程式，該應用程式會顯示在Teams桌面，但不會顯示在行動裝置上。 如需詳細資訊，請參閱 [行動客戶](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 端。

透過Teams行動用戶端，使用者會看到活動、聊天和Teams等核心Teams應用程式，而且您可以釘選 Microsoft 的一些第一方應用程式，例如 Shifts。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>使用者可以變更透過原則釘選的應用程式順序嗎？

如果已開啟 [**使用者釘** 選] 選項，使用者可以在Teams桌面和行動用戶端上變更釘選應用程式的順序。 使用者無法變更釘選應用程式在Teams網頁用戶端上的順序。

#### <a name="does-user-pinning-take-precedence"></a>使用者釘選優先順序是否優先

系統管理員釘選一律優先。 如果 [ **使用者釘選** ] 選項已開啟，使用者會將其釘選的應用程式保留在系統管理員釘選的應用程式下方。 如果 [ **使用者釘選** ] 選項已關閉，使用者將會失去其預先存在的圖釘，應用程式行中只會出現系統管理員釘選的應用程式。

### <a name="custom-teams-apps"></a>自訂Teams應用程式

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的組織已建置自訂Teams應用程式，並將它發佈到 AppSource 或租使用者應用程式目錄，但是當應用程式釘選到 Teams 中的應用程式行時，應用程式圖示不會如預期般顯示。 如何?修正嗎？

提交應用程式之前，請務必遵循標誌指導方針。 若要深入瞭解，請 [參閱銷售商儀表板提交檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-articles"></a>相關文章

[在 Teams 中管理應用程式的設定](admin-settings.md)

[在 Teams 中將原則指派給使用者](assign-policies-users-and-groups.md)
