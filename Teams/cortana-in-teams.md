---
title: Microsoft 團隊中的 Cortana 語音協助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何在團隊中使用 Cortana 語音協助
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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686439"
---
# <a name="cortana-voice-assistance-in-teams"></a>小組中的 Cortana 語音協助

> [!Note]
> Microsoft mobile iOS 和 Android 行動裝置 app 支援 Cortana 語音協助、Windows 上的 Microsoft 團隊聊天室，以及 Microsoft 團隊只會顯示美國的使用者。 此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。 在未來的版本中，延伸到其他語言和區域就會發生。

> [!Note]
> Microsoft 團隊聊天室中的 Cortana 語音協助功能已在 [預覽] 底下發布。 在其預覽發行版本中，只有在已連接 Rally 麥克風的裝置上，才支援使用 [美國] 語言的 Cortana。

在團隊行動應用程式中使用 Cortana 語音協助，在 Windows 上的 Microsoft 團隊聊天室，在 Microsoft 團隊顯示裝置上，Microsoft 365 企業版使用者可以使用語音、共同作業以及與會議相關的工作。 使用者可以透過選取位於團隊行動應用程式右上角的麥克風按鈕來朗讀 Cortana，或者說在 Microsoft 球隊聊天室中 &#8220;Cortana&#8221; 或使用 Microsoft 團隊顯示時。 若要快速地與其團隊保持聯繫，並在行動期間，使用者可以說出 &#8220;通話 Megan 的查詢&#8221; 或 &#8220;傳送訊息給我的下一個會議&#8221;。 使用者也可以說 &#8220;加入我的下一筆會議&#8221; 並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。 這些語音協助體驗是使用 [Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，在 [線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中反映。

此影像顯示在行動裝置上使用 Cortana 傳送聊天的活動。

![顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性的服務提供，在線上服務條款 (OST) 中反映。 預設會針對承租人啟用該功能。

租使用者管理員可以利用原則 (TeamsCortanaPolicy) ，控制其租使用者在小組中使用 Cortana 語音協助的人員。 此原則可以在使用者帳戶層級或租使用者層級設定。 系統管理員可以使用此原則控制中的 CortanaVoiceInvocationMode 欄位來判斷 Cortana 是停用、只啟用推播式撥號，或使用喚醒 word 的方式 (適用于支援它的裝置，例如 Microsoft 團隊顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則 (目前無法在 Microsoft 團隊系統管理中心) 中使用原則。

- [新-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [授與 CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [移除-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會建立名稱 &#8220;EmployeeCortanaPolicy&#8221; 的新原則，在其中停用 Cortana 語音協助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

這個範例示範如何使用名稱 &#8220;EmployeeCortanaPolicy&#8221; 更新現有的原則，並在只有按下按鈕通話的 Microsoft 團隊中啟用 Cortana 語音協助。 使用者可以透過選取 [小組] 中的 [Cortana] 麥克風按鈕來喚醒呼叫 Cortana。 喚醒 word ( # B0 你好 Cortana&#8221; 或 &#8220;Cortana&#8221;) 會停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

這個範例示範如何更新原則，以及如何使用 [推入] 按鈕和 [喚醒] 字通話來啟用 Cortana 語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在 Microsoft 365 企業使用者的初次發行時間（英文），以下是可用的功能：

- [團隊行動裝置] app 不支援喚醒 word 啟用，但將來會受到支援。  

- Windows 和 Microsoft 團隊中的 microsoft 團隊聊天室顯示裝置將支援喚醒 word 啟用。

## <a name="user-control"></a>使用者控制項

個別使用者可以在不同的裝置中試用 Cortana 語音協助：

- 選取 [團隊行動裝置] app 中的 [麥克風] 按鈕。

- 選取 [麥克風] 按鈕，或在 Microsoft 團隊聊天室中說「Cortana」。

- 在 Microsoft 團隊顯示裝置上說「Cortana」。

您可以使用裝置中的設定，控制是否已在您的裝置上啟用 Cortana。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>團隊行動應用程式或 Microsoft 團隊顯示

  1. 開啟 [小組行動裝置] app。

  2. 選取 [**設定**  >  **Cortana**]。

  3. 將開啟或 **關閉** 開關移 **開**。

### <a name="microsoft-teams-display"></a>Microsoft 團隊顯示

  1. 移至 Microsoft 團隊顯示的 [環境] ([家用) ] 畫面。

  2. 選取 [使用者頭像]，然後選取 [ **設定**]。 如果已啟用 Cortana，請說「Cortana，請移至 [設定]。

  3. 將開啟或 **關閉** 開關移 **開**。
  
### <a name="microsoft-teams-rooms-on-windows"></a>Windows 上的 Microsoft 團隊聊天室

如果在租使用者層級啟用 Cortana，就可以使用裝置層級進行變更。 Cortana 將預設為放開。

若要在裝置層級啟用 Cortana，必須在 SkypeSettings XML 檔案中新增這些 XML 屬性：

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

如果在裝置層級啟用 Cortana，就可以使用在會議層次進行變更。

若要在會議期間啟用 Cortana 語音協助，請將開關移至 **開啟** 或 **關閉**。 會議結束後，Cortana 會回到裝置層級設定。
