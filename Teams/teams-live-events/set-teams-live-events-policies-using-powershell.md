---
title: 使用 PowerShell 來設定即時活動原則
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 如何使用 PowerShell 在 Teams 中設定原則的範例，以控制誰能在貴組織中舉辦即時活動，以及事件中可用的功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767573"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中設定即時活動原則

您可以使用下列Windows PowerShell Cmdlet 來設定和指派 Teams 即時活動的原則設定：

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

以下是一些範例。

> [!NOTE]
> 您必須先連線至 商務用 Skype Online PowerShell，才能執行這些 Cmdlet。 如需詳細資訊，請參閱[使用 Microsoft 365 或 Office 365 PowerShell 管理 商務用 Skype Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

## <a name="allow-users-to-schedule-live-events"></a>允許使用者排程即時活動

> [!NOTE]
> 這些範例適用于 Teams 中產生的活動。

### <a name="allow-a-user-to-schedule-live-events"></a>允許使用者排程即時活動

如果使用者獲派全域原則，請執行並確認 *AllowBroadcastScheduling* 參數設定為 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

然後將使用者指派給全域原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>使用者案例

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>您希望組織中的所有使用者都能排程即時活動

如果使用者獲派全域原則，請執行並確認 *AllowBroadcastScheduling* 設為 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

如果指派了全域原則以外的使用者原則，請執行並確認 *-AllowBroadcastScheduling* 設定為 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>您希望停用整個組織的即時活動排程

停用即時活動排程，執行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

將貴組織中的所有使用者指派給全域原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>您希望有大量使用者能夠排程即時活動，並防止一組使用者排程活動

執行並確認 *AllowBroadcastScheduling* 設為 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

然後將使用者指派給全域原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

建立不允許排程即時活動的新原則，執行：

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```

停用即時活動排程，執行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```

然後指派使用者至此原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>您想要停用大量使用者的即時活動排程，並允許一組使用者排程他們

停用即時活動排程，執行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

然後將這些使用者指派給全域原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

建立原則以允許即時活動排程、執行：

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```

啟用即時活動排程、執行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```

然後指派使用者至此原則，執行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

## <a name="set-who-can-join-live-events"></a>設定誰可以加入即時活動

設定全域原則，允許使用者建立事件，讓包括匿名使用者在內的所有人參加、執行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>設定即時活動的錄製選項

> [!NOTE]
> 此設定僅適用于 Teams 中產生的活動。

設定全域原則以停用即時活動的錄製：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>在即時活動中設定即時輔助字幕和字幕

> [!NOTE]
> 此設定僅適用于 Teams 中產生的活動。

設定全域原則，為活動出席者開啟即時輔助字幕和字幕 (轉譯) ：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相關主題

- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
- [Teams PowerShell 概觀](../teams-powershell-overview.md)
