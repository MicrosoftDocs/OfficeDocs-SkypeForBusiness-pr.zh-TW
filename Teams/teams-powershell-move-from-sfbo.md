---
title: 從商務用 Skype Online Connector 移至 Teams PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從商務用 Skype Online Connector 移至 Teams PowerShell 模組來管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569079"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>從商務用 Skype Online Connector 移至 Teams PowerShell 模組

若要從使用商務用 Skype Online Connector 移至 Teams PowerShell 模組來管理 Teams，您必須更新現有的 PowerShell 腳本。 本文將說明如何執行此工作。

1. 安裝最新的 Teams PowerShell 模組。 有關步驟，請參閱[安裝 Microsoft Teams Powershell。](teams-powershell-install.md)
2. 卸載商務用 Skype Online 連接器。 若要這麼做，請在控制台中，前往程式和功能，選取 **商務用 Skype Online、Windows PowerShell 模組**，然後 **選取卸載**。 
3. 在 PowerShell 腳本中，變更參照自 或 至 ```Import-Module``` 的 ```SkypeOnlineConnector``` 模組 ```LyncOnlineConnector``` 名稱 ```MicrosoftTeams``` 。

    例如，變更 ```Import-Module -Name SkypeOnlineConnector``` 為 ```Import-Module -Name MicrosoftTeams``` 。
4. 使用 Teams PowerShell 模組 2.0 或更高版本時，請將 New-csOnlineSession 變更為 Connect-MicrosoftTeams。 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>相關主題

[安裝 Microsoft Teams Powershell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
