---
title: 使用 PowerShell 在 Microsoft 團隊中設定即時事件原則
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 如何使用 PowerShell 來設定小組中的原則，以控制哪些人可以在組織中擁有即時事件，以及他們所建立的事件中提供的功能
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "37570165"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft 團隊中設定即時事件原則

您可以在團隊中使用下列 Windows PowerShell Cmdlet 來設定及指派即時事件的原則設定： 
- [CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [新-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [授與 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

以下是一些範例。

## <a name="allow-users-to-schedule-live-events"></a>允許使用者排程即時事件 

> [!NOTE]
> 這些範例適用于小組中產生的活動。 對於使用外部 app 或裝置所產生的事件，您必須執行其他步驟。 如需詳細資訊，請參閱[讓使用者排程由外部 app 或裝置產生的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。

**允許使用者排程即時事件**

如果使用者指派了全域原則，請執行並確認*AllowBroadcastScheduling*參數設定為*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然後，將使用者指派給全域原則，執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>使用者案例
**您希望貴組織中的所有使用者都能夠排程即時事件**

如果使用者指派了全域原則，請執行並確認*AllowBroadcastScheduling* * 設定為*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果使用者指派了全域原則以外的原則，請執行並確認 *-AllowBroadcastScheduling*已設定為*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**您想要在整個組織中停用即時事件排程**

停用即時事件排程，執行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
將貴組織中的所有使用者指派給全域原則，請執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您想要有大量的使用者能夠排程即時事件，並防止一組使用者進行排程**

執行並確認*AllowBroadcastScheduling*已設定為*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然後，將使用者或使用者指派給全域原則，執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

建立不允許排程即時事件的新原則，請執行：
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
停用即時事件排程，執行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然後將使用者指派給此原則，執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**您想要針對大量的使用者停用即時事件排程，並允許一組使用者進行排程**

停用即時事件排程，執行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然後將這些使用者指派給全域原則，執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
建立原則以允許即時事件排程，請執行：
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
啟用即時事件排程，執行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然後將使用者指派給此原則，執行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>設定誰可以加入即時事件
 
將全域原則設定為允許使用者建立每個人（包括匿名使用者）都可以出席的事件，請執行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>設定即時事件的錄製選項
> [!NOTE]
> 此設定僅適用于小組中產生的活動。

設定全域原則，停用錄製即時事件：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>在即時事件中設定即時標題和字幕
> [!NOTE]
> 此設定僅適用于小組中產生的活動。 

設定 [全域原則]，為活動出席者開啟即時輔助字幕和字幕（會議）：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相關主題
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)


