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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 用戶端策略可協助判斷提供給使用者的商務用 Skype Online 功能;例如，您可能會給予部分使用者傳輸檔案的權利，同時拒絕其他使用者這項權利。
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569225"
---
# <a name="set-up-client-policies-for-your-organization"></a>設定組織的用戶端原則

用戶端策略可協助判斷提供給使用者的商務用 Skype Online 功能;例如，您可能會給予部分使用者傳輸檔案的權利，同時拒絕其他使用者這項權利。
  
您可以在建立策略時設定用戶端策略設定，或者您可以使用 **Set-CsClientPolicy** Cmdlet 來修改現有策略的設定。
  
## <a name="set-your-client-policies"></a>設定您的用戶端策略

> [!NOTE]
> 針對商務用 Skype Online 的所有用戶端策略設定，您必須使用 Windows PowerShell，而且無法使用商務用 **Skype 系統管理中心**。 
  
### <a name="start-windows-powershell"></a>啟動 Windows PowerShell

> [!NOTE]
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
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>停用圖釋和目前狀態通知，並防止存存的 IMS

- 若要為這些設定建立新策略，請執行：
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  查看 [New-CsClientPolicy Cmdlet](https://technet.microsoft.com/library/mt779155.aspx) 的更多資訊。
    
- 若要將您建立的新政策授予貴組織的所有使用者，請執行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  查看 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的更多資訊。
    
如果您已經建立原則，您可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用至您的使用者。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>在立即資訊中啟用可點按一下的 URL 或超連結

- 若要為這些設定建立新策略，請執行：
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  查看 [New-CsClientPolicy Cmdlet](https://technet.microsoft.com/library/mt779155.aspx) 的更多資訊。
    
- 若要將您建立的新政策授予貴組織的所有使用者，請執行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  查看 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的更多資訊。
    
如果您已經建立原則，您可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用至您的使用者。
  
### <a name="prevent-showing-recent-contacts"></a>防止顯示最近的連絡人

- 若要為這些設定建立新策略，請執行：
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  查看 [New-CsClientPolicy Cmdlet](https://technet.microsoft.com/library/mt779155.aspx) 的更多資訊。
    
- 若要將您建立的新策略授予 Amos Marble，請執行：
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  查看 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的更多資訊。
    
  如果您已經建立原則，您可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用至您的使用者。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對點檔案傳輸](block-point-to-point-file-transfers.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
 
