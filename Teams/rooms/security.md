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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解如何保護您的 Microsoft Teams 會議室裝置。
ms.openlocfilehash: 77c7d71cfb41318b123fb262ee4a57b9aaeba493
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117391"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 會議室安全性

Microsoft 會與合作夥伴合作，提供安全的解決方案，而且不需要採取其他動作來保護 Microsoft Teams 會議室。 本文將討論 Teams 會議室的許多安全性功能。

> [!NOTE]
> Microsoft Teams 會議室不應視為一般的使用者工作站。 不僅使用案例差異很大，而且預設安全性設定檔也差異很大。

有限的使用者資料會儲存在 Teams 會議室。 使用者資料可能會儲存在記錄檔案中，以用於疑難排解和支援。 使用 Teams 會議室的會議出席者一點都不得將檔案複製到硬碟，或以自己的方式登錄。 Microsoft Teams 會議室裝置不會將使用者資料傳輸至或可供其使用。

即使使用者無法將檔案放在 Teams 會議室硬碟上，Microsoft Defender 仍然已啟用。 使用 Microsoft Defender 測試 Teams 會議室的績效。 停用此功能或新增端點安全性軟體可能會導致無法預測的結果，並可能導致系統降級。

## <a name="hardware-security"></a>硬體安全性

在 Teams 會議室環境中，有一個執行 Windows 10 IoT Enterprise 版本的中央計算模組。 每個通過認證的計算模組都必須有安全安裝解決方案、安全鎖定插槽 (例如，Kensington lock) ，以及 I/O 埠存取安全性措施，以防止未經授權的裝置連接。 您也可以透過統一可擴展的固件介面或 UEFI (停用) 埠。

每個通過認證的計算模組都必須在預設啟用 2.0 相容 (TPM) 提供受信任的平臺模組。 TPM 是用來加密 Teams 會議室資源帳戶的登入資訊。

預設會啟用安全啟動。 安全啟動是電腦產業成員所開發的安全性標準，可協助確保裝置只使用原始設備製造商或 OEM (信任) 。 電腦啟動時，固件會檢查每個開機軟體的簽名，包括 UEFI (也稱為 Option ROM) 、EFI 應用程式和作業系統。 如果簽名有效，電腦會啟動，而該固件會提供作業系統的控制權。 詳細資訊，請參閱安全 [啟動](/windows-hardware/design/device-experiences/oem-secure-boot)。

只有附加實體鍵盤和滑鼠，才能存取 UEFI 設定。 這可防止透過 Teams 會議室觸控式主控台以及附加至 Teams 會議室的其他任何觸控顯示存取 UEFI。

核心直接記憶體存取 (DMA) 保護是 Windows 10 設定，在 Teams 會議室中啟用。 有了這項功能，作業系統和系統固件可保護系統，防範所有支援 DMA 的裝置受到惡意和意外的 DMA 攻擊：

- 在啟動過程中。

- 在 OS 執行時間期間，由裝置連接到易於訪問的內部/外部 DMA 埠 ，例如 M.2 PCIe 插槽和 Thunderbolt 3，以防範惡意 DMA。

Teams 會議室也可以啟用受 Hypervisor 保護 (HVCI) 。 HVCI 提供的功能之一是認證防護。 認證防護提供下列優點：

- **硬體安全性** NTLM、Kerberos 和認證管理員會利用平臺安全性功能 ，包括安全啟動和虛擬化來保護認證。

- **虛擬化安全性** Windows NTLM 和 Kerberos 衍生認證和其他機密是在與執行中的作業系統隔離的受保護環境中執行。

- **進一的保護，防範進一級的持續性威脅** 當認證管理員網域認證、NTLM 和 Kerberos 衍生認證使用虛擬化安全性受到保護時，許多目標攻擊中使用的認證竊取攻擊技術和工具會遭到封鎖。 在具有系統管理許可權的作業系統中執行惡意程式無法解壓縮受虛擬化安全性保護的機密。

## <a name="software-security"></a>軟體安全性

Microsoft Windows 啟動之後，Teams 會議室會自動登入名為 Skype 的本地 Windows 使用者帳戶。 Skype 帳戶沒有密碼。 若要確保 Skype 帳戶會話安全，請執行下列步驟。

> [!IMPORTANT]
> 請勿變更密碼或編輯當地 Skype 使用者帳戶。 這麼做可防止 Teams 會議室自動登入。

Microsoft Teams 會議室應用程式會使用 Windows 10 1903 及更新版本找到的已指派存取功能執行。 已指派 Access 是 Windows 10 中的一項功能，可限制公開給使用者的應用程式進入點。 這是啟用單一應用程式資訊站模式的方式。 使用 Shell 啟動器，Teams 會議室會配置為以使用者介面方式執行 Windows 桌面應用程式的資訊站裝置。 Microsoft Teams 會議室應用程式會取代預設 (explorer.exe) 命令，通常是在使用者登錄時執行。 換句話說，傳統的 Explorer shell 完全無法啟動。 這可大幅減少 Windows 中的 Microsoft Teams 會議室弱點表面。 若要詳細資訊，請參閱在 Windows 桌上出版上設定資訊站和 [數位記號](/windows/configuration/kiosk-methods)。

如果您決定在 Teams 會議室上執行安全性掃描或 Internet Security center (CIS) 基準，則掃描只能在當地系統管理員帳戶的情況下執行，因為 Skype 使用者帳戶不支援執行 Teams 會議室應用程式外的應用程式。 許多適用于 Skype 使用者上下文的安全性功能並不適用于其他當地使用者，因此這些安全性掃描無法顯示所有適用于 Skype 帳戶的安全性鎖定。 因此，不建議在 Teams 會議室上執行本地掃描。 不過，您可以執行外部穿透測試 ，如果需要的話。 因此，建議您針對 Teams 會議室裝置執行外部穿透測試，而不是執行本地掃描。

此外，鎖定原則會用來限制使用非系統管理功能。 已啟用鍵盤篩選來截取並封鎖指派的 Access 政策未涵蓋的潛在不安全鍵盤組合。 只有擁有當地或網域管理許可權的使用者才能登錄 Windows 來管理 Teams 會議室。 這些原則及其他適用于 Microsoft Teams 會議室裝置上的 Windows 原則，在產品生命週期期間會持續進行評估和測試。

## <a name="account-security"></a>帳戶安全性

Teams 會議室裝置包含具有預設密碼的名為「系統管理員」的管理帳戶。 我們強烈建議您完成設定後，儘快變更預設密碼。

系統管理帳戶不一定能夠正確運作 Teams 會議室裝置，而且可以重新命名或甚至刪除。 不過，刪除系統管理帳戶之前，請務必先設定已設定備用的本地系統管理員帳戶，再移除 Teams 會議室裝置所提供帳戶。 若要進一步瞭解如何使用內建的 Windows 工具或 PowerShell 變更當地 Windows 帳戶的密碼，請參閱下列內容：

- [變更或重設您的 Windows 密碼](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

您也可以將網域帳戶導入到本地 Windows 系統管理員群組。 您可以使用 Intune 為 Azure AD 帳戶執行此操作。 詳細資訊，請參閱策略 [CSP – 受限制的組。](/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!CAUTION]
> 如果您在將本地系統管理員許可權授予其他本地或網域帳戶之前先刪除或停用系統管理員帳戶，您可能會失去管理 Teams 會議室裝置的能力。 如果發生這種情況，您必須將裝置重設回其原始設定，然後再次完成設定程式。
>
> 請勿將本地系統管理員許可權授予 Skype 使用者帳戶。

Windows Configuration Designer 可用來建立 Windows 10 部署套件。 除了變更本機系統管理員密碼，您也可以執行變更電腦名稱稱及註冊 Azure Active Directory 等操作。 有關建立 Windows Configuration Designer 資源配置套件的資訊，請參閱 [Windows 10 的部署套件](/windows/configuration/provisioning-packages/provisioning-packages)。

您需要為每個 Teams 會議室裝置建立資源帳戶，以便它可以登錄 Teams。 此帳戶無法使用雙因素或多重要素驗證。 要求第二個要素會防止帳戶在重新開機後自動登入 Teams 會議室應用程式。 不過，您可以為此帳戶啟用新式驗證，以提供額外的安全性。 此外，您可以針對資源帳戶部署位置式條件式 Access 策略，以防止從未簽定的位置登入帳戶。 詳細資訊，請參閱在條件式 Access 策略 [中使用位置條件](/azure/active-directory/conditional-access/location-condition)

如果可能的話，建議您在 Azure AD 中建立資源帳戶。 雖然同步處理的帳戶可以在混合式部署中與 Teams 會議室合作，但這些同步處理的帳戶通常難以登錄 Teams 會議室，而且可能難以進行疑難排解。 如果您選擇使用協力廠商聯合服務驗證資源帳戶的認證，請確定協力廠商 IDP 會以設為 的屬性 `wsTrustResponse` 回應 `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>網路安全性

一般而言，Teams 會議室的網路需求與任何 Microsoft Teams 用戶端相同。 透過防火牆和其他安全性裝置存取 Teams 會議室與任何其他 Microsoft Teams 用戶端相同。 Teams 會議室特有的類別列為 Teams 的「必填」類別必須在您的防火牆上開啟。 如果您使用 Microsoft Intune 管理您的裝置，Teams 會議室也需要存取 Windows Update、Microsoft Store (Microsoft Intune) 。 有關 Microsoft Teams 會議室所需的 IP 和 URL 完整清單，請參閱：

- **Microsoft Teams** [Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [設定 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **商務與** 教育 [用 Microsoft Store 的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [網路 Enpoints for Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

如果您使用的是 Microsoft Teams 會議室進級版中的 Microsoft Teams 會議室管理服務元件，您也需要確認 Teams 會議室可以存取下列 URL：

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

Teams 會議室已配置為使用最新的 Windows 更新 ，包括安全性更新，自動進行修補。 Teams 會議室會使用預先設定的本地政策，每天從上午 2：00 開始安裝任何擱置的更新。 不需要使用其他工具來部署及應用 Windows 更新。 使用其他工具來部署及應用更新可能會延遲 Windows 修補程式的安裝，因此會導致較安全的部署。 Teams 會議室應用程式是使用 Microsoft Store 部署。 如果您的裝置是使用 Microsoft Teams 會議室標準版授權，則任何新版本的應用程式都會在夜間修補程式期間自動安裝。 如果您的裝置是使用 Microsoft Teams 會議室進級版授權，且已註冊 Microsoft Managed Service，則系統會按照您定義的推出計畫安裝新版本的 Teams 會議室應用程式。

Teams 會議室裝置可與大多數的 802.1X 或其他網路安全通訊協定共同作業。 不過，我們無法針對所有可能的網路安全性組組測試 Teams 會議室。 因此，如果發生可追蹤到網路性能問題的績效問題，您可能需要停用這些通訊協定 ，如果這些通訊協定已由貴組織所配置。

為了獲得最佳即時媒體的顯示效果，我們強烈建議您設定 Teams 媒體流量以忽略 Proxy 伺服器和其他網路安全性裝置。 即時媒體對於延遲非常敏感，Proxy 伺服器和網路安全性裝置可能會大幅降低使用者的視音訊品質。 此外，由於 Teams 媒體已經加密，因此透過 Proxy 伺服器傳遞流量並沒有明顯的好處。 若要詳細資訊，請參閱將 (網路) —一位架構設計師的觀點，探討使用 Microsoft Teams [和](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Microsoft Teams 會議室改善媒體績效的網路建議。

> [!IMPORTANT]
> Teams 會議室不支援經過驗證的 Proxy 伺服器。

Teams 會議室裝置不需要連接到內部 LAN。 請考慮將 Teams 會議室置於具有直接網際網路存取的安全網路區段中。 如果您的內部 LAN 遭到入侵，則 Teams 會議室的攻擊向量機會將會減少。

我們強烈建議您將 Teams 會議室裝置連接到有線網路。 不建議或認證 Teams 會議室裝置上的無線網路使用。 某些連接功能 ，例如 Wi-Fi，預設會停用。

鄰近連接和其他 Teams 會議室功能仰賴藍牙。 不過，Teams 會議室裝置上的藍牙實現不允許外部裝置連接到 Teams 會議室裝置。 Teams 會議室裝置上使用的藍牙技術目前僅限於廣告標誌和提示的正數連接。 通訊 `ADV_NONCONN_INT` 協定資料單位 (PDU) 用於廣告標誌。 此 PDU 類型適用于無法連接裝置向聆聽裝置廣告資訊。 這些功能沒有藍牙裝置配對。 您可以在藍牙 SIG 網站上找到藍牙通訊協定 [的其他詳細資料](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。