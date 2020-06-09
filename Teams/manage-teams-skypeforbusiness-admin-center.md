---
title: 管理將團隊轉換成新的團隊系統管理中心
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 瞭解如何在從 Microsoft 365 系統管理中心的團隊轉換到新的團隊系統管理中心中，管理團隊的整個租使用者和使用者設定。
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
ms.openlocfilehash: f30db1425c61e8cb5f916345c0b751bc81c90a0f
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637422"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>新的 Microsoft 團隊系統管理中心是什麼？  

新的系統管理中心體驗將提供統一的體驗，讓您管理團隊和商務用 Skype。 我們正在提供其他功能、端對端的深入分析，以及管理使用者層級的團隊設定能力。 您可以存取系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

![Microsoft 團隊系統管理中心的螢幕擷取畫面。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>遷移到新 Microsoft 團隊系統管理中心的設定

下表列出已遷移之小組經驗的各個區段，並顯示目前設定與新系統管理入口網站中的原則之間的關係。

|Microsoft 365 系統管理中心的團隊區段  |設定名稱（租使用者層級）  |Microsoft 團隊系統管理中心原則   |階層：租使用者或 User   |
|---------|---------|---------|---------|
|一般     |在個人資料中顯示組織結構        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Tenant       |
|一般     |針對沒有團隊的收件者使用商務用 Skype         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|電子郵件整合     |允許使用者傳送電子郵件到頻道         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|電子郵件整合     |[允許寄件者] 清單         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Tenant         |
|自訂雲端儲存空間     |框         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|自訂雲端儲存空間     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|自訂雲端儲存空間     |Egnyte （即將推出）        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|自訂雲端儲存空間     |Google 磁片磁碟機        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|自訂雲端儲存空間     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|依使用者/授權類型設定     |針對所有使用者開啟或關閉 Microsoft 團隊          |已棄用<sup>1</sup>        |         |
|團隊和頻道     |         |重新導向至 Azure Active Directory 群組管理（與目前的體驗相同）。              |使用者         |
|團隊和頻道     |         |重定向至 AAD 群組管理（與目前的經驗相同）。             |使用者          |
|應用程式|預設啟用新的外部應用程式|整個組織內的應用程式設定|Tenant|
|應用程式|允許外部應用程式|整個組織內的應用程式設定|Tenant|
|應用程式|允許側載外部應用程式<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|使用者|
|應用程式|預設 app<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|應用程式|外部應用程式<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|通話與會議     |允許針對私人會議進行排程         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許點對點通道頻道         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許針對頻道會議進行排程         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許會議中的影片         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許在會議中共用螢幕         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |使用者          |
|通話與會議     |允許私人通話         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |使用者          |
|傳訊     |啟用 Giphy，讓使用者可以在交談中新增 Gif         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |內容分級         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |啟用使用者可以編輯及新增至交談的 meme         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |啟用使用者可以編輯及新增至交談的不乾膠標籤         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |允許擁有者刪除所有郵件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |允許使用者編輯自己的郵件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |允許使用者刪除自己的郵件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |
|傳訊     |允許使用者私下聊天         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |使用者         |

<sup>1</sup>已過時的來賓。 您現在可以在 Microsoft 團隊系統管理中心管理啟用/停用來賓的功能。 啟用/停用商務用團隊企業、Edu 學生及 Edu 教職員將會在不久後過時。 您應該在 Microsoft 365 系統管理中心指派授權來加以管理。 請參閱[管理使用者對 Microsoft 團隊的存取權](user-access.md)。
<br><br>
<sup>2</sup>側載分為以下分割：

- 允許使用者側載可在[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)中的使用者層級進行管理的 app。
- 允許租使用者中的使用者與可在整個組織內應用程式設定中的租使用者層級管理的自訂 app 互動。
 
<sup>3</sup>在 TeamsAppPermissionPolicy 的使用者層級，可以啟用和停用預設 app 和外部 app。 此外，您也可以在組織範圍 app 設定中的租使用者層級封鎖應用程式，這會覆寫任何使用者和租使用者層級設定。 

> [!NOTE]
> 您將會繼續使用 Microsoft 365 系統管理中心的 [群組] 儀表板，以取得與團隊和頻道相關的配置。 應用程式的設定會保留在 Microsoft 365 管理中心的 [小組] 區域中，並會在稍後進行遷移。 

## <a name="manage-settings-during-the-migration"></a>在遷移期間管理設定

您可以繼續在 Microsoft 365 系統管理中心和商務用 Skype 系統管理中心中修改設定，直到針對您的租使用者完成某個區段的遷移。 

下表顯示您可以在遷移期間管理功能的位置。

|功能  |Microsoft 團隊系統管理中心                      |商務用 Skype 系統管理中心（舊版）  |Microsoft 365 系統管理中心  |
|---------|:---------:|:---------:|:---------:|
|團隊訊息、會議及即時事件原則     |     X    |         |         |
|團隊升級原則     |    X     |         |         |
|[訊息]、[會議] 和 [語音] 的來賓設定     |   X      |         |         |
|小組生命週期管理   |    X    |      |       |
|團隊設定   |    X    |      |       |
|外部存取設定     |    X    |      |       |
|使用者管理    |         |         |    X     |    
|音訊會議     |    X     |    X     |         |
|通話方案     |    X    |    X     |         |
|電話系統    |    X    |     X    |         |
|電話號碼管理     |    X    |   X      |         |
|雲端語音功能的授權     |         |         |    X     |
|自動語音應答     |    X    |          |         |
|通話佇列     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>在遷移之後管理設定

完成這些設定的遷移之後，我們會在 Microsoft 365 系統管理中心和商務用 Skype 系統管理中心將其停用，然後在新的 Microsoft 團隊系統管理中心管理它們。
