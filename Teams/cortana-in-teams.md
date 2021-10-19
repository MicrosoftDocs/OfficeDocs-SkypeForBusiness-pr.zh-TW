---
title: Cortana語音協助Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何使用語音Cortana語音協助Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a9dba32e74bcc1538f75e35f5c70172fe72ec1b
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462477"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana語音協助Teams

> [!Note]
> Cortana iOS 和 Android Microsoft Teams行動應用程式中支援語音協助，Microsoft Teams美國、英國、加拿大、印度和澳洲的使用者顯示語音協助。 Microsoft Teams 會議室上的Windows僅適用于設定為 en-us 的裝置。 Cortana目前不適用於 GCC、GCC高、DoD 和非美國 EDU 租使用者。 Cortana行動應用程式中Teams語音協助，現在適用于美國 EDU 客戶。 擴充至其他語言和地區，將在未來發行時進行。


Cortana Teams行動裝置 App、Microsoft Teams 會議室 Windows 和 Microsoft Teams 顯示裝置上提供語音協助，Microsoft 365 企業版 使用者可以使用口語自然語言。 使用者可以 Cortana選取 Teams 行動應用程式右上角的麥克風按鈕，或在 Microsoft Teams 會議室中念出 &#8220;Cortana&#8221;，或是使用 Microsoft Teams 顯示器來與 Microsoft Teams 說話。 若要不用手快速與小組聯繫，以及進行中，使用者可以說出查詢，例如 &#8220;打電話給 Megan&#8221; 或 &#8220;將訊息傳送至下一個會議&#8221;。 使用者也可以加入會議，&#8220;加入我的下一&#8221;，並使用語音協助來共用檔案、檢查他們的日曆等等。 這些語音協助體驗是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企業級服務提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 中反映。

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

Cortana中的 Teams語音協助是使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。 此功能預設為租使用者啟用。

租使用者管理員可以控制租使用者中的哪些人Cortana TeamsCortanaPolicy Teams使用 (語音) 。 此策略設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此策略控制項內的 CortanaVoiceInvocationMode 欄位，判斷 Cortana 是否停用、是否僅以按鈕啟動啟用，或是否同時啟用喚醒字詞 (也適用于支援此功能的裝置 ，例如 Microsoft Teams 顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此 (系統管理中心目前無法Microsoft Teams此) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會使用名稱 &#8220;EmployeeCortanaPolicy&#8221;在 Cortana中Microsoft Teams語音協助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此範例顯示使用名稱 &#8220;EmployeeCortanaPolicy&#8221;更新現有策略，Cortana僅使用按鈕Microsoft Teams啟用 Microsoft Teams 語音協助。 使用者可以在 Cortana 中選取 Cortana 麥克風按鈕來Teams。 喚醒字 (&#8220;嘿，Cortana&#8221;或&#8220;Cortana&#8221;) 會停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新策略，並啟用Cortana按鈕和喚醒字詞的語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在初次發行時，Microsoft 365 企業版英文的使用者，以下是可用的函數：

- Teams行動應用程式不支援喚醒字詞啟用，但日後會支援。  

- Microsoft Teams 會議室畫面Windows Microsoft Teams裝置上，將會支援喚醒字詞啟用。

## <a name="user-control"></a>使用者控制項

個別使用者可以嘗試Cortana裝置中的語音協助：

- 選取行動應用程式中的麥克風Teams按鈕。

- 選取麥克風按鈕，或在Cortana中Microsoft Teams 會議室。

- 在顯示Cortana上Microsoft Teams「Microsoft Teams」。

您可以使用裝置中的Cortana，Teams裝置中的設定來控制裝置是否已啟用此功能。

![顯示啟用移動視窗時移動視窗Cortana。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 會議室上Windows

只有在租使用者層級啟用Cortana才能在裝置層級進行變更。 

在裝置層級，您可以設定Cortana兩種不同的使用方式。 您可以同時啟用其中一個選項，或同時啟用兩個選項： 
- 點一下麥克風，Cortana _按以說話_
- 說「嗨，Cortana」，這稱為 _「Cortana語音啟用」_

Cortana _如果_ 裝置已設定為使用地區設定，則預設會啟用推入通話功能。 [瞭解更多資訊。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language)  Cortana圖示會 _取代更多__..._ Teams 功能表。 若要停用Cortana _按以交談，請使用_ PowerShell。[深入瞭解。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

若要啟用 _Cortana啟用，_ 必須符合以下條件：
- 已Cortana裝置必須連接到您的會議室Teams裝置。 您可以在本文結尾找到認證裝置清單。
- Teams會議室必須設定為使用地區設定。 日後將會提供更多語言。
- 必須進行下列其中一個組組變更：
  - 開啟系統管理中心中的Teams[深入瞭解。](/microsoftteams/rooms/rooms-manage)
  - 新增下列 XML 屬性至 SkypeSettings XML 檔案：
```xml
<SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
</SkypeSettings> 
```
在會議層級，只有在裝置層級啟用語音Cortana才能進行變更。   若要 _在Cortana啟用_ 語音啟用功能，請移動開關 **開啟** 或 **關閉** 以停用。 會議結束後，Cortana回到裝置層級設定集。


如果裝置層級已啟用 Cortana，可在會議層級進行變更。

若要在Cortana啟用語音啟用功能，請移動開關 **開啟或****關閉**。 會議結束後，Cortana回到裝置層級設定集。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana認證裝置Teams 會議室
Cortana _Lenovo_ Hub 500，或如果您將任何裝置連接到您的會議室，就可以啟用語音啟用：
- Jabra Panacast 50 
- 召集式麥克風
- Bose Video Bar VB1 __
