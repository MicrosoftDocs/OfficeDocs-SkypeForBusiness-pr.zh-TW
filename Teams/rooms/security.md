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
ms.openlocfilehash: 522cc845e2e6b8b1f57fc0ab1c1523452ec429f8
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395375"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 會議室安全性

Microsoft 與合作夥伴合作，以提供安全的解決方案，而且不需要額外動作來保護 Microsoft Teams 會議室。 本文將討論 Teams 會議室的許多安全性功能。

> [!NOTE]
> Microsoft Teams 會議室不應視為一般的使用者工作站。 不僅使用案例差異很大，預設的安全性設定檔也差異很大。

有限的使用者資料會儲存在 Teams 會議室中。 使用者資料可能儲存在記錄檔案中，只用于疑難排解和支援。 任何使用 Teams 會議室的會議出席者都不得將檔案複製到硬碟，或以自己的方式進行登錄。 使用者資料不會傳輸至 Microsoft Teams 會議室裝置，或供其便於使用。

即使使用者無法將檔案放在 Teams 會議室硬碟上，Microsoft Defender 仍然啟用。 使用 Microsoft Defender 測試 Teams 會議室的績效。 停用此功能或新增端點安全性軟體可能會導致無法預期的結果，並可能導致系統品質降低。

## <a name="hardware-security"></a>硬體安全性

在 Teams 會議室環境中，有一個執行 Windows 10 IoT Enterprise 版本的中央計算模組。 每個通過認證的計算模組都必須有安全的安裝解決方案、安全鎖定插槽 (例如，Kensington lock) ，以及 I/O 埠存取安全性措施，以防止未經授權的裝置連接。 您也可以透過 UEFI 或 UEFI 的一致可擴展 (停用) 埠。

每個通過認證的計算模組都必須在 TPM (中提供) 2.0 相容技術。 TPM 是用來加密 Teams 會議室資源帳戶的登入資訊。

安全開機預設為啟用。 安全開機是電腦產業成員所開發的安全性標準，可協助確保裝置只能使用原始設備製造商或 OEM (信任) 。 電腦啟動時，系統會檢查每個開機軟體的簽章，包括 UEFI (也稱為 Option ROMS) 、EFI 應用程式和作業系統。 如果簽章有效，則電腦會啟動，而該系式會提供作業系統的控制權。 詳細資訊請參閱安全 [開機](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

只有附加實體鍵盤和滑鼠，才能存取 UEFI 設定。 這可防止透過 Teams 會議室觸控式主機以及附加至 Teams 會議室的其他任何觸控式顯示器存取 UEFI。

核心直接記憶體存取 (DMA) 保護是 Teams 會議室上啟用的 Windows 10 設定。 使用這項功能，作業系統和系統功能可保護系統，防範所有支援 DMA 的裝置受到惡意和意外的 DMA 攻擊：

- 在開機過程中。

- 在作業系統執行時間期間，由裝置連接至易於易於訪問的內部/外部 DMA 支援埠的惡意 DMA，例如 M.2 PCIe 插槽和 Thunderbolt 3。

Teams 會議室也可在 HVCI (啟用受 Hypervisor 保護) 。 HVCI 提供的其中一項功能是認證防護。 認證防護提供下列優點：

- **硬體安全性** NTLM、Kerberos 和認證管理員利用平臺安全性功能 ，包括 Secure Boot 和虛擬化來保護認證。

- **虛擬化式安全性** Windows NTLM 和 Kerberos 衍生認證及其他機密檔是在與執行中的作業系統隔離的受保護環境中執行。

- **進一的保護，防範進一級的持續性威脅** 當認證管理員網域認證、NTLM 和 Kerberos 衍生認證受到虛擬化式安全性保護時，許多目標攻擊中使用的認證竊取攻擊技術和工具會遭到封鎖。 在具有系統管理許可權的作業系統中執行惡意程式無法解壓縮受到虛擬化安全性保護的機密。

## <a name="software-security"></a>軟體安全性

Microsoft Windows 啟動之後，Teams 會議室會自動進入名為 Skype 的當地 Windows 使用者帳戶。 Skype 帳戶沒有密碼。 若要確保 Skype 帳戶會話安全，請執行下列步驟。

> [!IMPORTANT]
> 請勿變更密碼或編輯當地 Skype 使用者帳戶。 如此一來，Teams 會議室就會無法自動進行登錄。

Microsoft Teams 會議室應用程式會使用 Windows 10 1903 及更新版本所找到的已指派存取功能執行。 指派的 Access 是 Windows 10 中的一項功能，可限制向使用者公開的應用程式進入點。 這是啟用單一應用程式資訊站模式的方式。 使用 Shell 啟動器，Teams 會議室會做為資訊站裝置，以使用者介面方式執行 Windows 桌面應用程式。 Microsoft Teams 會議室應用程式會取代預設命令 (explorer.exe) 命令命令，通常是在使用者登錄時執行。 換句話說，傳統的 Explorer 命令層完全不會啟動。 這會大幅縮減 Windows 中的 Microsoft Teams 會議室弱點表面。 詳細資訊請參閱在 Windows 桌上出版上設定資訊站 [和數位記號](https://docs.microsoft.com/windows/configuration/kiosk-methods)。

如果您決定在 Teams 會議室上執行安全性掃描或網際網路安全性中心 (或 INTERNET Security center) 的基準，則掃描只能在當地系統管理員帳戶的上下文下執行，因為 Skype 使用者帳戶不支援執行 Teams 會議室應用程式外的應用程式。 許多適用于 Skype 使用者內容的安全性功能不適用於其他當地使用者，因此，這些安全性掃描不會顯示 Skype 帳戶所適用的完整安全性鎖定。 因此，不建議在 Teams 會議室上執行本地掃描。 不過，如果需要，您可以執行外部測試。 因此，建議您對 Teams 會議室裝置執行外部測試，而不是執行本地掃描。

此外，鎖定原則會用來限制非系統管理功能的使用。 鍵盤篩選會啟用以截距並封鎖可能由指派的 Access 策略涵蓋的鍵盤組合。 只有擁有本地或網域管理許可權的使用者，才能使用 Windows 來管理 Teams 會議室。 Microsoft Teams 會議室裝置上適用于 Windows 的這些及其他原則，在產品生命週期期間會持續進行評估和測試。

## <a name="account-security"></a>帳戶安全性

Teams 會議室裝置包含一個名為「系統管理員」的管理帳戶，並包含預設密碼。 我們強烈建議您完成設定後，儘快變更預設密碼。

系統管理帳戶不需要，因此無法正確操作 Teams 會議室裝置，而且可以重新命名或甚至刪除。 不過，刪除系統管理員帳戶之前，請務必先設定替代的當地系統管理員帳戶，再移除 Teams 會議室裝置上提供的帳戶。 若要瞭解如何使用內建的 Windows 工具或 PowerShell 變更本地 Windows 帳戶的密碼，請參閱下列內容：

- [變更或重設您的 Windows 密碼](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

您也可以將網域帳戶導入到本地 Windows 系統管理員群組。 您可以使用 Intune 為 Azure AD 帳戶執行此工作。 詳細資訊請參閱政策[CSP – RestrictedGroups。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> 如果您在將本地系統管理員許可權授予另一個本地或網域帳戶之前刪除或停用系統管理員帳戶，可能會失去管理 Teams 會議室裝置的能力。 如果發生這種情況，您必須將裝置重設回原始設定，並再次完成設定程式。
>
> 不要將本地系統管理員許可權授予 Skype 使用者帳戶。

Windows 組組設計工具可用來建立 Windows 10 的部署套件。 除了變更本機系統管理員密碼，您也可以進行變更電腦名稱稱及註冊 Azure Active Directory 等操作。 有關建立 Windows 組組設計工具設置套件的資訊，請參閱 [Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)的部署套件。

您需要為每個 Teams 會議室裝置建立資源帳戶，以便它可以進入 Teams。 此帳戶無法使用雙因素或多重要素驗證。 要求第二個要素會防止帳戶在重新開機後自動進入 Teams 會議室應用程式。 不過，您可以針對此帳戶啟用新式驗證，以提供額外的安全性。 此外，您可以為資源帳戶部署位置式條件式存取政策，以防止從未申請的位置登入帳戶。 詳細資訊請參閱在條件 [式存取政策中使用位置條件](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

建議您盡可能在 Azure AD 中建立資源帳戶。 雖然同步處理的帳戶可以在混合式部署中與 Teams 會議室一起使用，但這些同步處理的帳戶通常難以進入 Teams 會議室，而且可能難以進行疑難排解。 如果您選擇使用協力廠商聯合服務來驗證資源帳戶的認證，請確定協力廠商 IDP 會以屬性設為 `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` 來回應。

## <a name="network-security"></a>網路安全性

一般而言，Teams 會議室的網路需求會和任何 Microsoft Teams 用戶端相同。 透過防火牆和其他安全性裝置存取 Teams 會議室的方式，與任何其他 Microsoft Teams 用戶端相同。 針對 Teams 會議室，列為「必填」的類別必須在您的防火牆上開啟。 如果您使用 Microsoft Intune 管理裝置或裝置，Teams 會議室也需要存取 Windows Update、Microsoft Store 和 Microsoft Intune)  (。 有關 Microsoft Teams 會議室所需的 IP 和 URL 完整清單，請參閱：

- **Microsoft Teams** [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [設定 WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **商務用**[與教育用 Microsoft Store 的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [網路 Enpoints for Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

如果您使用的是 Microsoft Teams Rooms Premium 的 Microsoft Teams 會議室管理服務元件，您也需要確認 Teams 會議室可以存取下列 URL：

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

Teams 會議室已進行自動修補，以使用最新的 Windows 更新 ，包括安全性更新。 Teams 會議室會使用預先設定的本地政策，從每天上午 2：00 開始安裝任何擱置的更新。 不需要使用其他工具來部署及使用 Windows Updates。 使用其他工具來部署及應用更新可能會延遲 Windows 修補程式的安裝，因而導致較不安全的部署。 Teams 會議室應用程式是使用 Microsoft Store 部署。 如果您的裝置已授權使用 Microsoft Teams 會議室標準版，則任何新版本的應用程式都會在夜間修補程式期間自動安裝。 如果您的裝置是使用 Microsoft Teams Rooms Premium 授權，且已註冊 Microsoft Managed Service，則系統會按照您定義的推出計畫安裝新版本的 Teams 會議室應用程式。

Teams 會議室裝置可與大多數的 802.1X 或其他網路式安全性通訊協定一起使用。 不過，我們無法針對所有可能的網路安全性組配置測試 Teams 會議室。 因此，如果發生可追蹤到網路績效問題的績效問題，您可能需要停用這些通訊協定 ，如果這些通訊協定在貴組織中已進行配置。

為了獲得最佳即時媒體的績效，我們強烈建議您將 Teams 媒體流量設定為忽略 Proxy 伺服器和其他網路安全性裝置。 即時媒體對於延遲非常敏感，Proxy 伺服器和網路安全性裝置可能會大幅降低使用者的視音訊品質。 此外，由於 Teams 媒體已加密，因此透過 Proxy 伺服器傳遞流量並沒有明顯的好處。 詳細資訊請參閱將網路 (到雲端 [) —](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) 這是一位架構的點子，其探討使用 Microsoft Teams 和 Microsoft Teams 會議室改善媒體的績效的網路建議。

> [!IMPORTANT]
> Teams 會議室不支援已驗證的 Proxy 伺服器。

Teams 會議室裝置不需要連接到內部 LAN。 考慮將 Teams 會議室置於安全的網路區段中，並直接存取網際網路。 如果您的內部 LAN 遭到入侵，對 Teams 會議室的攻擊向量機會將會減少。

強烈建議您將 Teams 會議室裝置連接至有線網路。 不建議或認證 Teams 會議室裝置上使用無線網路。 某些連接功能 ，例如 Wi-Fi，預設會停用。

鄰近連接和其他 Teams 會議室功能仰賴藍牙。 不過，Teams 會議室裝置上的藍牙實現不允許外部裝置連接到 Teams 會議室裝置。 Teams 會議室裝置上的藍牙技術目前僅限於廣告燈和提示的正數連接。 在 `ADV_NONCONN_INT` 廣告燈中 (PDU) 類型的通訊協定資料單位。 此 PDU 類型適用于無法連接裝置向聆聽裝置廣告資訊。 這些功能沒有藍牙裝置配對。 您可以在藍牙 SIG 網站上找到藍牙通訊協定的其他 [詳細資料](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
