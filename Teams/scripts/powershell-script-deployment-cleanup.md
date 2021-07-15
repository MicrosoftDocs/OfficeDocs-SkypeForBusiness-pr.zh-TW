---
title: PowerShell 腳本範例 - Teams清理
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本卸載Teams使用者Teams資料夾。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96f3c7f6d9d9fa52edd09b7ecf690f43d6730367
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428189"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="02ecf-103">PowerShell 腳本範例 - Teams清理部署</span><span class="sxs-lookup"><span data-stu-id="02ecf-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="02ecf-104">使用此腳本移除Teams。</span><span class="sxs-lookup"><span data-stu-id="02ecf-104">Use this script to remove Teams.</span></span> <span data-ttu-id="02ecf-105">此腳本會卸載Teams並移除Teams資料夾。</span><span class="sxs-lookup"><span data-stu-id="02ecf-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="02ecf-106">針對每一個使用者設定檔執行此腳本，Teams電腦上安裝此設定檔。</span><span class="sxs-lookup"><span data-stu-id="02ecf-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="02ecf-107">範例腳本</span><span class="sxs-lookup"><span data-stu-id="02ecf-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

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

## <a name="related-topics"></a><span data-ttu-id="02ecf-108">相關主題</span><span class="sxs-lookup"><span data-stu-id="02ecf-108">Related topics</span></span>

- [<span data-ttu-id="02ecf-109">使用 Microsoft Teams 安裝Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02ecf-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="02ecf-110">使用 Teams 部署Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="02ecf-110">Deploy Teams with Microsoft 365 Apps</span></span>](/deployoffice/teams-install)
