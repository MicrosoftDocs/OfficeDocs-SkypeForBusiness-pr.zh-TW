---
title: 取得 Microsoft Teams 用戶端
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在電腦、Mac 及行動裝置上安裝適用於 Microsoft Teams 的各種用戶端。
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33175aecc41dbc631fe8ab16db225762969b5ad6
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614035"
---
# <a name="get-clients-for-microsoft-teams"></a>取得 Microsoft Teams 用戶端

> [!TIP]
> **想要在您的 PC、Mac 或行動裝置上安裝 Teams 嗎?** 請查看 [安裝 Teams 用戶端](https://go.microsoft.com/fwlink/?linkid=855754)。

Microsoft Teams 可以安裝在電腦、Mac 及行動裝置上，也可以透過網頁瀏覽器存取。 大部分使用者只要自行[安裝用戶端](https://go.microsoft.com/fwlink/?linkid=855754)，就可以開始使用 Teams。 安裝 Teams 用戶端之後，只需要使用使用者名稱和密碼登入。

如果您是 IT 專業人員，且想要深入了解有關 Teams 安裝體驗及其需求的資訊，請選取本文中的用戶端作業系統以了解更多資訊。

如需有關不同平台上每個用戶端功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="desktop-clients"></a>桌面用戶端

Teams 桌面用戶端是獨立應用程式及 [Microsoft 365 Apps 企業版](/deployoffice/teams-install)的一部分，適用於下列作業系統:

- Windows 的 32 位元和 64 位元版本 (8.1 或更新版本，不含 Windows 10 LTSC) 
- ARM 上適用於 Windows 10 的 ARM64 
- Windows Server (2012 R2 或更新版本)
- macOS
- Linux (`.deb` 和 `.rpm` 格式)
- Chrome OS (如需詳細資訊，請參閱[如何在 Chromebook 上使用 Microsoft Office](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions. Admin permissions aren't required to install the Teams client on Windows PCs but are required on Macs.

IT 專業人員可以選擇其偏好的方式，將安裝檔案發佈到組織中的電腦。 例如 Microsoft Endpoint Configuration Manager (Windows) 或 Jamf Pro (macOS)。 如需發佈 Teams 的資訊，請參閱下列內容。

- **Windows** [使用 Endpoint Configuration Manager 安裝 Teams](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> 透過這些機制發佈的用戶端只適用於一開始的 Teams 用戶端安裝，不適用於未來的更新。 如需 Teams 更新流程的資訊，請參閱 [Teams 更新流程](teams-client-update.md)。

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> 請觀看下列工作階段，以了解 Windows 桌面版用戶端的優點、規劃方式及部署方式：[Teams 的 Windows 桌面版用戶端](https://aka.ms/teams-clients)

Windows 上的 Teams 在 [32 位元](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)、[64 位元](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)和 [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) 架構中提供可下載的 MSI 安裝程式。 Teams 的 x86 架構 (32 位元和 64 位元) 並不受限於已安裝的 Windows 和 Office 架構。 我們建議您在 64 位元系統上使用 64 位元版本的 Teams。

Teams 需要 .NET Framework 4.5 或更新版本。 如果未安裝 .NET Framework 或更新版本，Teams 安裝程式會為您提供安裝。

Windows 用戶端會部署至使用者設定檔中的 [AppData] 資料夾。 部署至使用者的本機設定檔中，即可在不需要提高權限的情況下安裝用戶端。 Windows 用戶端會利用下列位置：

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

使用者第一次使用 Teams 用戶端進行通話時，可能會注意到要求使用者允許通訊的 Windows 防火牆設定警告。 系統可能會指示使用者忽略這則訊息，因為即使忽略警告，您仍然能進行通話。

![Windows 安全性警示對話方塊的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows 防火牆設定將會變更。 TCP 和 UDP 通訊協定的兩個teams.exe輸入規則將以 
> - 如果使用者是本機系統管理員，並按一下 [僅允許存取]，請允許執行動作。
> - 如果使用者不是本機系統管理員，且在任何情況下選取 [取消] 關閉提示時，請封鎖動作。

如果您想要防止 Teams 在使用者第一次從 Teams 進行呼叫時提示使用者建立防火牆規則，請使用[範例指令碼 - Microsoft Teams 防火牆 PowerShell 指令碼](client-firewall-script.md)。

### <a name="mac"></a>[Mac](#tab/Mac)

Mac 使用者可以使用 macOS 電腦的 PKG 安裝檔來安裝 Teams。 安裝 Mac 用戶端必須具備系統管理存取權。 MacOS 用戶端會安裝至 /Applications 資料夾。

1. 在 **Mac** 底下的 [Teams 下載頁面](https://teams.microsoft.com/downloads)中，按一下 [下載]。
2. 按兩下 PKG 檔案。
3. 遵循安裝精靈來完成安裝。
4. Teams 將會安裝到 /Applications 資料夾。 這是全機器安裝。

> [!NOTE]
> 在安裝期間，PKG 會提示您輸入系統管理員認證。 無論使用者是否為系統管理員，使用者都需要輸入系統管理員認證。

如果使用者目前已具有 Teams 的 DMG 安裝，但想要將其取代為 PKG 安裝，使用者應該：

1. 結束 Teams 應用程式。
2. 取消安裝 Teams 應用程式。
3. 安裝 PKG 檔案。

IT 專業人員可以使用受管理的部署解決方案 (例如 Jamf Pro)，以將 Teams 安裝檔案發佈至其組織的所有 Mac。

### <a name="linux"></a>[Linux](#tab/Linux)

在 Linux 上，套件管理員 (例如 `apt` 和 `yum`) 會嘗試為您安裝任何需求。 不過，如果套件管理員沒有這麼做，您必須先安裝所有回報的需求，然後再安裝 Linux 版 Teams。

使用者能夠安裝 `.deb` 和 `.rpm` 格式的原生 Linux 套件。 安裝 DEB 或 RPM 套件時會自動安裝套件存放庫。

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

使用系統套件管理員來啟用自動更新所需的簽署金鑰也會自動安裝。 不過，也可以在以下位置找到：<https://packages.microsoft.com/keys/microsoft.asc>。 Teams 會每月傳送，而且如果存放庫安裝正確，則系統套件管理員會使用與系統中其他套件相同的方式處理自動更新。

#### <a name="install-teams-using-deb-package"></a>使用 DEB 套件安裝 Teams

1. 從 <https://aka.ms/getteams> 下載套件。
2. 利用下列其中一個選項進行安裝：
    - 開啟相關套件管理工具，並進行自助式 Linux 應用程式安裝程序。
    - 或者，如果您喜歡終端機，請輸入： `sudo dpkg -i **teams download file**`

您可以輸入 `teams`，以透過活動或終端機來啟動 Teams。

#### <a name="install-teams-using-rpm-package"></a>使用 RPM 套件來安裝 Teams

1. 從 <https://aka.ms/getteams> 下載套件。
2. 利用下列其中一個選項進行安裝：
    - 開啟相關套件管理工具，並進行自助式 Linux 應用程式安裝程序。
    - 或者，如果您喜歡終端機，請輸入： `sudo yum install **teams download file**`

您可以輸入 `teams`，以透過活動或終端機來啟動 Teams。

#### <a name="install-manually-from-the-command-line"></a>從命令列手動安裝

在 Debian 和 Ubuntu 發行版本上手動安裝：

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg

sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

在 RHEL、Fedora 和 CentOS 發行版本中手動安裝：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

或者，若要使用 yum (而不是 dnf)：

```bash
yum check-update
sudo yum install teams
```

在 openSUSE 發行版本上手動安裝：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>行動裝置用戶端

Teams 行動裝置應用程式適用於 Android 和 iOS，可讓使用者在任何地方參與聊天式對話，並且允許對等音訊通話。 若需行動裝置應用程式，請移至相關的行動裝置商店：Google Play 和 Apple App Store。

Teams 行動裝置應用程式支援的行動平台如下：

- **Android**：僅支援 Android 最新的四個主要版本。 發行新的 Android 主要版本時，此新版本和前三個版本都可受到正式支援。

- **iOS**：僅支援 iOS 最新的兩個主要版本。 發行新的 iOS 主要版本時，此新版 iOS 和前一版本都可受到正式支援。

> [!NOTE]
> 為了讓 Teams 正常運作，您必須公開使用行動裝置版本。

行動裝置應用程式只可透過各別行動平台的應用程式商店來發行及更新。 Microsoft 不支援透過 MDM 或側載來發行行動裝置應用程式。 當行動裝置應用程式安裝在支援的行動裝置平台上之後，在目前版本發行後的三個月內，該版本仍能支援 Teams 行動裝置應用程式本身。

如果您在中國，可以從下列 App Store 安裝 Teams:

- **小米** <https://aka.ms/TeamsXiaomi>
- **華為** <https://aka.ms/TeamsHuawei>
- **歐珀** 在 Oppo 商店中搜尋 "Teams"
- **百度** <https://aka.ms/teams_baidu_direct_dl>

> [!NOTE]
> 當使用者從其中一個中國 Android 應用程式市集安裝 Teams 並啟用 Teams 推入通知時，Microsoft 會透過中國推播通知服務提供 Teams 推入通知。

## <a name="browser-client"></a>瀏覽器用戶端

瀏覽器用戶端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是功能完整的用戶端，可在多種瀏覽器中使用。 瀏覽器用戶端使用 webRTC 來支援通話和會議，因此不需要外掛程式或任何下載，即可在瀏覽器中執行 Teams。 瀏覽器必須設定為允許第三方 Cookie。

[!INCLUDE [browser-support](includes/browser-support.md)]

The browser client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). If an unsupported browser version is detected, it will block access to the browser interface and recommend that the user download the desktop client or mobile app.
