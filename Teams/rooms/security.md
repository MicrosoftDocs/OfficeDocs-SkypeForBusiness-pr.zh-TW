---
title: Microsoft Teams 會議室安全性
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
description: 瞭解如何保護您的Microsoft Teams 會議室裝置。
ms.openlocfilehash: 7043b49406b0865ef38108519040374d792ac1dd
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306108"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 會議室安全性

Microsoft 會與我們的合作夥伴合作，提供安全的解決方案，而且不需要採取其他動作來Microsoft Teams 會議室。 本文討論許多在 Teams 會議室 中Teams 會議室。

> [!NOTE]
> Microsoft Teams 會議室不應該視為一般的使用者工作站。 不僅使用案例差異很大，而且預設安全性設定檔也差異很大。
> 本文適用于在 Microsoft Teams 會議室 上Windows。

有限的使用者資料會儲存在 Teams 會議室。 使用者資料可能儲存于記錄檔中，僅提供疑難排解和支援。 會議出席者在將檔案複製到硬碟Teams 會議室或以本身方式登錄時，一點都不行。 使用者資料不會傳輸至裝置，也不得Microsoft Teams 會議室裝置。

即使使用者無法將檔案放在硬碟Teams 會議室，Microsoft Defender 仍然已啟用。 Teams 會議室 Microsoft Defender 測試其性能。 停用此功能或新增端點安全性軟體可能會導致無法預測的結果，並可能導致系統降級。

## <a name="hardware-security"></a>硬體安全性

在Teams 會議室環境中，有一個中央計算模組可執行Windows 10 IoT 企業版版本。 每個通過認證的計算模組都必須有安全安裝解決方案、安全鎖定插槽 (例如，Kensington lock) ，以及 I/O 埠存取安全性措施，以防止未經授權的裝置連接。 您也可以透過統一可擴展的固件介面或 UEFI (停用) 埠。

每個通過認證的計算模組都必須在預設啟用的 2.0 相容 (TPM) 中提供受信任的平臺模組。 TPM 是用來加密資源帳戶Teams 會議室資訊。

預設會啟用安全啟動。 安全啟動是電腦產業成員所開發的安全性標準，可協助確保裝置只使用原始設備製造商或 OEM (信任) 。 電腦啟動時，固件會檢查每個開機軟體的簽名，包括 UEFI (也稱為 Option ROM) 、EFI 應用程式和作業系統。 如果簽名有效，電腦會啟動，而該固件會提供作業系統的控制權。 詳細資訊，請參閱安全 [啟動](/windows-hardware/design/device-experiences/oem-secure-boot)。

只有附加實體鍵盤和滑鼠，才能存取 UEFI 設定。 這可防止您透過啟用觸控Teams 會議室主控台，以及任何其他附加至鍵盤上的觸控顯示來存取 UEFI Teams 會議室。

核心直接記憶體存取 (DMA) 保護Windows 10是在 Teams 會議室 上啟用的一項Teams 會議室。 有了這項功能，作業系統和系統固件可保護系統，防範所有支援 DMA 的裝置受到惡意和意外的 DMA 攻擊：

- 在啟動過程中。

- 在 OS 執行時間期間，由裝置連接到易於訪問的內部/外部 DMA 埠 ，例如 M.2 PCIe 插槽和 Thunderbolt 3，以防範惡意 DMA。

Teams 會議室啟用受 Hypervisor 保護的代碼完整性 (HVCI) 。 HVCI 提供的功能之一是認證防護。 認證防護提供下列優點：

- **硬體安全性** NTLM、Kerberos 和認證管理員會利用平臺安全性功能 ，包括安全啟動和虛擬化來保護認證。

- **以虛擬化為基礎的** 安全性Windows NTLM 和 Kerberos 衍生認證及其他機密，在與執行中的作業系統隔離的受保護環境中執行。

- **進一的保護，防範進一級的持續性威脅** 當認證管理員網域認證、NTLM 和 Kerberos 衍生認證使用虛擬化安全性受到保護時，許多目標攻擊中使用的認證竊取攻擊技術和工具會遭到封鎖。 在具有系統管理許可權的作業系統中執行惡意程式無法解壓縮受虛擬化安全性保護的機密。

## <a name="software-security"></a>軟體安全性

Microsoft Windows啟動後，Teams 會議室自動登入名為 Windows 的Skype。 Skype帳戶沒有密碼。 若要確保Skype會話安全，請執行下列步驟。

> [!IMPORTANT]
> 請勿變更密碼或編輯Skype使用者帳戶。 這麼做可防止Teams 會議室自動登入。

應用程式Microsoft Teams 會議室使用 1903 Windows 10更新版本找到的已指派存取功能執行。 已指派的 Access 是 Windows 10中的一項功能，可限制公開給使用者的應用程式進入點。 這就是啟用單一應用程式資訊站模式的方式。 使用 Shell Launcher，Teams 會議室已配置為以使用者介面Windows桌面應用程式執行資訊站裝置。 應用程式Microsoft Teams 會議室取代預設 shell (explorer.exe) 通常會在使用者登錄時執行。 換句話說，傳統的 Explorer shell 完全無法啟動。 這可大幅減少Microsoft Teams 會議室內漏洞Windows。 若要詳細資訊，請參閱在桌上出版上設定Windows[站和數位標記](/windows/configuration/kiosk-methods)。

如果您決定在 Teams 會議室 上執行安全性掃描或 Internet Security center (CIS) 基準，則掃描只能在當地系統管理員帳戶的情況下執行，因為 Skype 使用者帳戶不支援執行 Teams 會議室 應用程式外的應用程式。 適用于 Skype 使用者上下文的許多安全性功能並不適用于其他本地使用者，因此這些安全性掃描無法顯示已用於 Skype 帳戶的完整安全性鎖定。 因此，不建議在 Teams 會議室 上執行Teams 會議室。 不過，您可以執行外部穿透測試 ，如果需要的話。 因此，建議您針對這些裝置執行外部Teams 會議室測試，而不是執行本地掃描。

此外，鎖定原則會用來限制使用非系統管理功能。 已啟用鍵盤篩選來截取並封鎖指派的 Access 政策未涵蓋的潛在不安全鍵盤組合。 只有具有本地或網域管理許可權的使用者才能Windows管理Teams 會議室。 這些原則和其他原則Windows裝置Microsoft Teams 會議室在產品生命週期期間持續進行評估和測試。

## <a name="account-security"></a>帳戶安全性

Teams 會議室裝置包含一個名為「系統管理員」的系統管理帳戶，並包含預設密碼。 我們強烈建議您完成設定後，儘快變更預設密碼。

系統管理帳戶不一定可正確Teams 會議室，而且可以重新命名或甚至刪除。 不過，刪除系統管理帳戶之前，請確定您設定了備用的本地系統管理員帳戶，然後再移除隨裝置Teams 會議室帳戶。 若要進一步瞭解如何使用內建的 Windows工具或 PowerShell 變更Windows帳戶的密碼，請參閱下列內容：

- [變更或重設Windows密碼](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

您也可以將網域帳戶Windows系統管理員群組。 您可以使用 Intune Azure AD帳戶執行此工作。 詳細資訊，請參閱策略 [CSP – 受限制的組。](/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!NOTE]
> 如果您使用的是Crsron主機，請務必同時更新主機上的系統管理密碼，以及計算模組上的系統管理密碼。 如需詳細資訊，請聯絡Crsron。

> [!CAUTION]
> 如果您在將本地系統管理員許可權授予其他本地或網域帳戶之前先刪除或停用系統管理員帳戶，您可能會失去管理Teams 會議室的能力。 如果發生這種情況，您必須將裝置重設回其原始設定，然後再次完成設定程式。

請勿將本地系統管理員許可權授予Skype使用者帳戶。

Windows組組設計工具可用來建立Windows 10套件。 除了變更本機系統管理員密碼，您也可以執行變更電腦名稱稱及註冊至 Azure Active Directory。 有關建立組Windows設計工具的套件詳細資訊，請參閱針對 Windows 10[的部署套件](/windows/configuration/provisioning-packages/provisioning-packages)。

您需要為每個裝置建立資源Teams 會議室，以便它Teams。 此帳戶無法使用雙因素或多重要素驗證。 要求第二個要素會防止帳戶在重新開機後自動Teams 會議室應用程式。 不過，您可以為此帳戶啟用新式驗證，以提供額外的安全性。 此外，您可以針對資源帳戶部署位置式條件式 Access 策略，以防止從未通過批准的位置登入帳戶。 詳細資訊，請參閱在條件式 Access 策略 [中使用位置條件](/azure/active-directory/conditional-access/location-condition)

如果可能的話，建議您在 Azure AD 中建立資源帳戶。 雖然同步處理的帳戶可以在混合式部署Teams 會議室，但這些同步處理的帳戶通常難以Teams 會議室且可能難以進行疑難排解。 如果您選擇使用協力廠商聯合服務驗證資源帳戶的認證，請確定協力廠商 IDP 會以設為 的屬性 `wsTrustResponse` 回應 `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>網路安全性

一般而言，Teams 會議室用戶端的網路需求Microsoft Teams相同。 透過防火牆和其他安全性裝置存取，Teams 會議室用戶端的存取Microsoft Teams相同。 針對Teams 會議室，列為「必填」Teams必須在防火牆上開啟。 Teams 會議室使用 Windows管理裝置Microsoft Store，Microsoft Intune (使用者也需要存取 Microsoft Intune、) 。 有關所需 IP 和 URL 的完整清單，請參閱Microsoft Teams 會議室：

- **Microsoft Teams Office 365** [URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows更新**[設定 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store**[與教育商務用 Microsoft Store先決條件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune**[網路端點Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

如果您使用的是 Microsoft Teams 會議室 的受Microsoft Teams 會議室進階版服務元件，您也需要確認Teams 會議室能夠存取下列 URL：

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams 會議室已配置為使用最新的更新 ，包括安全性更新Windows自行修補。 Teams 會議室使用預先設定的本地策略，每天從上午 2：00 開始安裝任何擱置的更新。 不需要使用其他工具來部署並Windows更新。 使用其他工具來部署及應用更新可能會延遲安裝Windows修補程式，因此會導致較安全的部署。 系統Teams 會議室應用程式是使用 Microsoft Store。 如果您的裝置已授權Microsoft Teams 會議室標準版，任何新版本的應用程式都會在夜間修補程式期間自動安裝。 如果您的裝置已授權Microsoft Teams 會議室進階版 Microsoft Managed Service 註冊，系統會根據您定義的部署Teams 會議室安裝新版本的 App。

Teams 會議室裝置可與大多數的 802.1X 或其他網路安全通訊協定一起使用。 不過，我們無法針對所有可能的Teams 會議室安全性組進行測試。 因此，如果發生可追蹤到網路性能問題的績效問題，您可能需要停用這些通訊協定 ，如果這些通訊協定已由貴組織所配置。

為了獲得最佳即時媒體的顯示效果，我們強烈建議您設定Teams媒體流量，以忽略 Proxy 伺服器和其他網路安全性裝置。 即時媒體對於延遲非常敏感，Proxy 伺服器和網路安全性裝置可能會大幅降低使用者的視音訊品質。 此外，Teams媒體已經加密，因此透過 Proxy 伺服器傳遞流量並沒有明顯的好處。 若要詳細資訊，請參閱將 (網路) [雲端](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide)網路 —一位架構設計師的觀點，探討網路建議，以使用 Microsoft Teams 和 Microsoft Teams 會議室。

> [!IMPORTANT]
> Teams 會議室不支援經過驗證的 Proxy 伺服器。

Teams 會議室裝置不需要連接到內部 LAN。 請考慮將Teams 會議室直接網際網路存取置於安全網路區段中。 如果您的內部 LAN 遭到入侵，將會減少攻擊Teams 會議室的機會。

我們強烈建議您將您的Teams 會議室裝置連接到有線網路。 不建議或Teams 會議室裝置上使用無線網路。 某些連接功能 ，例如 Wi-Fi，預設會停用。

鄰近連接和其他Teams 會議室功能仰賴藍牙。 不過，藍牙裝置上的Teams 會議室，不允許外部裝置與裝置Teams 會議室連接。 藍牙裝置上Teams 會議室目前僅限於廣告標誌和提示的親數連接。 通訊 `ADV_NONCONN_INT` 協定資料單位 (PDU) 類型用於廣告標誌。 此 PDU 類型適用于無法連接裝置向聆聽裝置廣告資訊。 這些功能藍牙裝置配對。 您可以在 SIG 藍牙 上找到有關藍牙[通訊協定的其他詳細資料](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
