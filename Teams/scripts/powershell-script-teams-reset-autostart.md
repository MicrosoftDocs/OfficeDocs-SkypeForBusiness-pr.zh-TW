---
title: PowerShell 腳本範例 - 在 Teams 中重設自動啟動設定
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本，以每個使用者為基礎重設 Teams 中的自動啟動設定。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2f9b2388cef619728f5ecdd912e61448cc3524c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117261"
---
# <a name="powershell-script-sample---reset-the-autostart-setting-in-teams"></a><span data-ttu-id="8f0e0-103">PowerShell 腳本範例 - 在 Teams 中重設自動啟動設定</span><span class="sxs-lookup"><span data-stu-id="8f0e0-103">PowerShell script sample - Reset the autostart setting in Teams</span></span>

<span data-ttu-id="8f0e0-104">使用此腳本可依據每個使用者重設 Teams 自動啟動設定。</span><span class="sxs-lookup"><span data-stu-id="8f0e0-104">Use this script to reset the Teams autostart setting on a per-user basis.</span></span> <span data-ttu-id="8f0e0-105">這包括使用者或 Teams 應用程式所設定的任何值。</span><span class="sxs-lookup"><span data-stu-id="8f0e0-105">This includes any values set by the user or the Teams app.</span></span> <span data-ttu-id="8f0e0-106">根據預設，當使用者在安裝之後，系統會自動啟動 Teams 來登錄其電腦。</span><span class="sxs-lookup"><span data-stu-id="8f0e0-106">By default, Teams automatically starts when a user logs in to their computer after it's installed.</span></span>

<span data-ttu-id="8f0e0-107">如果您已經部署 Teams，並想要設定安裝群組原則之後自動啟動 [Microsoft Teams](../msi-deployment.md#use-group-policy-recommended) 設定以停用 Teams 自動啟動，您必須先將群組原則設定為您想要的值，然後執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="8f0e0-107">If you've already deployed Teams and want to set the [Prevent Microsoft Teams from starting automatically after installation Group Policy setting](../msi-deployment.md#use-group-policy-recommended) to disable Teams autostart, you'll need to first set the Group Policy setting to the value you want, and then run this script.</span></span>

<span data-ttu-id="8f0e0-108">在使用者啟動 Teams 之後，使用群組原則無法停用自動啟動設定。</span><span class="sxs-lookup"><span data-stu-id="8f0e0-108">After Teams is started for a user, the autostart settings can't be disabled by using Group Policy.</span></span>

## <a name="sample-script"></a><span data-ttu-id="8f0e0-109">範例腳本</span><span class="sxs-lookup"><span data-stu-id="8f0e0-109">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script allows you to reset all autostart settings to the default settings for Teams.
.DESCRIPTION
If you want to use the "Prevent Microsoft Teams from starting automatically after installation"
Group Policy setting, make sure you first set the Group Policy setting to the value you want 
before you run this script.
#>

$ErrorActionPreference = "Stop"

$TeamsDesktopConfigJsonPath = [System.IO.Path]::Combine($env:APPDATA, 'Microsoft', 'Teams', 'desktop-config.json')

$TeamsUpdatePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

Function Test-RegistryValue {
    param(
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    ) 

    process {
        if (Test-Path $Path) {
            $Key = Get-Item -LiteralPath $Path
            if ($null -ne $Key.GetValue($Name, $null)) {
                $true
            } else {
                $false
            }
        } else {
            $false
        }
    }
}

Function Test-Remove-RegistryValue {
    param (
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    )

    process {
        if (Test-RegistryValue -Path $Path -Name $Name) {
            Write-Host "Removing registry key $Path\$Name"
            Remove-ItemProperty -Path $Path -Name $Name
        }
    }
}

# when determining whether Teams should be auto-started we are checking three flags
Write-Host "Removing Auto-Start-related artifacts"

# 0. Close Teams, if running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue
if ($null -ne $teamsProc) {
    Write-Host  "Stopping Microsoft Teams..."
    Stop-Process -Name Teams -Force
    # wait some time
    Start-Sleep 5
} else {
    Write-Host  "No running Teams process found"
}

# 1. Check that Teams process isn't still running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue

if($null -eq $teamsProc) {
    # 2. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\LoggedInOnce registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "LoggedInOnce"

    # 3. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\HomeUserUpn registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "HomeUserUpn"

    # 4. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\DeadEnd registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "DeadEnd"

    # 5. remove HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect registry key
    Remove-Item -Path "HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect" -ErrorAction SilentlyContinue

    # 6. restore HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams
    if (!(Test-RegistryValue -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams")) {
        Write-Host "Restoring registry key HKCU\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams"
        Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams" -Value "$TeamsUpdatePath --processStart ""Teams.exe"" --process-start-args ""--system-initiated"""
    }

    # 7. We are checking whether there are entries 'isLoggedOut' and 'openAtLogin' in the desktop-config.json file
    if (Test-Path -Path $TeamsDesktopConfigJsonPath) {
        Write-Host "Changing entries 'guestTenantId', 'isLoggedOut' and 'openAtLogin' in the desktop-config.json, if exist"

        # open desktop-config.json file
        $desktopConfigFile = Get-Content -path $TeamsDesktopConfigJsonPath -Raw | ConvertFrom-Json
        $desktopConfigFile.PSObject.Properties.Remove("guestTenantId")
        $desktopConfigFile.PSObject.Properties.Remove("isLoggedOut")
        try {
            $desktopConfigFile.appPreferenceSettings.openAtLogin = $true
        } catch {
            Write-Host  "openAtLogin JSON element doesn't exist"
        }
        $desktopConfigFile | ConvertTo-Json -Compress | Set-Content -Path $TeamsDesktopConfigJsonPath -Force
    }
} else {
    Write-Host  "Teams process is still running, aborting script execution"
}
````

## <a name="related-topics"></a><span data-ttu-id="8f0e0-110">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f0e0-110">Related topics</span></span>

- [<span data-ttu-id="8f0e0-111">使用 MSI 安裝 Teams</span><span class="sxs-lookup"><span data-stu-id="8f0e0-111">Install Teams using MSI</span></span>](../msi-deployment.md)
- [<span data-ttu-id="8f0e0-112">使用 Microsoft 365 企業版應用程式部署 Teams</span><span class="sxs-lookup"><span data-stu-id="8f0e0-112">Deploy Teams with Microsoft 365 Apps for enterprise</span></span>](/deployoffice/teams-install)