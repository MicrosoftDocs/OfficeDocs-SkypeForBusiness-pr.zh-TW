---
title: Microsoft Teams PowerShell 版本資訊
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解 Teams PowerShell 中的最新變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22688a6e4fbeb11e09eb0c2765a9de1408ce6484
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756169"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 版本資訊

此頁面提供適用于公開發行和公開預覽版的最新 Teams PowerShell 變更記錄。

## <a name="release-notes"></a>版本資訊

> [!NOTE]
> **-以下版本** 欄中的預覽代表 Teams PowerShell 公開預覽的更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 進行驗證&授權</li><li>已重新群組原則套件 Cmdlet 並新增群組套件指派</li><li>Cmdlet 的Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄與錯誤選項 </li> <li>新增範本管理 Cmdlet</li> <li>已New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>新增範本管理 Cmdlet</li><li>Cmdlet 的 Mezzo 和批次Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄與錯誤選項 </li> <li>已重做要素的 Policy Package Cmdlet</li>|
| 2020 年 12 月 | [1.1.10 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新至 New-team Cmdlet 且提高重試和睡眠持續時間</li>|
| 2020 年 12 月 | [1.1.9 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>商務用 Skype Online 整合的更新</li><li>使用 Teams 修正重複Connect-Microsoft提示</li>|
| 2020 年 11 月 | [1.1.8 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>新增自訂策略套件 Cmdlet</li><li>目標階層上傳命令的修正</li>|
| 2020 年 11 月 | [1.1.7 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 進行驗證&授權</li><li>已重新群組原則套件 Cmdlet 並新增群組套件指派</li><li>已重新建立目標階層的上傳命令，以使用非同步模型</li> <li>初始驗證期間，使用者不使用 -credential 參數時，系統會提示使用者兩次。 使用者可以使用 -credential 參數傳遞認證，以避免重複的提示。 此行為將在下一次發行中修正。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>商務用 Skype Online Connector 整合</li> |
| 2020 年 9 月 | [1.1.5 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>商務用 Skype Online Connector 整合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>已 [新增群組原則指派 Cmdlet](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>商務用 Skype Online Connector 整合<li>Get-Team優化<li>增強的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>已新增 Cmdlet 預先載入<li>.Net Framework 優化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 和程式集簽署<li>已新增Get-CsPolicyPackage<li>已新增Get-CsUserPolicyPackage<li>已新增Get-CsUserPolicyPackageRecommendation<li>已新增Grant-CsUserPolicyPackage<li>已新增New-CsBatchPolicyPackageAssignmentOperation<li>已新增Set-TeamArchivedState<li>已新增Set-TeamPicture<li>已移除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>已新增New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team優化</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 可用性

> [!NOTE]
> 下表中的清單僅包含原始為 Teams PowerShell 模組一部分的 Cmdlet。 不會顯示商務用 S[kype Online 連接器模組](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) 中的 Teams Cmdlet。 不過，當這些 Cmdlet 以原生移轉至 Teams PowerShell 時，我們會將它們新增到這個資料表中。

| Cmdlet | 在公開預覽中提供 | 可在 GA 中使用 |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 是 | 是 |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 是 | **否**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 是 | 是 |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 是 | 是 |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | 是 | **否** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | 是 | 是 |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | 是 | 是 |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | 是 | 是 |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | 是 | 是 |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | 是 | 是 |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | 是 | 是|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | 是 | 是 |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | 是 | 是 |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | 是 | 是 |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession?view=skype-ps) | 是 | 是 |
| [新團隊](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | 是 | 是 |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps) | 是 | 是 |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | 是 | 是 |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [移除小組](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | 是 | 是 |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | 是 | 是 |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | 是 | **否** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | 是 | 是 |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#remove-your-hierarchy) | 是 | **否**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | 是 | 是 |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | 是 | **否** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | 是 | 是 |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | 是 | 是 |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | 是 | 是 |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | 是 | 是 |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamsapp?view=teams-ps) | 是 | 是 |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#apply-your-hierarchy) | 是 | **否** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamsappinstallation?view=teams-ps) | 是 | **否** |

## <a name="related-topics"></a>相關主題

[Teams PowerShell 概觀](teams-powershell-overview.md)

[安裝 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
