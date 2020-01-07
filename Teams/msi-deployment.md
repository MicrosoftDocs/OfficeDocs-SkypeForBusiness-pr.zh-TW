---
title: 透過 SCCM 使用 MSI 安裝 Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 系統管理員可以使用團隊 MSI 來大量部署 Microsoft 團隊來選取使用者或電腦。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a621c4e1cfcf9e485b68fd96a76d9179cef84a48
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952596"
---
# <a name="install-microsoft-teams-using-msi"></a>使用 MSI 安裝 Microsoft 團隊

> [!Tip]
> 請觀看下列會話，瞭解 Windows 桌面用戶端的優點，以及如何進行規劃，以及部署方式：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)

若要使用 System Center Configuration Manager，或群組原則，或適用于廣泛部署的任何協力廠商發佈機制，Microsoft 提供了 MSI 檔案（32位與64位），管理員可以使用它來大量部署團隊來選取使用者或電腦。 系統管理員可以使用這些檔案來遠端部署團隊，讓使用者不需要手動下載團隊 app。 部署時，小組會自動啟動在該電腦上登入的所有使用者。 （您可以在安裝應用程式後停用自動啟動。 [請參閱下文](#disable-auto-launch-for-the-msi-installer)。）我們建議您將套件部署到電腦，讓電腦的所有新使用者也能從這項部署獲益。

以下是 MSI 檔案的連結：


|實體  |32位      |64位      |
|---------|---------|---------|
|商用     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|聯邦政府-GCC     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|聯邦政府-GCC 高    | [32位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|聯邦政府-DoD     | [32位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

團隊也可以包含在 Office 365 專業增強版的部署中。 如需詳細資訊，請參閱[使用 Office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/deployoffice/teams-install)。

> [!Note]
> 若要深入瞭解 SCCM，請參閱[System Center Configuration Manager 簡介](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署程式（建議使用）

1. 取得最新套件。
2. 使用 MSI 預先填入的預設值。
3. 如有可能，請部署到電腦。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 團隊 MSI 套件的運作方式

### <a name="pc-installation"></a>電腦安裝

[團隊 MSI] 會在程式檔案中放置安裝程式。 每當使用者登入新的 Windows 使用者設定檔時，系統就會啟動安裝程式，並將 [小組] app 複本安裝在該使用者的 appdata 資料夾中。 如果使用者已在 appdata 資料夾中安裝 [團隊] 應用程式，MSI 安裝程式將會略過該使用者的程式。

請勿使用 MSI 來部署更新，因為用戶端會在檢測到可從服務取得新版本時自動更新。 若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。如果您部署舊版的 MSI 套件，則用戶端可能會自動更新（在 VDI 環境中除外）。 如果部署的是較舊的版本，MSI 將觸發應用程式更新，讓使用者能夠使用團隊。

> [!Important]
> 我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。 如果版本太舊，最終會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

- .NET framework 4.5 或更新版本
- Windows 7 或更新版本
- 每個使用者設定檔 3 GB 的磁碟空間（建議使用）

### <a name="vdi-installation"></a>VDI 安裝

如需如何在 VDI 上部署團隊桌面應用程式的完整指南，請參閱[虛擬化桌面基礎結構的團隊](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理及重新部署程式

如果使用者從使用者設定檔中移除團隊，MSI 安裝程式將會追蹤使用者已卸載小組應用程式，而且不會再安裝該使用者設定檔的小組。 若要在已卸載此使用者的特定電腦上重新部署團隊，請執行下列動作：

1. 針對每個使用者設定檔卸載已安裝的團隊 App。
2. 卸載之後，以遞迴方式在%localappdata%\Microsoft\Teams\. 下刪除目錄
3. 將 MSI 套件重新部署到該特定電腦。

> [!TIP]
> 您可以使用我們的[Microsoft 團隊部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)腳本，透過 SCCM 完成步驟1和2。

## <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

MSI 的預設行為是在使用者登入後立即安裝團隊用戶端，然後自動啟動團隊。 您可以使用下列參數來修改此行為，如下所示：

- 當使用者登入 Windows 時，系統會使用 MSI 安裝團隊
- 不過，小組用戶端將無法啟動，直到使用者手動開始團隊為止
- [開始] 團隊的快捷方式將會新增至使用者的桌面
- 手動開始之後，每次使用者登入時，小組就會自動啟動

針對32位版本
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
針對64位版本
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> 如果您是手動執行 MSI，請務必以提升許可權執行。 即使您是以系統管理員身分執行，而且不是以提升許可權執行，安裝程式也無法將選項設定為停用自動啟動。
