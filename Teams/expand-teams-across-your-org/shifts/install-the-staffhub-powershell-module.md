---
title: 安裝 StaffHub PowerShell 模組
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何安裝和連線到 Microsoft StaffHub PowerShell 模組。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246176"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>安裝 Microsoft StaffHub PowerShell 模組

> [!IMPORTANT]
> 2019年10月1日生效, Microsoft StaffHub 將停用。 我們正在將 StaffHub 功能組建至 Microsoft 團隊。 今天, 小組包含針對排程管理的倒班應用程式, 而其他功能則會隨著時間推移而推出。 StaffHub 將會停止針對2019年10月1日的所有使用者使用。 任何試圖開啟 StaffHub 的人, 都會顯示一則訊息, 讓他們下載小組。 若要深入瞭解, 請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。  

請使用本文中的步驟來安裝並聯機至 Microsoft StaffHub PowerShell 模組。 您需要使用 PowerShell 來管理 StaffHub, 並將 StaffHub 團隊移至 Microsoft 團隊。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>安裝 Microsoft StaffHub PowerShell 模組

1. 下載[StaffHub PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)。 
2. 以系統管理員身分開啟 Windows PowerShell 3.0 或更新版本。若要這樣做, 請按一下 [**開始**], 輸入**Windows powershell**, 以滑鼠右鍵按一下 [ **windows powershell**], 然後選取 [**以系統管理員身分執行**]。
    > [!NOTE]
    > 若要取得最新版本的 Windows PowerShell, 請參閱[安裝 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。 
3. 執行下列動作:

    ```
    $ENV:PSModulePath
    ```
    

4. 檢查輸出中的資料夾路徑, 並確認路徑中的所有資料夾都存在於您的電腦上, 然後再移至下一個步驟。 如果資料夾遺失, 請建立。
5. 執行下列動作, 以允許安裝 StaffHub PowerShell 模組:

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. 執行下列動作, 其中&lt;path&gt;是步驟2輸出中的路徑。 例如, 路徑看起來可能像 C:\Users\User1\Documents\WindowsPowerShell\Modules。

    請務必分別執行每個命令。

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. 退出 Windows PowerShell。
8. 以全域系統管理員身分開啟 Windows PowerShell 3.0 或更新版本, 然後執行下列動作:

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>連線到 Microsoft StaffHub PowerShell 模組

1. 執行下列動作:

    ```
    Connect-StaffHub
    ```

2. 出現提示時, 請以全域管理員身分登入。

## <a name="related-topics"></a>相關主題

- [Microsoft StaffHub PowerShell 參考](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [將 Microsoft StaffHub 小組移至團隊中](move-staffhub-teams-to-shifts-in-teams.md)
