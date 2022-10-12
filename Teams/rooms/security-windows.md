---
title: 適用于 Windows 安全性Microsoft Teams 會議室
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
description: 瞭解如何保護 Windows 裝置Microsoft Teams 會議室。
ms.openlocfilehash: b35d856afb7ca044388802aa514039bd9b8d40d3
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532422"
---
# <a name="microsoft-teams-rooms-for-windows-security"></a>適用于 Windows 安全性Microsoft Teams 會議室

Microsoft 與我們的合作夥伴合作，提供安全且不需要額外動作來保護 Windows Microsoft Teams 會議室的解決方案。 本文探討 Windows 版 Teams 會議室 中找到的許多安全性功能。

如需 Android 裝置Teams 會議室安全性的相關資訊，請參[閱 Android 安全性Microsoft Teams 會議室](security-android.md)。

> [!NOTE]
> Microsoft Teams 會議室不應該被視為一般的使用者工作站。 不僅使用案例有很大的不同，預設的安全性設定檔也有很大的不同。
> 本文適用于在 Windows 上執行Microsoft Teams 會議室裝置。

有限的使用者資料會儲存在Teams 會議室上。 使用者資料可能儲存在記錄檔中，僅供疑難排解和支援。 出席者在任何時候都無法使用Teams 會議室將檔案複製到硬碟或自行登入。 系統不會將使用者資料傳輸至Microsoft Teams 會議室裝置，或無法存取該裝置。

雖然使用者無法將檔案放在Teams 會議室硬碟上，但仍Microsoft Defender啟用。 Teams 會議室效能是使用 Microsoft Defender 測試。 停用此功能或新增端點安全性軟體可能會導致無法預期的結果和潛在的系統降級。

## <a name="hardware-security"></a>硬體安全性

在Teams 會議室環境中，有一個執行Windows 10 IoT 企業版版本的中央計算模組。 每個通過認證的計算模組都必須有安全安裝解決方案、安全性鎖定插槽 (例如，對通通鎖定) ，以及 I/O 埠存取安全性措施，以防止未經授權的裝置連線。 您也可以透過整合可延伸韌體介面 (UEFI) 設定停用特定埠。

每個認證的計算模組都必須隨附信賴平臺模組 (TPM) 預設啟用 2.0 相容技術。 TPM 是用來加密Teams 會議室資源帳戶的登入資訊。

預設會啟用安全開機。 安全開機是電腦產業成員所開發的安全性標準，可協助確保裝置僅使用原始設備製造商 (OEM) 信任的軟體啟動。 電腦啟動時，韌體會檢查每一個開機軟體的簽章，包括 UEFI 韌體驅動程式 (也稱為 Option ROM) 、EFI 應用程式和作業系統。 如果簽章有效，電腦就會啟動，而韌體則會對作業系統進行控制。 如需詳細資訊，請參閱 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。

只有附加實體鍵盤和滑鼠才能存取 UEFI 設定。 這可防止透過Teams 會議室觸控式主機以及連接到Teams 會議室的任何其他觸控式顯示器存取 UEFI。

核心直接記憶體存取 (DMA) 保護是已在 Teams 會議室 啟用的Windows 10設定。 使用此功能，作業系統和系統韌體可保護系統，避免所有支援 DMA 功能的裝置遭受惡意和非預期的 DMA 攻擊：

- 在開機程式期間。

- 在作業系統執行時間期間，透過連接到可輕鬆存取內部/外部 DMA 埠的裝置來抵禦惡意 DMA，例如 M.2 PCIe 插槽和 Thunderbolt 3。

Teams 會議室也啟用受 Hypervisor 保護的程式碼完整性 (HVCI) 。 HVCI 提供的其中一項功能是 Credential Guard。 Credential Guard 提供下列優點：

- **硬體安全性** NTLM、Kerberos 和認證管理員利用平臺安全性功能，包括安全開機和虛擬化，以保護認證。

- **虛擬化型安全性** Windows NTLM 和 Kerberos 衍生認證和其他機密會在與執行中作業系統隔離的受保護環境中執行。

- **針對進階持續性威脅提供更佳的保護** 當 Credential Manager 網域認證、NTLM 和 Kerberos 衍生認證使用虛擬化型安全性受到保護時，會封鎖在許多目標攻擊中使用的認證竊取攻擊技術和工具。 在作業系統中以系統管理許可權執行的惡意程式碼無法擷取受到虛擬化型安全性保護的機密。

## <a name="software-security"></a>軟體安全性

Microsoft Windows 啟動之後，Teams 會議室自動登入名為 Skype 的本機 Windows 使用者帳戶。 Skype 帳戶沒有密碼。 若要確保 Skype 帳戶會話的安全，請執行下列步驟。

> [!IMPORTANT]
> 請勿變更密碼或編輯本機 Skype 使用者帳戶。 這麼做可以防止Teams 會議室自動登入。

Microsoft Teams 會議室應用程式會使用 Windows 10 1903 和更新版本中的 [指派的存取] 功能執行。 指派的存取權是Windows 10中的一項功能，可限制向使用者公開的應用程式進入點。 這是啟用單一應用程式 kiosk 模式的原因。 使用 Shell Launcher，Teams 會議室設定為 kiosk 裝置，以執行 Windows 桌面應用程式做為使用者介面。 Microsoft Teams 會議室應用程式會取代使用者登入時通常會執行的預設殼層 (explorer.exe) 。 換句話說，傳統的檔案總管殼層完全不會啟動。 這會大幅減少 Windows 內Microsoft Teams 會議室弱點。 如需詳細資訊，請參閱在 [Windows 桌上出版上設定 kiosk 和數位記號](/windows/configuration/kiosk-methods)。

如果您決定執行安全性掃描或網際網路安全性中心 (CIS) Teams 會議室基準，掃描只能在本機系統管理員帳戶的內容下執行，因為 Skype 使用者帳戶不支援執行 Teams 會議室 應用程式以外的應用程式。 許多套用至 Skype 使用者內容的安全性功能不適用於其他本機使用者，因此這些安全性掃描不會顯示套用至 Skype 帳戶的完整安全性鎖定。 因此，不建議您在Teams 會議室上執行本機掃描。 不過，如有需要，您可以執行外部測試。 因此，建議您對Teams 會議室裝置執行外部測驗，而不是執行本機掃描。

此外，鎖定原則會套用以限制非系統管理功能的使用。 已啟用鍵盤篩選器來截距並封鎖可能不安全的鍵盤組合，但指派的存取原則未涵蓋這些組合。 只有具有本機或網域系統管理許可權的使用者才有權登入 Windows 以管理Teams 會議室。 在Microsoft Teams 會議室裝置上套用至 Windows 的這些原則及其他原則會在產品生命週期期間持續受到評估和測試。

## <a name="account-security"></a>帳戶安全性

Teams 會議室裝置包含名為「管理員」的系統管理帳戶，並具有預設密碼。 我們強烈建議您在完成設定後儘快變更預設密碼。

管理員帳戶不需要適當操作Teams 會議室裝置，也可以重新命名或甚至刪除。 不過，在刪除管理員帳戶之前，請務必先設定替代的本機系統管理員帳戶，再移除隨Teams 會議室裝置一起出貨的帳戶。 如需如何使用內建 Windows 工具或 PowerShell 變更本機 Windows 帳戶密碼的詳細資訊，請參閱下列內容：

- [變更或重設 Windows 密碼](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

您也可以將網域帳戶匯入本機 Windows 系統管理員群組。 您可以使用 Intune，針對 Azure AD 帳戶執行此動作。 如需詳細資訊，請參閱 [原則雲端解決方案提供者 – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!NOTE]
> 如果您使用的是 Cres tenant 主機，也請務必更新主機和計算模組上的管理員密碼。 如需詳細資訊，請連絡 Cres 要點。

> [!CAUTION]
> 如果您先刪除或停用管理員帳戶，再將本機系統管理員許可權授與另一個本機或網域帳戶，您可能會失去管理Teams 會議室裝置的能力。 如果發生這種情況，您將需要將裝置重設回其原始設定，然後再次完成設定程式。

請勿將本機系統管理員許可權授與 Skype 使用者帳戶。

Windows 設定設計工具可用來建立Windows 10布建套件。 除了變更本機管理員密碼，您也可以執行變更電腦名稱稱和註冊 Azure Active Directory 等動作。 如需有關建立 Windows 設定設計工具布建套件的詳細資訊，請參閱[布建Windows 10套件](/windows/configuration/provisioning-packages/provisioning-packages)。

您必須為每個Teams 會議室裝置建立資源帳戶，讓它可以登入 Teams。 您無法在此帳戶中使用雙因素或多重要素驗證。 要求第二個因素可防止帳戶在重新開機後自動登入Teams 會議室應用程式。 不過，您可以為此帳戶啟用新式驗證以獲得額外的安全性。 此外，Azure Active Directory 條件式存取原則和Intune合規性原則可以部署來保護資源帳戶。 如需詳細資訊，請參閱Microsoft Teams 會議室和條件式[存取及Intune](supported-ca-and-compliance-policies.md)合規性的條件式存取和[Intune裝置合規性原則Microsoft Teams 會議室](conditional-access-and-compliance-for-devices.md)

建議您盡可能在 Azure AD 中建立資源帳戶。 雖然同步處理的帳戶可以在混合式部署中使用Teams 會議室，但這些同步處理的帳戶通常很難登入Teams 會議室，而且可能難以進行疑難排解。 如果您選擇使用協力廠商同盟服務驗證資源帳戶的認證，請確定協力廠商 IDP 會在屬性設為 `urn:oasis:names:tc:SAML:1.0:assertion` 時回應 `wsTrustResponse` 。

## <a name="network-security"></a>網路安全性

一般而言，Teams 會議室的網路需求與任何 Microsoft Teams 用戶端相同。 透過防火牆和其他安全性裝置存取的Teams 會議室與任何其他 Microsoft Teams 用戶端相同。 針對Teams 會議室，Teams 列為「必要」的類別必須在您的防火牆上開啟。 如果您使用 Microsoft Intune 管理裝置) ，Teams 會議室也需要存取 Windows Update、Microsoft Store 和 Microsoft Intune (。 如需Microsoft Teams 會議室所需的 IP 和 URL 完整清單，請參閱：

- **Microsoft Teams** [Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows Update**[設定 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- [適用于 商務用 Microsoft Store 和教育](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)的 **Microsoft Store** 必要條件
- **Microsoft Intune**[適用于 Microsoft Intune 的網路端點](/mem/intune/fundamentals/intune-endpoints)

如果您使用的是 Microsoft Teams 會議室 Pro 的Microsoft Teams 會議室受管理服務元件，您也需要確認Teams 會議室可以存取下列 URL：

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams 會議室設定為自動讓自己保持修補最新的 Windows 更新，包括安全性更新。 Teams 會議室使用預先設定的本地原則，每天從早上 2：00 開始安裝任何擱置中的更新。 您不需要使用其他工具來部署和套用 Windows 更新。 使用其他工具來部署和套用更新可能會延遲安裝 Windows 修補程式，因此導致部署較不安全。 Teams 會議室應用程式是使用 Microsoft Store 來部署。

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Teams 會議室裝置可搭配大部分的 802.1X 或其他網路安全性通訊協定使用。 不過，我們無法針對所有可能的網路安全性設定測試Teams 會議室。 因此，如果出現可追蹤到網路效能問題的效能問題，如果您的組織已設定這些通訊協定，您可能需要停用這些通訊協定。

為了獲得即時媒體的最佳效能，我們強烈建議您將 Teams 媒體流量設定為略過 Proxy 伺服器及其他網路安全性裝置。 即時媒體非常延遲，Proxy 伺服器和網路安全性裝置可能會大幅降低使用者的視訊和音訊品質。 此外，由於 Teams 媒體已加密，因此透過 Proxy 伺服器傳遞流量沒有任何明顯的優點。 如需詳細資訊，請參閱[將 (連線到雲端) — 一個架構的](/microsoft-365/solutions/networking-design-principles)架構，其中討論網路建議，以改善 Microsoft Teams 和 Microsoft Teams 會議室 媒體效能。

> [!IMPORTANT]
> Teams 會議室不支援已驗證的 Proxy 伺服器。

Teams 會議室裝置不需要連線到內部 LAN。 考慮將Teams 會議室放在具有直接網際網路存取的安全網路區段中。 如果您的內部 LAN 遭到入侵，將減少向Teams 會議室的攻擊向量機會。

我們強烈建議您將Teams 會議室裝置連線到有線網路。 不建議或認證在Teams 會議室裝置上使用無線網路。 某些連線功能，例如Wi-Fi感知器，預設為停用。

鄰近連接及其他Teams 會議室功能仰賴藍牙。 不過，Teams 會議室裝置上的藍牙實作不允許外部裝置連線至Teams 會議室裝置。 Teams 會議室裝置上的藍牙技術目前僅限於廣告指標和提示的近似連線。 PDU `ADV_NONCONN_INT`) 類型 (通訊協定資料單位會用於廣告指標中。 此 PDU 類型適用于無法連線裝置的廣告資訊給聆聽的裝置。 這些功能中沒有藍牙裝置配對。 您可以在 [藍牙 SIG 網站上找到藍](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)牙通訊協定的其他詳細資料。
