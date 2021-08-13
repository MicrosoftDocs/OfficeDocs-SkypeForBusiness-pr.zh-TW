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
description: 瞭解如何從線上連接器商務用 Skype到 powerShell 模組Teams以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9dd03b414eba2ebc10dcfdbbb4e0ea2712fff73ca2cb0eb643aa132936ab1470
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299003"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>從線上連接器商務用 Skype移Teams PowerShell 模組

TeamsPowerShell 模組提供一組完整的 Cmdlet，Teams直接從 PowerShell 命令列管理資料。 系統管理員不需要Skype商務用 Online 連接器進行Teams管理。

> [!NOTE]
> Teams已于 2021 年 3 月 16 (MC244740 郵件中心張貼公告通知系統管理員;MC250940 于 2021 年 4 月 16 日) 此變更。
>
> TeamsPowerShell 模組使用新式驗證，Windows遠端系統管理 (WinRM) 用戶端必須配置為允許基本驗證。 請參閱[下載並安裝Windows PowerShell，](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)以取得如何啟用 WinRM for Basic 驗證的指示。

> [!WARNING]
> 商務用 Skype線上連接器連線將于 2021 年 5 月 17 日拒絕。 如需移至 PowerShell 模組的協助和支援，Teams Microsoft 支援服務。

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

## <a name="online-support"></a>線上支援

線上啟動服務要求以節省時間。 我們會協助您尋找解決方案，或將您連至技術支援。

1.  請前往 系統管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。 如果您收到一則訊息，指出您沒有存取此頁面或執行此動作的許可權，表示您不是系統管理員。神秘擁有我企業中的系統管理員許可權？

2.  選取需要 **協助** 嗎？按鈕。

3.  在需要 **協助**？窗格，告訴我們您需要哪些協助，然後按 Enter。

4.  如果結果沒有説明，請選取 連絡人 **支援**。

5.  輸入問題的描述、確認您的連絡人號碼和電子郵件地址、選取您偏好的連絡人方法，然後選取 **連絡人給我**。 預期等候時間會以需要協助？窗 格。

## <a name="related-topics"></a>相關主題

[在 PowerShell Microsoft Teams安裝](teams-powershell-install.md)

[使用 powerShell Teams管理Teams管理](teams-powershell-managing-teams.md)

[TeamsPowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)
