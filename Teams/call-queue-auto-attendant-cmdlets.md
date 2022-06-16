---
title: 自動語音應答和通話佇列的 PowerShell Cmdlet 參照
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System - seo-marvel-apr2020
description: 請參閱這篇文章以取得 PowerShell Cmdlet，以建立及管理Microsoft Teams中的自動語音應答和通話佇列。
ms.openlocfilehash: 33e553f90677eb0b1fa3e230215ff97d8d05066c
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124569"
---
# <a name="powershell-cmdlet-reference-for-call-queues-and-auto-attendants"></a>通話佇列和自動語音應答的 PowerShell Cmdlet 參照

下列 Cmdlet 參照適用于Microsoft Teams自動語音應答和通話佇列。

## <a name="auto-attendant-cmdlets"></a>自動語音應答 Cmdlet

下列 Cmdlet 可讓您管理自動語音應答：

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

您也需要下列 Cmdlet 來管理使用者、資源帳戶、Microsoft Teams 電話授權、電話號碼、音訊檔案，以及搭配自動語音應答使用的支援語言：

### <a name="usersteams"></a>使用者/Teams

- 使用者
  - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams：
  - [Get-Team](/powershell/module/teams/Get-Team)

### <a name="resource-accounts"></a>資源帳戶

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

### <a name="virtual-teams-phone-licenses"></a>虛擬Teams 電話授權

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

### <a name="phone-number-assignment"></a>電話編號指派

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

### <a name="audio-files"></a>音訊檔案

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

### <a name="support-languages-and-time-zones"></a>支援語言和時區

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

如需使用 PowerShell 建立自動語音應答的逐步指南，請參閱[使用 PowerShell Cmdlet 建立自動語音](create-a-phone-system-auto-attendant-via-cmdlets.md)應答

## <a name="call-queue-cmdlets"></a>通話佇列 Cmdlet

下列 Cmdlet 可讓您管理通話佇列：

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

下列 Cmdlet 也需要管理使用者、資源帳戶、Microsoft Teams 電話授權、電話號碼、音訊檔案，以及搭配通話佇列使用的支援語言：

### <a name="users-and-teams"></a>使用者和Teams

- 使用者
  - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams：
  - [Get-Team](/powershell/module/teams/Get-Team)
  - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

### <a name="resource-accounts"></a>資源帳戶

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

### <a name="virtual-teams-phone-standard-licenses"></a>虛擬Teams 電話標準方案授權

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

### <a name="assign-phone-numbers"></a>指派電話號碼

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

### <a name="audio-files"></a>音訊檔案

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

### <a name="support-language-lists"></a>支援語言清單

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

如需使用 PowerShell 建立通話佇列的逐步指南，請參閱 [使用 PowerShell Cmdlet 建立通話佇列](create-a-phone-system-call-queue-via-cmdlets.md)
