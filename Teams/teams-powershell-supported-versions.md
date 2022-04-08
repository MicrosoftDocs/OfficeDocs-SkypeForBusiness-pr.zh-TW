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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712957"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模組 - 支援的版本

Microsoft Teams 4.x.x 系列或更新版本中的 PowerShell 模組 (TPM) 版本將是唯一支援的版本。 所有舊版都處於淘汰路徑。 建議您將 PowerShell 模組Teams更新為最新版本。



## <a name="new-organizations"></a>新組織

從 2022 年 4 月 1 日開始，新入Teams的組織只能使用 4.x.x.x 系列或更新版本中的 Teams PowerShell 模組。



## <a name="current-organizations-non-tpm-active"></a>目前組織 (非 TPM 作用中) 

從 2022 年 4 月 1 日開始， (1 月 22 日 - 3 月 22 日) ，過去三個月內未使用 powerShell 模組Teams的組織，只能使用 4.x.x.x 系列或更新版本中的 Teams PowerShell 模組。



## <a name="current-organizations-tpm-active"></a>目前組織 (TPM 作用中) 

從 2022 年 6 月 15 日開始 (1 月 22 日 - 3 月 22 日) ，過去三個月內一直使用 Teams PowerShell 模組的組織，只能在 4.x.x.x 系列或更新版本中使用 Teams PowerShell 模組。 訊息中心文章供參考 - MC350371。 



## <a name="important-notes"></a>重要筆記

- 您可以在[powerShell 版本資訊Teams找到所有 PowerShell 模組Teams版本的版本資訊](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模組，您應該使用相同的方法來安裝模組。 例如，如果您原本使用 Install-Module，則應該使用 [Update-Module](/powershell/module/powershellget/update-module) 來取得最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果從 Teams PowerShell 模組版本 1.1.6 更新，請更新腳本以取代 `New-CsOnlineSession` 。 `Connect-MicrosoftTeams`

-   在更新期間，建議您不要同時使用 TPM 4.x.x/3.x.x.x 及 3.0.0 以上的版本。 例如，不建議將版本 4.x.x & 2.6.0 用於同一個組織中不同的系統管理作業。 

- 相關變更
  * TPM 3.x.x 及更新版本中Get-CsOnlineUser & Get-CsOnlineVoiceUser的更新 – [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser)  &  (訊息中心文章 – MC340774) 中的更多詳細資料。[ ](/powershell/module/skype/get-csonlinevoiceuser)

  * 電話數位指派的變更 -[在 Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance)  &  (訊息中心文章中提供更多詳細資料 – MC316139) [ ](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>已取代的 Cmdlet

下列列出一些最近已取代或不支援Microsoft Teams案例的 Cmdlet。 您可以在個別的公開檔中找到相同的詳細資料。 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings)， [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)， [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)， [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)， [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom)、 [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom)、 [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom)、 [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities)， [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas)， [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)， [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)， [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)， [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)， [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)， [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)， [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation)， [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation)， [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>相關主題

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[安裝 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/module/teams) 

[商務用 Skype Cmdlet 參照](/powershell/module/skype) 
