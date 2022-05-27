---
title: 在 Teams 面板上Microsoft Teams應用程式/商務 (LOB) 應用程式支援
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 說明Teams應用程式/LOB 應用程式的支援。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f9d2e3b17f852dcd020dc11c323bbc24c2dfc30
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675905"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>在 Teams 面板上Microsoft Teams應用程式/商務 (LOB) 應用程式支援

Teams面板新增[Teams應用程式/商務營運 (LOB) 應用程式的支援](/microsoftteams/platform/overview)。 這可讓企業在面板上新增其他體驗，以符合貴組織的需求。 此版本支援靜態網頁內容。

> [!IMPORTANT]
> 只有在更新Teams面板裝置 () 之後，才能使用此功能。 您必須擁有 Teams 應用程式版本 1449/1.0.97.2021070601 或更新版本，才能在Teams面板中取得應用程式支援。

## <a name="teams-app-experience-on-teams-panels"></a>在Teams面板上Teams應用程式體驗

![顯示哪個區段可讓使用者流覽至應用程式的Teams系統管理中心的螢幕擷取畫面。](media/tac1update.png)

*Teams面板主畫面包含應用程式流覽選項，以紅色螢幕擷取畫面標示。請注意，這些是範例圖示，可能無法使用。*

![應用程式畫布的螢幕擷取畫面，其中可以新增應用程式。](media/appscreen.png)

*當使用者點選其中一個應用程式圖示時，他們會在上一個螢幕擷取畫面中看到Teams應用程式畫面。螢幕擷取畫面中的灰色矩形是應用程式在Teams 面板上顯示的位置。應用程式行已修正，屬於Teams面板應用程式的一部分。*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>在 Teams 系統管理中心中設定和管理Teams面板應用程式

Microsoft Teams應用程式會將重要資訊、常用工具和信任的程式帶入人們收集、學習及工作的地點。 Teams應用程式[可透過整合功能運作](/microsoftteams/platform/concepts/capabilities-overview)。 現在，身為 IT 系統管理員，您可以選擇要在貴組織的 Teams 面板裝置中加入哪些應用程式，並透過[Teams系統管理中心自訂許可權](https://admin.teams.microsoft.com/)。

您現在可以在Teams面板上使用Teams應用程式，並根據貴組織的需求自訂使用者體驗。 您可以決定使用者可以存取及使用哪個 Web 應用程式，並排列應用程式檢視的優先順序。 目前不支援某些選項，例如 Bot 和訊息中心功能。 深入瞭解[Teams應用程式](/microsoftteams/platform/overview)，以及[如何在 Microsoft Teams 中管理您的裝置](/microsoftteams/devices/device-management)。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>在 Teams 系統管理中心管理Teams面板上的應用程式

**注意**：您必須是全域系統管理員或Teams服務系統管理員，才能存取 [Teams系統管理中心](https://admin.teams.microsoft.com/)。

使用者可以在Teams面板上檢視但無法安裝應用程式。 身為系統管理員，您可以透過Teams系統管理中心檢視和管理貴組織的所有Teams應用程式。 透過 [管理應用程式] 頁面深入瞭解如何 [在 Microsoft Teams 系統管理中心管理](/microsoftteams/manage-apps)**您的應用程式**。 Teams系統管理中心內的 [**管理應用程式**] 頁面也是您可以上傳 [自訂應用程式](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)的地方。

設定應用程式之後，您可以使用 [應用程式許可權原則](/microsoftteams/teams-app-permission-policies) 和 [應用程式設定原則](/microsoftteams/teams-app-setup-policies) ，為組織中的特定聊天室帳戶設定應用程式體驗。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>使用應用程式設定原則將應用程式釘選到Teams面板上

由於Teams提供顯示各種應用程式的功能，系統管理員可以決定哪些應用程式對組織最為重要，並且只將這些應用程式釘選到Teams面板 **主** 畫面以供快速存取。 如果有超過五個釘選的應用程式或任何未釘選的應用程式，它們將會顯示在 [ **其他** ] 畫面下方。 Microsoft 建議您特別針對Teams面板建立自訂應用程式設定原則。

![應用程式設定原則頁面的使用者介面螢幕擷取畫面。](media/appsetup1.png)

若要管理Teams面板上顯示的釘選應用程式，請登入貴組織的Teams系統管理中心，並流覽至 **Teams應用程式** \> **設定原則** \> **選取或建立釘選的新原則** \> 。****

![使用者介面內已釘選應用程式區段的螢幕擷取畫面。](media/appsetup2.png)

*此影像中包含的應用程式只是範例，可能無法使用。*

Microsoft 建議您關閉 **Upload自訂應用程式** 和 **使用者釘選**，以在Teams面板上獲得最佳Teams應用程式體驗。

如需釘選應用程式的詳細資訊，請參閱 [管理應用程式設定原則](/microsoftteams/teams-app-setup-policies)。

## <a name="manage-apps-display-order-in-teams-panels"></a>管理Teams面板中的應用程式顯示順序

![使用者介面內應用程式區段的螢幕擷取畫面。](media/appsetup3.png)

*此影像中包含的應用程式只是範例，可能無法使用。*

若要管理應用程式顯示在Teams面板上的順序，請登入貴組織的Teams系統管理中心，並流覽至 **Teams應用程式** \> **設定原則** \> **選取 [原則** \> **釘選的應用程式：****上移/下移]**。

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>將設定原則指派給會議室資源帳戶

建立設定原則之後，系統管理員必須將此原則指派給要登入Teams面板的聊天室資源帳戶。 如需詳細資訊，請參閱 [指派原則給使用者和群組](/microsoftteams/assign-policies-users-and-groups)。

## <a name="faq"></a>常見問題集

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Teams面板需要多久時間才能取得新的或更新的應用程式設定原則？

在 Teams系統管理中心編輯或指派新原則之後，最多可能需要 24 小時，變更才會生效。 系統管理員可以嘗試從面板登出/登入、點選 **設定** 圖示，然後返回首 **頁** 畫面嘗試重新整理原則。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>「更多」畫面上應用程式的順序為何？

在 [ **其他應用程式]** 頁面上，釘選的應用程式會先出現。 然後，任何其他已安裝的應用程式將會依字母順序顯示。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>為什麼 Bot 應用程式無法顯示在Teams面板上？

目前僅支援靜態索引標籤網頁內容。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>為什麼原生Teams應用程式，例如行事曆和工作，不會出現在Teams面板上？

原生Teams應用程式，例如行事曆和工作，不會顯示在Teams面板上。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>在Teams系統管理中心，在 [設定原則] 區段底下，已安裝的應用程式與釘選的應用程式之間有何不同？

針對Teams面板，Microsoft 建議您使用釘選的應用程式，讓系統管理員能夠選取所需的應用程式，並重新排列其順序。

**注意：** 有些應用程式不支援應用程式釘選。 請連絡應用程式開發人員以啟用應用程式釘選功能。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>為什麼其他應用程式即使不屬於已安裝或釘選的應用程式，還是會出現在 [其他] 畫面上，Teams應用程式設定原則一節中？

如果應用程式先前是透過其他應用程式原則安裝，或是手動在Teams桌面/Web 用戶端中安裝Teams面板上使用的聊天室資源帳戶，系統管理員可能需要登入Teams中的聊天室資源帳戶，然後以滑鼠右鍵按一下應用程式，然後選取 [**卸載**]，手動卸載應用程式。

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我在 [新增釘選的應用程式] 窗格中找不到應用程式？

並非所有應用程式都可以透過應用程式設定原則釘選到Teams。 某些應用程式可能不支援此功能。 若要尋找可以釘選的應用程式，請在 [ **新增釘選的應用程式** ] 窗格中搜尋應用程式。 如需詳細資訊，請參閱 [使用應用程式設定原則中的常見問題](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)。

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>為什麼在關閉 [使用者釘選] 之後，我在設定原則面板中看到「使用者釘選」快顯？

![使用者介面內的設定原則區段的螢幕擷取畫面，其中包含確認使用者釘選為作用中的快顯。](media/appsetup4.png)

*此影像中包含的應用程式只是範例，可能無法使用。*

這是裝置在共用空間中的預期行為，有助於防止非意意的應用程式釘選。
