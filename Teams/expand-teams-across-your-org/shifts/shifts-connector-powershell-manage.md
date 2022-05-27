---
title: 使用 PowerShell 管理您與 Blue Yonder 員工管理的 Shifts 連線
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 PowerShell 來管理您與 Blue Yonder 員工管理的 Shifts 連線。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a102001c9c35b3d93467a9955329ce9d314532d0
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675365"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>使用 PowerShell 管理您與 Blue Yonder 員工管理的 Shifts 連線

## <a name="overview"></a>概觀

[Blue Yonder 的 Microsoft Teams Shifts 連接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)可讓您將 Microsoft Teams 中的 Shifts 應用程式與 Blue Yonder 員工管理 (Blue Yonder WFM) 整合。 設定連線之後，第一線工作人員就可以從班次中順暢地檢視和管理他們在 Blue Yonder WFM 中的排程。

您可以使用 Microsoft 365 系統管理中心 或[PowerShell](shifts-connector-blue-yonder-powershell-setup.md)中的[Shifts 連接器精](shifts-connector-wizard.md)靈來設定連線。 設定連線之後，您可以使用 [Shifts 連接器 PowerShell Cmdlet](#shifts-connector-cmdlets)來管理連線。

本文說明如何使用 PowerShell 執行下列動作：

- [檢查連線設定狀態](#check-connection-setup-status)
- [檢視連線的錯誤報表](#view-an-error-report-for-a-connection)
- [解決連線錯誤](#resolve-connection-errors)
- [變更連線設定](#change-connection-settings)
- [從一個連線取消對應小組，並將它對應到另一個連線](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [停用連線的同步處理](#disable-sync-for-a-connection)

> [!NOTE]
> 本文假設您已經使用精靈或 PowerShell 來設定與 Blue Yonder WFM 的連線。

## <a name="before-you-begin"></a>開始之前

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>設定您的環境

> [!NOTE]
> 請務必遵循下列步驟來設定您的環境，然後再執行本文中的任何命令或腳本。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. 連線Teams。

    ```powershell
    Connect-MicrosoftTeams
    ```

    出現提示時，請使用您的系統管理員認證登入。 您現在已設定為執行本文中的腳本和 Shifts 連接器 Cmdlet。

## <a name="check-connection-setup-status"></a>檢查連線設定狀態

<a name="setup_status"> </a>

若要使用您在電子郵件中收到的作業識別碼檢查您所設定連線的狀態：

1. 如果您尚未) ，請 (設定[您的環境](#set-up-your-environment)。
1. 執行下列命令。 此命令會提供您連線之小組對應的整體狀態。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)。

## <a name="view-an-error-report-for-a-connection"></a>檢視連線的錯誤報表

<a name="error_report"> </a>

您可以執行顯示連線錯誤詳細資料的報告。 報告會列出成功與失敗的小組和使用者對應。 它也會提供與連線相關聯之帳戶相關之任何問題的相關資訊。

1. 如果您尚未) ，請 (設定[您的環境](#set-up-your-environment)。
1. 取得連線的錯誤報表清單。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 若要檢視特定的錯誤報表，請執行下列命令：

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)。

## <a name="resolve-connection-errors"></a>解決連線錯誤

### <a name="user-mapping-errors"></a>使用者對應錯誤

如果 Blue Yonder WFM 網站中的一或多個使用者不是Teams中對應小組的成員，可能會發生使用者對應錯誤。 若要解決此問題，請確認對應小組中的使用者符合 Blue Yonder WFM 網站中的使用者。

若要檢視未對應使用者的詳細資料，請 (如果您尚未) ，請 [設定您的環境](#set-up-your-environment) ，然後執行下列腳本。

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>帳戶授權錯誤

如果 Blue Yonder WFM 服務帳戶或Microsoft 365系統帳號憑證不正確或沒有必要許可權，可能會發生帳戶授權錯誤。

若要變更連線的 Blue Yonder WFM 服務帳戶或Microsoft 365系統帳號憑證，您可以執行[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) Cmdlet 或使用本文 [[變更連線設定](#change-connection-settings)] 區段中的 PowerShell 腳本。

## <a name="change-connection-settings"></a>變更連線設定
<a name="change_settings"> </a>

使用此腳本變更連線設定。 您可以變更的設定包括您的 Blue Yonder WFM 服務帳戶和密碼、Microsoft 365系統帳戶、小組對應和同步設定。

同步設定包括 (分鐘) 的同步處理頻率，以及在 Blue Yonder WFM 和 Shifts 之間同步的排程資料。 排程資料是在下列參數中定義，您可以執行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)來檢視。

- **EnabledConnectorScenarios** 參數會定義從 Blue Yonder WFM 同步到 Shifts 的資料。 選項包括 `Shift` 、 `SwapRequest` 、、 `UserShiftPreferences` 、 `OpenShift` 、 `OpenShiftRequest` 、 `TimeOff` 。 `TimeOffRequest`
- **enabledWfiScenarios** 參數會定義從 Shifts 同步到 Blue Yonder WFM 的資料。 選項包括 `SwapRequest` 、 `OpenShiftRequest` 、 `TimeOffRequest` 、 `UserShiftPreferences` 。

    > [!NOTE]
    > 如果您選擇不在 Shifts 與 Blue Yonder WFM 之間同步處理開啟的班次、開啟班次要求、調班要求或休假要求，則需要執行另一個步驟來隱藏 Shifts 中的功能。 執行此腳本之後，請務必依照本文稍後的 [[停用開啟班次]、[開啟班次要求]、[調班要求] 和 [休假要求](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) ] 一節中的步驟進行。

> [!IMPORTANT]
> 針對您不想要變更的設定，當腳本提示您時，您必須重新輸入原始設定。

如果您尚未) ，請 (設定[您的環境](#set-up-your-environment)，然後執行下列腳本。

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>停用開啟班、開啟班次要求、調班要求和休假要求

> [!IMPORTANT]
> Follow these steps only if you chose to disable open shifts, open shift requests, swap requests, or time off requests using the script in the [Change connection settings](#change-connection-settings) section earlier in this article or by using the [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet. 完成此步驟會隱藏 Shifts 中的功能。 如果沒有此第二個步驟，使用者仍會在 Shifts 中看到此功能，如果他們嘗試使用該功能，則會收到「不支援的作業」錯誤訊息。

若要在 Shifts 中隱藏開啟的班次、調班要求和休假要求，請使用圖形 API[排程資源類型](/graph/api/resources/schedule)，為您對應到 ```false``` Blue Yonder WFM 網站的每一個小組設定下列參數：

- 開啟班次： ```openShiftsEnabled```
- 調換要求：  ```swapShiftsRequestsEnabled```
- 休假要求： ```timeOffRequestsEnabled```

若要在班次中隱藏開啟的班次要求，請移至 **[班次] 中的 [設定**]，然後關閉 [**開啟班次**] 設定。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>從一個連線取消對應小組，並將它對應到另一個連線

> [!NOTE]
> Microsoft 365系統帳戶對兩個連線都必須相同。 如果沒有，您會收到「此指定的動作人員設定檔沒有團隊擁有許可權」錯誤訊息。

如果您想要從一個連線取消對應小組，並將它對應到另一個連線：

1. 如果您尚未) ，請 (設定[您的環境](#set-up-your-environment)。
1. 檢視連線的所有團隊對應清單。

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 從連線中移除小組對應。

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. 將小組對應到另一個連線。

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)和 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)。

## <a name="disable-sync-for-a-connection"></a>停用連線的同步處理

使用此腳本停用連線的同步處理。 請記住，此腳本不會移除或刪除連線。 它會關閉同步，如此一來就不會在班次和 Blue Yonder WFM 之間針對您指定的連線同步處理任何資料。

如果您尚未) ，請 (設定[您的環境](#set-up-your-environment)，然後執行下列腳本。

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Shifts 連接器 Cmdlet

如需 Shifts 連接器 Cmdlet 的說明，請在 [powerShell Cmdlet 參照Teams](/powershell/teams/intro)中搜尋 **CsTeamsShiftsConnection**。 以下是一些常用 Cmdlet 的連結。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>相關文章

- [Shifts 連接器](shifts-connectors.md)
- [使用 Shifts 連接器精靈將 Shifts 連線到 Blue Yonder 員工管理](shifts-connector-wizard.md)
- [使用 PowerShell 將班次連線到 Blue Yonder 員工管理](shifts-connector-blue-yonder-powershell-setup.md)
- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概觀](../../teams-powershell-overview.md)
