---
title: 將通話路由到未指派的號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何將通話路由至貴組織中未指派的號碼。
ms.openlocfilehash: 3f3d0b9e6962cce7abdb91efa8539dd559c38956
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272298"
---
# <a name="routing-calls-to-unassigned-numbers"></a>將通話路由到未指派的號碼

身為系統管理員，您可以將通話路由至貴組織中未指派的號碼。 例如，您可能會想要將通話路由至未指派的號碼，如下所示： 

- 將所有通話路由至指定的未指派號碼至自訂公告。

- 將所有通話路由至指定的未指派號碼到主切換板。

您可以將通話路由至未指派的號碼給使用者、與自動語音應答或通話佇列相關聯的資源帳戶，或傳送公告服務，向來電者播放自訂音訊檔案。

## <a name="configuration"></a>設定

若要將通話路由至未指派的號碼，請使用 Teams PowerShell 模組 2.5.1 或更新版本中提供的 New/Get/Set/Remove-CsTeamsUnasignedNumberMent Cmdlet。

您必須指定呼叫號碼或號碼範圍，以及這些號碼的相關路由。 例如，下列命令指定將所有撥打到號碼 +1 (555) 222-3333 的電話，都會路由至資源帳戶 aa@contoso.com：

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

下一個範例指定所有撥打到號碼範圍 +1 (555) 333-0000 到 +1 (555) 333-9999 的所有通話都會路由至公告服務，這會將音訊檔案 MainAnnouncement.wav 播放給來電者。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>注釋

- 如果路由到公告，音訊檔案會對來電者播放一次。

- 若要將通話路由至未指派的 Microsoft 通話方案訂閱者號碼，您的租使用者必須具備可用的 [通訊點數](what-are-communications-credits.md)。

- 若要將通話路由至未指派的 Microsoft 通話方案服務號碼，您的租使用者必須至少有一 **個Microsoft Teams 電話資源帳戶** 授權。

- 支援的自訂音訊檔格式為 WAV (未壓縮、單聲道或身歷聲) 深度為 8/16/32 位的線性 PCM、僅限 WMA (單聲道) ，以及 MP3。 音訊檔案內容不能超過 5 MB。

- Microsoft Teams 的輸入通話和 Microsoft Teams 的撥出電話，都會根據未指派的號碼範圍檢查來電號碼。

- 如果指定的模式/範圍包含指派給租使用者中的使用者或資源帳戶的電話號碼，這些電話號碼的呼叫將會路由至適當的目標，而不會路由至指定的未指派號碼處理。 不會對範圍中的數位進行其他檢查。 如果範圍包含有效的外部電話號碼，則會根據處理方式從 Microsoft Teams 撥出至該電話號碼。

## <a name="related-topics"></a>相關主題

- [Get-CsTeamsUnassignedNumber必要](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumber必要](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumber必要](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnasignedNumber必要](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumber必要](/powershell/module/teams/test-csteamsunassignednumbertreatment)
