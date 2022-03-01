---
title: 在 PowerShell Microsoft Teams安裝
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
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039971"
---
# <a name="install-microsoft-teams-powershell-module"></a>安裝 Microsoft Teams PowerShell 模組

本文將說明如何使用 PowerShell 圖庫Microsoft Teams PowerShell 模組。 所有Microsoft Teams平臺都支援 PowerShell 模組Windows模組。 不支援 Mac 和 Linux。

## <a name="requirements"></a>需求

Microsoft Teams PowerShell 模組在所有平臺上都需要 PowerShell 5.1 或更高版本。 為 [作業系統安裝最新版的 PowerShellavailable](/powershell/scripting/install/installing-powershell)   。 

若要檢查 PowerShell 版本，請在 PowerShell 會話內執行下列命令： 

```powershell
$PSVersionTable.PSVersion 
```
我們建議您使用 Install-Module Cmdlet 來安裝 Microsoft Teams PowerShell 模組。 
 
如果 PowerShell 圖庫 (PSGallery) 未配置為 **PowerShellGet** 的受信任的存放庫，當您第一次使用 PSGallery 時，會看到下列訊息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 **是** 或 **全部是** 以繼續安裝。

## <a name="installing-using-the-powershellgallery"></a>使用 PowerShellGallery 安裝

Microsoft Teams PowerShell 模組目前支援與 PowerShell 5.1 一Windows。 請遵循下列步驟安裝模組： 

- 更新至[Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)。 如果您是使用 1607 Windows 10版本，表示您已安裝 PowerShell 5.1。 
- 安裝[.NET Framework 4.7.2](/dotnet/framework/install)或更新版。 
- 執行下列命令以安裝最新的 PowerShellGet：
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- 安裝 powerShell Teams模組。

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>離線安裝 

在某些環境中，無法連接到 PowerShell 圖庫。 在這些情況下，請遵循這些 [手動安裝步驟](https://aka.ms/psgallery-manualdownload)。  

## <a name="sign-in"></a>登錄

若要開始使用 PowerShell 模組Microsoft Teams，請以 Azure 認證來登錄。

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>更新 Teams PowerShell 模組

若要更新任何 PowerShell 模組，您應該使用與安裝模組相同的方法。 例如，如果您原本是使用 Install-Module，您應該使用 [Update-Module](/powershell/module/powershellget/update-module) 取得最新版本。  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果Teams PowerShell 已導入 PowerShell 會話，更新模組將會失敗。 關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。


## <a name="uninstall-teams-powershell"></a>卸載 Teams PowerShell

若要卸載 powerShell Microsoft Teams，請開啟新的 PowerShell 命令提示，然後執行下列操作： 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>後續步驟 

現在，您可以使用 PowerShell Microsoft Teams管理Microsoft Teams程式。 請參閱[使用 powerShell Teams管理Teams以](teams-powershell-managing-teams.md)開始使用。 

## <a name="related-topics"></a>相關主題

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)
