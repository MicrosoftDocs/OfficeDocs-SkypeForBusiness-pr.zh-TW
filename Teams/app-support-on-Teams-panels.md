---
title: Microsoft Teams 應用程式/業務線 (LOB) 應用程式在 Teams 面板上的支援
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 說明 Teams app/LOB 應用程式的支援。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591217"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams 應用程式/業務線 (LOB) 應用程式在 Teams 面板上的支援

Teams 的欄目會新增對 Teams app/業務線 (LOB) 應用程式的支援。 這可讓企業在面板上新增額外的經驗，以符合組織的需求。 此版本支援靜態 web 內容。

> [!IMPORTANT]
> 只有在更新 Teams 面板裝置 (s) 之後，才能使用此功能。 您需要 Teams 應用程式版本 1449/1.0.97.2021070601 或更新版本，才能在 Teams 面板中使用應用程式支援。

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>設定及管理 Teams 系統管理中心的 Teams 面板應用程式 

Microsoft Teams 應用程式會將重要資訊、一般工具和受信任的程式，帶入人員收集、學習和使用的位置。 Teams 應用程式[透過整合功能](/platform/concepts/capabilities-overview)運作。 現在，以 IT 管理員的身分，您可以選擇要在組織的 Teams 面板裝置中包含哪些應用程式，以及透過 Teams 系統管理中心自訂許可權。

您現在可以使用 Teams 面板上的 Teams 應用程式，並根據組織的需求自訂使用者體驗。 您可以決定使用者可以存取和使用的 web 應用程式，並決定應用程式視圖的優先順序。 有些選項（如 bot 和郵件功能）目前不支援。 深入瞭解 Teams 的應用程式，以及如何在 Microsoft Teams 中管理裝置。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>管理 Teams 系統管理中心中 Teams 面板上的應用程式

**附注**：您必須是全域系統管理員或 Teams 服務管理員，才可存取 Teams 系統管理中心。

使用者可以在 Teams 面板上查看但不安裝應用程式。 做為系統管理員，您可以透過 Teams 系統管理中心，查看及管理組織的所有 Teams 應用程式。 深入瞭解如何在 Microsoft Teams 系統管理中心中透過 [**管理應用程式**] 頁面來管理您的應用程式。 Teams 系統管理中心內的 [**管理應用程式**] 頁面也是可上傳 [自訂應用程式](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)的所在位置。

在設定應用程式之後，您可以使用 [應用程式許可權原則](/teams-app-permission-policies) 和 [應用程式安裝原則](/teams-app-setup-policies) ，設定組織中特定聊天室帳戶的應用程式經驗。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>在應用程式安裝原則的 Teams 面板上固定應用程式

因為 Teams 提供的功能可顯示廣泛的應用程式，所以系統管理員可以決定組織最重要的應用程式，並只 pin Teams 面板 **主** 畫面以供快速存取。 如果有超過五個已固定的應用程式或任何已固定的應用程式，則會出現在 [ **更多** ] 畫面下。 Microsoft 建議您專門為 Teams 面板建立自訂應用程式安裝原則。

![應用程式安裝原則頁面的使用者介面螢幕擷取畫面。](media/appsetup1.png) 

若要管理顯示在 Teams 面板上的固定應用程式，請登入組織的 Teams 系統管理中心，並流覽至 **Teams 應用** \> **程式安裝原則** \> **選取或建立新的原則** \> **固定應用程式**。

![使用者介面內已附加的應用程式區段的螢幕擷取畫面。](media/appsetup2.png) 

Microsoft 建議您關閉 **Upload 自訂應用程式**，並 **允許使用者固定** Teams Teams 面板上的最佳應用程式體驗。

如需有關釘選應用程式的詳細資訊，請參閱 [管理 app 安裝原則](/teams-app-setup-policies)。

## <a name="manage-apps-display-order-in-teams-panels"></a>在 Teams 面板中管理應用程式顯示順序 

![使用者介面中應用程式區段的螢幕擷取畫面。](media/appsetup3.png) 

若要管理應用程式在 Teams 面板上的顯示順序，請登入組織的 Teams 系統管理中心，並流覽至 **Teams 應用** \> **程式安裝原則** \> **選取原則** \> **固定的應用程式：** **向上移動/向下**。

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>將安裝原則指派給會議室資源帳戶

在建立安裝原則之後，系統管理員必須將此原則指派給將會登入 Teams 面板的聊天室資源帳戶。 如需詳細資訊，請參閱 [指派原則給使用者和群組](/assign-policies-users-and-groups)。

## <a name="faq"></a>常見問題集

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Teams 面板取得新的或更新的應用程式安裝原則需要多久的時間？

在 Teams 系統管理中心中編輯或指派新原則之後，變更才會生效長達24小時。 系統管理員可以嘗試從面板中登出/登入，點擊 **設定** 圖示，然後回到 **主** 畫面以嘗試重新整理原則。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>在 "More" 畫面上的應用程式順序為何？

在 [ **其他** 應用程式] 頁面上，會先出現固定的應用程式。 然後，其他所有已安裝的應用程式都會以字母順序顯示。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>為何不會在 Teams 面板上顯示 bot 應用程式？

目前只支援靜態索引標籤網頁內容。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>為什麼原生 Teams 的應用程式（例如行事曆和工作）未出現在 Teams 面板上？

Teams 面板上不會顯示原生 Teams 應用程式，例如行事曆和工作。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>在 Teams 系統管理中心的 [安裝原則] 區段下，已安裝應用程式與固定應用程式之間的差異為何？

在 Teams 面板中，Microsoft 建議使用已附加的應用程式，因此系統管理員可以選取所需的應用程式，然後重新排列其順序。

**附注：** 部分應用程式不支援應用程式釘住。 請與應用程式開發人員聯繫，以啟用應用程式釘選功能。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>為什麼其他應用程式會出現在 "More" 畫面上，即使這些應用程式不是安裝或已固定應用程式的 Teams app setup policy 區段中的部分？

如果先前已透過其他應用程式原則或在 Teams 面板上使用之會議室資源帳戶的 Teams 桌面/web 用戶端中安裝應用程式，則系統管理員可能需要在 Teams 中登入會議室資源帳戶，並以滑鼠右鍵按一下 app，然後選取 [**卸載**] 以手動卸載應用程式。

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為何在「新增已附加的應用程式」窗格中找不到應用程式？

並非所有應用程式都可以透過應用程式安裝原則釘住 Teams。 某些應用程式可能不支援此功能。 若要尋找可釘住的應用程式，請在 [ **新增附加的應用** 程式] 窗格中搜尋該應用程式。 如需詳細資訊，請參閱使用 [app 安裝原則的常見問題解答](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)。

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>為什麼我關閉「允許使用者釘住」時，才會在安裝原則面板中看到「允許使用者釘住」快顯視窗？

![使用者介面內安裝原則區段的螢幕擷取畫面，以確認使用者釘住作用中狀態。](media/appsetup4.png) 

共用空間中的裝置會出現此行為，並協助防止無意中的應用程式釘住。
