---
title: 管理Teams新系統管理中心的Teams轉換
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 瞭解如何在從 Teams 中的 Teams 轉換至新的系統管理中心Microsoft 365 系統管理中心管理整個租使用者Teams使用者設定。
localization_priority: Normal
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
ms.openlocfilehash: 036d4ddd2768a531d32eed03d5bc4b35e09a0a229ad98a0d6fd0d17adcf09d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281546"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>系統管理中心Microsoft Teams是什麼  

新的系統管理中心體驗會為您提供統一體驗，以管理Teams商務用 Skype。 我們正在提供其他功能、端對端深入見解，以及管理使用者層級Teams設定的能力。

![系統管理中心Microsoft Teams螢幕擷取畫面。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>設定已移Microsoft Teams系統管理中心

下表指出已移Teams體驗的區段，並顯示新系統管理入口網站中目前設定與策略之間的關係。

|在 Teams 中Microsoft 365 系統管理中心  |設定租使用者 (等級)   |Microsoft Teams系統管理中心政策   |層級：租使用者或使用者   |
|---------|---------|---------|---------|
|一般     |在個人設定檔中顯示組織結構        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  租戶       |
|一般     |針對商務用 Skype的收件者使用Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|電子郵件整合     |允許使用者將電子郵件傳送至頻道         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|電子郵件整合     |允許寄件者清單         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |租戶         |
|自訂雲端儲存空間     |箱         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|自訂雲端儲存空間     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|自訂雲端儲存空間     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|自訂雲端儲存空間     |Google 雲端硬碟        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|自訂雲端儲存空間     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租戶         |
|設定使用者/授權類型來選擇     |為Microsoft Teams開啟或關閉          |已棄用<sup>1</sup>        |         |
|小組和頻道     |         |重新導向至Azure Active Directory管理 (目前體驗) 。              |使用者         |
|小組和頻道     |         |重新導向至 AAD 群組管理 (目前使用體驗) 。             |使用者          |
|應用程式|預設啟用新的外部應用程式|全組織應用程式設定|租戶|
|應用程式|允許外部應用程式|全組織應用程式設定|租戶|
|應用程式|允許側載外部應用程式<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|使用者|
|應用程式|預設應用程式<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|應用程式|外部應用程式<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|通話與會議     |允許排程私人會議         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許臨時通道開會         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許排程頻道會議         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許會議中的影片         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |在會議中允許螢幕畫面共用         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許私人通話         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |使用者          |
|訊息傳送     |啟用 Giphy，讓使用者可以在交談中新增 GIF         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |內容分級         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |啟用使用者可以編輯和新增到交談的 Meme         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |啟用使用者可以編輯並新增到交談的貼圖         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |允許擁有者刪除所有郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |允許使用者編輯自己的郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |允許使用者刪除自己的郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|訊息傳送     |允許使用者私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |

<sup>1</sup> 來賓已棄用。 現在可以在系統管理中心管理啟用/停用來賓Microsoft Teams管理。 啟用/停用商務Teams、Enterprise、Edu Student 和 Edu 教職員的商務用軟體即將被停用。 這應該會以指派授權的方式Microsoft 365 系統管理中心。 請參閱[管理使用者對 Microsoft Teams](user-access.md)的存取權。
<br><br>
<sup>2</sup> 側載分割方式如下：

- 允許使用者在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)中側載可在使用者層級管理的應用程式。
- 允許租使用者中的使用者與自訂應用程式互動，自訂應用程式可在全組織 App 設定中的租使用者層級管理。

<sup>3</sup> 在 TeamsAppPermissionPolicy 的使用者層級，可以啟用和停用預設應用程式和外部應用程式。 此外，您可以在整個組織的應用程式設定中，在租使用者層級封鎖應用程式，以取代任何使用者和租使用者層級設定。

> [!NOTE]
> 您會繼續使用群組儀表板Microsoft 365 系統管理中心與頻道和頻道Teams相關。 設定應用程式將會保留在 Teams的 Microsoft 365 系統管理中心區域，並稍後移移。

## <a name="manage-settings-during-the-migration"></a>在移移期間管理設定

您可以繼續修改系統管理中心Microsoft 365 系統管理中心系統管理商務用 Skype中的設定，直到您的租使用者完成節的移移。

下表顯示您可以在移移期間管理功能的地方。

|功能  |Microsoft Teams系統管理中心                      |商務用 Skype系統管理中心 (舊版)   |Microsoft 365 系統管理中心  |
|---------|:---------:|:---------:|:---------:|
|Teams訊息、會議和即時活動政策     |     X    |         |         |
|Teams升級政策     |    X     |         |         |
|訊息、會議和語音的來賓設定     |   X      |         |         |
|Teams生命週期管理   |    X    |      |       |
|Teams 設定   |    X    |      |       |
|外部存取設定     |    X    |      |       |
|使用者管理    |         |         |    X     |
|音訊會議     |    X     |    X     |         |
|通話方案     |    X    |    X     |         |
|電話系統    |    X    |     X    |         |
|電話號碼管理     |    X    |   X      |         |
|雲端語音功能的授權     |         |         |    X     |
|自動語音應答     |    X    |          |         |
|通話佇列     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>移移之後管理設定

這些設定移移完成後，我們將在 Microsoft 365 系統管理中心 和 商務用 Skype 系統管理中心停用這些設定，然後可以在新的 Microsoft Teams 系統管理中心管理這些設定。