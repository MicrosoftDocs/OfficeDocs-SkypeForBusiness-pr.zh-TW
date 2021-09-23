---
title: 管理Teams新系统管理中心Teams转换
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在从 Teams 中的 Teams 转换至新的系统管理中心Microsoft 365 系統管理中心管理整个租用户Teams用户设定。
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
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491733"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>系统管理中心Microsoft Teams是什么  

新的系统管理中心体验会为您提供统一体验，以管理Teams商務用 Skype。 我们正在提供其他功能、端对端深入见解，以及管理用户层级Teams设定的能力。

![系统管理中心Microsoft Teams屏幕快照。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>設定移至新的系统管理Microsoft Teams中心

下表识别已移Teams体验的区段，并显示新系统管理入口网站中目前设定与策略之间的关系。

|在 Teams 中Microsoft 365 系統管理中心  |将名称 (租用户层级)   |Microsoft Teams系统管理中心政策   |层级：租用户或用户   |
|---------|---------|---------|---------|
|一般     |在个人配置文件中显示组织结构        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  租户       |
|一般     |针对商務用 Skype的收件者使用Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|電子郵件整合     |允许用户将电子邮件传送至频道         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|電子郵件整合     |允许发件人列表         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |租户         |
|自定义云端储存空间     |箱         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云端储存空间     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云端储存空间     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云端储存空间     |Google 雲端硬碟        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云端储存空间     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|設定用户/授权类型来显示     |为Microsoft Teams开启或关闭          |已弃用<sup>1</sup>        |         |
|小組和頻道     |         |重新导向至Azure Active Directory管理 (目前体验) 。              |使用者         |
|小組和頻道     |         |重新导向至 AAD 群组管理 (目前使用体验) 。             |使用者          |
|應用程式|默认启用新的外部应用程序|全组织应用程序设定|租户|
|應用程式|允许外部应用程序|全组织应用程序设定|租户|
|應用程式|允许侧载外部应用程序<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|使用者|
|應用程式|默认应用程序<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|應用程式|外部应用程序<sup>3</sup>|TeamsAppPermissionPolicy|使用者|
|通话与会议     |允许排程私人会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通话与会议     |允许临时信道会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通话与会议     |允许频道会议的排程         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通话与会议     |在会议中允许影片         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通话与会议     |在会议中允许屏幕画面共享         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |使用者          |
|通话与会议     |允许私人通话         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |使用者          |
|訊息中心     |啟用 Giphy，讓使用者可以在交談中新增 GIF         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |內容分級         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |啟用使用者可以編輯和新增到交談的 Meme         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |啟用使用者可以編輯並新增到交談的貼圖         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |允許擁有者刪除所有郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |允許使用者編輯自己的郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |允許使用者刪除自己的郵件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |
|訊息中心     |允許使用者私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |使用者         |

<sup>1</sup> 來賓已棄用。 現在可以在系統管理中心管理啟用/停用來賓Microsoft Teams管理。 啟用/停用商務Teams、Enterprise、Edu Student 和 Edu 教職員的商務用軟體即將被停用。 這應該會以指派授權的方式Microsoft 365 系統管理中心。 請參閱[管理使用者對 Microsoft Teams](user-access.md)的存取權。
<br><br>
<sup>2</sup> Sideloading 分割方式如下：

- 允許使用者在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)中側載可在使用者層級管理的應用程式。
- 允許租使用者中的使用者與自訂應用程式互動，這些自訂應用程式可在全組織 App 設定中的租使用者層級管理。

<sup>3</sup> 在 TeamsAppPermissionPolicy 的使用者層級，可以啟用和停用預設應用程式和外部應用程式。 此外，您可以在整個組織的應用程式設定中，在租使用者層級封鎖應用程式，以取代任何使用者和租使用者層級設定。

> [!NOTE]
> 您會繼續使用群組儀表板Microsoft 365 系統管理中心組和Teams相關的組。 設定應用程式將會保留在 Teams 的 Microsoft 365 系統管理中心 區域，並稍後移移。

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
