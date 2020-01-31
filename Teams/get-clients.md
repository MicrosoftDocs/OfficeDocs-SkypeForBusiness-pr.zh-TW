---
title: 為 Microsoft 團隊取得用戶端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 Microsoft 團隊提供的各種用戶端，包括 web、桌面（Windows 和 Mac），以及行動裝置（Android 與 iOS）。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed6b86aacf13b577d45ee982d32fae7565d37314
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628539"
---
# <a name="get-clients-for-microsoft-teams"></a>為 Microsoft 團隊取得用戶端 


Microsoft 團隊擁有適用于桌面（Windows、Mac 和 Linux）、web 和 mobile （Android 和 iOS）的用戶端。 這些用戶端都需要使用中的網際網路連線，而且不支援離線模式。

> [!NOTE]
> 2018年11月29日，您將無法再使用 microsoft 網上商店提供的 Windows 10 S （預覽版） app Microsoft 團隊。 您現在可以改為在執行 Windows 10 S 模式的裝置上下載並安裝小組桌面用戶端。 若要下載桌面用戶端，請[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)移至。 在執行 Windows 10 S 模式的裝置上，不提供團隊桌面用戶端的 MSI 組建。
>
> 如需 Windows 10 S 模式的詳細資訊，請參閱[在 S 模式中簡介 Windows 10](https://www.microsoft.com/windows/s-mode)。 

## <a name="desktop-client"></a>桌面用戶端

> [!TIP]
> 請觀看下列會話，瞭解 Windows 桌面用戶端的優點、如何規劃它，以及如何部署：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)

Microsoft 團隊桌面用戶端是獨立的應用程式，也[可在 Office 365 專業增強版中](https://docs.microsoft.com/deployoffice/teams-install)取得。 團隊可在 Windows （7 +）、Windows Server （2012 R2 +）、32位與64位版本、macOS （10.10 +）及 Linux （ `.deb` `.rpm`格式）中取得。 在 Windows 上，小組需要 .NET Framework 4.5 或更新版本;如果您沒有，團隊安裝程式將會提供將它安裝給您的人員。 在 Linux 上，套件管理員（例如 apt 和 yum）會嘗試為您安裝任何需求。 不過，如果不是這樣，在 Linux 上安裝小組之前，您將需要安裝任何已報告的需求。

桌面用戶端可為小組會議、群組通話和私人一對一通話提供即時通訊支援（音訊、影片和內容共用）。

如果使用者具有適當的本地許可權（在 PC 上安裝[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)團隊用戶端但在 Mac 上是必要的系統管理員許可權），則使用者可以直接從桌面用戶端下載並安裝。

IT 管理員可以選擇其慣用的方法，將安裝檔案分發給組織中的電腦。 一些範例包括 Microsoft 端點建構管理員（Windows）或 Jamf Pro （macOS）。 若要取得適用于 Windows 發佈的 MSI 套件，請參閱[使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)。  

> [!NOTE]
> 透過這些機制發佈用戶端只適用于 Microsoft 團隊用戶端的初始安裝，不適用於未來的更新。

### <a name="windows"></a>時間

Windows 版 Microsoft 團隊安裝會提供32位與64位架構中的可下載的安裝程式。

> [!NOTE]
> Microsoft 團隊的架構（32位與64位）不可知是已安裝的 Windows 與 Office 體系結構。

Windows 用戶端會部署至位於使用者設定檔中的 [AppData] 資料夾。 部署到使用者的本機設定檔後，就能在不需要提升許可權的情況下安裝用戶端。 Windows 用戶端會利用下列位置：

- % LocalAppData%\\Microsoft\\團隊

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- % AppData%\\Microsoft\\團隊

- % LocalAppData%\\SquirrelTemp

當使用者第一次使用 Microsoft 團隊用戶端啟動通話時，可能會注意到 Windows 防火牆設定要求使用者允許通訊的警告。 使用者可能會指示您略過這封郵件，因為通話會起作用，即使關閉警告也一樣。

![[Windows 安全性警報] 對話方塊的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> 您也可以在關閉提示時選取 [取消] 來變更 Windows 防火牆設定。 針對 TCP 和 UDP 通訊協定，會建立兩個針對團隊 .exe 的入站規則。

### <a name="mac"></a>版

Mac 使用者可以使用 INSTALLER.PKG 安裝檔 macOS 電腦來安裝團隊。 必須具備系統管理存取權才能安裝 Mac 用戶端。 MacOS 用戶端已安裝至 [/Applications] 資料夾。

#### <a name="install-teams-by-using-the-pkg-file"></a>使用 INSTALLER.PKG 檔案安裝團隊

1. 從 [[團隊下載] 頁面](https://teams.microsoft.com/downloads)的 [ **Mac**] 底下，按一下 [**下載**]。
2. 按兩下 INSTALLER.PKG 檔案。
3. 依照安裝精靈完成安裝。
4. 團隊將會安裝至/Applications 資料夾。 這是整個電腦的安裝。

> [!NOTE]
> 在安裝期間，INSTALLER.PKG 會提示您輸入管理員認證。 無論使用者是否為系統管理員，使用者都必須輸入管理員認證。

如果使用者目前已安裝 .DMG 的團隊，而想要將它取代為 INSTALLER.PKG 安裝，使用者應該：

1. 結束團隊 app。
2. 卸載 [團隊] 應用程式。
3. 安裝 INSTALLER.PKG 檔案。

IT 管理員可以使用小組的 managed 部署來將安裝檔案發佈到其組織中的所有 Mac，例如 Jamf Pro。

> [!NOTE]
> 如果您在安裝 INSTALLER.PKG 時遇到問題，請告訴我們。 在本文結尾的 [**意見**反應] 區段中，按一下 [**產品意見**反應]。

### <a name="linux"></a>Linux

使用者將能夠安裝原生 Linux 套件`.deb`及`.rpm`格式。
安裝 DEB 或 RPM 套件時會自動安裝套件儲存庫
- DEB`https://packages.microsoft.com/repos/ms-teams stable main`
- RPM`https://packages.microsoft.com/yumrepos/ms-teams` 

使用系統的套件管理員來啟用自動更新的簽名金鑰會自動安裝。 不過，您也可以在以下網址找到：https://packages.microsoft.com/keys/microsoft.asc)（。 Microsoft 團隊每月都會隨附，而且如果儲存庫已正確安裝，系統套件管理員就會以與系統中其他套件相同的方式處理自動更新。

> [!NOTE] 
> 如果您發現錯誤，請使用`Report a Problem`用戶端中的 [從] 進行提交。 如有已知問題，請參閱[已知問題](Known-issues.md)。
> 對於 Linux 版團隊支援，您可以使用[Microsoft Q&的 Linux 論壇支援頻道](https://docs.microsoft.com/answers/topics/teams.html)。 在張貼問題時， `teams-linux`請務必使用標記。 

#### <a name="install-teams-using-deb-package"></a>使用 DEB 套件安裝團隊

1. 從https://aka.ms/getteams下載套件。
2. 使用下列其中一項進行安裝：  
    - 開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。
    - 或者，如果您喜歡 [終端]，請輸入：`sudo apt install **teams download file**`

您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。 

#### <a name="install-teams-using-rpm-package"></a>使用 RPM 套件安裝團隊

1. 從https://aka.ms/getteams下載套件。
2. 使用下列其中一項進行安裝：
    - 開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。
    - 或者，如果您喜歡 [終端]，請輸入：`sudo yum install **teams download file**`

您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。

#### <a name="install-manually-from-the-command-line"></a>從命令列手動安裝

在 Debian 和 Ubuntu 發行時手動安裝：
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

在 RHEL、Fedora 和 CentOS 的發佈上手動安裝：
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

或者，若要使用 yum 而不是 dnf：
```
yum check-update
sudo yum install teams
```

在 openSUSE 的發佈上手動安裝：
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>網頁用戶端 

Web 用戶端（[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)）是一種完整的功能用戶端，可在各種不同的瀏覽器中使用。 網頁用戶端支援使用 webRTC 進行通話與會議，因此在網頁瀏覽器中不需要使用外掛程式或下載來執行團隊。 瀏覽器必須設定為允許協力廠商 cookie。 

[!INCLUDE [browser-support](includes/browser-support.md)]

網頁用戶端會在連線時執行瀏覽器[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)版本檢測。 如果偵測到不受支援的瀏覽器版本，它會封鎖網頁介面的存取權，並建議使用者下載桌面用戶端或行動裝置 app。

## <a name="mobile-clients"></a>行動用戶端

Microsoft 團隊行動應用程式適用于 Android 和 iOS，且適用于參與聊天交談和允許對等音訊通話的使用者。 若是行動裝置應用程式，請移至相關的行動裝置商店 [Google Play] 和 [Apple App Store]。 Windows Phone 應用程式已于2018年7月20日停用，可能無法再運作。 

Microsoft 團隊行動裝置 app 支援的行動平臺如下：

-   **Android**：支援僅限最新四個 Android 主要版本。 發行新的 Android 主要版本時，正式支援新版本及前三個版本。

-   **iOS**：支援僅限於 ios 的兩個最新主要版本。 發行新版 iOS 的新主要版本時，系統會正式支援新版 iOS 和舊版本。

> [!NOTE]
> 行動裝置版必須提供給公眾，小組才能如期運作。

行動應用程式只會透過各個行動平臺的 app store 進行散佈與更新。 Microsoft 不支援透過 MDM 或側載來傳播行動應用程式。 在支援的行動平臺上安裝行動應用程式後，如果版本在目前發行的三個月內，就會支援小組行動應用程式本身。


| | | |
|---------|---------|---------|
|![描述決策點的圖示](media/Get_clients_for_Microsoft_Teams_image4.png)      |決策點         |是否有任何限制讓使用者在他們的裝置上安裝適當的 Microsoft 團隊用戶端？         |
|![描繪後續步驟的圖示](media/Get_clients_for_Microsoft_Teams_image5.png)     |後續步驟         |如果您的組織限制軟體安裝，請確定此程式與 Microsoft 團隊相容。 注意：電腦用戶端安裝不需要系統管理員許可權，但在 Mac 上安裝則是必要的。         |

## <a name="client-update-management"></a>用戶端更新管理

用戶端目前會自動由 Microsoft 團隊服務更新，不需要 IT 管理員干預。 如果有可用的更新，用戶端會自動下載更新，當 app 在一段時間內有 idled 時，更新程式就會開始。

## <a name="client-side-configurations"></a>用戶端設定

目前，沒有任何受支援的選項可用來透過租使用者管理員、PowerShell、群組原則物件或登錄設定用戶端。

## <a name="notification-settings"></a>通知設定

目前沒有可供 IT 系統管理員設定用戶端通知設定的選項。 所有通知選項都是由使用者設定。 下圖概述預設用戶端設定。

![通知設定的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a>範例 PowerShell 腳本

這個範例腳本（需要在已提升許可權的管理員帳戶的內容中執行用戶端電腦）會針對在 c:\users. 中找到的每個使用者資料夾，建立新的入站防火牆規則。 當團隊找到這個規則時，會防止團隊應用程式在使用者第一次從小組通話時提示使用者建立防火牆規則。 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
