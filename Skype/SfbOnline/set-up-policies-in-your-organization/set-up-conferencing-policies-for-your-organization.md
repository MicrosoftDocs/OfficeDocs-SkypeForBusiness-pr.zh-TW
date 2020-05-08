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
description: 會議是商務用 Skype Online 的重要部分：「會議」可讓使用者群組線上進行，以查看投影片和影片、共用應用程式、exchange 檔案，以及其他溝通與共同作業。
ms.openlocfilehash: 20bb000cfe4cf2056877db07423b1c7791249b03
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164462"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>設定組織的會議原則

會議是商務用 Skype Online 的重要部分：「會議」可讓使用者群組線上進行，以查看投影片和影片、共用應用程式、exchange 檔案，以及其他溝通與共同作業。
  
您必須維持對會議與會議設定的控制權，這一點非常重要。 在某些情況下，可能會發生安全性問題：根據預設，任何人（包括未經驗證的使用者）都可以參與會議，並儲存在這些會議中散佈的任何投影片或講義。 此外，可能還有一些偶然的法律問題。 例如，在預設情況下，會議參與者可以在共用內容上加上批註;不過，當會議封存時，這些注釋不會儲存。 如果您的組織必須保留所有電子通訊的記錄，您可能會想要停用注釋。 
  
在商務用 Skype Online 中，會議是透過會議原則來管理。 會議原則決定可在會議中使用的功能和功能，包括不論會議是否可將 IP 音訊與影片加入會議的人數上限。 您可以在全域範圍或針對每個使用者範圍設定會議原則。 這可讓系統管理員在決定將哪些功能提供給哪些使用者時，提供巨大的彈性。
  
原則設定可以在建立原則時設定，或者您可以使用**CsConferencingPolicy** Cmdlet 來修改現有原則的設定。
  
## <a name="set-your-conferencing-policies"></a>設定您的會議原則

> [!NOTE]
> 針對商務用 Skype Online 中的所有會議原則設定，您必須使用 Windows PowerShell，而且您**無法使用商務用** **Skype 系統管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>驗證並啟動 Windows PowerShell

- **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
    
    1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。
        
    2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
        
    3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
        
    4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
    如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **啟動 Windows PowerShell 會話**
    
    1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
        
    2. 在**Windows PowerShell**視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：
        
        > [!NOTE]
        > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在會議期間封鎖檔案傳輸與桌面共用

- 若要為這些設定建立新的原則，請執行：
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   如需進一步瞭解，請參閱[新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。
    
- 若要將您建立的新原則授與貴組織中的所有使用者，請執行：
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   如需[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。
    
  如果您已建立原則，您可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>封鎖會議錄製並防止匿名會議參與者

- 若要為這些設定建立新的原則，請執行： 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   如需進一步瞭解，請參閱[新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。
    
- 若要將您建立的新原則授與 Amos 大理石，請執行：
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   如需[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。
    
如果您已建立原則，您可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>封鎖匿名參與者的錄製會議與外部使用者無法儲存會議內容

- 若要為這些設定建立新的原則，請執行：  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   如需進一步瞭解，請參閱[新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。
    
- 若要將您建立的新原則授與貴組織中的所有使用者，請執行：
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

如需[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。
    
如果您已建立原則，您可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對端檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

  
 
