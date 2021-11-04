---
title: 使用 Teams 安裝Microsoft Endpoint Configuration Manager
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 您可以使用 Microsoft Endpoint Configuration Manager大量部署Microsoft Teams以選取使用者或電腦。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d8344c0b8a40f39816ce3a14dc79fb66d3fd965
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758275"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft Teams 安裝Microsoft Endpoint Configuration Manager

> [!Tip]
> 觀看下列會話以瞭解桌面用戶端Windows、如何規劃及部署它：Teams Windows[用戶端](https://aka.ms/teams-clients)。

若要使用 Microsoft Endpoint Configuration Manager、群組原則或任何協力廠商發佈機制進行廣泛部署，Microsoft 已提供 MSI 檔案 (32 位和 64 位) 系統管理員可用於大量部署 Teams 以選取使用者或電腦。 系統管理員可以使用這些檔案來遠端部署Teams，讓使用者不需要手動下載Teams應用程式。 部署後，Teams將針對所有在該電腦上登錄的使用者自動啟動。  (安裝應用程式之後，您可以停用自動啟動。 [請參閱下方的](#disable-auto-launch-for-the-msi-installer).) 我們建議您將套件部署到電腦，因此電腦的所有新使用者也會受益于此部署。

這些是 MSI 檔案的連結：

|實體  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商業     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美國政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - GCC高    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**若要確保部署成功，請注意下列事項：**

- 在 64 位作業系統上Teams 64 位版本的作業系統。 如果您嘗試在 32 位作業系統上安裝 64 位版本的 Teams，安裝將不會成功，而且您目前不會收到錯誤訊息。

- 如果客戶租使用者位於 GCCH 或 DoD 雲端上，客戶應新增 **CloudType** 值至註冊表中的HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams鍵，以在註冊表中設定初始端點。 CloudType的類型是 **DWORD，** 值為 (0 = 未套用、1 = 商業、2 = GCC、3 = GCCH、4 = DOD) 。 使用登錄鍵設定端點Teams限制使用者連接到正確的雲端端點，以使用 Teams。

- Teams，也可以包含在部署 Microsoft 365 Apps 企業版。 詳細資訊，請參閱使用 Microsoft Teams[部署Microsoft 365 Apps 企業版。](/deployoffice/teams-install)

- 若要進一Microsoft Endpoint Configuration Manager，請參閱什麼是 Configuration [Manager？](/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>部署程式 (建議) 

1. 取回最新的套件。
2. 使用 MSI 預先填充的預設值。
3. 盡可能部署到電腦。

## <a name="how-the-microsoft-teams-msi-package-works"></a>MSI 套件Microsoft Teams運作方式

### <a name="pc-installation"></a>電腦安裝

MSI Teams將安裝程式放在程式檔案中。 每當使用者登錄新的 Windows使用者設定檔時，安裝程式就會啟動，Teams應用程式的副本會安裝在該使用者 `AppData` 的資料夾中。 如果使用者已在資料夾中Teams應用程式 `AppData` ，MSI 安裝程式會略過該使用者的程式。

請勿使用 MSI 來部署更新，因為當用戶端偵測到可從服務使用新版本時，就會自動更新。 若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。 如果您部署舊版 MSI 套件，用戶端會自動更新 (VDI 環境除外) 使用者可能的話。 如果部署非常舊的版本，MSI 會先觸發應用程式更新，使用者才能Teams。

> [!IMPORTANT]
> 預設位置為 64 位作業系統上的 C：\Program Files (x86) \Teams Installer，以及 32 位作業系統上的 C：\Program Files\Teams Installer。
> 我們不建議您變更預設安裝位置，因為這樣做可能會中斷更新流程。 版本太舊，最終會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

- .NET framework 4.5 或更高版本
- Windows 8.1或更高版本
- Windows Server 2012R2 或更高版本
- 每個使用者設定檔的磁碟空間為 3 GB， (建議) 

### <a name="vdi-installation"></a>VDI 安裝

若要瞭解如何在 VDI 上部署Teams桌面應用程式的完整指南，請參閱Teams桌面基礎結構[的指南](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署程式

如果使用者從Teams卸載，MSI 安裝程式會追蹤使用者已卸載 Teams 應用程式，且不再Teams使用者設定檔。 若要將Teams使用者重新部署至已卸載的特定電腦上，請執行下列操作：

> [!IMPORTANT]
> 下列步驟包含如何修改註冊表的資訊。 請務必先備份該註冊表，再進行修改，並瞭解如何在發生問題時還原註冊表。 若要進一步瞭解如何備份、還原及修改登錄，請參閱Windows使用者的登錄[資訊](https://support.microsoft.com/help/256986)。

1. 卸載每個Teams安裝的應用程式。 若要詳細資訊，請參閱卸載[Microsoft Teams。](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)
2. 在 下遞迴刪除目錄 `%localappdata%\Microsoft\Teams\` 。
3. 刪除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 註冊表值。
4. 將 MSI 套件重新部署至該特定電腦。

> [!TIP]
> 您也可以使用我們的部署清理[Teams腳本](scripts/powershell-script-deployment-cleanup.md)來完成步驟 1 和 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>防止Teams安裝後自動啟動

MSI 的預設行為是一旦使用者Teams安裝應用程式，然後自動Teams。 如果您不希望系統安裝Teams使用者自動啟動，您可以使用群組原則設定或停用 MSI 安裝程式的自動啟動。

### <a name="use-group-policy-recommended"></a>使用群組原則 (建議) 

啟用安裝 **Microsoft Teams自動啟動組** 策略設定。 您可以在 User Configuration\Policy\Administrative Templates\Microsoft Teams 找到此Microsoft Teams。 這是建議的方法，因為您可以根據組織的需求關閉或開啟策略設定。

當您在安裝之前啟用此Teams設定時，Teams登入系統時，系統不會自動Windows。 使用者第一次Teams之後，Teams下次使用者登錄時，系統會自動啟動。

若要深入瞭解，請參閱[使用群組原則防止Teams安裝後自動啟動。](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)

> [!CAUTION]
> 如果您已經部署 Teams 並想要設定此策略以停用 Teams 自動啟動，請先將群組原則設定設為您想要的值，然後根據每個使用者執行[Teams](scripts/powershell-script-teams-reset-autostart.md)自動啟動重設腳本。

### <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

您可以使用 **OPTIONS="noAutoStart=true"** 參數來停用 MSI 安裝程式的自動啟動，如下所示。  

針對 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

針對 64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

當使用者以 msI Windows時Teams，系統即會使用 MSI 安裝Teams快捷方式會新增到使用者的桌面。 Teams使用者手動啟動Teams。 在使用者手動啟動Teams，Teams使用者每次登錄時自動啟動。

請注意，這些範例也會使用 **ALLUSERS=1** 參數。 當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，&應用程式會顯示Windows 設定適用于電腦的所有使用者。 然後所有使用者都可以卸載Teams，如果他們的電腦上有系統管理員認證。

> [!Note]
> 如果您手動執行 MSI，請務必以較高的權限執行。 即使您以系統管理員執行，但不以較高的權限執行，安裝程式將無法設定停用自動啟動的選項。