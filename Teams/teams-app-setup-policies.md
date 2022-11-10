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
ms.openlocfilehash: b9dfe2ad2598e47175a0af433c0febac17255c09
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912462"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>使用應用程式設定原則在 Teams 中釘選和自動安裝應用程式

身為系統管理員，您可以使用應用程式設定原則來安裝和釘選應用程式，以及控制哪些特定使用者可以上傳自訂應用程式。 釘選可協助促進採用，並提供您組織中相關應用程式的快速存取權。

* **[釘選應用程式](#pin-apps)：** 應用程式設定原則可讓您選擇要釘選的應用程式，並設定應用程式在 Teams 應用程式行或撰寫訊息區域中顯示給使用者的順序。 系統管理員也可以控制使用者是否可以釘選其自己的應用程式。

* **[安裝應用程式](#install-apps)：** 應用程式設定原則可讓您在使用者啟動 Teams 和會議期間，代表使用者安裝允許的應用程式。

* **上傳自訂應用程式：** 應用程式設定原則可讓您控制哪些使用者可以將自訂應用程式上傳到 Teams。 請參閱 [上傳自訂應用程式](teams-custom-app-policies-and-settings.md) 文章。

Microsoft Teams 系統管理中心預設提供下列內建應用程式設定原則：

* **全域 (全組織預設值)**：除非您指派另一個原則，否則此預設原則會套用至組織中的所有使用者。 編輯全域原則以釘選對使用者最重要的應用程式。

* **FirstlineWorker**：此原則適用於前線員工。 無法自訂此原則。 您可以將它指派給組織的前線員工。

## <a name="pin-apps"></a>釘選應用程式

釘選應用程式會在 Teams 用戶端的應用程式行中顯示應用程式。 系統管理員可以釘選應用程式，並允許使用者釘選。 釘選是用來醒目提示使用者最需要的應用程式，並促進輕鬆存取。 釘選適用于 [Teams 中所有類型的應用程式](deploy-apps-microsoft-teams-landing-page.md) ，包括核心應用程式、Microsoft 提供的應用程式、協力廠商應用程式，以及您組織內開發的自訂應用程式。

系統管理員可以透過應用程式設定原則釘選應用程式。 系統管理員釘選的應用程式會自動為允許該應用程式的使用者安裝。 這類應用程式無法由使用者卸載。 使用應用程式設定原則，您可以執行下列工作：

* 為使用者自訂 Teams，為使用者醒目提示最重要的應用程式。 您可以選擇要釘選的應用程式，以及應用程式顯示的順序。
* 控制使用者是否可以釘選應用程式。

應用程式會釘選到 Teams 桌面用戶端左邊和 Teams 行動用戶端底部的應用程式列。 撰寫郵件區域底部提供訊息延伸模組。

|Teams 桌面用戶端  |Teams 行動用戶端 |
|---------|---------|
|![顯示 Teams 桌面用戶端中應用程式行的螢幕擷取畫面。](media/app-setup-policies-desktop-app-bar.png).  |   ![顯示 Teams 行動用戶端中應用程式行的螢幕擷取畫面。](media/mobile-app-ui.png)      |

若要使用應用程式設定原則釘選應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 [Teams 應用程式 **]**  >  **[[設定原則]](https://admin.teams.microsoft.com/policies/app-setup)**。

1. 選取 [新增 **]**。

1. 輸入原則的名稱和描述。

1. 或者，開啟 **[使用者釘選** ]，允許使用者釘選應用程式並變更釘選應用程式的順序。

1. 在 [釘選的應用程式 **]** 底下，選取 [新增應用程式 **]**。

1. 在 **[新增釘選的應用程式]** 窗格中，搜尋您要新增的應用程式，然後選取 **[新增]**。

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="螢幕擷取畫面顯示如何在應用程式設定原則中新增釘選的應用程式。" lightbox="media/add-pinned-apps-large.png":::

1. 選取 [新增 **]**。

1. 在 **[應用程式行** ] 或 [ **訊息中心] 延伸模組** 底下，依照您希望應用程式在 Teams 用戶端中顯示的順序排列應用程式。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="設定原則中釘選的應用程式和釘選的訊息延伸模組的螢幕擷取畫面。":::

1. 選取 [儲存 **]**。

> [!NOTE]
> 在 Teams 教育版中，預設會在全域原則中釘選作業應用程式，即使您未在全域原則中看見它列出亦然。

> [!NOTE]
> 針對組織的前線員工，建議您使用量身打造的前線應用程式體驗。 此功能會針對擁有 [F 授權](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline)的使用者，在 Teams 中釘選最相關的應用程式。 若要深入了解，請參閱 [為您的前線員工量身打造 Teams 應用程式](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

## <a name="install-apps"></a>安裝應用程式

使用應用程式設定原則，系統管理員可以完成下列工作：

* 為使用者在其個人 Teams 環境中安裝應用程式。
* 為使用者安裝應用程式做為[訊息延伸模組](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)。

如果應用程式許可權原則允許使用者安裝 [應用程式](teams-app-permission-policies.md) ，且 Teams 系統管理員允許該應用程式，使用者就可以自行安裝應用程式。如果應用程式遭到封鎖，使用者就可以 [要求系統管理員核准](user-requests-approve-apps.md)。

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

* 如果原則允許使用者釘選，使用者可以取消釘選透過應用程式設定原則釘選的應用程式。

* 如果已開啟使用者釘選選項，使用者可以在 Teams 桌面和行動用戶端上變更釘選應用程式的順序。 使用者無法變更 Teams Web 用戶端上其釘選應用程式的順序。

* 系統管理員釘選一律優先。 如果 [使用者釘選] 選項已開啟，則由使用者釘選的應用程式會顯示在系統管理員釘選的應用程式下方。 如果 [使用者釘選] 選項已關閉，則使用者會遺失現有的 PIN 碼，而且應用程式行中只會提供由系統管理員釘選的應用程式。

* 使用者釘選設定可在 Microsoft 365 政府社群雲端的 Teams 系統管理中心使用， (GCC) 環境 (GCC、GCC High 和 DoD) ，但沒有作用。

* 在 Teams 教育版中，預設會在全域原則中釘選作業應用程式，即使您未在全域原則中看見它列出亦然。

* 您可以新增至一個原則的釘選應用程式數目沒有上限。 不過，至少必須將兩個應用程式釘選到 Teams 行動用戶端 (iOS 和 Android)。 如果一個原則的應用程式少於兩個，行動用戶端將不會反映該原則設定，而是將繼續使用現有的設定。

* 編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

* 並非所有應用程式都可以透過應用程式設定原則釘選到 Teams。 某些應用程式可能不支援此功能。 若要尋找可釘選的應用程式，請在 [新增釘選的應用程式 **]** 窗格中搜尋應用程式。 具有個人範圍 (靜態索引標籤) 和 Bot 的索引標籤可以釘選到 Teams 桌面用戶端，而這些應用程式可在 [新增釘選的應用程式 **]** 窗格中取得。 當 Teams 應用程式儲存時，會列出所有 Teams 應用程式。 [新增釘選的應用程式 **]** 窗格僅包含可透過原則釘選到 Teams 的應用程式。

* 在 Teams 教育版 中，無法使用通話應用程式。 當您在應用程式設定原則中建立新的自訂原則時，通話應用程式會顯示在應用程式清單中。 不過，該應用程式不會釘選到 Teams 用戶端，因此 Teams 教育版使用者不會在 Teams 中看見通話應用程式。

## <a name="related-articles"></a>相關文章

* [在 Teams 中管理應用程式的設定](admin-settings.md)
* [在 Teams 中將原則指派給使用者](assign-policies-users-and-groups.md)
