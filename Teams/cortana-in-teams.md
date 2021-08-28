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
description: 瞭解如何在語音Cortana使用語音Teams
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
ms.openlocfilehash: 45d2112dc7b81d72ccffcb8b4f04471b629d52a1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633397"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana語音協助Teams

> [!Note]
> Cortana iOS 和 Android 的 Microsoft Teams 行動應用程式中支援語音協助，Microsoft Teams適用于美國、英國、加拿大、印度和澳洲的使用者。 Microsoft Teams 會議室Windows僅適用于美國的使用者。 Cortana語音協助目前不適用於 GCC、GCC-High、DoD 和非美國 EDU 租使用者。 Cortana行動應用程式中Teams語音協助，現在適用于美國 EDU 客戶。 擴充至其他語言和地區，將在未來發行時進行。

> [!Note]
> Cortana預覽Microsoft Teams 會議室中提供語音協助。 在預覽版中，Cortana在連接了拉力麥克風的裝置上，僅支援美國的語言 EN-US。

Cortana Teams行動裝置 App、Windows Microsoft Teams 會議室 和 Microsoft Teams 顯示裝置上的語音協助，可讓 Microsoft 365 企業版 使用者使用口語自然語言簡化通訊、共同作業和會議相關工作。 使用者可以在 Teams 行動Cortana中選取麥克風按鈕，或在 Microsoft Teams 會議室中念出 &#8220;Cortana&#8221;，或是使用 Microsoft Teams 顯示器。 若要不用手快速與小組聯繫，以及進行中，使用者可以說出查詢，例如 &#8220;打電話給 Megan&#8221; 或 &#8220;將訊息傳送至下一個會議&#8221;。 使用者也可以說要加入&#8220;會議&#8221;，並使用語音協助來共用檔案、檢查他們的日曆等等。 這些語音協助體驗是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企業級服務提供，完全遵守 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 。

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

Cortana，Teams語音協助會使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。 此功能預設為租使用者啟用。

租使用者管理員可以控制租使用者中的哪些人Cortana TeamsCortanaPolicy Teams使用 (語音) 。 此策略設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此策略控制項中的 CortanaVoiceInvocationMode 欄位，判斷 Cortana 是否停用、是否僅以按鈕式啟用啟用，或是啟用適用于支援它的裝置 (，例如 Microsoft Teams 顯示) 。

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

此範例顯示使用名稱 &#8220;EmployeeCortanaPolicy&#8221;更新現有策略，Cortana使用按鈕Microsoft Teams啟用語音協助。 使用者可以在 Cortana 中選取 Cortana 麥克風按鈕來Teams。 喚醒字 (&#8220;嗨Cortana&#8221;或&#8220;Cortana&#8221;) 會停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新策略，並啟用Cortana按鈕和喚醒字詞的語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在初次發行時，Microsoft 365 企業版英文的使用者，以下是可用的函數：

- Teams行動應用程式不支援喚醒字詞啟用，但日後會支援啟用。  

- Microsoft Teams 會議室畫面Windows Microsoft Teams裝置上，將會支援喚醒字詞啟用。

## <a name="user-control"></a>使用者控制項

個別使用者可以嘗試Cortana裝置中的語音協助：

- 選取行動應用程式中的麥克風Teams按鈕。

- 選取麥克風按鈕，或在Cortana中Microsoft Teams 會議室。

- 在顯示裝置Cortana上Microsoft Teams「Microsoft Teams」。

您可以使用裝置中的Cortana，Teams裝置中的設定來控制裝置是否已啟用該裝置。

![顯示啟用移動視窗時移動視窗Cortana](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 會議室上Windows

如果在租使用者層級啟用 Cortana，可在裝置層級進行變更。 Cortana將預設為關閉。

若要啟用Cortana層級的 XML 屬性，必須在 SkypeSettings XML 檔案中新增這些 XML 屬性：

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

如果裝置層級已啟用Cortana，可在會議層級進行變更。

若要在Cortana啟用語音協助，請移動開關 **開啟或****關閉**。 會議結束後，Cortana回到裝置層級設定設定。
