---
title: Android 版 Microsoft Teams 安全性
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 瞭解如何保護 Android 裝置的 Microsoft Teams。
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532433"
---
# <a name="microsoft-teams-for-android-security"></a>Android 版 Microsoft Teams 安全性

本文不涵蓋 Microsoft 端點管理員為專用裝置模式設定的 Android 裝置。 Teams Android 裝置在 Kiosk 模式中執行的設計。 如需 Android Kiosk 的相關資訊，請參閱 [Android 企業版專用裝置註冊](/mem/intune/enrollment/android-kiosk-enroll)。

Microsoft 與我們的 OEM 合作夥伴合作，以提供符合客戶需求之安全且可自訂的解決方案。 本文探討 Teams Android 裝置中找到的許多安全性功能，以及我們的做法。 它會分割成四個主要區段，方便您流覽。

> [!NOTE]
> Microsoft Teams Android 裝置不應該被視為一般的 Android 裝置。 Teams Android 裝置是專為搭配 Teams 使用及其個別使用案例所設計的專用設備。 本文僅適用于執行 Android 作業系統的經過認證和專用的 Microsoft Teams 裝置。 Teams 認證裝置只能向經過認證的 OEM 廠商購買。 如需 Microsoft Teams 認證 Android 裝置的相關資訊，請參閱 [Microsoft Teams 認證的 Android 裝置](/microsoftteams/devices/teams-ip-phones)。

如需 Windows 裝置Teams 會議室安全性的相關資訊，請參[閱 Windows 安全性Microsoft Teams 會議室](security-windows.md)。

## <a name="software-security"></a>軟體安全性

### <a name="android-kiosk-mode"></a>Android kiosk 模式

Teams Android 裝置在 Android Kiosk 模式下執行裝置，鎖定以僅執行核准的應用程式。 Kiosk 模式會停用任何啟動器功能的存取權，並協助保護裝置安全，讓授權應用程式在裝置上啟動。  

| 應用程式名稱            | 應用程式描述                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android 應用程式 | Microsoft Teams 裝置應用程式        |
| Microsoft Teams 管理員專員 | Teams 系統管理中心遠端系統管理      |
| Intune 公司入口網站       | 裝置註冊、註冊&登入 |
| OEM 合作夥伴專員           | OEM 合作夥伴專員&裝置設定應用程式   |

根據設計，Microsoft Teams Android 應用程式會在 Android Kiosk 模式的啟動時啟動，並且不會提供使用者任何作業系統存取權，也不會在指定的 Teams 使用者體驗之外存取元件。

### <a name="application-code-signing"></a>應用程式代碼簽署

所有 Microsoft 和 OEM 應用程式都會簽署程式碼。 代碼簽署有助於驗證在裝置上執行的軟體是來自 Microsoft 和我們的硬體合作夥伴的正版軟體。 代碼簽署也會嘗試驗證在裝置上執行之軟體的完整性，如此一來，只有正版軟體才能啟動並執行。  

### <a name="third-party-applications"></a>協力廠商應用程式

Teams 認證裝置沒有依設計安裝的 Google Play 商店、Amazon App Store 或 Google Play 服務。 這有助於確保無法從 Microsoft Store 將協力廠商應用程式安裝到裝置上。  

### <a name="android-debug-bridge"></a>Android 偵錯橋接器

在執行發行軟體的所有 Teams Android 裝置上， (ADB) 設計停用 Android 偵錯橋接器。 ADB 是一種命令列工具，可讓系統管理員在 Android 裝置上執行功能，並可安裝應用程式、存取裝置殼層及其他系統管理員功能。  

### <a name="file-system-encryption"></a>檔案系統加密

Teams Android 裝置必須支援 Android 型加密，而且可以使用 Microsoft 端點管理員合規性原則強制執行。 如需端點管理員合規性原則的相關資訊[：使用端點管理員合規性原則為您使用Intune管理的裝置設定規則](/mem/intune/protect/device-compliance-get-started)。

### <a name="android-os-version"></a>Android OS 版本

Teams Android 裝置執行支援的 Android 版本。 Android 作業系統是由 OEM 合作夥伴管理、合併到 Teams 認證韌體，然後從 Teams 系統管理中心推送到裝置。 如需 Teams Android 裝置上執行哪些 Android 版本的相關資訊，請參閱 [Microsoft Teams 認證的 Android 裝置](/microsoftteams/devices/teams-ip-phones)。

### <a name="android-security-updates"></a>Android 安全性更新

OEM 廠商會在韌體更新程式中加入適當的 Android 安全性更新比較基準，以協助確保基本作業系統的安全。 確保裝置上執行適當的 Android 安全性更新，請務必定期更新您的裝置。 如需詳細資訊，請參閱您的裝置製造商。

### <a name="account-security"></a>帳戶安全性

Teams Android 裝置是以兩種帳戶類型為內建，可讓裝置順利運作。

- 本機裝置系統管理員帳戶

- 使用者或資源帳戶  

Teams Android 裝置也相容于某些條件式存取原則，可用來做為裝置登入的額外安全性層級。 如需最佳做法和支援的條件式存取原則，請參閱 [支援的條件式存取合規性原則](/microsoftteams/rooms/supported-ca-and-compliance-policies)。

### <a name="local-device-administrator-account"></a>本機裝置系統管理員帳戶

Teams Android 裝置包括可存取裝置設定的系統管理帳戶、安裝裝置時的本機網頁伺服器，以及任何 OEM 特定設定。

您可以向裝置製造商取得初始裝置設定和設定專案，例如此帳戶的預設使用者名稱和密碼。

> [!CAUTION]
> 請務必儘快變更本機裝置系統管理員密碼。  

> [!TIP]
> Teams 系統管理中心可用來套用組態設定檔來變更已登入 Teams Android 裝置的本機裝置系統管理員密碼。 建議您在初始裝置登入之後使用此方法，以保護 Android 裝置提升的功能。 提高許可權的功能可以包含裝置設定和 Web 系統管理入口網站，如果有支援的話。

### <a name="user-or-resource-account"></a>使用者或資源帳戶

Teams Android 裝置需要使用使用者或專用資源帳戶來登入 Microsoft 365。 我們會嘗試以特定方式保護這些帳戶，視其為個人裝置的標準使用者帳戶或共用裝置的資源帳戶而定。 如需詳細資訊，請參閱 [建立及設定會議室和共用裝置的資源帳戶](/microsoftteams/rooms/with-office-365)。

### <a name="device-updates"></a>裝置更新

Teams Android 裝置設定為從 Teams 系統管理中心下載 Microsoft 認證的更新。 系統管理員可以自動推入或手動叫用這些專案。 我們 OEM 合作夥伴的協力廠商工具也可在必要時執行此函數。 Teams Android 裝置可以在數小時後安裝更新，以避免對使用者造成影響。 您可以在 Teams 系統管理中心或使用 OEM 合作夥伴的協力廠商工具，設定數小時後的排程。

> [!IMPORTANT]
> Microsoft 建議您透過 Teams 系統管理中心完成所有 Teams Android 裝置的韌體管理。

## <a name="network-security"></a>網路安全性

Teams Android 裝置的網路需求與任何 Microsoft Teams 用戶端相同，包括透過防火牆和其他安全性裝置存取。 具體來說，Teams **所需的** 類別必須與其他支援服務一起在您的防火牆上開啟，如下所列。 如需 Teams Android 裝置所需的 IP 和 URL 完整清單，請參閱：

- Microsoft Teams、Exchange Online、SharePoint Online、Microsoft 365 Common 和 Office Online [Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune[適用于 Microsoft Intune 的網路端點](/mem/intune/fundamentals/intune-endpoints)

Teams Android 裝置可搭配大部分的 802.1X 和其他網路安全性通訊協定使用。 不過，我們無法針對所有網路安全性設定測試 Teams Android 裝置。 因此，如果出現可追蹤到網路效能問題的效能問題，如果您在組織中設定這些通訊協定，您可能需要停用這些通訊協定，或連絡您的 OEM 合作夥伴以尋求協助。

為了獲得即時媒體的最佳效能，我們強烈建議您將 Teams 媒體流量設定為略過 Proxy 伺服器及其他網路安全性裝置。 即時媒體會對網路延遲敏感，這可能是 Proxy 伺服器及其他網路安全性裝置所造成。 網路延遲可能會大幅降低使用者的視訊和音訊品質。 如需詳細資訊，請參閱 [將 (連線到雲端) — 一個架構的](/microsoft-365/solutions/networking-design-principles) 架構，其中討論網路建議，以改善 Microsoft Teams 媒體效能。

Teams Android 裝置在網際網路上使用加密的通訊和端點驗證。 Teams Android 裝置使用 TLS 1.2+。  

> [!IMPORTANT]
> Teams Android 裝置不支援已驗證的 Proxy 伺服器或租使用者限制。 如需 Proxy 支援資訊，請連絡您的 OEM 合作夥伴。

Teams Android 裝置不需要連線到內部 LAN。 考慮將 Teams Android 裝置置於具有直接網際網路存取的安全網路區段中。 例如，Teams Phone 可以部署在語音 VLAN 上。 如果您的內部 LAN 遭到入侵，將實作此網路隔離來降低對 Teams Android 裝置的攻擊向量機會。

我們強烈建議您將 Teams Android 裝置連線到有線網路。 使用無線網路需要審慎規劃和評估，才能獲得最佳體驗。

鄰近連接、共同作業更好、Teams 投射和 Teams 面板配對都仰賴藍牙。 Android 裝置的Teams 會議室藍牙技術目前僅限於廣告指標和提示的近似連線。 PDU `ADV_NONCONN_INT`) 類型 (通訊協定資料單位會用於廣告指標中。 此 PDU 類型適用于無法連線裝置的廣告資訊給聆聽的裝置。 這些功能中沒有藍牙裝置配對。 您可以在藍牙 SIG 網站上找到藍牙通訊協定的其他詳細資料。

Teams 手機和顯示器提供藍牙配對功能，可使用藍牙Hands-Free設定檔來配對耳機。

如需有關 Microsoft Teams 中安全性的資訊，請參閱 [安全性與 Microsoft Teams](/microsoftteams/teams-security-guide)。  
