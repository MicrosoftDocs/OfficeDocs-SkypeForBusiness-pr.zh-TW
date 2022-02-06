---
title: Cortana語音協助Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
---

# <a name="cortana-voice-assistance-in-teams"></a>Cortana語音協助Teams

> [!Note]
> Cortana iOS 和 Android Microsoft Teams 行動應用程式中支援語音協助，Microsoft Teams適用于美國、英國、加拿大、印度和澳洲的使用者。 Microsoft Teams 會議室上Windows僅適用于設定為 en-us 的裝置。 Cortana目前不適用於 GCC、GCC高、DoD 和非美國 EDU 租使用者。 Cortana行動應用程式中Teams語音協助，現在適用于美國 EDU 客戶。 擴充至其他語言和地區，將在未來發行時進行。


Cortana行動裝置應用程式中Teams、Microsoft Teams 會議室上Windows，以及Microsoft Teams裝置上的語音Microsoft 365 企業版 使用者使用自然口語來簡化通訊、共同作業和會議相關工作。 使用者可以 Cortana選取 Teams 行動應用程式右上角的麥克風按鈕，或在 Microsoft Teams 會議室或使用 Microsoft Teams Cortana 顯示器時，對 Microsoft Teams 說話。 若要不用手快速與小組聯繫，以及進行中，使用者可以說出「打電話給 Megan」或「傳送訊息到下一個會議」等查詢。 使用者也可以說「加入我的下一個會議」，並使用語音協助來共用檔案、檢查他們的日曆等來加入會議。 這些語音協助體驗是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企業級服務提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 中反映。

## <a name="admin-control-and-limitations"></a>系統管理控制與限制

Cortana，Teams 中的語音協助會使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。 此功能預設為租使用者啟用。

租使用者管理員可以控制租使用者中的哪些人Cortana TeamsCortanaPolicy Teams使用 (語音) 。 此策略設定為使用者帳戶層級或租使用者層級。 系統管理員可以使用此策略控制項中的 CortanaVoiceInvocationMode 欄位來判斷 Cortana 是否停用、是否僅以按鈕式啟用啟用，或是否同時啟用適用于支援它的裝置 (，例如 Microsoft Teams 顯示) 。

系統管理員可以使用下列 PowerShell Cmdlet 來管理此 (系統管理中心目前Microsoft Teams此) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下列命令會建立名稱為「EmployeeCortanaPolicy」的新Cortana，Microsoft Teams語音協助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此範例顯示更新名稱為「EmployeeCortanaPolicy」的現有Cortana，並僅使用按鈕Microsoft Teams啟用語音協助。 使用者可以在 Cortana 中選取 Cortana麥克風按鈕來Teams。 喚醒 (「嗨Cortana」或「Cortana」) 會停用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此範例顯示更新策略，並啟用Cortana按鈕和喚醒字詞的語音協助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在初次發行時，Microsoft 365 企業版英文的使用者，以下是可用的函數：

- Teams行動應用程式不支援喚醒字詞啟用，但日後會支援。  

- Microsoft Teams 會議室裝置Windows Microsoft Teams裝置上，將會支援喚醒字詞啟用。

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
- 說「嗨，Cortana」，Cortana _語音啟用_

Cortana 如果您的房間設定為下列任何一種語言，則預設會啟用按按交談：en-au (澳洲)  (、加拿大) 、en-gb (英國) 、en-in (印度) 、美國 () 。 [瞭解更多資訊。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana圖示會 _取代更多__..._ Teams 功能表。 若要停用Cortana _按以交談，請使用_ PowerShell。[瞭解更多資訊。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

若要啟用Cortana _啟用_，必須符合以下條件：
- 已Cortana裝置必須連接到您的會議室Teams裝置。 您可以在本文結尾找到認證裝置清單。
- Teams 會議室必須以下列任何語言設定：en-au (澳洲) 、加拿大 () 、en-gb (英國) 、en-in (印度) 、en-us (美國) 。 日後將會提供更多語言。
- 必須進行下列其中一個組組變更：
  - 在系統管理中心開啟Teams[深入瞭解。](/microsoftteams/rooms/rooms-manage)
  - 新增下列 XML 屬性至 SkypeSettings XML 檔案：

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
在會議層級，只有在裝置層級啟用語音Cortana才能進行變更。   若要 _在Cortana啟用_ 語音啟用功能，請移動開關 **開啟** 或 **關閉** 以停用。 會議結束後，Cortana回到裝置層級設定設定。


如果裝置層級已啟用 Cortana，可在會議層級進行變更。

若要在Cortana啟用語音，請移動開關 **開啟或****關閉**。 會議結束後，Cortana回到裝置層級設定設定。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana認證裝置Teams 會議室
Cortana _Lenovo_ Hub 500，或如果您將任何裝置連接到您的會議室，就可以啟用語音啟用：
- Jabra Panacast 50 
- 召集式麥克風
- Bose 視線 VB1

