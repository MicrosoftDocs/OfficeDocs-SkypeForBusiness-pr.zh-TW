---
title: 安裝 Microsoft 團隊 PowerShell
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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814462"
---
# <a name="install-microsoft-teams-powershell"></a>安裝 Microsoft 團隊 PowerShell

本文說明如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)來安裝 Microsoft 團隊 PowerShell 模組。 這些指示適用于 [Azure 雲端 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平臺。

## <a name="requirements"></a>需求

團隊 PowerShell 在所有平臺上都需要 PowerShell 5.1 或更高版本。 安裝適用于您作業系統的 [最新版本 PowerShell](/powershell/scripting/install/installing-powershell) 。

> [!WARNING]
> PowerShell 7 和團隊 PowerShell 存在已知問題。 我們建議您使用 PowerShell 5.1，以獲得最佳使用體驗。

## <a name="install-the-teams-powershell-module"></a>安裝團隊 PowerShell 模組

> [!NOTE]
> 若要獲得最佳體驗，請使用一般可用性 (GA) 或公用預覽模組，不包括兩者。 它們不是共同合作。


使用 **PowerShellGet** Cmdlet 來安裝團隊 PowerShell 模組。 針對系統上的所有使用者安裝模組需要提升許可權。 在 Windows 中使用 [ **以系統管理員身分執行** ] 或使用 `sudo` macOS 或 Linux 上的命令來啟動 PowerShell 會話：

```powershell
Install-Module MicrosoftTeams
```

根據預設，PowerShell 圖庫 (PSGallery) 未設定為 **PowerShellGet**的可信儲存庫。 第一次使用 PSGallery 時，您會看到下列訊息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 **[是]** 或 **[是]** 以繼續安裝。


## <a name="install-teams-powershell-public-preview"></a>安裝團隊 PowerShell 公開預覽版

> [!NOTE]
> 如果您使用的是公開預覽版的團隊 PowerShell，我們強烈建議您先卸載商務用 Skype Online 連接器。

針對系統上的所有使用者安裝團隊 PowerShell 公用預覽模組需要提升許可權。 在 Windows 中使用 [ **以系統管理員身分執行** ] 或使用 `sudo` macOS 或 Linux 中的命令來啟動 PowerShell 會話。

如果您使用的是 PowerShell 5.1，您必須事先更新 **PowerShellGet** 模組。 更新 **PowerShellGet**之後，請關閉並重新開啟提升許可權的 PowerShell 會話，以確保載入最新的 **PowerShellGet** 。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

若要安裝團隊 PowerShell 公開預覽版，請執行下列 PowerShell 命令。

> [!NOTE]
> 您可以透過執行「Find-Module MicrosoftTeams-AllowPrerelease」，在 [Powershell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams) 或 powershell 中尋找最新的預覽版本。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>安裝商務用 Skype Online 連接器

> [!NOTE]
>
> 商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。
> 如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>登錄

若要開始使用團隊 PowerShell，請使用您的 Azure 認證登入。

> [!NOTE]
> 如果您使用的是最新的 [團隊 PowerShell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>更新團隊 PowerShell

若要更新團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果團隊 PowerShell 已匯入您的 PowerShell 會話，更新模組將會失敗。 關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。


## <a name="uninstall-teams-powershell"></a>卸載團隊 PowerShell



若要卸載團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 如果團隊 PowerShell 已匯入您的 PowerShell 會話，則卸載模組將會失敗。 關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。

## <a name="next-steps"></a>後續步驟

現在您已經準備好使用團隊 PowerShell 管理團隊。 請參閱 [使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md) 以開始使用。

## <a name="related-topics"></a>相關主題

[使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)

[團隊 PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
