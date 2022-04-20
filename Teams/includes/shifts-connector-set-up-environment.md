---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976013"
---
1. 安裝 PowerShell 版本 7 或更新版本。 如需逐步指引，請參閱[在 Windows 上安裝 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。

1. 以系統管理員模式執行 PowerShell。
1. 安裝 Microsoft Graph PowerShell 模組。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    確認是版本 1.6.1 或更新版本。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. 安裝 Teams Preview PowerShell 模組。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    確認它至少為 4.1.0 版，且包含 Shifts 連接器 Cmdlet。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. 設定 PowerShell 在執行腳本時發生錯誤時結束。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 啟用腳本以Windows執行。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```