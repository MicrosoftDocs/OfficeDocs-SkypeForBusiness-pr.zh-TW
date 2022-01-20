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
- m365initiative-deployteams
ms.localizationpriority: high
search.appverid: MET150
description: 在本文中，您將了解安裝及執行 Microsoft Teams 所需的硬體需求。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c975abb16b8c131b21733d57463435aa7e643639
ms.sourcegitcommit: 6e7af2e556526bd8b2bcc8f689192e254d8cb4a3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2022
ms.locfileid: "62146250"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams 的硬體需求

下列各節中的所有需求適用於 Microsoft Teams 傳統型應用程式和 Teams Web 應用程式。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | 最小 1.1 GHz 或更快、雙核心<br><br>注意：對於 Intel 處理器，必須考慮使用 Intel Frequency Boost Technology (最大渦輪頻率) 所達成的最大速度         |
|記憶體     |  4.0 GB RAM |
|硬碟    | 3.0 GB 的可用磁碟空間        |
|顯示器    |   1024 x 768 螢幕解析度 |
|圖形硬體 |  Windows OS：圖形硬體加速需要 DirectX 9 或更新版本，以及適用於 Windows 10 的 WDDM 2.0 或更新版本 (或適用於 Windows 10 Fall Creators Update 的 WDDM 1.3 或更新版本)
|作業系統  |    Windows 11、Windows 10 (Windows 10 LTSC 除外)、ARM 版 Windows 10、Windows 8.1、Windows Server 2019、Windows Server 2016、Windows Server 2012 R2。 注意：建議您使用最新的 Windows 版本及可用的安全性修補程式。|
|.NET 版本    |  需要 .NET 4.5 CLR 或更新版本       |
|影片    |  USB 2.0 視訊攝影機       |
|裝置    |   標準膝上型電腦攝影機、麥克風、喇叭    |
|視訊通話和會議|<ul><li>需要雙核心處理器。對於較高的視訊/螢幕分享解析度和畫面播放速率，建議使用 4 核心處理器或更佳的處理器。</li> <li>背景影片效果需要 Windows 10 或具有 AVX2 指令集的處理器。</li> <li>如需不支援的解碼器和編碼器清單，請參閱[硬體解碼器和解碼驅動程式建議](hardware-decoders-and-encoders.md)。</li><li>在 Microsoft Teams 會議室中使用「鄰近偵測」功能加入會議，需要在用戶端裝置上啟用藍牙，且對於 Windows 用戶端其必須有 64 位元 Teams 用戶端。此功能不適用於 32 位元 Teams 用戶端。</li></ul> |
|Teams 即時活動 | 如果您會產生 Teams 即時活動，建議您使用配備 Core i5 Kaby Lake 處理器、4.0-GB RAM (或更高)、硬體編碼器的電腦。 如需 **不支援的** 解碼器和編碼器清單，請參閱 [硬體解碼器和解碼驅動程式建議](hardware-decoders-and-encoders.md)。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | Intel Core Duo 處理器 |
|記憶體     |   4.0 GB RAM|
|硬碟    |   1.5 GB 的可用磁碟空間      |
|顯示器    | 1280 x 800 或更高解析度    |
|作業系統  |    macOS 三個最新版本的其中一個。 您可以在[這裡](https://support.apple.com/en-us/HT201260)找到最新 macOS 版本的資訊以及如何升級 macOS 版本。 例如，當新版本的 macOS 發行時，新版本和前兩個版本會變成支援的版本。      |
|影片  |    相容的網路攝影機     |
|語音    |  相容的麥克風與喇叭、具備麥克風的耳機、或同等級裝置       |
|視訊通話和會議 | <ul><li>需要雙核心處理器。對於較高的視訊/螢幕分享解析度和畫面播放速率，建議使用 4 核心處理器或更佳的處理器。 </li><li>macOS 無法使用 Microsoft Teams 會議室的「鄰近偵測」功能加入會議。</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux 電腦上 Teams 的硬體需求

| 元件 | 需求 |
|---------|---------|
|電腦與處理器    | 1.6 GHz (或更高) (32 位元或 64 位元)、雙核心        |
|記憶體     |    4.0 GB RAM |
|硬碟    | 3.0 GB 的可用磁碟空間        |
|顯示器    |   1024 x 768 螢幕解析度 |
|圖形硬體 |  128 MB 圖形記憶體
|作業系統  | 可安裝 DEB 或 RPM 的 Linux 發行版。 |
|影片    |  USB 2.0 視訊攝影機       |
|裝置    |   標準膝上型電腦攝影機、麥克風、喇叭    |
|語音    |  相容的麥克風與喇叭、具備麥克風的耳機、或同等級裝置       |
|視訊通話和會議 | <ul><li>需要雙核心處理器。對於較高的視訊/螢幕分享解析度和畫面播放速率，建議使用 4 核心處理器或更佳的處理器。</li><li>Linux 無法使用 Microsoft Teams 會議室的「鄰近偵測」功能加入會議。</li></ul>
|支援的 Linux 發行版 | Ubuntu 18.04 LTS、20.04 LTS、Fedora 30 Workstation、RHEL 8 Workstation、CentOS 8       |
|支援的桌面環境 | GNOME、KDE       |
|支援的顯示伺服器 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>行動裝置上 Teams 的硬體需求

您可以在下列行動平台上使用 Teams：

- Android：與 Android 手機和平板電腦相容。

  僅支援 Android **最新的四個** 主要版本。 例如，當 Android 發行新的主要版本時，Android 需求是新版本及其前三個最新版本。

- iOS：與 iPhone、iPad、iPod Touch 相容。

  僅支援 iOS 最新的 **兩個** 主要版本。 例如，當新的 iOS 主要版本發行時，iOS 需求是新版本及其之前的最新版本。 iOS 上的選擇性 **[模糊我的背景]** 視訊效果需要 iOS 12 或更新版本的作業系統，與下列裝置相容：iPhone 7 或更新版本、iPad 2018 (第 6 代) 或更新版本，以及 iPod touch 2019 (第 7 代)。

> [!Note]
> 為了獲得最佳的 Teams 使用體驗，請使用最新版的 iOS 和 Android。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>虛擬桌面基礎結構 (VDI) 環境中 Teams 的硬體需求

如需在虛擬環境中執行 Teams 的需求條件，請參閱[在虛擬環境中執行 Teams 的需求](teams-for-vdi.md)。

### <a name="related-topics"></a>相關主題

- [取得 Teams 應用程式](get-clients.md)
- [行動裝置上的 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [使用 MSI 安裝 Microsoft Teams 應用程式](msi-deployment.md)
- [Microsoft Teams 的限制和規格](limits-specifications-teams.md)
