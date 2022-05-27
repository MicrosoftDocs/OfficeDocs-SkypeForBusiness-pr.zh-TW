---
title: 安裝 Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何使用 PowerShell 控制項來管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682004"
---
# <a name="install-microsoft-teams-powershell-module"></a>安裝 Microsoft Teams PowerShell 模組

本文說明如何使用 PowerShell 資源庫 安裝 Microsoft Teams PowerShell 模組。 所有Windows平臺都支援Microsoft Teams PowerShell 模組。 不支援 Mac 和 Linux。

## <a name="requirements"></a>需求

Microsoft Teams PowerShell 模組在所有平臺上都需要 PowerShell 5.1 或更新版本。 安裝適用于您作業系統 [的最新版 PowerShell](/powershell/scripting/install/installing-powershell) 。

若要檢查您的 PowerShell 版本，請在 PowerShell 會話中執行下列命令：

```powershell
$PSVersionTable.PSVersion
```

建議您使用 Install-Module Cmdlet 來安裝 Microsoft Teams PowerShell 模組。

如果 PowerShell 資源庫 (PSGallery) 未設定為 **PowerShellGet** 值得信任的存放庫，第一次使用 PSGallery 時，您會看到下列訊息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 **[是]** 或 **[是到全部]** 以繼續安裝。

## <a name="installing-using-the-powershellgallery"></a>使用 PowerShellGallery 安裝

Microsoft Teams PowerShell 模組目前支援與 Windows 上的 PowerShell 5.1 搭配使用。 請依照下列步驟安裝模組：

- 更新為[Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)。 如果您使用的是 Windows 10 版本 1607 或更新版本，則已安裝 PowerShell 5.1。
- 安裝[.NET Framework 4.7.2](/dotnet/framework/install)或更新版本。
- 執行下列命令以安裝最新的 PowerShellGet：

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- 安裝 Teams PowerShell 模組。

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>離線安裝

在某些環境中，無法連線到PowerShell 資源庫。 在這些情況下，請遵循這些 [手動安裝步驟](https://aka.ms/psgallery-manualdownload)。

## <a name="sign-in"></a>登錄

若要開始使用 Microsoft Teams PowerShell 模組，請使用您的 Azure 認證登入。

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>更新Teams PowerShell 模組

若要更新任何 PowerShell 模組，您應該使用相同的方法來安裝模組。 例如，如果您原本使用 Install-Module，則應該使用 [Update-Module](/powershell/module/powershellget/update-module) 來取得最新版本。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果Teams PowerShell 已匯入 PowerShell 會話，則更新模組將會失敗。 關閉 PowerShell，並重新開啟新的提升許可權的 PowerShell 會話。

## <a name="uninstall-teams-powershell"></a>卸載 powerShell Teams

若要卸載 PowerShell Microsoft Teams，請開啟新的 PowerShell 命令提示字元，然後執行下列動作：

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>後續步驟

現在您已準備好使用 Microsoft Teams PowerShell 管理Microsoft Teams。 請參閱[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)以開始使用。

## <a name="related-topics"></a>相關主題

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro)
