---
title: Microsoft TeamsPowerShell 版本資訊
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 10/25/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解 PowerShell 中Teams變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 232a41dce111b0d913c3888c0e00140bf2b904c0
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579613"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft TeamsPowerShell 版本資訊

此頁面提供適用于一般Teams公開預覽版的最新 PowerShell 變更記錄。

## <a name="release-notes"></a>版本資訊

> [!NOTE]
> **-以下版本** 欄中的預覽代表 PowerShell Teams預覽的更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2021 年 10 月 | [2.6.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.1-preview) |<li>發行 [設定 \| Remove]-CsPhoneNumberAssignment Cmdlet。 這些 Cmdlet 將會逐步推出。因此，有些租使用者會收到一則錯誤訊息，指出他們可以使用的現有 Cmdlet (直到推出完成) 。</li><li>發行Get-CsOnlineTelephoneNumberCountry和Get-CsOnlineTelephoneNumberType Cmdlet。</li><li>發行 [Set \| New]-CsTeamsEmergencyCallingPolicy Cmdlet 的新參數 EnhancedEmergencyServiceDisclaimer。</li><li>Cmdlet Get-CsUserCallingSettings發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li>
| 2021 年 9 月 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>修正當 MicrosoftTeams 模組成為另一個自訂 PowerShell 模組的巢式模組時，MicrosoftTeams 模組尋找失敗的錯誤。 現在，MicrosoftTeams Cmdlet 可供使用，即使它是另一個模組的巢式模組。</li><li>發行 [取得 \| 全新 \| 完整 \| 清除]-CsOnlineTelephoneNumberOrder Cmdlets。</li><li>發行Get-CsOnlineTelephoneNumberCountry和Get-CsOnlineTelephoneNumberType Cmdlet。</li><li>發行這些 Cmdlet 的新參數： Get-CsOnlineApplicationInstance， New-CsExternalAccessPolicy， New-CsTeamsAppSetupPolicy， New-CsTeamsCallingPolicy， New-CsTeamsCallParkPolicy， New-CsTeamsMeetingPolicy， New-CsTeamsMesingPolicy， Set-CsTeamsAppSetupPolicy， Set-CsTeamsCallParkPolicy， Set-CsTeamsGuestMessagingConfiguration， Set-CsTeamsMeetingPolicy， Set-CsTenantFederationConfiguration， Set-CsExternalAccessPolicy， Set-CsTeamsCallingPolicy.</li><li>修正在嘗試登入錯誤之後，以 Connect-MicrosoftTeams登入時發生的失敗。</li><li>更新，讓模組的版本資訊可在 PowerShell 圖庫中針對每個新版本使用。</li>
| 2021 年 9 月 | [2.5.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2-preview) |<li>注意：從此版本開始，版本資訊也會連同模組本身一起發佈于 PowerShell 圖庫中，以減少版本資訊可用性的延遲。</li><li>版本 [取得 \| Set Grant New \| \| \| Remove]-CsTeamsEnhancedEncryptionPolicy Cmdlets。</li><li>移除 [取得 \| 設定 \| 新 \| 移除]-CsTenantBlockedNumberExceptionPattern Cmdlet。</li><li>修正當模組Microsoft Teams成為另一個自訂 PowerShell 模組的巢式模組時失敗的錯誤。 現在，Microsoft Teams Cmdlet 可供使用，即使它是另一個模組的巢式模組。</li><li>發行 [取得 \| 全新 \| 完整 \| 清除]-CsOnlineTelephoneNumberOrder Cmdlets。</li><li>發行Get-CsOnlineTelephoneNumberCountry和Get-CsOnlineTelephoneNumberType Cmdlet。</li><li>修正在嘗試錯誤之後以 Connect-MicrosoftTeams重新嘗試登錄時發生的失敗。</li><li>修正Add-TeamChannelUserRemove-TeamChannelUser通道失敗的問題。</li>
| 2021 年 8 月 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>使用者的 Access Token 登入Connect-MicrosoftTeams現在會使用統一權杖陣列，而不是每個特定資源權杖的個別參數。 您可以在這裡找到更多 [詳細資料](/powershell/module/teams/connect-microsoftteams)。</li><li>已修正雲端shell 中Connect-MicrosoftTeams登入失敗的問題。 現在預設使用使用者的登入身分識別，而不是提示重新驗證。</li><li>TeamsUnasignedNumberTreatment Cmdlet 現已提供。</li><li>Get-CsOnlineDialInConferencingBridge Cmdlet Set-CsOnlineDialInConferencingBridge從較舊的實現移轉至較新的 API。</li><li>系統僅發行Get-CsTenantGet-CsOnlineUser (-identity 參數的) 更新版本。 它們不會再發出已棄用的屬性，而且與它們的遠端處理屬性相比，有一些格式變更。</li><li>注意：New-Team相關更新已從 2.5.0 還原，且已提供先前的版本，以避免任何中斷變更。</li>|
| 2021 年 7 月 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>現在可以使用授予 Cmdlet 變更。</li><li>新的 Voice 相關 Cmdlet 會發行。</li><li>移除 -Cs* Cmdlet 的憑證指紋驗證。</li><li>記錄所有 Cmdlet 檔案的記錄修正程式。</li><li>修正 *TeamChannelUser Cmdlet 的問題。</li>|
| 2021 年 6 月 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>僅預覽更新版本的 Get-CsTenant、Get-CsOnlineUser (僅包含 -identity 參數) 、Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile 的版本。</li><li>現代化版本的 Get-CsOnlineDialInConferencingLanguagesSupported和Import-CsOnlineAudioFile預期會與它們的遠端處理版本類似/相同。</li><li>使用 -identity 參數Get-CsTenantGet-CsOnlineUser (更新版本) 不會散發已使用的屬性。</li><li>使用 -identity 參數執行Get-CsTenantGet-CsOnlineUser (更新版本) 與遠端處理計數器元件相比，其格式設定會有些變更。</li><li>版本 [取得 \| 設定 \| 授予 \| 新 \| 移除]-CsTeamsAudioConferencingPolicy Cmdlets。</li><li>發行Get-CsOnlineAudioFile和Remove-CsOnlineAudioFile Cmdlet。</li><li>Set-TeamTargetingHierarchy、Remove-TeamTargetingHierarchy、Get-TeamTargetingHierarchyStatus現在可供GCC使用。</li><li>修正由 Get-TeamTargetingHierarchyStatus 命令所Get-TeamTargetingHierarchyStatus端點。</li>|
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>支援使用 MicrosoftTeams 連線 AccessToken 登入。 已新增 -AccessTokens 參數，接受權杖陣列。 使用 AccessTokens Teams時，需要 MSGraph 和 Teams資源權杖。</li><li>已移除 AadAccessToken 和 MsAccessToken 參數。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>從 更新。NETCore 2.1 到 3.1</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域</li><li>整合式 Windows 驗證的修正，以使用 -AccountId Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy Cmdlet 現已提供</li><li>許多命令的輸入參數和輸出格式更新</li><li>修正重處理命令時出現的大型延遲問題</li><li>GA 自訂套件功能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>整合式驗證Windows -AccountId 與 microsoftTeams 連線的修正。</li><li>新增 Cmdlet 以取得可發送給使用者的變更通知事件總數詳細資料。</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域。</li><li>處理傳遞至 TeamsEnvironment 名稱的值是區分大小寫的。 這個問題已經修正。</li><li>模組內遠端會話管理的主要要素，以協助進行單次測試。 租使用者系統管理員不應有功能變更。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>已修正某些重排 Cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMesingPolicy 等) 的輸出格式。</li><li>已更新策略管理 Cmdlet 的參數清單。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 進行驗證&授權</li> <li>Connect-MicrosoftTeams是所有 Cmdlet 的切入點。</li><li>不再提供 New-csOnlineSession。 它已被 連線 MicrosoftTeams 取代。</li><li>不再需要 Enable-csonlinesionforreconnection。 此功能已在 PowerShell 模組Teams中執行。</li> <li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>Cmdlet Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄與調試選項 </li> <li>新增範本管理 Cmdlet</li> <li>已取消New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>新增範本管理 Cmdlet</li><li>Cmdlet 的 Mezzo 和批次處理增強功能Get-Team Cmdlet</li> <li>改善現有 Cmdlet 的記錄與調試選項 </li> <li>已重構的策略套件 Cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新至 New-team Cmdlet，增加重試和睡眠持續時間</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>線上整合商務用 Skype更新</li><li>修正重複提示與Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>新增自訂策略套件 Cmdlet</li><li>目標階層上傳命令的修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 進行驗證&授權</li><li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>重新建立目標階層上傳命令，以使用非同步模型</li> <li>當使用者不使用 -credential 參數時，在初始驗證期間，系統會提示使用者兩次。 使用者可以使用 -credential 參數傳遞認證，以避免重複提示。 此行為將在下一個版本中修正。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>新增 [群組原則指派 Cmdlet](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>商務用 Skype線上連接器整合<li>Get-Team優化<li>增強的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>新增 Cmdlet 預載入<li>.NET Framework優化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 和程式集簽署<li>新增Get-CsPolicyPackage<li>新增Get-CsUserPolicyPackage<li>新增Get-CsUserPolicyPackageRecommendation<li>新增Grant-CsUserPolicyPackage<li>新增New-CsBatchPolicyPackageAssignmentOperation<li>新增Set-TeamArchivedState<li>新增Set-TeamPicture<li>已移除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新增New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team優化</li>  |

## <a name="related-topics"></a>相關主題

[TeamsPowerShell 概觀](teams-powershell-overview.md)

[安裝 powerShell Teams PowerShell](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro)
