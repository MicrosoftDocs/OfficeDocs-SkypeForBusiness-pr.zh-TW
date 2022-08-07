---
title: 腳本範例 - Microsoft Teams 防火牆 PowerShell 腳本
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
ms.localizationpriority: medium
search.appverid: MET150
description: 可用來設定 Windows 以允許 Teams 透過 Windows 防火牆連線的範例腳本。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b15c8e141f8a3cd5cde1915901d3dbcd9e29b23a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269398"
---
# <a name="sample-script---microsoft-teams-firewall-powershell-script"></a>腳本範例 - Microsoft Teams 防火牆 PowerShell 腳本

此指令碼範例必須在系統管理員帳戶權限已提升的用戶端電腦上執行，才能為 c:\users 中的每個使用者資料夾建立新的輸入防火牆規則。 當 Teams 找到此規則時，該規則會防止 Teams 應用程式在使用者第一次從 Teams 進行通話時，提示使用者建立防火牆規則。

```powershell

<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
