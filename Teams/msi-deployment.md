---
title: '在 MSI Teams安裝程式Windows大量 (安裝) '
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用 Windows安裝程式 (MSI) 檔案，將Teams用戶端發佈給多個使用者和電腦。
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
ms.openlocfilehash: fc9e17f958b1770573cf6729ef6aca9b22ffe03d
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893562"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>在 MSI Teams安裝程式Windows大量 (安裝) 

> [!Tip]
> 觀看下列會話以瞭解桌面用戶端Windows、如何規劃及部署：Teams Windows[桌面用戶端](https://aka.ms/teams-clients)。

Microsoft 提供 32 位、64 位和 ARM64 MSI 檔案，您可以使用這些檔案大量部署Microsoft Teams選取使用者和電腦。 MSI 檔案可以與[Microsoft Endpoint Configuration Manager、](/configmgr/core/understand/introduction)[組](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)策略或協力廠商發佈軟體一Teams部署至貴組織。 大量部署很有用，因為使用者不需要手動下載並安裝Teams用戶端。 相反地Teams，系統將會部署至電腦，然後在使用者第一次登錄電腦時自動啟動。

我們建議您將套件部署到電腦，而不是特定使用者。 以電腦為目標，這些電腦的所有新使用者都會受益于此部署。

>[!NOTE]
> Teams發佈至貴組織，做為Microsoft 365 Apps 企業版。 詳細資訊，請參閱使用Microsoft Teams[部署Microsoft 365 Apps 企業版](/deployoffice/teams-install)。

## <a name="msi-files"></a>MSI 檔案

下表提供 32 位、64 位和 ARM64 MSI 檔案的連結，Teams。 下載您想要安裝在貴組織電腦上的 MSI。 x86 架構 (32 位或 64 位) Teams與電腦上安裝的其他Office應用程式無關。

如果您有 64 位電腦，建議您安裝 64 位 Teams MSI，即使電腦是 32 位版本的 Office。 ARM64 MSI 只能安裝在使用 ARM 架構的電腦上，例如 X Surface Pro安裝。

> [!IMPORTANT]
> 僅于 64 位作業系統Teams 64 位版本的版本。 如果您嘗試在 32 位作業系統上Teams 64 位版本的 Teams，安裝將不會成功，也不會收到錯誤訊息。

|實體  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商業     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美國政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - GCC高    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美國政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>MSI 檔案Microsoft Teams運作方式

### <a name="pc-installation"></a>電腦安裝

MSI Teams MSI `%SystemDrive%\Program Files\Teams Installer` 將安裝程式放在 32 `%SystemDrive%\Program Files (x86)\Teams Installer` 位Windows 64 位Windows。 每當使用者以新的使用者Windows登錄時，安裝程式就會啟動，Teams應用程式的副本會安裝在該使用者的資料夾中 `%LocalAppData%\Microsoft\Teams` 。 如果使用者已在資料夾中安裝 `%LocalAppData%\Microsoft\Teams` Teams應用程式，MSI 安裝程式會略過該使用者的程式。

MSI 檔案無法用來部署更新。 Teams用戶端會在偵測到可從服務使用新版本時自動更新。 若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。 如果您部署舊版 MSI 檔案，用戶端會自動更新 (VDI 環境除外) 使用者可能的話。 如果部署非常舊的版本，MSI 會先觸發應用程式更新，使用者才能Teams。

> [!IMPORTANT]
> 我們不建議您變更預設安裝位置，因為這樣做可能會中斷更新流程。 版本太舊，最終會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

請確定您安裝的電腦Teams符合硬體需求中列出的[Microsoft Teams。](hardware-requirements-for-the-teams-app.md)

### <a name="vdi-installation"></a>VDI 安裝

若要瞭解如何在 VDI 上部署Teams桌面應用程式的完整指南，請參閱[Teams桌面基礎結構的指南](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署程式

如果使用者從使用者設定檔Teams，MSI 安裝程式會追蹤使用者已卸載 Teams 應用程式，且不再安裝Teams設定檔的 Teams。 若要將Teams使用者重新部署至已卸載的特定電腦上，請執行下列操作：

> [!IMPORTANT]
> 下列步驟包含如何修改註冊表的資訊。 請務必先備份該註冊表，再進行修改，並瞭解如何在發生問題時還原註冊表。 若要進一步瞭解如何備份、還原及修改登錄，請參閱Windows使用者的登錄[資訊](https://support.microsoft.com/help/256986)。

1. 卸載Teams設定檔安裝的應用程式。 若要詳細資訊，請參閱卸載[Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 針對每個使用者設定檔以遞迴 `%LocalAppData%\Microsoft\Teams\` 式刪除目錄。
3. 刪除每個 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 使用者設定檔的登錄值。
4. 將 MSI 檔案重新部署至該特定電腦。

> [!TIP]
> 您也可以使用我們的部署清理Teams[腳本](scripts/powershell-script-deployment-cleanup.md)來完成步驟 1 和 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>防止Teams安裝後自動啟動

MSI 的預設行為是，使用者一Teams安裝應用程式，然後自動Teams。 如果您不希望系統安裝Teams使用者自動啟動，您可以使用群組原則設定或停用 MSI 安裝程式的自動啟動。

### <a name="use-group-policy-recommended"></a>使用群組原則 (建議) 

啟用安裝 **Microsoft Teams自動啟動組**[策略](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)設定。 您可以在 User **ConfigurationPoliciesAdministrist-templates** \\ **** \\ **** \\ **中** 找到此Microsoft Teams。 這是建議的方法，因為您可以根據組織的需求關閉或開啟策略設定。

當您在安裝之前啟用此Teams設定時，Teams登入系統時，系統不會自動Windows。 使用者第一次Teams之後，Teams下次使用者登錄時，系統會自動啟動。

若要深入瞭解，請參閱[使用群組原則防止Teams安裝後自動啟動。](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)

> [!CAUTION]
> 如果您已經部署 Teams，並想要設定此策略以停用 Teams 自動啟動，請先將群組原則設定設為您想要的值，然後根據每個使用者執行[Teams](scripts/powershell-script-teams-reset-autostart.md)自動啟動重設腳本。

### <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

您可以使用參數來停用 MSI 安裝程式 `OPTIONS="noAutoStart=true"` 的自動啟動，如下所示。  

針對 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

針對 64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

當使用者以 msI Windows時Teams，系統即會以 MSI 安裝，Teams快捷方式會新增到使用者的桌面。 Teams使用者手動啟動Teams。 在使用者手動啟動Teams，Teams使用者每次登錄時自動啟動。

請注意，這些範例也會使用 **ALLUSERS=1** 參數。 當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，&應用程式Windows 設定所有電腦使用者Windows 設定中的功能。 如果使用者在電腦上擁有系統管理員Teams，則所有使用者都可以卸載這些帳戶。

> [!Note]
> 如果您手動執行 MSI，請務必以較高的權限執行。 即使您以系統管理員執行，但不以較高的權限執行，安裝程式將無法設定停用自動啟動的選項。
