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
description: 您可以使用行動裝置上的商務用 Skype 應用程式來設定使用者連線至商務用 Skype Online 的連線方式，例如，讓使用者使用公司電話號碼而非行動電話號碼，在行動電話上撥打和接聽電話的功能。 在撥打或接聽電話時，行動Wi-Fi也可以用來要求建立連線。
ms.openlocfilehash: b0e2f7524f300733840159eacfcf27bb54f5e815
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100489"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>設定組織的行動原則

您可以使用行動裝置上的商務用 Skype 應用程式來設定使用者連線至商務用 Skype Online 的連線方式，例如，讓使用者使用公司電話號碼而非行動電話號碼，在行動電話上撥打和接聽電話的功能。 在撥打或接聽電話時，行動Wi-Fi也可以用來要求建立連線。
  
您可以在建立原則時設定行動策略設定，或者您可以使用 **Set-CsMobilityPolicy** Cmdlet 修改現有原則的設定。
  
## <a name="set-your-mobile-policies"></a>設定行動策略

> [!NOTE]
> 針對商務用 Skype Online 中所有的行動策略設定，您必須使用 Windows PowerShell，而且您不得使用 **商務用 Skype 系統管理中心**。  
  
### <a name="start-windows-powershell"></a>啟動 Windows PowerShell

> [!NOTE]
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。
1. 安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示符，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>需要使用者視像的 WiFi 連接

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   請參閱 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) Cmdlet 上的更多資訊。
    
- 若要將您建立的新政策授予貴組織中所有使用者，請執行：
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   請參閱 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet。
    
  如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>防止使用者使用商務用 Skype 應用程式

- 若要為這些設定建立新策略，請執行：
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  請參閱 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) Cmdlet 上的更多資訊。
    
- 若要將您建立的新政策授予 Amos Marble，請執行：  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   請參閱 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet。
    
  如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>防止使用者使用行動裝置撥打 IP 電話

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   請參閱 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) Cmdlet 上的更多資訊。
    
- 若要將您建立的新政策授予貴組織中所有使用者，請執行：
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  請參閱 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet。
    
如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) Cmdlet 將設定套用給使用者。
  
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

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
