---
title: Microsoft Teams 的硬體需求
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 在本文中，您將瞭解安裝及執行 Microsoft 團隊所需的硬體需求。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5aeeee4bf16a05b24056a6602f008b5ecaee12bb
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766756"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams 的硬體需求

下列各節中的所有需求適用於 Microsoft Teams 傳統型應用程式和  Teams Web 應用程式。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | 最低 1.6 GHz (或較高版本的) ，2核心        |
|記憶體     |    4.0 GB RAM     |
|硬碟    | 3.0 GB 的可用磁碟空間        |
|顯示器    |   1024 x 768 螢幕解析度 |
|圖形硬體 |  Windows 作業系統：圖形硬體加速需要 DirectX 9 或更新版本，2.0 且適用于 Windows 10 (或 windows 10 的 wddm 1.3 或更高版本的 microsoft 秋季更新) 
|作業系統  |    Windows 10、ARM 上的 Windows 10、windows 8.1、Windows Server 2019、Windows Server 2016|
|.NET 版本    |  需要 .NET 4.5 CLR 或更新版本       |
|影片    |  USB 2.0 視訊攝影機       |
|裝置    |   標準膝上型電腦攝影機、麥克風、喇叭    |
|視訊通話和會議|<ul><li>需要2核處理器。 若要獲得較高的影片/畫面共用解析度和畫面播放速率，建議使用4核處理器或更佳的速度。</li> <li>背景影片效果需要 Windows 10 或含 AVX2 指令集的處理器。</li> <li>如需不支援的解碼器和編碼器清單，請參閱[硬體解碼器和解碼驅動程式建議](hardware-decoders-and-encoders.md)。</li><li>使用 Microsoft 團隊聊天室中的鄰近性偵測來加入會議需要藍牙 LE （需要在用戶端裝置上啟用藍牙），而且 Windows 用戶端也需要64位的團隊用戶端。 此功能不適用於32位團隊用戶端。</li></ul> |
|Teams 即時活動 | 如果您正在產生團隊即時活動，我們建議您使用的電腦具有 Core i5 Kaby Lake processor、4.0 GB RAM (或更高版本的) ，以及硬體編碼器。 如需 **不支援** 的解碼器與編碼器清單，請參閱 [硬體解碼器和編碼器驅動程式建議](hardware-decoders-and-encoders.md)。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | 英特爾酷睿雙核處理器 |
|記憶體     |   4.0 GB RAM      |
|硬碟    |   1.5 GB 的可用磁碟空間      |
|顯示器    | 1280 x 800 或更高解析度    |
|作業系統  |    三個最新版本的 macOS 中的一個。 您可以在 [此](https://support.apple.com/en-us/HT201260)找到最新 macOS 版本的相關資訊，以及如何升級您的 macOS 版本。 例如，當發行新版本的 macOS 時，新的版本及前面緊鄰的兩個版本即成為支援的版本。      |
|影片  |    相容的網路攝影機     |
|語音    |  相容的麥克風與喇叭、具備麥克風的耳機、或同等級裝置       |
|視訊通話和會議 | <ul><li>需要2核處理器。 若要獲得較高的影片/畫面共用解析度和畫面播放速率，建議使用4核處理器或更佳的速度。 </li><li>在 macOS 上無法使用 Microsoft 團隊聊天室中的鄰近性偵測來加入會議。</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | 1.6 GHz (或更高版本的)  (32 位或64位) ，2核心        |
|記憶體     |    4.0 GB RAM     |
|硬碟    | 3.0 GB 的可用磁碟空間        |
|顯示器    |   1024 x 768 螢幕解析度 |
|圖形硬體 |  128 MB 圖形記憶體
|作業系統  | 可安裝 DEB 或 RPM 的 Linux 發行版。 |
|影片    |  USB 2.0 視訊攝影機       |
|裝置    |   標準膝上型電腦攝影機、麥克風、喇叭    |
|語音    |  相容的麥克風與喇叭、具備麥克風的耳機、或同等級裝置       |
|視訊通話和會議 | <ul><li>需要2核處理器。 若要獲得較高的影片/畫面共用解析度和畫面播放速率，建議使用4核處理器或更佳的速度。</li><li>Linux 無法使用 Microsoft Teams 會議室的「鄰近偵測」功能加入會議。</li></ul>
|支援的 Linux 發行版 | Ubuntu 18.04 LTS、20.04 LTS、Fedora 30 Workstation、RHEL 8 工作站、CentOS 8       |
|支援的桌面環境 | GNOME、KDE       |
|支援的顯示伺服器 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>行動裝置上 Teams 的硬體需求

您可以在下列行動平台上使用 Teams：

- Android：與 Android 手機和平板電腦相容。

  支援僅限於 Android 的 **最後四個** 主要版本。 例如，當您發行新的 Android 主要版本時，Android 需求就是新版本，也就是在它之前的三個最新版本。

- iOS：與 iPhone、iPad、iPod Touch 相容。

  支援僅限於 iOS 的 **兩個** 最新主要版本。 例如，在發行新的主要 iOS 版本時，iOS 需求就是新版本，也就是最新版本。 [選擇性 **模糊** ] ios 上的背景影片效果需要 ios 12 或更新版本的作業系統，且相容下列裝置： iPhone 7 或更新版本、iPad 2018 (第6代) 或更新版本，以及 iPod touch 2019 (7 代) 。

> [!Note]
> 為了獲得最佳的 Teams 使用體驗，請使用最新版的 iOS 和 Android。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>虛擬桌面基礎結構 (VDI) 環境中 Teams 的硬體需求

如需在虛擬環境中執行 Teams 的需求條件，請參閱[在虛擬環境中執行 Teams 的需求](teams-for-vdi.md)。

### <a name="related-topics"></a>相關主題

- [取得 Teams 應用程式](get-clients.md)
- [行動裝置上的 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [使用 MSI 安裝 Microsoft Teams 應用程式](msi-deployment.md)
- [Microsoft Teams 的限制和規格](limits-specifications-teams.md)
