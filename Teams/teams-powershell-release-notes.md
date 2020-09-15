---
title: Microsoft 團隊 PowerShell 版本資訊
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
description: 瞭解團隊 PowerShell 中的最新變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 175b5120ad981ba695f02f7c6403c9254e266501
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814412"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft 團隊 PowerShell 版本資訊

此頁面提供一般可用性和公開預覽版發行的最新團隊 PowerShell 變更記錄。

## <a name="release-notes"></a>版本資訊

> [!NOTE]
> **-** [版本] 資料行中的預覽代表 [團隊 PowerShell 公用預覽] 的更新。

| 為止 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2020年9月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>商務用 Skype Online 連接器整合</li> |
| 2020年9月 | [1.1.5-預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>商務用 Skype Online 連接器整合</li> |
| 2020年7月 | [類庫](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>已新增 [群組原則指派 Cmdlet](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020年6月 | [1.1.3-預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>商務用 Skype Online 連接器整合<li>取得團隊優化<li>增強的可靠性</li> |
| 2020年6月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>已新增 Cmdlet 預載入<li>.Net Framework 優化</li>   |
| 2020年4月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>驗證碼與程式集簽名<li>已新增取得 CsPolicyPackage<li>已新增取得 CsUserPolicyPackage<li>已新增取得 CsUserPolicyPackageRecommendation<li>已新增授與 CsUserPolicyPackage<li>新增 CsBatchPolicyPackageAssignmentOperation<li>已新增設定 TeamArchivedState<li>已新增設定 TeamPicture<li>已移除取得 TeamHelp</li>  |
| 2020年3月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新增 CsBatchPolicyAssignmentOperation</li> |
| 2020年2月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>取得團隊優化</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 可用性

> [!NOTE]
> 下表中的清單只包含本身屬於團隊 PowerShell 模組的 Cmdlet。 [[商務用 kype For Business Online 連接器] 模組](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) 中的團隊 Cmdlet 不會顯示。 不過，因為這些 Cmdlet 會以本機方式遷移到團隊 PowerShell 中，所以我們會將它們新增到此資料表中。

| Cmdlet | 可在公用預覽中使用 | 正式推出 |
| -| -- | --|
| [附加 TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 是 | **否** |
| [附加 TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 是 | 是 |
| [附加 TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 是 | **否**|
| [連接-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 是 | 是 |
| [中斷連線-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 是 | 是 |
| [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | 是 | **否** |
| [CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | 是 | 是 |
| [CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | 是 | 是 |
| [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | 是 | 是 |
| [CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | 是 | 是 |
| [取得團隊](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | 是 | 是 |
| [TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | 是 | 是|
| [TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | 是 | **否** |
| [TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | 是 | 是 |
| [TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | 是 | 是 |
| [TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [授與 CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | 是 | 是 |
| [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | 是 | 是 |
| [新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [新-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | 是 | 是 |
| [新-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | 是 | 是 |
| [新團隊](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | 是 | 是 |
| [新-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | 是 | 是 |
| [新-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | 是 | 是 |
| [移除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | 是 | 是 |
| [移除團隊](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | 是 | 是 |
| [移除-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | 是 | 是 |
| [移除-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | 是 | **否** |
| [移除-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | 是 | 是 |
| [移除-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | 是 | **否** |
| [移除-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | 是 | **否**|
| [移除-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | 是 | 是 |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | 是 | **否** |
| [集-小組](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | 是 | 是 |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | 是 | 是 |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | 是 | 是 |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | 是 | 是 |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | 是 | 是 |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | 是 | **否** |
| [更新-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | 是 | **否** |

## <a name="related-topics"></a>相關主題

[團隊 PowerShell 概覽](teams-powershell-overview.md)

[安裝團隊 PowerShell](teams-powershell-install.md)

[使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)

[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
