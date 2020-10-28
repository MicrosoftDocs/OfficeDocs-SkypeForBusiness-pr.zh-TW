---
title: PowerShell 腳本範例-小組部署清除
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本卸載小組，並移除使用者的 [小組] 資料夾。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7245e3cfee88beb51389f20bc99bbcc312f55b0
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778907"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="11cc7-103">PowerShell 腳本範例-小組部署清理</span><span class="sxs-lookup"><span data-stu-id="11cc7-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="11cc7-104">使用此腳本來移除團隊。</span><span class="sxs-lookup"><span data-stu-id="11cc7-104">Use this script to remove Teams.</span></span> <span data-ttu-id="11cc7-105">此腳本會卸載小組，並移除使用者的 [小組] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="11cc7-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="11cc7-106">針對在電腦上安裝團隊的每個使用者設定檔執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="11cc7-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="11cc7-107">範例腳本</span><span class="sxs-lookup"><span data-stu-id="11cc7-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a><span data-ttu-id="11cc7-108">相關主題</span><span class="sxs-lookup"><span data-stu-id="11cc7-108">Related topics</span></span>

- [<span data-ttu-id="11cc7-109">使用 Microsoft 端點 Configuration Manager 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="11cc7-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="11cc7-110">使用 Microsoft 365 應用程式部署團隊</span><span class="sxs-lookup"><span data-stu-id="11cc7-110">Deploy Teams with Microsoft 365 Apps</span></span>](https://docs.microsoft.com/deployoffice/teams-install)
