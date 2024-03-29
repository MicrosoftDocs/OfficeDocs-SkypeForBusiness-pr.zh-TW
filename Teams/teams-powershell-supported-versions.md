---
title: Teams PowerShell 模組 - 支援的版本
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解用於管理 Microsoft Teams 的 Teams PowerShell 模組支援的版本。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28e16c248957518ca16eb3eff7e082ebe6bd9bd
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590320"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模組 - 支援的版本

4.x.x 系列或更新版本中的 Microsoft Teams PowerShell 模組 (TPM) 版本是目前唯一支援的版本。 自 2022 年 6 月 15 日起，所有舊版都會在商業環境中完全停用，&將會停止 (訊息中心文章以供參考 - MC350371) 。 

建議您更新至最新的 Teams PowerShell 模組版本。


## <a name="important-notes"></a>重要筆記

- 您可以在 [Teams PowerShell 版本資訊中找到所有 Teams PowerShell 模組版本的版本資訊](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模組，您應該使用相同的方法來安裝模組。 例如，如果您原本使用 Install-Module，則應該使用 [Update-Module](/powershell/module/powershellget/update-module) 來取得最新版本。

  ```powershell
  Update-Module MicrosoftTeams
  ```

- 如果從 Teams PowerShell 模組版本 1.1.6 更新，請將腳本更新為使用，而非 `New-CsOnlineSession` 。 `Connect-MicrosoftTeams`

- 在更新期間，建議您不要同時使用 TPM 4.x.x/3.x.x.x 與 3.0.0 之前的版本。 例如，不建議將版本 4.x.x & 2.6.0 用於同一個組織中不同的系統管理作業。

- 相關變更
  - 更新在 TPM 3.x.x 及更新版本中Get-CsOnlineUser & Get-CsOnlineVoiceUser – [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)[Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser)  &  (訊息中心文章 - MC340774) 中的更多詳細資料。

  - 電話號碼指派的變更 -[在 Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance)  &  [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (訊息中心文章 - MC316139) 中的更多詳細資料。

  - Get-CsTenant中的參數變更 - [Get-CsTenant](/powershell/module/skype/get-cstenant) (訊息中心文章 - MC365397) 中的詳細資料。
  
  - 如果您的腳本使用 New/Set of Policy 或 Configuration Cmdlet 搭配 PSListModifier 類型參數，建議您使用最新版本的 (4.2.0 或更新版本) 。 訊息中心文章供參考 - MC397428。

  - [新增|Get]-CsCloudCallDataConnection Cmdlet 現在支援版本 4.6.0 或更新版本， (訊息中心文章 - MC408993) 。

- 使用 TPM 4.x.x 或更新版本時，建議不要使用 [以下](#deprecated-cmdlets)所述任何已取代或不支援的 Cmdlet。

## <a name="deprecated-cmdlets"></a>已取代的 Cmdlet

- 以下列出一些最近已取代的 Cmdlet。 您可以在個別的公開檔中找到相同的詳細資料。
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)， [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)， [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)， [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)、Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities)， [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas)， [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)， [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)， [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)， [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)， [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)， [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)， [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation)， [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation)， [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)、 [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy)、 [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy)、 [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- 下列列出不支援/與 Microsoft Teams 案例相關聯的 Cmdlet。
  - [取得|Set]-CsUserPstnSettings
  - [取得|Set|啟用|Disable]-CsMeetingRoom
  - [授與|取得|Set|新增|Remove]-CsConferencingPolicy
  - [授與|取得|Set|新增|Remove]-CsClientPolicy
  - [授與|Get]-CsHostedVoicemailPolicy
  - [授與|取得|Set|新增|Remove]-CsMobilityPolicy
  - [授與|Get]-CsVoiceRoutingPolicy
  - [授與|Get]-CsBroadcastMeetingPolicy
  - [授與|Get]-CsCloudMeetingPolicy
  - [授與|Get]-CsGraphPolicy
  - [授與|取得|Set|新增|Remove]-CsExternalUserCommunicationPolicy
  - [授與|取得|Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [取得|Set]-CsBroadcastMeetingConfiguration
  - [取得|Set]-CsOAuthConfiguration
  - [取得|Set]-CsMeetingConfiguration
  - [取得|Set]-CsTenantHybridConfiguration
  - [取得|Set]-CsPushNotificationConfiguration
  - [取得|Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [取得|Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [取得|Set|註冊|Unregister]-CsHybridPSTNAppliance
  - [取得|Set|新增|Remove]-CsHybridPSTNSite
  - [取得|Set]-CsHybridMediationServer
  - [取得|Set|新增|Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [取得|Set|新增|Remove]-CsTeamsPinnedApp
  - [取得|Set|新增|Remove]-CsTenantCatalogApp
  - [取得|Set|新增|Remove]-CsGlobalCatalogApp
  - [取得|Set|新增|Remove]-CsDefaultCatalogApp
  - [取得|Set|新增|Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [取得|Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>相關主題

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[安裝 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/module/teams)

[商務用 Skype Cmdlet 參照](/powershell/module/skype)
