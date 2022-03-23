---
title: Microsoft Teams PowerShell 版本資訊
ms.reviewer: gothambi
author: sumitb18
ms.author: subadjat
manager: pbafna03
ms.date: 12/10/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解 PowerShell 中Teams變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dea6b9d93d3950d4a831fdf669a98e28028f3c41
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711707"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 版本資訊

此頁面提供適用于一般Teams公開預覽版的最新 PowerShell 變更記錄。

## <a name="release-notes"></a>版本資訊

> [!NOTE]
> **-以下版本** 欄中的預覽代表 PowerShell Teams預覽的更新。

| 日期 | 版本 | 更新 |
|------- | -------------------- | ------------------------------ |
| 2022 年 3 月 | [4.0.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/4.0.1-preview) |<li>修正 ErrorAction 常見參數的問題。</li>
| 2022 年 3 月 | [4.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/4.0.0) |<li>本 GA 發行完成所有與組織相關之 Cmdlet 的Teams更新。 新式版本將會陸續推出，因此部分組織會繼續看到舊版的重處理版本。</li><li>發行 [NewSetRemove \| \| ]-CsUserCallingDelegate 和 [GetSet \| ]-CsUserCallingSettings CMdlet 在 GA 中。</li><li>[中斷變更]New-CsVoiceNormalizationRule 除外;其他 Cmdlet 不再支援 InMemory 開關。</li><li>取消使用下列 Cmdlet：ConvertTo-JsonForPSWS， Set-CsUserServicesPolicy， [GetSet \| ]-CsNetworkConfiguration， [SetRemove]-CsTenantNetworkConfiguration， New-CsNetworkMediaBypassConfiguration， [GetGrantNewRemoveSet \| \| \| \| ]-CsTeamsVerticalPackagePolicy，[GetRemoveSet \| \| \| ]-CsVoiceNormalizationRule。</li>
| 2022 年 2 月 | [3.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/3.2.0-preview) |<li>此版本已完成所有與組織相關的 Cmdlet Teams更新。 新式版本將會陸續推出，因此部分組織會繼續看到舊版的重處理版本。</li><li>[中斷變更]New-CsVoiceNormalizationRule 除外;其他 Cmdlet 不再支援 InMemory 開關。</li><li>Connect-MicrosoftTeams提升績效。</li><li>使用首碼Import-Module的修正。</li><li>修正處理 [GetSetRemove \| \| ]-CsOnlineLisPort 中斜線字元 "/" 的埠。</li><li>Cmdlet Test-CsTeamsUnassignedNumberTreatment發行。</li><li>取消使用下列 Cmdlet：ConvertTo-JsonForPSWS， Set-CsUserServicesPolicy， [GetSet \| ]-CsNetworkConfiguration， [SetRemove]-CsTenantNetworkConfiguration， New-CsNetworkMediaBypassConfiguration， [GetGrantNewRemoveSet \| \| \| \| ]-CsTeamsVerticalPackagePolicy， [GetRemoveSet \| \| \| ]-CsVoiceNormalizationRule.</li>
| 2022 年 2 月 | [3.1.1](https://www.powershellgallery.com/packages/MicrosoftTeams/3.1.1) |<li>Import-Module 的改良功能。</li><li>PSListModifier 取消序列化問題已修正。</li>
| 2022 年 1 月 | [3.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.1.0) |<li>重新命名 Cmdlet Get-CsTeamsShiftsConnectionUser Get-CsTeamsShiftsConnectionWfmUser。</li><li>發行新參數 ResultSize、SkipUserPolicies for Get-CsOnlineUser。 </li><li>發行新參數 Get-CsOnlineDialInConferencingUser 的 ResultSize。</li><li>發行新參數：First、NumberAssigned、NumberNotAssigned、PSTNConnectivity、EnterpriseVoiceStatus、CivicAddressId、Get-CsOnlineVoiceUser 的 LocationId。</li>
| 2021 年 12 月 | [3.0.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.1-preview) |<li>發行更新版本的 Grant-CsTeamsFilesPolicy 和 Remove-CsTeamsFilesPolicy。 這些預期會與它們的遠端處理類似。 新式版本將會陸續推出。因此，部分租使用者會看到較舊的重 (版本，直到推出完成) 。</li><li> 發行 [NewSetRemove \| \| ]-CsUserCallingDelegate Cmdlets。 這些 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li><li>發行 [GetRemove \| ]-CsTeamsShiftsConnectionErrorReport Cmdlets。 這些 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li><li>Cmdlet Get-CsTeamsShiftsConnectionOperation發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li><li>Cmdlet New-CsTeamsShiftsConnectionBatchTeamMap發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li><li>Cmdlet Remove-CsTeamsShiftsScheduleRecord發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li>
| 2021 年 11 月 | [3.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0) |<li>[中斷變更] Get-CsOnlineUser Get-CsOnlineVoiceUser：下列變更適用于 TeamsOnly 租使用者：<ul><li>這些 Cmdlet 現在已從較舊版本的實現移轉至較新的 API。</li><li> (使用 -identity 參數) ：對於 TeamsOnly 租使用者，不再與 Teams 相關的屬性已被使用。 某些屬性也重新命名/取代，請參閱 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser?view=skype-ps) 和 [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)。</li><li>Get-CsOnlineUser (-Filter 參數) ：已修改根據 AssignedPlans 和 EnterpriseVoice 篩選的格式設定。 根據 TeamsOnly 使用者的使用狀況 (可篩選屬性) 限制 ，請參閱 [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)。</li><li>這些 Cmdlet 會逐步推出，有些租使用者不會遇到這些變更，直到 CY21 結束推出。</ul></li><li>[中斷變更]Get-CsTenant：在 Teams 中不再相關的屬性已被 TeamsOnly 租使用者所代用—請參閱[Get-CsTenant](/powershell/module/skype/get-cstenant?view=skype-ps)。</li><li> 發行所有 75+ Grant-CsPolicy \<Name\> Cmdlet 的現代化版本， (所有參數集) 。 這些預期會與它們的遠端處理類似。 新式版本將會陸續推出，因此部分租使用者會看到較舊版本的重新 (，直到推出完成) 。</li><li> 發行所有 75+ Remove-CsPolicy \<Name\> Cmdlet 的現代化版本。 這些預期會與它們的遠端處理類似。 新式版本將會陸續推出，因此部分租使用者會看到較舊版本的重新 (，直到推出完成) 。</li><li> 發行 [SetRemove \| ]-CsPhoneNumberAssignment Cmdlets。 這些 Cmdlet 會逐步推出，因此部分租使用者會收到參照現有 Cmdlet 的錯誤訊息， (直到推出完成) 。</li><li> 發行 [SetNew \| ]-CsTeamsEmergencyCallingPolicy Cmdlet 的新參數 EnhancedEmergencyServiceDisclaimer。<li> 發行 [GetAddRemove \| \| ]-TeamChannelUser Cmdlets。</li><li> Cmdlet Export-CsOnlineAudioFile發行。</li><li> 修正 [GetImportRemove \| \| ]-CsOnlineAudioFile Cmdlet 的錯誤處理。</li><li>錯誤處理Get-Team修正。 如果抓取團隊資料失敗，會輸出錯誤訊息。</li><li>修正Connect-MicrosoftTeams - AccessTokens 會增加到期日的差異。</li>
| 2021 年 11 月 | [2.6.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.2-preview) |<li>發行所有 75+ Grant-CsPolicy \<Name\> Cmdlet 的現代化版本， (所有參數集) 。 這些預期會類似其遠端處理對應專案。 新式版本將陸續推出，未外租的租使用者將會看到較舊的遠端處理版本。</li><li>發行所有 75+ Remove-CsPolicy \<Name\> Cmdlet 的現代化版本。 這些預期會類似其遠端處理對應專案。 新式版本將陸續推出，未外租的租使用者將會看到較舊的遠端處理版本。</li><li>Cmdlet Set-CsUserCallingSettings發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li><li>Cmdlet Export-CsOnlineAudioFile發行。</li><li>修正 [GetImportRemove \| \| ]-CsOnlineAudioFile Cmdlet 的錯誤處理。</li>
| 2021 年 10 月 | [2.6.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.1-preview) |<li>發行 [SetRemove \| ]-CsPhoneNumberAssignment Cmdlets。 這些 Cmdlet 將會逐步推出。因此，部分租使用者會收到參照現有 Cmdlet 的錯誤訊息， (推出完成) 。</li><li>發行Get-CsOnlineTelephoneNumberCountryGet-CsOnlineTelephoneNumberType Cmdlet。</li><li>發行 [SetNew \| ]-CsTeamsEmergencyCallingPolicy Cmdlet 的新參數 EnhancedEmergencyServiceDisclaimer。</li><li>Cmdlet Get-CsUserCallingSettings發行。 此 Cmdlet 最終將在 GA 模組中發行。 在預覽模組中發行試用版。</li>
| 2021 年 9 月 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>修正當 MicrosoftTeams 模組成為另一個自訂 PowerShell 模組的巢式模組時，MicrosoftTeams 模組尋找失敗的錯誤。 現在，MicrosoftTeams Cmdlet 可供使用，即使它是另一個模組的巢式模組。</li><li>發行 [GetNewCompleteClear \| \| \| ]-CsOnlineTelephoneNumberOrder Cmdlets。</li><li>發行Get-CsOnlineTelephoneNumberCountryGet-CsOnlineTelephoneNumberType Cmdlet。</li><li>發行這些 Cmdlet 的新參數：Get-CsOnlineApplicationInstance、New-CsExternalAccessPolicy、New-CsTeamsAppSetupPolicy、New-CsTeamsCallingPolicy、New-CsTeamsCallParkPolicy、New-CsTeamsMeetingPolicy、New-CsTeamsMesingPolicy， Set-CsTeamsAppSetupPolicy， Set-CsTeamsCallParkPolicy， Set-CsTeamsGuestMessagingConfiguration， Set-CsTeamsMeetingPolicy， Set-CsTenantFederationConfiguration， Set-CsExternalAccessPolicy， Set-CsTeamsCallingPolicy.</li><li>修正在嘗試登入錯誤之後，以 Connect-MicrosoftTeams登入時發生的失敗。</li><li>更新，讓模組的版本資訊可在 PowerShell 圖庫中針對每個新版本使用。</li>
| 2021 年 9 月 | [2.5.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2-preview) |<li>注意：從此版本開始，版本資訊也會連同模組本身一起發佈于 PowerShell 圖庫中，以減少版本資訊可用性的延遲。</li><li>發行 [GetSetGrantNewRemove \| \| \| \| ]-CsTeamsEnhancedEncryptionPolicy Cmdlets。</li><li>移除 [GetSetNewRemove \| \| \| ]-CsTenantBlockedNumberExceptionPattern Cmdlet。</li><li>修正當模組Microsoft Teams另一個自訂 PowerShell 模組的巢式模組時，模組的尋找失敗的錯誤。 現在，Microsoft Teams Cmdlet 可供使用，即使它是另一個模組的巢式模組。</li><li>發行 [GetNewCompleteClear \| \| \| ]-CsOnlineTelephoneNumberOrder Cmdlets。</li><li>發行Get-CsOnlineTelephoneNumberCountryGet-CsOnlineTelephoneNumberType Cmdlet。</li><li>修正在嘗試錯誤之後以 Connect-MicrosoftTeams重新嘗試登錄時發生的失敗。</li><li>修正Add-TeamChannelUserRemove-TeamChannelUser通道失敗的問題。</li>
| 2021 年 8 月 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>使用者的 Access Token 登入Connect-MicrosoftTeams現在會使用統一權杖陣列，而不是每個特定資源權杖的個別參數。 您可以在這裡找到更多詳細資料：[連線-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams)。</li><li>已修正雲端shell Connect-MicrosoftTeams登入失敗的問題。 現在預設使用使用者的登入身分識別，而不是提示重新驗證。</li><li>TeamsUnasignedNumberTreatment Cmdlet 現已提供。</li><li>Get-CsOnlineDialInConferencingBridge Cmdlet Set-CsOnlineDialInConferencingBridge從較舊的實現移轉至較新的 API。</li><li>系統僅發行Get-CsTenantGet-CsOnlineUser (-identity 參數) 更新版本。 它們不會再發出已棄用的屬性，而且與它們的遠端處理屬性相比，有一些格式變更。</li><li>注意：New-Team相關更新已從 2.5.0 還原，且已提供先前的版本，以避免任何中斷變更。</li>|
| 2021 年 7 月 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>現在可以使用授予 Cmdlet 變更。</li><li>新的 Voice 相關 Cmdlet 會發行。</li><li>移除 -Cs* Cmdlet 的憑證指紋驗證。</li><li>記錄所有 Cmdlet 檔案的記錄修正程式。</li><li>修正 *TeamChannelUser Cmdlet 的問題。</li>|
| 2021 年 6 月 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>僅預覽更新版本的 Get-CsTenant、Get-CsOnlineUser (僅包含 -identity 參數) 、Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile 的版本。</li><li>現代化版本的 Get-CsOnlineDialInConferencingLanguagesSupported 和 Import-CsOnlineAudioFile 預期會類似/相同于其遠端處理版本。</li><li>使用 -identity 參數Get-CsTenantGet-CsOnlineUser (更新版本) 不會發出已使用的屬性。</li><li>使用 -identity 參數執行Get-CsTenantGet-CsOnlineUser (更新版本) 與遠端處理計數器元件相比，其格式設定會有些變更。</li><li>發行 [GetSetGrantNewRemove \| \| \| \| ]-CsTeamsAudioConferencingPolicy Cmdlets。</li><li>發行Get-CsOnlineAudioFileRemove-CsOnlineAudioFile Cmdlet。</li><li>Set-TeamTargetingHierarchy、Remove-TeamTargetingHierarchy、Get-TeamTargetingHierarchyStatus現在可供GCC使用。</li><li>修正由 Get-TeamTargetingHierarchyStatus 命令所Get-TeamTargetingHierarchyStatus端點。</li>|
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>支援 AccessToken 使用 連線-MicrosoftTeams 登入。 已新增 -AccessTokens 參數，接受權杖陣列。 使用 AccessTokens Teams時，需要 MSGraph 和 Teams資源權杖。</li><li>已移除 AadAccessToken 和 MsAccessToken 參數。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>從 更新。NETCore 2.1 到 3.1</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域</li><li>整合式 Windows 驗證的修正程式，以使用 -AccountId Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy Cmdlet 現已提供</li><li>許多命令的輸入參數和輸出格式更新</li><li>修正重處理命令時出現的大型延遲問題</li><li>GA 自訂套件功能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>整合式驗證Windows -AccountId 與 microsoftTeams 連線的修正。</li><li>新增 Cmdlet 以取得可發送給使用者的變更通知事件總數詳細資料。</li><li>新增 Cmdlet 以取得使用者和群組的多地理位置區域。</li><li>處理傳遞到 TeamsEnvironment 名稱的值是區分大小寫的。 這個問題已經修正。</li><li>模組內遠端會話管理的主要要素，以協助進行單次測試。 租使用者系統管理員不應有功能變更。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>已修正某些重排 Cmdlet (例如 Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMesingPolicy 等) 的輸出格式。</li><li>已更新策略管理 Cmdlet 的參數清單。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>使用 MSAL 進行驗證&授權</li> <li>Connect-MicrosoftTeams是所有 Cmdlet 的切入點。</li><li>不再提供 New-csOnlineSession。 它已被 連線 MicrosoftTeams 取代。</li><li>不再需要 Enable-csonlinesionforreconnection。 此功能已在 PowerShell 模組Teams中執行。</li> <li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>Cmdlet Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄與調試選項 </li> <li>新增範本管理 Cmdlet</li> <li>已取消New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>新增範本管理 Cmdlet</li><li>Cmdlet 的 Mezzo 和批次Get-Team增強功能</li> <li>改善現有 Cmdlet 的記錄與調試選項 </li> <li>已重構的策略套件 Cmdlet</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>更新至 New-team Cmdlet，增加重試和睡眠持續時間</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>線上整合商務用 Skype更新</li><li>修正重複提示Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>新增自訂策略套件 Cmdlet</li><li>目標階層上傳命令的修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>使用 MSAL 進行驗證&授權</li><li>已重做群組原則套件 Cmdlet 並新增群組套件指派</li><li>重新建立目標階層上傳命令，以使用非同步模型</li> <li>當使用者不使用 -credential 參數時，在初始驗證期間，系統會提示使用者兩次。 使用者可以使用 -credential 參數傳遞認證，以避免重複提示。 此行為將在下一個版本中修正。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>商務用 Skype線上連接器整合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>新增 [群組原則指派 Cmdlet](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3 預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>商務用 Skype線上連接器整合<li>Get-Team優化<li>增強的可靠性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>新增 Cmdlet 預載入<li>.NET Framework優化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 和程式集簽署<li>新增Get-CsPolicyPackage<li>新增Get-CsUserPolicyPackage<li>新增Get-CsUserPolicyPackageRecommendation<li>新增Grant-CsUserPolicyPackage<li>新增New-CsBatchPolicyPackageAssignmentOperation<li>新增Set-TeamArchivedState<li>新增Set-TeamPicture<li>已移除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新增New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team優化</li>  |

## <a name="related-topics"></a>相關主題

[Teams PowerShell 概觀](teams-powershell-overview.md)

[安裝 powerShell Teams PowerShell](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro)
