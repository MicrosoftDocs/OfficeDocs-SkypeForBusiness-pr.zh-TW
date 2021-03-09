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
description: 會議是商務用 Skype Online 的重要一部分：會議可讓使用者群組在線上一起觀看幻燈片和視訊、共用應用程式、交換檔案，以及進行通訊和共同合作。
ms.openlocfilehash: 9a2e18ad23eaa08813c87e83058ecc0dcd1dfec1
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569205"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>設定組織的會議原則

會議是商務用 Skype Online 的重要一部分：會議可讓使用者群組在線上共同觀看幻燈片和視訊、共用應用程式、交換檔案，以及進行通訊和共同合作。
  
對於您來說，保持對會議與會議設定的控制非常重要。 在某些情況下，可能有安全性考慮：根據預設，任何人 ，包括未經驗證的使用者，都可以參與會議，並儲存會議期間散發的任何一張或多張講義。 此外，偶爾可能也會有法律上的問題。 例如，根據預設，會議參與者可以針對共用內容進行注釋;不過，這些注釋不會在會議被存檔時儲存。 如果貴組織需要保留所有電子通訊的記錄，您可能會想要停用注釋。 
  
在商務用 Skype Online 中，會議是使用會議策略管理。 會議政策會決定可在會議中使用的功能，包括從會議是否可以包含 IP 音訊和視音訊到可參與會議人數的上限等所有專案。 會議策略可以在全域範圍或每個使用者範圍中進行。 這提供系統管理員在決定哪些功能可供哪些使用者使用時，擁有極大的彈性。
  
您可以在建立策略時設定策略設定，或者您可以使用 **Set-CsConferencingPolicy** Cmdlet 來修改現有策略的設定。
  
## <a name="set-your-conferencing-policies"></a>設定您的會議政策

> [!NOTE]
> 針對商務用 Skype Online 中所有的會議政策設定，您必須使用 Windows PowerShell，而且不能使用商務用 **Skype 系統管理中心**。 

### <a name="start-windows-powershell"></a>啟動 Windows PowerShell

 > [!Note]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。
1. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示程式，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在會議期間封鎖檔案傳輸和桌面共用

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。
    
- 若要將您建立的新政策授予貴組織的所有使用者，請執行：
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。
    
  如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>封鎖會議的錄製，並防止匿名會議參與者

- 若要為這些設定建立新策略，請執行： 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。
    
- 若要將您建立的新策略授予 Amos Marble，請執行：
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。
    
如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>封鎖匿名參與者，禁止錄製會議，以及禁止外部使用者存存會議內容

- 若要為這些設定建立新策略，請執行：  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。
    
- 若要將您建立的新政策授予貴組織的所有使用者，請執行：
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。
    
如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 與只使用 Microsoft 365 系統管理中心相比，Windows PowerShell 在速度、簡化和生產力方面有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

  
 
