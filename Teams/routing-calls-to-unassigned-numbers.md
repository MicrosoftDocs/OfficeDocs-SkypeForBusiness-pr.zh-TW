---
title: 將通話路由至未指定的號碼
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何將通話路由至貴組織中未指定的號碼。
ms.openlocfilehash: 4d9c40a0b4a01f7fae4a755603cb5cf7eb132f5c
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767366"
---
# <a name="routing-calls-to-unassigned-numbers"></a>將通話路由至未指定的號碼

做為系統管理員，您可以將通話路由至貴組織中未指定的號碼。 例如，您可能會想要將通話路由至未指定的號碼，如下所示： 

- 將所有通話路由至已未指定的號碼至自訂公告。

- 將所有通話路由至一個未指定的號碼到主切換台。

您可以將未指定號碼的通話路由給使用者、與自動語音機或通話佇列相關聯的資源帳戶，或將播放自訂音訊檔案的公告服務路由給來電者。

## <a name="configuration"></a>配置

若要將通話路由至未指定的號碼，請使用 Teams PowerShell 模組 2.5.1 或更新版本提供的 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment Cmdlet。

您需要指定號碼或號碼範圍，以及撥打這些號碼的相關路由。 例如，下列命令指定號碼 +1 (555) 222-3333 的所有通話都會路由至資源帳戶 aa@contoso.com：

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

下一個範例指定號碼範圍 +1 (555) 333-0000 到 +1 (555) 333-9999 的所有通話都會路由至公告服務，該服務會播放音訊檔案 MainAnnouncement.wav 給來電者。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>注釋

- 如果路由至公告，音訊檔案會播放一次給來電者。

- 若要將通話路由至未指定的 Microsoft 通話方案訂閱者號碼，您的租使用者必須擁有可用的 [通訊信用額度](what-are-communications-credits.md)。

- 若要將通話路由至未指定的 Microsoft 通話方案服務號碼，您的租使用者至少必須擁有一電話系統 – 虛擬使用者授權。

- 支援的自訂音訊檔案格式為 WAV (未壓縮、線性PCM，其深度為 8/16/32 位的單聲道或身歷聲) 、WMA (單聲道) 和 MP3。 音訊檔案內容不能超過 5 MB。

## <a name="related-topics"></a>相關主題

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnasignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)