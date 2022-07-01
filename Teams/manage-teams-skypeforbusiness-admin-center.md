---
title: 管理 Teams 轉換到新的 Teams 系統管理中心
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何在從Microsoft 365 系統管理中心中的 Teams 轉換到新的 Teams 系統管理中心期間，管理 Teams 的全租使用者和使用者設定。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 39566c490a5de37adc699c39c049717525bd5821
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563951"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>什麼是新的 Microsoft Teams 系統管理中心  

新的系統管理中心體驗將為您提供管理 Teams 和 商務用 Skype 的整合體驗。 我們正在提供其他功能、端對端深入解析，以及在使用者層級管理 Teams 設定的功能。

![Microsoft Teams 系統管理中心的螢幕擷取畫面。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>設定移轉到新的 Microsoft Teams 系統管理中心

下表可識別已移轉的 Teams 體驗區段，並顯示目前設定與新系統管理入口網站中原則之間的關係。

|Microsoft 365 系統管理中心 中的 Teams 區段  | (租使用者層級設定名稱)   |Microsoft Teams 系統管理中心原則   |層級：租使用者或使用者   |
|---------|---------|---------|---------|
|一般     |在個人設定檔中顯示組織結構        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  租戶       |
|一般     |針對沒有 Teams 的收件者使用商務用 Skype         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|電子郵件整合     |允許使用者傳送電子郵件到頻道         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|電子郵件整合     |允許寄件者清單         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |租戶         |
|自訂雲端儲存空間     |箱         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|自訂雲端儲存空間     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|自訂雲端儲存空間     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|自訂雲端儲存空間     |Google 雲端硬碟        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|自訂雲端儲存空間     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租戶         |
|依使用者/授權類型的設定     |為所有使用者開啟或關閉 Microsoft Teams          |已取代<sup>1</sup>        |         |
|小組和頻道     |         |重新導向至 Azure Active Directory 群組管理 (目前體驗) 。              |使用者         |
|小組和頻道     |         |重新導向至 AAD 群組管理 (與目前體驗) 相同。             |使用者          |
|應用程式|預設啟用新的外部應用程式|全組織應用程式設定|租戶|
|應用程式|允許外部應用程式|全組織應用程式設定|租戶|
|應用程式|允許側載外部應用程式<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|使用者|
|應用程式|預設應用程式<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|應用程式|外部應用程式<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|通話和會議     |允許私人會議排程         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通話和會議     |允許臨機操作頻道會議         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通話和會議     |允許頻道會議排程         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通話和會議     |允許會議中的視訊         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通話和會議     |允許在會議中共用螢幕畫面         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通話和會議     |允許私人通話         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |使用者          |
|訊息傳送     |啟用 Giphy，讓使用者可以在交談中新增 GIF         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |內容分級         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |啟用使用者可編輯並新增至交談的 Meme         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |啟用貼圖，讓使用者可以編輯並新增至交談         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |允許擁有者刪除所有郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |允許使用者編輯自己的訊息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |允許使用者刪除自己的訊息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息傳送     |允許使用者私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |

<sup>1</sup> 已取代為來賓。 現在可以在 Microsoft Teams 系統管理中心管理啟用/停用來賓。 即將淘汰啟用/停用商務用 Teams 企業版、教育版學生版和教育系。 這應該由在Microsoft 365 系統管理中心中指派授權來管理。 請參閱 [管理使用者對 Microsoft Teams 的存取權](user-access.md)。
<br><br>
<sup>2</sup> 側載分割如下：

- 允許使用者側載可在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)中以使用者層級管理的應用程式。
- 允許租使用者中的使用者與可在整個組織應用程式設定的租使用者層級管理的自訂應用程式互動。

<sup>3</sup> 您可以在 TeamsAppPermissionPolicy 的使用者層級啟用和停用預設應用程式和外部應用程式。 此外，應用程式可以在全組織應用程式設定的租使用者層級封鎖，以覆寫任何使用者和租使用者層級的設定。

> [!NOTE]
> 您將繼續使用Microsoft 365 系統管理中心中的 [群組] 儀表板來設定 Teams 和頻道的相關設定。 應用程式的設定會保留在Microsoft 365 系統管理中心的 Teams 區域，稍後將會移轉。

## <a name="manage-settings-during-the-migration"></a>管理移轉期間的設定

您可以繼續修改Microsoft 365 系統管理中心和商務用 Skype系統管理中心的設定，直到您的租使用者完成某一節的移轉為止。

下表顯示您可以在移轉期間管理功能的位置。

|功能  |Microsoft Teams 系統管理中心                      |商務用 Skype系統管理中心 (舊版)   |Microsoft 365 系統管理中心  |
|---------|:---------:|:---------:|:---------:|
|Teams 訊息中心、會議和即時活動原則     |     X    |         |         |
|Teams 升級原則     |    X     |         |         |
|傳訊、會議和語音的來賓設定     |   X      |         |         |
|Teams 生命週期管理   |    X    |      |       |
|Teams 設定   |    X    |      |       |
|外部存取設定     |    X    |      |       |
|使用者管理    |         |         |    X     |
|音訊會議     |    X     |    X     |         |
|通話方案     |    X    |    X     |         |
|電話系統    |    X    |     X    |         |
|電話號碼管理     |    X    |   X      |         |
|雲端語音功能授權     |         |         |    X     |
|自動語音應答     |    X    |          |         |
|通話佇列     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>管理移轉後的設定

這些設定移轉完成後，我們會在 Microsoft 365 系統管理中心 和 商務用 Skype 系統管理中心停用這些設定，然後在新的 Microsoft Teams 系統管理中心進行管理。
