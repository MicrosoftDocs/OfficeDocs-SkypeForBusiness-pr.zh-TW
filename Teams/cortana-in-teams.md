---
title: Microsoft Teams 中的 Cortana 語音協助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何在 Teams 中使用 Cortana 語音協助
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886732"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams 中的 Cortana 語音協助

> [!Note]
> 適用于 iOS 和 Android 的 Microsoft Teams 行動應用程式支援 Cortana 語音協助，而 Microsoft Teams 會針對美國、英國、加拿大、印度和澳洲的使用者顯示。  Windows 上的 Microsoft Teams 會議室僅支援美國使用者。 Cortana 語音協助目前不適用於 GCC、GCC-High、DoD、EDU 租使用者。 擴充至其他語言和地區，將在未來發行時進行。

> [!Note]
> Microsoft Teams 會議室中的 Cortana 語音協助會發佈在預覽下。 在預覽版中，只有美國支援 Cortana，在連接了拉力麥克風的裝置上支援語言 EN-US。

Teams 行動裝置 App、Windows 版 Microsoft Teams 會議室和 Microsoft Teams 顯示裝置上的 Cortana 語音協助可讓 Microsoft 365 企業版使用者使用自然口語簡化通訊、共同作業和會議相關工作。 使用者可以選取 Teams 行動應用程式右上角的麥克風按鈕，或在 Microsoft Teams 會議室或使用 Microsoft Teams 顯示器時，說出 &#8220;Cortana&#8221; 來與 Cortana 說話。 若要不用手快速與小組聯繫，以及進行中，使用者可以說出查詢，例如 &#8220;打電話給 Megan&#8221; 或 &#8220;將訊息傳送給下一個會議&#8221;。 使用者也可以加入會議，&#8220;加入我的下一&#8221;，並使用語音協助來共用檔案、檢查他們的日曆等等。 這些語音協助體驗是使用 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 企業級服務提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款 [ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 所反映。

影像顯示使用行動裝置上的 Cortana 傳送聊天。

![顯示 Cortana 聊天會話的一系列行動畫面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

Teams 中的 Cortana 語音協助是使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。 此功能預設為租使用者啟用。

租使用者管理員可以控制租使用者中的哪些人可以使用 Teams 中的 Cortana 語音協助， (TeamsCortanaPolicy) 。 此策略可以設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此策略控制項中的 CortanaVoiceInvocationMode 欄位，判斷 Cortana 是否停用、僅以按鈕啟動啟用，或啟用喚醒字詞 (也適用于支援此功能的裝置 ，例如 Microsoft Teams 顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此 (Microsoft Teams 系統管理中心目前) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會使用名稱建立一個新&#8220;EmployeeCortanaPolicy&#8221;停用 Microsoft Teams 中的 Cortana 語音協助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此範例顯示使用名稱更新現有&#8220;EmployeeCortanaPolicy&#8221;，並啟用 Microsoft Teams 中的 Cortana 語音協助，且僅提供按鈕的啟用。 使用者可以在 Teams 中選取 Cortana 麥克風按鈕來啟動 Cortana。 將啟用 (&#8220;Cortana&#8221;或&#8220;Cortana&#8221;) 將停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新策略，以及啟用 Cortana 語音協助，同時使用按鈕和喚醒字詞。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

目前，美國 Microsoft 365 企業版使用者英文版初次發行時，可以使用下列函數：

- Teams 行動應用程式不支援喚醒字詞啟用，但日後會支援啟用。  

- Windows 和 Microsoft Teams 顯示裝置上的 Microsoft Teams 會議室將支援喚醒字啟用。

## <a name="user-control"></a>使用者控制項

個別使用者可以在不同的裝置上試用 Cortana 語音協助：

- 選取 Teams 行動應用程式中的麥克風按鈕。

- 在 Microsoft Teams 會議室中選取麥克風按鈕或說出「Cortana」。

- 在 Microsoft Teams 顯示裝置上說「Cortana」。

您可以使用裝置中的設定來控制 Teams 中的 Cortana 是否已啟用您的裝置。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams 行動應用程式或 Microsoft Teams 顯示

  1. 開啟 Teams 行動應用程式。

  2. 選取 **設定**  >  **Cortana**。

  3. 移動開關 **開啟或****關閉**。

### <a name="microsoft-teams-display"></a>Microsoft Teams 顯示

  1. 前往 Microsoft Teams (畫面) 環境環境。

  2. 選取使用者虛擬人像， **然後選取** 設定 。 如果 Cortana 已啟用，請說「Cortana，請前往設定」。

  3. 移動開關 **開啟或****關閉**。
  
### <a name="microsoft-teams-rooms-on-windows"></a>Windows 上的 Microsoft Teams 會議室

如果租使用者層級已啟用 Cortana，可在裝置層級進行變更。 Cortana 預設為關閉。

若要在裝置層級啟用 Cortana，這些 XML 屬性必須新增到 SkypeSettings XML 檔案中：

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

如果裝置層級已啟用 Cortana，可在會議層級進行變更。

若要在會議期間啟用 Cortana 語音協助，請移動開關 **開啟或****關閉**。 會議結束後，Cortana 會回到裝置層級設定集。
