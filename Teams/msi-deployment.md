---
title: 使用 Windows Installer (MSI) 大量安裝 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用 Windows Installer (MSI) 檔案，將 Teams 用戶端發佈給多個使用者和電腦。
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
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713321"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>使用 Windows Installer (MSI) 大量安裝 Teams

> [!Tip]
> 請觀看下列會話，以瞭解 Windows 桌面用戶端的優點、如何規劃及部署： [Teams Windows 桌面用戶端](https://aka.ms/teams-clients)。

Microsoft 提供 32 位、64 位和 ARM64 MSI 檔案，您可以使用這些檔案大量部署 Microsoft Teams 來選取使用者和電腦。 MSI 檔案可以與[Microsoft 端點Configuration Manager](/configmgr/core/understand/introduction)、[群組原則](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)或協力廠商發佈軟體搭配使用，以將 Teams 部署到您的組織。 大量部署很有用，因為使用者不需要手動下載及安裝 Teams 用戶端。 相反地，Teams 會部署到電腦，然後在使用者第一次登入電腦時自動啟動。

建議您將套件部署到電腦，而不是將特定使用者部署。 藉由以電腦為目標，這些電腦的所有新使用者將受益于此部署。

>[!NOTE]
> 團隊也可以在Microsoft 365 Apps 企業版中發佈給您的組織。 如需詳細資訊，請參閱[使用 Microsoft 365 Apps 企業版 部署 Microsoft Teams](/deployoffice/teams-install)。

## <a name="msi-files"></a>MSI 檔案

下表提供適用于 Teams 的 32 位、64 位和 ARM64 MSI 檔案的連結。 下載您要安裝在組織電腦上的 MSI。  (32 位或 64 位) Teams 支援的 x86 架構，與電腦上安裝的其他 Office 應用程式無關。

如果您有 64 位電腦，建議您安裝 64 位的 Teams MSI，即使電腦執行的是 32 位版本的 Office。 ARM64 MSI 只能安裝在使用 ARM 架構的電腦上，例如 Surface Pro X。

> [!IMPORTANT]
> 只在 64 位作業系統上安裝 64 位版本的 Teams。 如果您嘗試在 32 位作業系統上安裝 64 位版本的 Teams，安裝將無法成功，也不會收到錯誤訊息。

|實體  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商業     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美國政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - GCC High    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Microsoft Teams MSI 檔案的運作方式

### <a name="pc-installation"></a>電腦安裝

Teams MSI 會在 `%SystemDrive%\Program Files\Teams Installer` 32 位 Windows 和 `%SystemDrive%\Program Files (x86)\Teams Installer` 64 位 Windows 上放置安裝程式。 每當使用者登入新的 Windows 使用者設定檔時，就會啟動安裝程式，並在該使用者的資料夾中安裝 Teams 應用程式的 `%LocalAppData%\Microsoft\Teams` 複本。 如果使用者已在資料夾中 `%LocalAppData%\Microsoft\Teams` 安裝 Teams 應用程式，MSI 安裝程式會略過該使用者的程式。

MSI 檔案無法用來部署更新。 Teams 用戶端會在偵測到服務中提供的新版本時自動更新。 若要重新部署最新的安裝程式，請使用下方所述的重新部署 MSI 程式。 如果您部署較舊版本的 MSI 檔案，用戶端會自動更新 (，但 VDI 環境中) 使用者可能的情況除外。 如果部署非常舊的版本，MSI 會觸發應用程式更新，使用者才能使用 Teams。

> [!IMPORTANT]
> 我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。 使用過舊的版本最終會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

確定您安裝 Teams 的電腦符合 [Microsoft Teams 硬體需求](hardware-requirements-for-the-teams-app.md)中列出的需求。

### <a name="vdi-installation"></a>VDI 安裝

如需如何在 VDI 上部署 Teams 桌面應用程式的完整指導方針，請參閱 [適用于虛擬化桌面基礎結構的 Teams](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署程式

如果使用者從使用者設定檔卸載 Teams，MSI 安裝程式會追蹤使用者已卸載 Teams 應用程式，且不再安裝該使用者設定檔的 Teams。 若要在已卸載的特定電腦上為此使用者重新部署 Teams，請執行下列動作：

> [!IMPORTANT]
> 接下來的步驟包含如何修改登錄的相關資訊。 請務必先備份登錄，再進行修改，並瞭解發生問題時如何還原登錄。 如需有關如何備份、還原及修改登錄的詳細資訊，請參閱 [進階使用者的 Windows 登錄資訊](https://support.microsoft.com/help/256986)。

1. 卸載每個使用者設定檔所安裝的 Teams 應用程式。 如需詳細資訊，請參閱 [卸載 Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 在每個使用者設定檔底下 `%LocalAppData%\Microsoft\Teams\` ，週期性地刪除目錄。
3. 刪除每個使用者設定檔的 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 登錄值。
4. 將 MSI 檔案重新部署到該特定電腦。

> [!TIP]
> 您也可以使用我們的 [Teams 部署清理腳本](scripts/powershell-script-deployment-cleanup.md) 來完成步驟 1 和 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>防止 Teams 在安裝後自動啟動

MSI 的預設行為是在使用者登入後立即安裝 Teams 應用程式，然後自動啟動 Teams。 如果您不希望使用者在 Teams 安裝之後自動啟動，您可以使用群組原則來設定原則設定或停用 MSI 安裝程式的自動啟動。

### <a name="use-group-policy-recommended"></a>使用建議群組原則 () 

啟用 **[防止 Microsoft Teams 在安裝後自動啟動**[群組原則](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)設定。 您可以在 **Microsoft Teams** 的 **[使用者設定** \\ **原則** \\ **管理模** \\ 板] 中找到此原則設定。 這是建議的方法，因為您可以根據組織的需求關閉或開啟原則設定。

當您在安裝 Teams 之前啟用此原則設定時，當使用者登入 Windows 時，Teams 並不會自動啟動。 使用者第一次登入 Teams 後，Teams 會在使用者下次登入時自動啟動。

若要深入瞭解，請參閱[使用群組原則防止 Teams 在安裝後自動啟動](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果您已經部署 Teams，並想要設定此原則來停用 Teams 自動啟動，請先將群組原則設定設為您要的值，然後按個別使用者執行[Teams 自動啟動重設腳本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

您可以使用下列參數，停用 MSI 安裝程式的 `OPTIONS="noAutoStart=true"` 自動啟動。  

針對 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

當使用者登入 Windows 時，Teams 會與 MSI 一起安裝。 在使用者手動啟動 Teams 之前，Teams 不會啟動。 使用者手動啟動 Teams 之後，每當使用者登入時，Teams 都會自動啟動。

請注意，這些範例也會使用 **ALLUSERS=1** 參數。 當您設定此參數時，Teams Machine-Wide安裝程式會出現在 主控台 的 [程式和功能] 以及 [Windows 設定] 中 [應用程式] &功能中，以供電腦的所有使用者使用。 如果所有使用者在電腦上都有系統管理員認證，就可以卸載 Teams。

> [!Note]
> 如果您手動執行 MSI，請務必以提升許可權執行。 即使您以系統管理員身分執行，但未以提升許可權執行，安裝程式將無法設定停用自動啟動的選項。
