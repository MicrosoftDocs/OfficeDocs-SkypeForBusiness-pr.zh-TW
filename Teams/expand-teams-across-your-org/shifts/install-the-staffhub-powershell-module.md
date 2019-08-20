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
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464662"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>安裝 Microsoft StaffHub PowerShell 模組

> [!IMPORTANT]
> 2019年10月1日生效, Microsoft StaffHub 將停用。 我們正在將 StaffHub 功能組建至 Microsoft 團隊。 今天, 小組包含針對排程管理的倒班應用程式, 而其他功能則會隨著時間推移而推出。 StaffHub 將會停止針對2019年10月1日的所有使用者使用。 任何試圖開啟 StaffHub 的人, 都會顯示一則訊息, 讓他們下載小組。 若要深入瞭解, 請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。  

請使用本文中的步驟來安裝並聯機至 Microsoft StaffHub PowerShell 模組。 您需要使用 PowerShell 來管理 StaffHub, 並將 StaffHub 團隊移至 Microsoft 團隊。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>安裝 Microsoft StaffHub PowerShell 模組

1. 以系統管理員身分開啟 Windows PowerShell 3.0 或更新版本。若要這樣做, 請按一下 [**開始**], 輸入**Windows powershell**, 以滑鼠右鍵按一下 [ **windows powershell**], 然後選取 [**以系統管理員身分執行**]。
    > [!NOTE]
    > 若要取得最新版本的 Windows PowerShell, 請參閱[安裝 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。 
2. 執行下列動作以安裝目前穩定版本的 StaffHub PowerShell 模組:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    只有在您需要安裝最新版本時, 才能執行這個命令, 這可能會有比目前穩定版本更多的 instabilities:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > 如果您在使用更多 instabilities 安裝最新版本期間收到錯誤, 您可以執行下列動作:`Install-Module PowershellGet -Force`

3. 您可能會看到警告訊息:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

鍵入`Y`並按一下`Enter`。
 
4. 退出 Windows PowerShell。

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>連線到 Microsoft StaffHub PowerShell 模組

1. 執行下列動作:

    ```
    Connect-StaffHub
    ```

2. 出現提示時, 請以全域管理員身分登入。

## <a name="related-topics"></a>相關主題

- [Microsoft StaffHub PowerShell 參考](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [將 Microsoft StaffHub 小組移至團隊中](move-staffhub-teams-to-shifts-in-teams.md)
