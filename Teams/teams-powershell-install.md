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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6ba8545159f8b18ebe39e49356f64378f946b29
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874803"
---
# <a name="install-microsoft-teams-powershell"></a>安裝 Microsoft Teams PowerShell

本文說明如何使用 PowerShellGet 安裝 Microsoft Teams [PowerShell 模組](/powershell/scripting/gallery/installing-psget)。 這些指示可于 [Azure Cloud Shell、Linux、macOS](/azure/cloud-shell/overview)和 Windows 平臺上使用。

## <a name="requirements"></a>需求

Teams PowerShell 需要在所有平臺上使用 PowerShell 5.1 或更高版本。 安裝[適用于您作業系統的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)

> [!WARNING]
> PowerShell 7 和 Teams PowerShell 有已知問題。 為了獲得最佳體驗，建議您使用 PowerShell 5.1。

## <a name="install-the-teams-powershell-module"></a>安裝 Teams PowerShell 模組

> [!NOTE]
> 為了獲得最佳體驗，請使用一般 (GA) 或公用預覽模組 -而不是兩者。 它們並不適合共同作業。


使用 **PowerShellGet** Cmdlet 來安裝 Teams PowerShell 模組。 在系統上為所有使用者安裝模組時，需要提升許可權。 使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令：

```powershell
Install-Module MicrosoftTeams
```

根據預設，PSGallery (的 PowerShell 圖庫) 未配置為 **PowerShellGet** 的受信任的存放庫。 第一次使用 PSGallery 時，會看到下列訊息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 **是** 或 **全部是** 以繼續安裝。


## <a name="install-teams-powershell-public-preview"></a>安裝 Teams PowerShell 公開預覽版

> [!NOTE]
> 如果您使用的是 Teams PowerShell 的公用預覽版，我們強烈建議您先卸載商務用 Skype Online Connector。

在系統上為所有使用者安裝 Teams PowerShell 公用預覽模組時，需要提升許可權。 使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令。

如果您使用的是 PowerShell 5.1，則必須事先更新 **PowerShellGet** 模組。 更新 **PowerShellGet** 之後，關閉並重新開啟提升的 PowerShell 會話，以確保載入最新的 **PowerShellGet。**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

若要安裝 Teams PowerShell 公開預覽版，請執行下方的 PowerShell 命令。

> [!NOTE]
> 您可以在 PowerShell 圖庫或 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 中，使用「Find-Module MicrosoftTeams -AllowPrerelease -AllVersions」來尋找最新的預覽版本

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>安裝商務用 Skype Online 連接器

> [!NOTE]
>
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。
> 如果您使用的是最新的 [Teams PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，則不需要安裝商務用 Skype Online 連接器。


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>登錄

若要開始使用 Teams PowerShell，請以 Azure 認證來登錄。

> [!NOTE]
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開預覽版，則不需要安裝商務用 Skype Online 連接器。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>使用 MFA 和新式驗證來登錄

 如果您的帳戶使用多重要素驗證，請使用本節中的步驟。

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>更新 Teams PowerShell

若要更新 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果 Teams PowerShell 已導入 PowerShell 會話，更新模組將會失敗。 關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。


## <a name="uninstall-teams-powershell"></a>卸載 Teams PowerShell



若要卸載 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 如果 Teams PowerShell 已導入 PowerShell 會話，卸載模組將會失敗。 關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。

## <a name="next-steps"></a>後續步驟

現在，您已準備好使用 Teams PowerShell 來管理 Teams。 請參閱 [使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以開始使用。

## <a name="related-topics"></a>相關主題

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
