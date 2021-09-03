---
title: 從線上連接器商務用 Skype移Teams PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從線上連接器商務用 Skype到 Teams PowerShell 模組來管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866355"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>從線上連接器商務用 Skype移Teams PowerShell 模組

TeamsPowerShell 模組提供一組完整的 Cmdlet，Teams直接從 PowerShell 命令列管理資料。 系統管理員不需要Skype商務用 Online 連接器，Teams管理。

> [!NOTE]
> Teams已于 2021 年 3 月 16 (MC244740 郵件中心張貼公告通知系統管理員;MC250940 于 2021 年 4 月 16 日) 此變更。
>
> TeamsPowerShell 模組使用新式驗證，Windows遠端系統管理 (WinRM) 用戶端必須配置為允許基本驗證。 請參閱[下載並安裝Windows PowerShell，](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)以取得如何啟用 WinRM for Basic 驗證的指示。

## <a name="how-to-migrate"></a>如何遷移

從使用線上連接器商務用 Skype移Teams PowerShell 模組非常簡單。 下列步驟說明如何執行此操作。

1. 安裝最新的 PowerShell Teams模組。 有關步驟，請參閱[在 PowerShell Microsoft Teams安裝](teams-powershell-install.md)。

2. 卸載Skype商務用 Online 連接器。 若要這麼做，請在控制台中，前往程式和功能，選取 商務用 Skype **線上，Windows PowerShell模組**，**然後選取卸載**。

3. 在 PowerShell 腳本中，變更從 ```Import-Module```

    `SkypeOnlineConnector` 或 `LyncOnlineConnector` `MicrosoftTeams` to 。

    例如，變更 `Import-Module -Name SkypeOnlineConnector` 為 `Import-Module -Name MicrosoftTeams` 。

4. 使用 Teams PowerShell 模組 2.0 或更新版本時，請更新您參照的 `New-CsOnlineSession` 腳本 `Connect-MicrosoftTeams` 。 `Import-PsSession`不再需要建立線上遠端 powerShell 會話商務用 Skype，因為使用 時隱含完成 `Connect-MicrosoftTeams` 。

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

[在 PowerShell Microsoft Teams安裝](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[TeamsPowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)
