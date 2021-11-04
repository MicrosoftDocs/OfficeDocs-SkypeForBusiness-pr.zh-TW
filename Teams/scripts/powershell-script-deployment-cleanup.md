---
title: PowerShell 腳本範例 - Teams清理
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本卸載Teams並移除Teams資料夾。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4853cf99bc6d600f8673df065c3dee3e0068207b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767151"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell 腳本範例 - Teams清理部署

使用此腳本移除Teams。 此腳本會卸載Teams並移除Teams資料夾。 針對每一個使用者設定檔執行此腳本，Teams電腦上安裝此設定檔。


## <a name="sample-script"></a>範例腳本

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

## <a name="related-topics"></a>相關主題

- [使用 Microsoft Teams 安裝Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [使用 Teams 部署Microsoft 365 Apps](/deployoffice/teams-install)
