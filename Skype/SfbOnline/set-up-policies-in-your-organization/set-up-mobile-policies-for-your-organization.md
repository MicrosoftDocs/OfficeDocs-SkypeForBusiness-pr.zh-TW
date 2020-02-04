---
title: 設定組織的行動原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 您可以使用行動裝置上的商務用 Skype app 來設定使用者連線到商務用 Skype Online 的方式，例如可讓使用者使用公司電話號碼在手機上撥打及接聽電話的功能，而不是在其行動電話上撥打電話mber. 行動原則也可以用於在撥打或接聽來電時，需要使用 Wi-fi 連線。
ms.openlocfilehash: 7457b89014395a5ee833b8a35bde68751ade9cfd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692948"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>設定組織的行動原則

您可以使用行動裝置上的商務用 Skype app 來設定使用者連線到商務用 Skype Online 的方式，例如可讓使用者使用公司電話號碼在手機上撥打及接聽電話的功能，而不是在其行動電話上撥打電話mber. 行動原則也可以用於在撥打或接聽來電時，需要使用 Wi-fi 連線。
  
行動原則設定可以在建立原則時設定，或者您可以使用**CsMobilityPolicy** Cmdlet 來修改現有原則的設定。
  
## <a name="set-your-mobile-policies"></a>設定您的行動裝置原則

> [!NOTE]
> 針對商務用 Skype Online 中的所有行動原則設定，您必須使用 Windows PowerShell，而且您**無法使用商務用** **Skype 系統管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>驗證並啟動 Windows PowerShell

- **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
    
1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
    如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **啟動 Windows PowerShell 會話**
    
1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
    
2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：
    
    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>使用者需要一個 WiFi 連線才能取得影片

- 若要為這些設定建立新的原則，請執行：
  > 
  > ```PowerShell
  > New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  > ```
  > 如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。
    
- 若要將您建立的新原則授與貴組織中的所有使用者，請執行：
  > 
  > ```PowerShell
  > Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  > ```
  > 如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。
    
  如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>防止使用者使用商務用 Skype 應用程式

- 若要為這些設定建立新的原則，請執行：
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。
    
- 若要將您建立的新原則授與 Amos 大理石，請執行：  
  > 
  > ```PowerShell
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  > ```
  > 如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。
    
  如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>防止使用者使用行動裝置撥打電話給 IP 電話

- 若要為這些設定建立新的原則，請執行：
  > 
  > ```PowerShell
  > New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  > ```
  > 如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。
    
- 若要將您建立的新原則授與貴組織中的所有使用者，請執行：
  > 
  > ```PowerShell
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  > ```

  如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。
    
如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對端檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議原則](set-up-conferencing-policies-for-your-organization.md)

  
 
