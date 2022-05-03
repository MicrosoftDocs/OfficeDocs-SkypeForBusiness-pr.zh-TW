---
title: 在 Microsoft Teams 中Cortana語音協助
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何搭配使用Cortana語音協助Teams
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
ms.openlocfilehash: 5f888e36d9c0cdd19a0fdd8184d72eeee5ad2a45
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171699"
---
# <a name="cortana-voice-assistance-in-teams"></a>在 Teams 中Cortana語音協助

> [!Note]
> iOS 和 Android Microsoft Teams 行動裝置 App 以及Microsoft Teams、英國、加拿大、印度和澳洲的使用者Microsoft Teams行動裝置 App 支援 美國Cortana語音協助。 Windows上的Microsoft Teams 會議室僅支援地區設定為 en-us 的裝置。 Cortana語音協助目前不適用於 GCC、GCC-High、DoD 和非美國 EDU 租使用者。 Cortana行動裝置應用程式 Teams中的語音協助現在適用于 en-US 的 EDU 客戶。 擴充至其他語言和地區時，將會成為未來版本的一部分。


Cortana行動裝置應用程式、Windows Microsoft Teams 會議室以及Microsoft Teams顯示裝置上的Teams行動裝置上的語音協助可Microsoft 365 企業版 使用者使用口語自然語言簡化通訊、共同作業和會議相關工作。 使用者可以透過選取Teams行動裝置應用程式右上角的麥克風按鈕，或在Microsoft Teams會議室或使用Microsoft Teams顯示器說「Cortana」來與Cortana交談。 若要在外出時以免持聽筒的方式快速與小組聯繫，使用者可以說出「打電話給 Megan」或「傳送訊息至我的下一場會議」等查詢。 使用者也可以說出「加入我的下一場會議」來加入會議，並使用語音協助來共用檔案、檢查行事曆等等。 這些語音協助體驗是使用Cortana完全符合Office 365隱私權、安全性和合規性承諾[的企業級服務](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)所提供，如[OST)  (線上服務條款](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)所反映。

## <a name="admin-control-and-limitations"></a>系統管理員控制與限制

Teams中的Cortana語音協助是使用完全遵守 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如 OST)  (線上服務條款所反映。 租使用者預設會啟用此功能。

租使用者系統管理員可以使用 TeamsCortanaPolicy)  (原則，控制其租使用者中的誰可以在Teams使用Cortana語音協助。 此原則設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此原則控制項內的 CortanaVoiceInvocationMode 欄位來判斷是否停用Cortana、僅以推播按鈕叫用啟用，或使用喚醒字叫功能，以及適用于支援該功能之裝置的 (，例如Microsoft Teams顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則， (目前Microsoft Teams系統管理中心) 不提供該原則。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會建立名為「EmployeeCortanaPolicy」的新原則，其中會停用Microsoft Teams中的Cortana語音協助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此範例顯示更新現有原則，名稱為「EmployeeCortanaPolicy」，並僅在Microsoft Teams中啟用Cortana語音協助， 使用者可以 Cortana透過選取Teams中的 [麥克風] 按鈕來叫用Cortana。 將會停用 (「Hey Cortana」 或 「Cortana」) 語句。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新原則，並啟用Cortana按鍵和喚醒單字叫用的語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

目前，美國Microsoft 365 企業版使用者的英文版初次發行版本中，有下列可用功能：

- Teams行動裝置 App 不支援喚醒 word 啟用，但未來會受到支援。  

- Windows和Microsoft Teams顯示裝置上的Microsoft Teams 會議室將支援喚醒 word 啟用。

## <a name="user-control"></a>使用者控制

個別使用者可以在不同的裝置上嘗試Cortana語音協助：

- 在行動應用程式Teams選取麥克風按鈕。

- 選取麥克風按鈕或在Microsoft Teams 會議室中說出「Cortana」。

- 在Microsoft Teams顯示器裝置上說「Cortana」。

您可以使用裝置中的設定來控制Teams中的Cortana是否已為您的裝置啟用。

![顯示啟用Cortana時行動裝置視窗的進度。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>在 Windows 上Microsoft Teams 會議室

只有在租使用者層級啟用Cortana時，才能在裝置層級進行變更。 

在裝置層級，您可以設定Cortana以兩種不同的方式使用。 您可以同時啟用其中一個選項或兩者： 
- 點選麥克風，此麥克風稱為Cortana _推入說話_
- 說「嘿，Cortana」，這稱為 _「Cortana語音啟動」_

Cortana 如果您的聊天室是使用下列任何語言來設定，預設會啟用「_推入交談_」：en-au (Australia) 、en-ca (Canada) 、en-gb (United Kingdom) 、en-in (India) 、en-us (美國) 。 [瞭解更多資訊。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana圖示會取代 [_其他..._] 底下的 [_簡報]_ 按鈕... 功能表 Teams。 若要停用Cortana _按下以說話_，請使用 PowerShell。[瞭解更多資訊。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

若要啟用Cortana _語音啟動_，必須符合下列條件：
- Cortana認證的裝置必須連線到Teams會議室。 您可以在本文結尾處找到已認證裝置的清單。
- Teams會議室必須使用下列任何語言來設定：en-au (Australia) 、en-ca (Canada) 、en-gb (United Kingdom) 、en-in (India) 、en-us (美國) 。 日後將會提供更多語言。
- 您必須進行下列其中一項設定變更：
  - 在 Teams 系統管理中心開啟此功能[以深入瞭解。](/microsoftteams/rooms/rooms-manage)
  - 將下列 XML 屬性新增至 SkypeSettings XML 檔案：

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
在會議層級，只有在裝置層級啟用Cortana _語音啟動_ 時，才能進行變更。  若要在會議期間啟用Cortana _語音啟動_，請將開關移至 **[開啟**] 或 [**關閉]** 以停用。 會議結束後，Cortana會回到裝置層級設定。


如果已在裝置層級啟用Cortana，則可在會議層級進行變更。

若要在會議期間啟用Cortana _語音啟動_，請將開關移至 [**開****啟] 或 [關閉]**。 會議結束後，Cortana會回到裝置層級設定。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana Teams 會議室認證的裝置
Cortana如果您使用的是 Lenovo Hub 500 或是您已將下列任何裝置連接到會議室，則可以啟用 _語音啟動_：
- Jabra Panacast 50 
- 麥克風
- Bose 視訊列 VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech  

