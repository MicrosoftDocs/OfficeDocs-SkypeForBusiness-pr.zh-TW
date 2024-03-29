---
title: 設定組織的用戶端原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 用戶端政策可協助判斷商務用 Skype Online 的可用功能;例如，您可以給予部分使用者傳輸檔案的權利，同時拒絕將這項權利授予其他使用者。
ms.openlocfilehash: e5fe976e3adb566c469d2c58a5d2b6a976776ac3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619249"
---
# <a name="set-up-client-policies-for-your-organization"></a>設定組織的用戶端原則

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

用戶端政策可協助判斷商務用 Skype Online 的可用功能;例如，您可以給予部分使用者傳輸檔案的權利，同時拒絕將這項權利授予其他使用者。
  
您可以在建立策略時設定用戶端策略設定，或者您可以使用 **Set-CsClientPolicy** Cmdlet 修改現有策略的設定。
  
## <a name="set-your-client-policies"></a>設定用戶端策略

> [!NOTE]
> 針對 商務用 Skype Online 中所有的用戶端Windows PowerShell設定，您不得使用 商務用 Skype **系統管理中心**。  
  
### <a name="start-windows-powershell"></a>開始Windows PowerShell

> [!NOTE]
> 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。
1. 安裝 Teams [PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell命令提示符，然後執行下列命令： 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   若要進一Windows PowerShell，請參閱連線視窗中連線所有 Microsoft 365 或 Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>停用圖釋和目前狀態通知，並防止保存 IMS

- 若要為這些設定建立新策略，請執行：
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。
    
- 若要將您建立的新政策授予貴組織中所有使用者，請執行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。
    
如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>啟用 URL 或超連結在 IMs 中可按一下

- 若要為這些設定建立新策略，請執行：
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。
    
- 若要將您建立的新政策授予貴組織中所有使用者，請執行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。
    
如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。
  
### <a name="prevent-showing-recent-contacts"></a>防止顯示最近的連絡人

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。
    
- 若要將您建立的新政策授予 Amos Marble，請執行：
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。
    
  如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理Microsoft 365或 Office 365 商務用 Skype管理線上，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [您可能會想要使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點到點檔案傳輸](block-point-to-point-file-transfers.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
