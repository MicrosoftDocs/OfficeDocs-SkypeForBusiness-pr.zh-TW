---
title: Microsoft Teams 中的 Cortana 語音協助
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何在 Teams 中使用 Cortana 語音協助
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 502f09891942796a326deba35e29fab234e6548a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198495"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams 中的 Cortana 語音協助

> [!NOTE]
> 適用于 iOS 和 Android 的 Microsoft Teams 行動裝置 App、Microsoft Teams 顯示器，以及適用于美國、英國、加拿大、印度和澳大利亞使用者的 Windows 上Microsoft Teams 會議室支援 Cortana 語音協助。 Teams 行動裝置 App 中的 Cortana 語音協助現已可供 en-US 的 EDU 客戶使用。 擴充至其他語言和地區時，將會成為未來版本的一部分。 Cortana 語音協助目前不適用於 GCC、GCC-High、DoD 和非美國 EDU 租使用者。

Teams 行動裝置 App、Windows 上的 Microsoft Teams 會議室，以及在 Microsoft Teams 顯示裝置上的 Cortana 語音協助，可讓Microsoft 365 企業版使用者使用口語自然語言簡化通訊、共同作業和會議相關工作。 使用者可以透過選取 Teams 行動應用程式右上角的麥克風按鈕，或在 Teams 會議室中說出「Cortana」Microsoft，或是使用 Microsoft Teams 顯示器，來與 Cortana 交談。 若要在外出時以免持聽筒的方式快速與小組聯繫，使用者可以說出「打電話給 Megan」或「傳送訊息至我的下一場會議」等查詢。 使用者也可以說出「加入我的下一場會議」來加入會議，並使用語音協助來共用檔案、檢查行事曆等等。 這些語音協助體驗是使用[Cortana 企業級服務](/microsoft-365/admin/misc/cortana-integration)所提供，這些服務完全符合Office 365隱私權、安全性和合規性承諾，如[OST)  (線上服務條款](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)所反映。

## <a name="admin-control-and-limitations"></a>管理員控制與限制

Teams 中的 Cortana 語音協助是使用完全符合Office 365企業層級隱私權、安全性和合規性承諾的服務所提供，如 OST)  (線上服務條款所反映。 租使用者預設會啟用此功能。

租使用者系統管理員可以使用 Teams 中的原則 (TeamsCortanaPolicy) ，控制其租使用者中的誰可以使用 Cortana 語音協助。 此原則設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此原則控制項內的 CortanaVoiceInvocationMode 欄位來判斷 Cortana 是否已停用、僅以推播按鈕叫用來啟用，或使用喚醒文字叫用，以及 (適用于支援 Cortana 的裝置，例如 Teams 顯示) Microsoft。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則， (目前無法在 Microsoft Teams 系統管理中心) 使用原則。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會建立名為「EmployeeCortanaPolicy」的新原則，其中會停用 Microsoft Teams 中的 Cortana 語音協助。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此範例顯示更新現有原則，名稱為「EmployeeCortanaPolicy」，並僅在 Microsoft Teams 中啟用 Cortana 語音協助， 使用者可以在 Teams 中選取 Cortana 麥克風按鈕來叫用 Cortana。 將會停用喚醒單字 (「嗨 Cortana」或「Cortana」) 。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新原則，並透過按鍵和喚醒文字叫用啟用 Cortana 語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

目前，美國Microsoft 365 企業版使用者的英文版初次發行版本中，有下列可用功能：

- Teams 行動裝置 App 不支援喚醒 word 啟用，但日後將會受到支援。

- 在 Windows 和 Microsoft Teams 顯示裝置上Microsoft Teams 會議室將支援喚醒文字啟用。

## <a name="user-control"></a>使用者控制

個別使用者可以在不同的裝置上嘗試 Cortana 語音協助：

- 在 Teams 行動應用程式中選取麥克風按鈕。

- 選取麥克風按鈕或在Microsoft Teams 會議室中說「Cortana」。

- 在 Teams 顯示裝置Microsoft說「Cortana」。

您可以使用裝置中的設定，控制 Teams 中的 Cortana 是否已為您的裝置啟用。

![顯示啟用 Cortana 時行動裝置視窗的進度。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>在 Windows 上Microsoft Teams 會議室

只有在租使用者層級啟用 Cortana 時，才能在裝置層級進行變更。

在裝置層級，您可以將 Cortana 設定為以兩種不同的方式使用。 您可以同時啟用其中一個選項或兩者：

- 點選麥克風，稱為 Cortana _推播說話_
- 說「嗨，Cortana」，這稱為 _Cortana 語音啟用_

如果您的聊天室是使用下列任何語言來設定，Cortana _推入式交談_ 預設會啟用：en-au (Australia) 、en-ca (Canada) 、en-gb (United Kingdom) 、en-in (India) 、en-us (美國) 。 [瞭解更多資訊。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana 圖示會取代 Teams 會議室主機中 [_其他...]_ 功能表底下的 [_簡報_] 按鈕。 若要停用 Cortana _推播以說話_ ，請使用 PowerShell。[瞭解更多資訊。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

若要啟用 Cortana _語音啟動_，必須符合下列條件：

- Cortana 認證的裝置必須連線到您的 Teams 會議室。 您可以在本文結尾處找到已認證裝置的清單。
- Teams 會議室必須使用下列任何語言來設定：en-au (Australia) 、en-ca (Canada) 、en-gb (英國) 、en-in (India) 、en-us (美國) 。 日後將會提供更多語言。
- 您必須進行下列其中一項設定變更：
  - 在 Teams 系統管理中心開啟此功能 [以深入瞭解。](/microsoftteams/rooms/rooms-manage)
  - 將下列 XML 屬性新增至 SkypeSettings XML 檔案：

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

在會議層級，只有在裝置層級啟用 Cortana _語音啟動_ 時，才能進行變更。  若要在會議期間啟用 Cortana _語音啟動_，請將開關移至 **[開啟****] 或 [關閉]** 以停用。 會議結束後，Cortana 會回到裝置層級設定集。

如果已在裝置層級啟用 Cortana，則可在會議層級進行變更。

若要在會議期間啟用 Cortana _語音啟動_，請將開關移至 [**開啟****] 或 [關閉]**。 會議結束後，Cortana 會回到裝置層級設定集。

## <a name="cortana-certified-devices-for-teams-rooms"></a>適用于 Teams 會議室 的 Cortana 認證裝置

如果您使用的是 Lenovo Hub 500，或如果您有將下列任何裝置連接到會議室，則可啟用 Cortana _語音啟動_ ：

- Jabra Panacast 50
- Logi 方塊加號會議系統
- Bose 視訊列 VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
