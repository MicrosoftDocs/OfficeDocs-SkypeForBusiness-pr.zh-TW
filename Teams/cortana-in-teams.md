---
title: Microsoft 團隊中的 Cortana 語音助手
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何搭配團隊使用 Cortana 語音助手
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522314"
---
# <a name="cortana-voice-assistance-in-teams"></a>小組中的 Cortana 語音協助

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> 只有在適用于美國的使用者，才能在 Microsoft 團隊 iOS 和 Android 行動裝置 app 上支援 Cortana 語音協助。 此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。 在未來的版本中，延伸到其他語言和區域就會發生。

在團隊行動應用程式中使用 Cortana 語音協助，Microsoft 365 企業版使用者就能利用語音的自然語言來簡化溝通、共同作業及會議相關工作。 使用者可以按一下位於團隊行動應用程式右上角的麥克風按鈕來與 Cortana 通話。 若要在旅途中快速與其小組連線，使用者可以說出「呼叫 Megan」或「將訊息傳送到我的下一筆會議」的查詢。 使用者也可以說「加入我的下一筆會議」，並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。 這些語音協助體驗是使用[Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)提供，完全符合 Office 365 的隱私權、安全性和合規性承諾反映在[線上服務條款（OST）](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。

影像會顯示在行動裝置上的 Cortana 中傳送聊天的活動。

![影像顯示顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性承諾的服務來提供，以反映線上服務條款（OST）中。 預設會針對承租人啟用該功能。

租使用者管理員可以利用原則（TeamsCortanaPolicy）控制其租使用者可以在小組中使用 Cortana 語音協助的人員。 此原則可以在使用者帳戶層級或租使用者層級設定。 系統管理員可以使用此原則控制中的 [CortanaVoiceInvocationMode] 欄位來判斷 Cortana 是停用、只在按下按鈕的情況下啟用，還是同時使用喚醒 word 調用（適用于支援它的裝置）。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則（此原則目前無法用於 Microsoft 團隊系統管理中心）。

- [新-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [授與 CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [移除-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會建立名稱為 "EmployeeCortanaPolicy" 的新原則，在 Microsoft 團隊中的 Cortana 語音助手已停用。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

這個範例示範如何更新名稱為 "EmployeeCortanaPolicy" 的現有原則，以及如何在 Microsoft 團隊中啟用 Cortana voice assistant，只需按下按鈕即可。 使用者可以點擊 [小組] 中的 [Cortana] 麥克風按鈕來呼叫 Cortana。 喚醒 word （"你好 Cortana"）調用將會停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

這個範例示範如何更新原則，以及如何使用 [推入] 按鈕和 [喚醒字] 通話來啟用 Cortana 語音助手。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 在 Microsoft 365 的初次發行時，[小組行動] app 將不支援喚醒 word 啟用，但將來會受到支援。

## <a name="user-control"></a>使用者控制項

個別使用者可以按一下 [麥克風] 按鈕，在小組行動應用程式中試用 Cortana 語音協助。 他們也可以使用 [團隊行動應用程式] 中的設定，控制是否已針對其裝置啟用 [在小組中使用 Cortana]。

1. 開啟 [小組行動裝置] app。

2. 移至 [**設定**]。

3. 選取 [ **Cortana**]。

4. 根據您是否要在裝置上進行 Cortana 語音協助，將開關移至 [**開啟**] 或 [**關閉**]。
