---
title: 使用 PowerShell 設定即時活動政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 如何使用 PowerShell 在 Teams中設定策略的範例，以控制哪些人可以舉辦貴組織的即時活動，以及活動提供的功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b55589a3cabf1b696c1034ce4e20cd7a56af3444f7fa51e0f81f44430ead6bb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328928"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams

您可以使用下列 Cmdlet Windows PowerShell，為即時活動設定及指派Teams： 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

以下是一些範例。

> [!NOTE]
> 執行這些 Cmdlet 之前，您必須連線至 商務用 Skype PowerShell。 詳細資訊，請參閱使用[powerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)或 商務用 Skype 管理 Microsoft 365 Office 365 Online 。

## <a name="allow-users-to-schedule-live-events"></a>允許使用者排程即時活動 

> [!NOTE]
> 這些範例適用于在 Teams 中Teams。 對於使用外部 App 或裝置產生的事件，您必須執行其他步驟。 若要取得詳細資訊，請參閱讓使用者排程使用外部 App 或裝置產生的 [事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。

**允許使用者排程即時活動**

如果使用者已指派全域原則，請執行並驗證 *AllowBroadcast 排程* 參數設為 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然後將使用者指派給全域原則，執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>使用者案例
**您希望貴組織中所有使用者都能排程即時活動**

如果使用者已指派全域原則，請執行並驗證 *AllowBroadcastScheduling* *已設為 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果使用者被指派全域原則外的其他策略，請執行並驗證 *-AllowBroadcast 排程* 設定為 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**您希望整個組織停用即時活動排程**

停用即時活動排程，執行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
將貴組織中所有使用者指派給全域原則，請執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您希望大量使用者能夠排程即時事件，並防止一組使用者排程活動**

執行並驗證 *AllowBroadcast 排程* 設定為 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然後指派使用者或使用者至全域原則，執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

建立不允許排程即時事件的新策略，請執行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
停用即時活動排程，執行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然後指派使用者至此策略，執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**您想要針對大量使用者停用即時事件排程，並允許一組使用者排程**

停用即時活動排程，執行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然後將這些使用者指派給全域原則，執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
建立允許即時事件排程的策略，執行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
啟用即時活動排程，執行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然後指派使用者至此策略，執行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>設定誰可以加入即時活動
 
設定全域原則以允許使用者建立每個人都可以參加的活動，包括匿名使用者，執行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>設定即時事件的錄製選項
> [!NOTE]
> 此設定僅適用于在 Teams 中Teams。

設定全域原則以停用即時活動的錄製：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>在即時活動中設定即時字幕和字幕
> [!NOTE]
> 此設定僅適用于在 Teams 中Teams。 

設定全域原則，為活動出席者開啟即時 (字幕) 字幕：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相關主題
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
- [Teams PowerShell 概觀](../teams-powershell-overview.md)