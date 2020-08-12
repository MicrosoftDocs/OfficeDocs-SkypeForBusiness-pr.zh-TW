---
title: 使用 Microsoft 端點建構管理員安裝團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: 使用 Microsoft 端點設定管理員來大量部署 Microsoft 團隊以選取使用者或電腦。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55a514aa6aec6991e331b445a2fbb6e9c602ac91
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640828"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft 端點 Configuration Manager 安裝 Microsoft 團隊

> [!Tip]
> 請觀看下列會話，瞭解 Windows 桌面用戶端的優點，以及如何進行規劃，以及部署方式：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)。

若要使用 Microsoft 端點設定管理員（或群組原則），或適用于廣泛部署的任何協力廠商發佈機制，Microsoft 提供的 MSI 檔案 (32 位和64位) ，管理員可以使用它來大量部署團隊來選取使用者或電腦。 系統管理員可以使用這些檔案來遠端部署團隊，讓使用者不需要手動下載團隊 app。 部署時，小組會自動啟動在該電腦上登入的所有使用者。  (您可以在安裝應用程式後停用自動啟動。 [請參閱下方](#disable-auto-launch-for-the-msi-installer)。 ) 建議您將套件部署到電腦，所以電腦的所有新使用者也都能從這個部署獲益。

以下是 MSI 檔案的連結：

|實體  |32位      |64位      |
|---------|---------|---------|
|商用     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|聯邦政府-GCC     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|聯邦政府-GCC 高    | [32位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|聯邦政府-DoD     | [32位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

**若要確保成功地進行部署，請注意下列事項：**

- 在64位作業系統上安裝64位版本的團隊。 如果您嘗試在32位作業系統上安裝64位版本的團隊，安裝將無法成功完成，而且目前您不會收到錯誤訊息。

- 如果客戶租使用者是在 GCCH 或 DoD 雲彩，客戶應該在登錄中將**CloudType**值新增到登錄的**HKEY_CURRENT_USER \software\policies\microsoft\office\16.0\teams**金鑰中，以設定初始端點。 **CloudType**的類型是**DWORD** ，而值是 (0 = 取消，1 = 商業，2 = GCC，3 = GCCH，4 = DOD) 。 使用登錄金鑰設定端點會限制團隊連線至正確的雲端端點，以與團隊進行預先登入連線。

- 團隊也可以包含在企業版 Microsoft 365 應用程式的部署中。 如需詳細資訊，請參閱[使用適用于企業的 microsoft 365 應用程式部署 Microsoft 團隊](https://docs.microsoft.com/deployoffice/teams-install)。

- 若要深入瞭解 Microsoft Endpoint Configuration Manager，請參閱[何謂 Configuration manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>建議) 的部署程式 (

1. 取得最新套件。
2. 使用 MSI 預先填入的預設值。
3. 如有可能，請部署到電腦。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 團隊 MSI 套件的運作方式

### <a name="pc-installation"></a>電腦安裝

[團隊 MSI] 會在程式檔案中放置安裝程式。 每當使用者登入新的 Windows 使用者設定檔時，系統就會啟動安裝程式，而且會在該使用者的資料夾中安裝 [小組] app 的複本 `AppData` 。 如果使用者已在資料夾中安裝 [團隊] 應用程式 `AppData` ，則 MSI 安裝程式將會略過該使用者的進程。

請勿使用 MSI 來部署更新，因為用戶端會在檢測到可從服務取得新版本時自動更新。 若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。 如果您部署舊版的 MSI 套件，用戶端會自動更新 (但在使用 VDI 環境時，使用者可能會) 。 如果部署的是較舊的版本，MSI 將觸發應用程式更新，讓使用者能夠使用團隊。

> [!Important]
> 我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。 如果版本太舊，最終會封鎖使用者存取服務。

#### <a name="target-computer-requirements"></a>目的電腦需求

- .NET framework 4.5 或更新版本
- Windows 8.1 或更新版本
- Windows Server 2012 R2 或更新版本
- 每個使用者設定檔的 3 GB 磁碟空間 (建議) 

### <a name="vdi-installation"></a>VDI 安裝

如需如何在 VDI 上部署團隊桌面應用程式的完整指南，請參閱[虛擬化桌面基礎結構的團隊](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理及重新部署程式

如果使用者從使用者設定檔中移除團隊，MSI 安裝程式將會追蹤使用者已卸載小組應用程式，而且不會再安裝該使用者設定檔的小組。 若要在已卸載此使用者的特定電腦上重新部署團隊，請執行下列動作：

> [!IMPORTANT]
> 後續步驟包含如何修改註冊表的相關資訊。 修改之後，請務必先備份註冊表，然後在問題發生時，瞭解如何還原註冊表。 如需如何備份、還原及修改註冊表的詳細資訊，請參閱[適用于高級使用者的 Windows 註冊資訊](https://support.microsoft.com/help/256986)。

1. 卸載針對每個使用者設定檔所安裝的團隊 app。 如需詳細資訊，請參閱[卸載 Microsoft 團隊](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 在下遞迴刪除目錄 `%localappdata%\Microsoft\Teams\` 。
3. 刪除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 註冊表值。
4. 將 MSI 套件重新部署到該特定電腦。

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>避免團隊在安裝後自動啟動

MSI 的預設行為是在使用者登入後立即安裝 [小組] app，然後自動啟動小組。 如果您不想讓團隊在使用者安裝之後自動開始進行，您可以使用群組原則來設定策略設定，或停用 MSI 安裝程式的自動啟動。

### <a name="use-group-policy-recommended"></a>使用群組原則 (建議的) 

啟用 [在安裝群組原則設定**之後，禁止 Microsoft 小組自動啟動**]。 您可以在 User Configuration\Policies\Administrative Templates\Microsoft 團隊中找到此原則設定。 這是建議的方法，因為您可以根據組織的需求關閉或開啟原則設定。

在安裝團隊之前啟用此原則設定之後，小組就不會在使用者登入 Windows 時自動啟動。 使用者第一次登入團隊後，小組會在下次使用者登入時自動啟動。

若要深入瞭解，請參閱[使用群組原則避免團隊在安裝之後自動啟動](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果您已部署團隊，且想要將此原則設定為 [停用團隊自動啟動]，請先將 [群組原則] 設定設為 [您想要的值]，然後在每個使用者的基礎上執行團隊的 [[自動啟動] 重設腳本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>停用 MSI 安裝程式的自動啟動

您可以使用**選項 = "noAutoStart = true"** 參數來停用 MSI 安裝程式的自動啟動，如下所示。  

針對32位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

針對64位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

當使用者登入 Windows 時，會在 MSI 中安裝小組，並將開始團隊的快捷方式新增至使用者的桌面。 在使用者手動開始團隊前，小組將無法啟動。 使用者手動啟動團隊後，小組會在使用者登入時自動啟動。

請注意，這些範例也會使用**ALLUSERS = 1**參數。 當您設定此參數時，系統會在 [控制台] 的 [程式和功能] 和 [應用程式 & Windows 設定] 中的 [應用程式] 中，顯示「團隊電腦範圍」的安裝程式。 如果團隊在電腦上擁有管理員認證，則所有使用者都可以卸載小組。

> [!Note]
> 如果您是手動執行 MSI，請務必以提升許可權執行。 即使您是以系統管理員身分執行，而且不是以提升許可權執行，安裝程式也無法將選項設定為停用自動啟動。
