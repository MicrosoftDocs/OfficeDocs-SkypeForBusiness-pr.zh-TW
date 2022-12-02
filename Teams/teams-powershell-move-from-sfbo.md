---
title: 從 商務用 Skype Online Connector 移轉到 Teams PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從 商務用 Skype Online Connector 移至 Teams PowerShell 模組以管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242287"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>從 商務用 Skype Online Connector 移轉到 Teams PowerShell 模組

Teams PowerShell 模組提供一組完整的 Cmdlet，可直接從 PowerShell 命令列管理 Teams。 系統管理員不需要商務用 Skype Online Connector 來管理 Teams。

> [!NOTE]
> Teams 系統管理員在 2021 年 3 月 16 日 (MC244740 中收到訊息中心通知;2021 年 4 月 16 日的 MC250940) 此變更。
>
> Teams PowerShell 模組使用新式驗證，但必須設定基本的 Windows 遠端系統管理 (WinRM) 用戶端，才能允許基本驗證。 如需如何啟用 WinRM 基本驗證的指示，請參閱[下載並安裝Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)。

## <a name="how-to-migrate"></a>如何移轉

從使用 商務用 Skype Online Connector 移轉到 Teams PowerShell 模組很簡單。 下列步驟說明如何執行此動作。

1. 安裝最新的 Teams PowerShell 模組。 如需相關步驟，請[參閱安裝 teams PowerShell Microsoft](teams-powershell-install.md)。

2. 卸載商務用 Skype Online Connector。 若要這麼做，請在 主控台 中，移至 [**程式和功能]**，選 **取 [商務用 Skype Online]、[Windows PowerShell模組**]，然後選取 [**卸載]**。

3. 在 PowerShell 腳本中，變更參照 ```Import-Module``` 的模組名稱

    `SkypeOnlineConnector` 或 `LyncOnlineConnector` 到 `MicrosoftTeams` 。

    例如，變更 `Import-Module -Name SkypeOnlineConnector` 為 `Import-Module -Name MicrosoftTeams` 。

4. 使用 Teams PowerShell 模組 2.0 或更新版本時，請更新參照 `New-CsOnlineSession` `Connect-MicrosoftTeams` 的腳本。 `Import-PsSession`不再需要建立商務用 Skype Online 遠端 PowerShell 會話，因為使用 `Connect-MicrosoftTeams` 時會隱含。

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>相關主題

[安裝 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro)
