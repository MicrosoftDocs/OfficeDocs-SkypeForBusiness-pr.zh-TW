---
title: 設定組織的會議原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 會議是商務用 Skype Online 的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及通訊和共同合作。
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100519"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>設定組織的會議原則

會議是商務用 Skype Online 的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及以其他方式通訊和共同合作。
  
您必須維持對會議與會議設定的控制。 在某些情況下，可能有安全性考慮：根據預設，任何人 ，包括未經驗證的使用者，都可以參與會議，並儲存這些會議期間散發的任何幻燈片或講義。 此外，可能偶爾也會有法律上的問題。 例如，根據預設，會議參與者可以針對共用內容進行注釋;不過，這些注釋不會在會議儲存時儲存。 如果貴組織需要保留所有電子通訊的記錄，您可能會想要停用注釋。 
  
在商務用 Skype Online 中，會議是使用會議策略進行管理。 會議政策會決定可在會議中使用的功能，包括會議是否可以包含 IP 音訊和視像，以及可參加會議人數上限等所有專案。 會議策略可以在全域範圍或每個使用者範圍內進行配置。 當決定哪些功能可供哪些使用者使用時，這為系統管理員提供了極大的彈性。
  
您可以在建立策略時設定策略設定，或者您可以使用 **Set-CsConferencingPolicy** Cmdlet 修改現有策略的設定。
  
## <a name="set-your-conferencing-policies"></a>設定您的會議策略

> [!NOTE]
> 針對商務用 Skype Online 中所有的會議策略設定，您必須使用 Windows PowerShell，而且您不得使用商務用 **Skype 系統管理中心**。 

### <a name="start-windows-powershell"></a>啟動 Windows PowerShell

 > [!Note]
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。
1. 安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示符，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 服務，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在會議期間封鎖檔案傳輸和桌面共用

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。
    
- 若要將您建立的新政策授予貴組織的所有使用者，請執行：
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。
    
  如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>封鎖會議錄製，並防止匿名會議參與者

- 若要為這些設定建立新策略，請執行： 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。
    
- 若要將您建立的新政策授予 Amos Marble，請執行：
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。
    
如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>封鎖匿名參與者錄製會議，以及禁止外部使用者保存會議內容

- 若要為這些設定建立新策略，請執行：  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。
    
- 若要將您建立的新政策授予貴組織中所有使用者，請執行：
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。
    
如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點到點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

  
