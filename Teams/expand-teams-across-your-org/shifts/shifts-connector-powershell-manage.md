---
title: 使用 PowerShell 管理您與 Blue Yonder 員工管理之間的 Shifts 連接
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 PowerShell 管理您與 Blue Yonder 員工管理之間的 Shifts 連接。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593643"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>使用 PowerShell 管理您與 Blue Yonder 員工管理之間的 Shifts 連接

## <a name="overview"></a>概觀

Blue [Yonder Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)連接器可讓您在 Microsoft Teams 中整合 Shifts 應用程式與 Blue Yonder 員工管理 (Blue Yonder WFM) 。 設定連接之後，前線工作人員可以在 Shifts 中順暢地在 Blue Yonder WFM 中查看及管理排程。

您可以使用[PowerShell 或 powerShell Microsoft 365 系統管理中心 Shifts](shifts-connector-blue-yonder-powershell-setup.md)連接器精靈來設定連接。[ ](shifts-connector-wizard.md) 設定連接之後，您可以使用 [Shifts 連接器 PowerShell Cmdlet 來管理它](#shifts-connector-cmdlets)。

本文將說明如何使用 PowerShell 執行下列操作：

- [檢查連接設定狀態](#check-connection-setup-status)
- [查看連接的錯誤報表](#view-an-error-report-for-a-connection)
- [解決連接錯誤](#resolve-connection-errors)
- [變更連接設定](#change-connection-settings)
- [從一個連接取消繪製團隊地圖，然後將它映射至另一個連接](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [停用連接的同步](#disable-sync-for-a-connection)

> [!NOTE]
> 本文假設您已經使用精靈或 PowerShell 來設定與 Blue Yonder WFM 的關聯。

## <a name="before-you-begin"></a>開始之前

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>設定您的環境

> [!NOTE]
> 執行本文中任何命令或腳本之前，請務必遵循這些步驟來設定您的環境。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>檢查連接設定狀態
<a name="setup_status"> </a>

若要使用在電子郵件中收到的作業識別碼檢查您設定的連接狀態：

1. [如果您尚未 (](#set-up-your-environment) ，請設定您的) 。
1. 執行下列命令。 此命令提供您連接之小組映射的整體狀態。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)。

## <a name="view-an-error-report-for-a-connection"></a>查看連接的錯誤報表
<a name="error_report"> </a>

您可以執行顯示連接錯誤詳細資料的報告。 報表會列出成功和失敗的小組和使用者映射。 它也提供有關與關聯帳戶相關的任何問題的資訊。

1. [如果您尚未 (](#set-up-your-environment) ，請設定您的) 。
1. 取得連接的錯誤報表清單。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 若要查看特定錯誤報表，請執行下列命令：

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)。

## <a name="resolve-connection-errors"></a>解決連接錯誤

### <a name="user-mapping-errors"></a>使用者映射錯誤

如果 Blue Yonder WFM 網站中的一或多個使用者不是其中對應小組的成員，可能會發生使用者對應Teams。 若要解決此問題，請確定對應團隊中的使用者符合 Blue Yonder WFM 網站中的使用者。

若要查看未映射使用者的詳細資訊， (尚未[](#set-up-your-environment)建立) ，然後執行下列腳本。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

如果 Blue Yonder WFM 服務帳戶或 Microsoft 365系統帳號憑證不正確或沒有必要的許可權，可能會發生帳戶授權錯誤。

若要變更您的 Blue Yonder WFM 服務帳戶或 Microsoft 365 系統帳號憑證，您可以執行[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) Cmdlet，或使用本文的變更連接設定區段的 PowerShell 腳本。[ ](#change-connection-settings)

## <a name="change-connection-settings"></a>變更連接設定
<a name="change_settings"> </a>

使用此腳本來變更連接設定。 設定包括您的 Blue Yonder WFM 服務帳戶和密碼、Microsoft 365系統帳戶、小組地圖和同步設定。

同步處理設定包括同步處理頻率 (分鐘) 以及 Blue Yonder WFM 和 Shifts 之間同步的排程資料。 排程資料是在下列參數中定義，您可以執行 [Get-CsTeamsShiftsConnectionConnector 來查看](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。

- 已啟用 **的ConnectorScenarios參數** 會定義從 Blue Yonder WFM 同步處理至 Shifts 的資料。 選項為 `Shift` 、 `SwapRequest` 、 `UserShiftPreferences` 、 `OpenShift` `OpenShiftRequest` 、 `TimeOff` 、、 。 `TimeOffRequest`
- **enabledWfiScenarios 參數** 會定義從 Shifts 同步處理至 Blue Yonder WFM 的資料。 選項為 `SwapRequest` 、 `OpenShiftRequest` `TimeOffRequest` 、 `UserShiftPreferences` 。

    > [!NOTE]
    > 如果您選擇不在 Shifts 和 Blue Yonder WFM 之間同步處理開啟的班、開啟班要求、調班要求或請假要求，您需要執行另一個步驟來隱藏 Shifts 中的功能。 執行此腳本之後，請確定您遵循本文稍後的停用開啟[](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests)班、開啟班要求、調班要求和請假要求一節中的步驟。

> [!IMPORTANT]
> 針對您不想變更的設定，當腳本提示您時，您必須重新輸入原始設定。

[如果您尚未 (](#set-up-your-environment) ，請設定您的) ，然後執行下列腳本。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>停用開啟的班、開啟的班要求、調班要求，以及請假要求

> [!IMPORTANT]
> 只有在本文稍早的變更連接設定區段或[Set-CsTeamsShiftsConnectionInstance Cmdlet](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)中的腳本選擇停用[](#change-connection-settings)開啟班、開啟班要求、調班要求或請假要求時，才能遵循這些步驟。 完成此步驟會隱藏 Shifts 中的功能。 如果沒有這個第二個步驟，使用者仍然會看到 Shifts 中的功能，如果使用者嘗試使用此功能，就會收到「不支援的操作」錯誤訊息。

若要在 Shifts 中隱藏已開啟的班、調班要求和請假要求，請使用 圖形 API [](/graph/api/resources/schedule?view=graph-rest-1.0) ```false``` 排程資源類型，針對對應至 Blue Yonder WFM 網站的每個小組設定下列參數：

- 開啟班次： ```openShiftsEnabled```
- 調換要求：  ```swapShiftsRequestsEnabled```
- 請假要求： ```timeOffRequestsEnabled```

若要在 Shifts 中隱藏開啟的班要求，請 **設定中開啟** 的班數，然後關閉開啟 **班** 設定。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>從一個連接取消繪製團隊地圖，然後將它映射至另一個連接

> [!NOTE]
> 兩Microsoft 365系統帳戶必須相同。 如果沒有，您就會收到「此指定的參與者設定檔沒有團隊擁有許可權」的錯誤訊息。

如果您想要從一個連接取消繪製團隊的地圖，並把它與另一個連接進行比對：

1. [如果您尚未 (](#set-up-your-environment) ，請設定您的) 。
1. 查看所有小組的關聯清單。

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 從連接移除團隊映射。

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. 將小組繪製到另一個連接。

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

若要深入瞭解，請參閱 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)和 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)。

## <a name="disable-sync-for-a-connection"></a>停用連接的同步

使用此腳本來停用連接的同步處理。 請記住，此腳本不會移除或刪除連接。 它會關閉同步處理，因此您指定的連接不會在 Shifts 和 Blue Yonder WFM 之間同步處理資料。

[如果您尚未 (](#set-up-your-environment) ，請設定您的) ，然後執行下列腳本。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

有關 Shifts 連接器 Cmdlet 的協助，請搜尋 [PowerShell Cmdlet Teams中的](/powershell/teams/intro?view=teams-ps) **CsTeamsShiftsConnection**。 以下是一些常用的 Cmdlet 連結。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>相關文章

- [移轉連接器](shifts-connectors.md)
- [使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder 員工管理](shifts-connector-wizard.md)
- [使用 PowerShell 將 Shifts 連接到 Blue Yonder 員工管理](shifts-connector-blue-yonder-powershell-setup.md)
- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概觀](../../teams-powershell-overview.md)