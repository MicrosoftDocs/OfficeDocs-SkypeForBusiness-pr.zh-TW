---
title: Microsoft TeamsPowerShell 版本資訊
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
description: 瞭解 PowerShell 中Teams變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 986aebf2ae86e463976f4480fbd2f7dde440f0a1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684370"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft TeamsPowerShell 版本資訊

此頁面提供適用于一般Teams公開預覽版的最新 PowerShell 變更記錄。

## <a name="release-notes"></a>版本資訊

> [!NOTE]
> **-以下版本** 欄中的預覽代表 PowerShell Teams預覽的更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>支援 AccessToken 使用 連線 -MicrosoftTeams 登入。 已新增 -AccessTokens 參數，接受權杖陣列。 使用 AccessTokens Teams時，需要 MSGraph 和 Teams資源權杖。</li><li>已移除 AadAccessToken 和 MsAccessToken 參數。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>從 更新。NETCore 2.1 到 3.1</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域</li><li>整合式 Windows 驗證的修正程式，以使用 -AccountId Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy Cmdlet 現已提供</li><li>許多命令的輸入參數和輸出格式更新</li><li>修正重處理命令時的大型延遲問題</li><li>GA 自訂套件功能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>整合式驗證Windows -AccountId 與 microsoftTeams 連線的修正。</li><li>新增 Cmdlet 以取得可發送給使用者的變更通知事件總數詳細資料。</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域。</li><li>處理傳遞到 TeamsEnvironment 名稱的值時，會區分大小寫。 這個問題已經修正。</li><li>模組內遠端會話管理的主要要素，以協助進行單次測試。 租使用者系統管理員不應有功能變更。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>已修正現有 Cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMesagingPolicy 等) 的格式。</li><li>已更新策略管理 Cmdlet 的參數清單。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 進行驗證&授權</li> <li>Connect-MicrosoftTeams是所有 Cmdlet 的切入點。</li><li>不再提供 New-csOnlineSession。 它已被 連線 MicrosoftTeams 取代。</li><li>不再需要 Enable-csonlinesionforreconnection。 此功能已在 PowerShell 模組Teams中執行。</li> <li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>Cmdlet Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄及調試選項 </li> <li>新增範本管理 Cmdlet</li> <li>已取消New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>新增範本管理 Cmdlet</li><li>Cmdlet 的 Mezzo 和批次處理增強功能Get-Team Cmdlet</li> <li>改善現有 Cmdlet 的記錄及調試選項 </li> <li>已重構的策略套件 Cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新至 New-team Cmdlet，增加重試和睡眠持續時間</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>線上整合商務用 Skype更新</li><li>修正重複提示與Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>新增自訂策略套件 Cmdlet</li><li>目標階層上傳命令的修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 進行驗證&授權</li><li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>重新建立目標階層上傳命令，以使用非同步模型</li> <li>當使用者不使用 -credential 參數時，在初始驗證期間，系統會提示使用者兩次。 使用者可以使用 -credential 參數傳遞認證，以避免重複提示。 此行為將在下一次發行中修正。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>新增 [群組原則指派 Cmdlet](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>商務用 Skype線上連接器整合<li>Get-Team優化<li>增強的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>新增 Cmdlet 預載入<li>.Net Framework 優化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 和程式集簽署<li>新增Get-CsPolicyPackage<li>新增Get-CsUserPolicyPackage<li>新增Get-CsUserPolicyPackageRecommendation<li>新增Grant-CsUserPolicyPackage<li>新增New-CsBatchPolicyPackageAssignmentOperation<li>新增Set-TeamArchivedState<li>新增Set-TeamPicture<li>已移除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新增New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team優化</li>  |

## <a name="related-topics"></a>相關主題

[TeamsPowerShell 概觀](teams-powershell-overview.md)

[安裝 powerShell Teams PowerShell](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)
