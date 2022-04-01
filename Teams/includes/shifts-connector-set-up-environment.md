---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593647"
---
1. 安裝 PowerShell 版本 7 或更新版本。 有關逐步指南，請參閱在[Windows 安裝 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。

1. 在系統管理員模式中執行 PowerShell。
1. 安裝 Microsoft Graph PowerShell 模組。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    確認版本為 1.6.1 或更新版本。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. 安裝 Teams PowerShell 模組。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    確認至少為版本 4.1.0，並包含 Shifts 連接器 Cmdlet。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. 安裝 MSAL PowerShell 模組。

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. 如果執行腳本時發生錯誤，請設定 PowerShell 退出。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 啟用腳本在 Windows。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```