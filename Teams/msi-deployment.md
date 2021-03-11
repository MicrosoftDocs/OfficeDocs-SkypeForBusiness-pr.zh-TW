---
title: 使用 Microsoft 端點組組管理員安裝 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用 Microsoft 端點組組管理員大量部署 Microsoft Teams 以選取使用者或電腦。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cde5b2f04936afdd16eb7d0ff13a03840e6fa49
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50614949"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft 端點組組管理員安裝 Microsoft Teams

> [!Tip]
> 觀看下列會話以瞭解 Windows 桌面用戶端的好處、如何規劃它，以及如何部署 [：Teams Windows 桌面用戶端](https://aka.ms/teams-clients)。

若要使用 Microsoft 端點組態管理員、群組原則或任何協力廠商發佈機制進行廣泛部署，Microsoft 已提供 MSI 檔案 (32 位和 64 位) 系統管理員可用於大量部署 Teams 以選取使用者或電腦。 系統管理員可以使用這些檔案來遠端部署 Teams，讓使用者不需要手動下載 Teams 應用程式。 部署後，Teams 會針對所有在電腦中登錄的使用者自動啟動。  (安裝應用程式之後，您可以停用自動啟動。 [請參閱下方的](#disable-auto-launch-for-the-msi-installer).) 我們建議您將套件部署到電腦，這樣一來，這台電腦的所有新使用者也會從此部署獲益。

這些是 MSI 檔案的連結：

|實體  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商業     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美國政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - GCC High    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**若要確保部署成功，請注意下列事項：**

- 在 64 位作業系統上安裝 64 位版本的 Teams。 如果您嘗試在 32 位作業系統上安裝 64 位版本的 Teams，安裝將不會成功，而且您目前不會收到錯誤訊息。

- 如果客戶租使用者位於 GCCH 或 DoD 雲端上，客戶應新增 **CloudType** 值至HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams中的HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams鍵，以在註冊表中設定初始端點。 CloudType的類型是 **DWORD，** 值為 (0 = Unset，1 = 商業，2 = GCC，3 = GCCH，4 = DOD) 。 使用登錄鍵設定端點會限制 Teams 連接至正確的雲端端點，以使用 Teams 預先登錄連接。

- Teams 也可以包含在企業用 Microsoft 365 應用程式部署中。 詳細資訊請參閱使用[Microsoft 365 企業版應用程式部署 Microsoft Teams。](https://docs.microsoft.com/deployoffice/teams-install)

- 若要深入瞭解 Microsoft 端點組組管理員，請參閱 [什麼是 Configuration Manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>部署程式 (建議) 

1. 取回最新的套件。
2. 使用 MSI 預先預裝的預設值。
3. 盡可能部署到電腦。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI 套件如何運作

### <a name="pc-installation"></a>電腦安裝

Teams MSI 將在程式檔案中放置安裝程式。 每當使用者進入新的 Windows 使用者設定檔時，安裝程式就會啟動，而 Teams App 的一份副本會安裝在該使用者 `AppData` 的資料夾中。 如果使用者已在資料夾中安裝 Teams 應用程式 `AppData` ，MSI 安裝程式會略過該使用者的程式。

請勿使用 MSI 來部署更新，因為當用戶端偵測到新版本時，服務就會自動更新。 若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。 如果您部署舊版 MSI 套件，用戶端會自動更新 (VDI 環境除外) 盡可能讓使用者使用。 如果部署非常舊的版本，MSI 會先觸發應用程式更新，使用者才能使用 Teams。

> [!IMPORTANT]
> 預設位置為 64 位作業系統上的 C：\Program Files (x86) \Teams Installer，以及 32 位作業系統上的 C：\Program Files\Teams Installer。
> 我們不建議您變更預設安裝位置，因為這樣做可能會中斷更新流程。 如果版本太舊，最後會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

- .NET framework 4.5 或更高版本
- Windows 8.1 或更新版本
- Windows Server 2012 R2 或更新版本
- 每個使用者設定檔的磁碟空間為 3 GB， (建議) 

### <a name="vdi-installation"></a>VDI 安裝

有關如何在 VDI 上部署 Teams 桌面應用程式的完整指引，請參閱 [Teams 虛擬桌面基礎結構](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署程式

如果使用者從使用者設定檔卸載 Teams，MSI 安裝程式會追蹤該使用者已卸載 Teams 應用程式，並且不再安裝該使用者設定檔的 Teams。 若要將這個使用者的 Teams 重新部署到已卸載的特定電腦上，請執行下列操作：

> [!IMPORTANT]
> 接下來的步驟包含如何修改註冊表的資訊。 請確定您先備份註冊，再進行修改，並瞭解如何在發生問題時還原該註冊表。 若要進一步瞭解如何備份、還原及修改登錄，請參閱 [進一步使用者的 Windows](https://support.microsoft.com/help/256986)登錄資訊。

1. 卸載針對每個使用者設定檔安裝的 Teams 應用程式。 詳細資訊請參閱卸載[Microsoft Teams。](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)
2. 在 下遞迴刪除目錄 `%localappdata%\Microsoft\Teams\` 。
3. 刪除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 註冊表值。
4. 將 MSI 套件重新部署到該特定電腦。

> [!TIP]
> 您也可以使用我們的 Teams [部署清理腳本](scripts/powershell-script-deployment-cleanup.md) 來完成步驟 1 和 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>防止 Teams 在安裝後自動啟動

MSI 的預設行為是，使用者一旦登錄，即安裝 Teams 應用程式，然後自動啟動 Teams。 如果您不希望 Teams 在安裝後自動為使用者啟動，您可以使用群組原則設定或停用 MSI 安裝程式的自動啟動。

### <a name="use-group-policy-recommended"></a>使用群組原則 (建議) 

啟用安裝 **群組原則設定後** ，防止 Microsoft Teams 自動啟動。 您可以在 User Configuration\Policies\Administrative Templates\Microsoft Teams 中找到此策略設定。 這是建議的方法，因為您可以根據組織的需求關閉或開啟策略設定。

當您在安裝 Teams 之前啟用此策略設定時，使用者登入 Windows 時，Teams 不會自動啟動。 使用者第一次登錄 Teams 之後，下一次使用者登錄時，Teams 就會自動啟動。

若要深入瞭解，請參閱 [使用群組原則來防止 Teams 在安裝後自動啟動](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果您已經部署 [Teams，](scripts/powershell-script-teams-reset-autostart.md) 並想要設定此策略以停用 Teams 自動啟動，請先將群組原則設定設定為您想要的值，然後根據每個使用者執行 Teams 自動啟動重設腳本。

### <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

您可以使用 **OPTIONS="noAutoStart=true"** 參數停用 MSI 安裝程式的自動啟動，如下所示。  

針對 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

當使用者以 Windows 登錄時，Teams 會與 MSI 一起安裝，而啟動 Teams 的快捷方式會新增到使用者的桌面。 在使用者手動啟動 Teams 之前，Teams 不會啟動。 使用者手動啟動 Teams 之後，每當使用者進行登錄時，Teams 就會自動啟動。

請注意，這些範例也會使用 **ALLUSERS=1** 參數。 當您設定此參數時，Machine-Wide安裝程式會出現在控制台中的程式和功能中，以及 Windows &所有使用者的 Windows 設定中的應用程式功能。 所有使用者在電腦上擁有系統管理員認證時，都可以卸載 Teams。

> [!Note]
> 如果您手動執行 MSI，請務必以較高的權限執行。 即使您以系統管理員的目前狀態執行，但不以較高的權限執行，安裝程式將無法設定停用自動啟動的選項。
