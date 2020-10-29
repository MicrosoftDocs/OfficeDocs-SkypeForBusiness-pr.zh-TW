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
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785387"
---
# <a name="cortana-voice-assistance-in-teams"></a>小組中的 Cortana 語音協助

> [!Note]
> Microsoft mobile iOS 和 Android 行動裝置 app 支援 Cortana 語音協助，且僅限在美國使用者顯示的 Microsoft 團隊。 此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。 在未來的版本中，延伸到其他語言和區域就會發生。

[小組行動] app 和 Microsoft 團隊顯示裝置上的 Cortana 語音協助可讓 Microsoft 365 企業使用者使用語音的自然語言來簡化溝通、共同作業及會議相關工作。 使用者可以透過選取位於團隊行動應用程式右上角的麥克風按鈕來朗讀 Cortana，或在 Microsoft 團隊顯示中說 &#8220;Cortana&#8221;。 若要快速地與其團隊保持聯繫，並在行動期間，使用者可以說出 &#8220;通話 Megan 的查詢&#8221; 或 &#8220;傳送訊息給我的下一個會議&#8221;。 使用者也可以說 &#8220;加入我的下一筆會議&#8221; 並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。 這些語音協助體驗是使用 [Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，在 [線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中反映。

此影像顯示在行動裝置上使用 Cortana 傳送聊天的活動。

![影像顯示顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性的服務提供，在線上服務條款 (OST) 中反映。 預設會針對承租人啟用該功能。

租使用者管理員可以利用原則 (TeamsCortanaPolicy) ，控制其租使用者在小組中使用 Cortana 語音協助的人員。 此原則可以在使用者帳戶層級或租使用者層級設定。 系統管理員可以使用此原則控制中的 [CortanaVoiceInvocationMode] 欄位來判斷 Cortana 是停用、只在按下按鈕的情況下啟用，或是使用喚醒 word 調用來 (適用于支援它的裝置，例如 Microsoft 團隊顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則 (目前無法在 Microsoft 團隊系統管理中心) 中使用原則。

- [新-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

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

> [!Note]
> 在 Microsoft 365 的初次發行時，[小組行動] app 將不支援喚醒 word 啟用，但將來會受到支援。 喚醒 word 啟用功能會在初次發行時，在 Microsoft 團隊顯示的裝置上運作。

## <a name="user-control"></a>使用者控制項

個別使用者可以透過選取 [麥克風] 按鈕，在小組行動應用程式中試用 Cortana 語音協助。 他們可以在 Microsoft 團隊顯示裝置上，只要說 &#8220;Cortana]，就能試用 Cortana 語音協助。 &#8221; 他們也可以使用 [小組行動] 應用程式或 [Microsoft 團隊顯示] 中的設定，來控制是否已針對其裝置啟用 [在小組中使用 Cortana]。

1. 開啟 [小組行動裝置] app，或移至 Microsoft 團隊顯示的 [環境] ([家用) ] 畫面。

2. 在 [小組行動應用程式] 中，移至 [ **設定** ]。 在 [Microsoft 團隊顯示] 上，選取 [使用者頭像]，然後選取 [設定]。 如果已啟用 Cortana，請說 &#8220;Cortana，請移至 [設定]。 &#8221;

3. 選取 [ **Cortana** ]。

4. 根據您是否要在裝置上進行 Cortana 語音協助，將開關移至 [ **開啟** ] 或 [ **關閉** ]。
