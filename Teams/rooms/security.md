---
title: Microsoft 團隊聊天室安全性
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
description: 瞭解如何保護您的 Microsoft 團隊機房裝置。
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880871"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft 團隊聊天室安全性

Microsoft 可與我們的合作夥伴合作，提供安全且不需要其他動作來保護 Microsoft 團隊聊天室的方案。 本文將討論在團隊聊天室中找到的許多安全性功能。

> [!NOTE]
> Microsoft 團隊聊天室不應看作是一般的使用者工作站。 使用案例不僅會有很大的差別，而且預設的安全性設定檔也會有很大的差異。

有限的最終使用者資料會儲存在團隊會議室。 最終使用者資料可能會儲存在記錄檔中，僅供疑難排解及支援。 在任何時候，都可以使用團隊聊天室將檔案複製到硬碟，或以自己的身分登入，以取得會議的參與者。 Microsoft 團隊聊天室裝置不會傳送任何使用者資料，也不能加以存取。

即使最終使用者無法將檔案放在小組聊天室的硬碟上，Microsoft Defender 仍處於啟用狀態。 團隊會議室效能是使用 Microsoft Defender 進行測試。 停用此或新增端點安全性軟體可能會造成不可預期的結果，並可能造成系統降級。

## <a name="hardware-security"></a>硬體安全性

在團隊會議室環境中，有一個可執行 Windows 10 IoT Enterprise edition 的中央計算模組。 每個認證的計算模組都必須有一個安全的安裝方案， (例如，Kensington 鎖) ，以及輸入輸出連接埠存取安全性措施，以防止連線未獲授權的裝置。 您也可以透過整合的可延伸韌體介面 (UEFI) 設定來停用特定的埠。

每個認證的計算模組都必須隨附受信任的平臺模組， (預設會啟用 TPM) 2.0 相容性技術。 使用 TPM 來加密團隊聊天室資源帳戶的登入資訊。

預設會啟用 [安全啟動]。 [安全引導] 是由電腦行業成員所開發的安全性標準，以協助確保裝置只使用原始設備製造商所信任的軟體來啟動 (OEM) 。 當電腦啟動時，固件會檢查每一段啟動軟體的簽名，包括 UEFI 固件驅動程式 (也稱為選項 Rom) 、EFI 應用程式及作業系統。 如果簽章有效，電腦會啟動，且固件會將控制權提供給作業系統。 如需詳細資訊，請參閱 [安全啟動](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

只要附加物理鍵盤和滑鼠，即可存取 UEFI 設定。 這可防止透過 [小組會議室] 觸控式主機，以及附加至團隊聊天室的任何其他觸控式顯示器來存取 UEFI。

內核直接記憶體存取 (DMA) 防護是在團隊聊天室上啟用的 Windows 10 設定。 使用這項功能時，OS 和系統固件會針對所有支援 DMA 的裝置，防止系統受到惡意和非預期的 DMA 攻擊：

- 在啟動程式中。

- 在作業系統執行時間中，將裝置連線至易於存取的內部/外部 DMA 支援埠（例如 M. 2 PCIe 槽和 Thunderbolt 3），防範惡意的 DMA。

[團隊聊天室] 也會啟用受管理程式保護的程式碼完整性 (HVCI) 。 HVCI 提供的其中一個功能是認證防護。 Credential Guard 提供下列優點：

- **硬體安全性** NTLM、Kerberos 和認證管理員利用平臺安全性功能（包括安全的啟動和虛擬化）來保護認證。

- 以 **虛擬化為基礎的安全性** Windows NTLM 和 Kerberos 衍生的認證及其他機密都是在受保護的環境中執行，並獨立于執行中的作業系統。

- **針對高級持久性威脅提供更佳的防護** 如果認證管理員網域認證、NTLM 及 Kerberos 衍生認證是使用虛擬化安全性進行保護，則會封鎖在許多目標攻擊中使用的認證盜竊攻擊技術與工具。 在具有系統管理許可權的作業系統中執行的惡意程式碼無法提取受虛擬化安全性保護的機密資訊。

## <a name="software-security"></a>軟體安全性

在 Microsoft Windows 啟動後，小組聊天室會自動登入名為 Skype 的本機 Windows 使用者帳戶。 Skype 帳戶沒有密碼。 若要讓 Skype 帳戶會話安全，請採取下列步驟。

> [!IMPORTANT]
> 請勿變更密碼或編輯本機 Skype 使用者帳戶。 如此一來，就能防止小組聊天室自動登入。

Microsoft 團隊聊天室 app 會使用在 Windows 10 1903 和更新版本中找到的已指派 Access 功能來執行。 指派的存取權是 Windows 10 中的一項功能，可限制向使用者公開的應用程式進入點。 這就是啟用單一應用程式亭模式的情況。 使用 [Shell 啟動器]，將 [團隊聊天室] 設定為展臺裝置，並以使用者介面的方式執行 Windows 桌面應用程式。 Microsoft [小組聊天室] app 會取代預設的 shell ( # A0) ，該命令會在使用者登入時執行。 換句話說，傳統的瀏覽器 shell 根本無法啟動。 這可大大減少 Windows 中的 Microsoft 團隊聊天室漏洞表面。 如需詳細資訊，請參閱 [在 Windows 桌上出版上設定網亭和數位簽章](https://docs.microsoft.com/windows/configuration/kiosk-methods)。

如果您決定在 Internet 安全性 () CIS 上執行安全性掃描或中心，則在團隊間的內容中，掃描只能在本機管理員帳戶的內容下執行，因為 Skype 使用者帳戶不支援執行團隊聊天室 app 以外的應用程式。 套用至 Skype 使用者內容的許多安全功能不適用於其他當地使用者，因此，這些安全性掃描不會顯示已套用到 Skype 帳戶的完整安全性鎖定。 因此，建議您不要在團隊聊天室上執行本機掃描。 不過，您可以視需要執行外部滲透測試。 因此，建議您針對團隊機房裝置執行外部滲透測試，而不是執行本機掃描。

此外，還會套用鎖定原則，以限制非系統管理功能的使用。 已啟用鍵盤篩選，以截獲並封鎖指派的存取原則未涵蓋的可能不安全的鍵盤組合。 只有具備本機或網域系統管理許可權的使用者才能登入 Windows，以管理團隊聊天室。 在 Microsoft 團隊聊天室裝置上套用到 Windows 的這些及其他原則，都會在產品週期期間持續進行評定及測試。

## <a name="account-security"></a>帳戶安全性

團隊室裝置包括名為「Admin」的管理帳戶，且具有預設密碼。 我們強烈建議您在完成安裝後儘快變更預設密碼。

[管理員] 帳戶不需要用來適當運作小組室裝置，而且可以重新命名甚至刪除。 不過，在您刪除系統管理員帳戶之前，請先確認您已設定備用的本機系統管理員帳戶，然後再移除與團隊聊天室裝置一起隨附的帳戶。 如需如何使用內建 Windows 工具或 PowerShell 變更本機 Windows 帳戶的密碼的詳細資訊，請參閱下列內容：

- [變更或重設您的 Windows 密碼](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

您也可以匯入網域帳戶至本機 Windows 系統管理員群組。 您可以使用 Intune 針對 Azure AD 帳戶執行這項作業。 如需詳細資訊，請參閱[原則 CSP – RestrictedGroups。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> 如果您在將本機系統管理員許可權授與其他本地或網域帳戶之前，刪除或停用管理員帳戶，您可能會失去管理團隊聊天室裝置的功能。 如果發生這種情況，您必須將裝置重設回原始設定，然後再次完成設定程式。
>
> 不要將本機系統管理員許可權授與 Skype 使用者帳戶。

Windows 配置設計工具可以用來建立 Windows 10 預配套件。 除了變更本機管理員密碼以外，您也可以執行下列動作，例如變更電腦名稱稱並註冊至 Azure Active Directory。 如需建立 Windows 配置設計工具設計套件的詳細資訊，請參閱 [預配 Windows 10 套件](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)。

您必須為每個團隊聊天室裝置建立資源帳戶，才能登入團隊。 您無法在此帳戶中使用雙因素或多重要素驗證。 需要第二個因素會使帳戶在重新開機後無法自動登入小組聊天室 app。 不過，您可以針對此帳戶啟用 [新式驗證] 以取得額外的安全性。 此外，您還可以針對資源帳戶部署根據位置設定的條件式存取原則，避免從未核准的位置登入該帳戶。 如需詳細資訊，請參閱 [在條件式存取原則中使用位置條件](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

我們建議您在 Azure AD 中建立資源帳戶（如果可能的話）。 雖然已同步處理的帳戶可以與混合式部署中的團隊聊天室搭配運作，但是這些同步處理的帳戶通常難以登入小組聊天室，而且難以進行疑難排解。 如果您選擇使用協力廠商同盟服務驗證資源帳戶的認證，請確保協力廠商 IDP 回應 `wsTrustResponse` 屬性設定為 `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>網路安全性

一般來說，小組聊天室與任何 Microsoft 團隊用戶端的網路需求相同。 透過防火牆和其他安全裝置存取，與任何其他 Microsoft 團隊用戶端一樣，都是對團隊聊天室而言。 針對團隊聊天室而言，您必須在防火牆上開啟列為團隊的 [必要] 類別的類別。 如果您使用 Microsoft Intune 管理裝置) ，小組聊天室也需要存取 Windows Update、Microsoft Store 及 Microsoft Intune (。 如需 Microsoft 團隊聊天室所需的 IPs 與 Url 完整清單，請參閱：

- **Microsoft 團隊** [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [設定 WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- Microsoft **Store** [商務用 Microsoft store For Business 和教育版的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- Microsoft intune 的 **Microsoft intune** [Network Enpoints](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

如果您使用的是 Microsoft 團隊聊天室 Premium 的 Microsoft 團隊聊天室 [託管服務] 元件，您也必須確認小組聊天室可以存取下列 Url：

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

[團隊聊天室] 會設定為使用最新的 Windows 更新自動修補，包括安全性更新。 [小組聊天室] 會從2：00am 使用預先設定的本機原則，在每天開始安裝任何掛起的更新。 您不需要使用額外的工具來部署和套用 Windows 更新。 使用其他工具來部署和套用更新可能會延遲 Windows 修補程式的安裝，因此會導致部署較不安全。 [團隊聊天室] app 是透過 Microsoft Store 來部署。 如果您的裝置是由 Microsoft 團隊聊天室標準授權，則任何新的應用程式版本都會在夜間修補程式期間自動安裝。 如果您的裝置是使用 Microsoft 團隊聊天室的授權，且已註冊 Microsoft Managed 服務，則新版本的團隊聊天室 app 會根據您定義的推出方案進行安裝。

團隊會議室裝置可搭配大部分的 802.1 X 或其他網路安全通訊協定使用。 不過，我們無法針對所有可能的網路安全性設定來測試小組聊天室。 因此，如果發生性能問題，可能會追蹤網路效能問題，您可能需要停用這些通訊協定（如果您的組織已設定）。

為了獲得即時媒體的最佳效能，我們強烈建議您將小組媒體流量設定為略過 proxy 伺服器及其他網路安全裝置。 即時媒體非常容易受到影響，而且 proxy 伺服器和網路安全裝置會大大降低使用者的影片和音訊品質。 此外，因為團隊媒體已加密，所以透過 proxy 伺服器傳遞流量沒有實實在在的好處。 如需詳細資訊，請參閱 [將 (加入雲端) —一種結構化的視點，](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) 討論網路建議，以利用 microsoft 團隊和 Microsoft 團隊聊天室來改善媒體效能。

> [!IMPORTANT]
> 團隊聊天室不支援驗證的 proxy 伺服器。

團隊室裝置不需要連線至內部局域網。 考慮透過直接網際網路存取將小組放在安全的網段中。 如果內部 LAN 遭到破壞，就會減少對團隊聊天室的攻擊向量機會。

我們強烈建議您將團隊機房裝置連線至有線網路。 不建議或驗證在團隊室裝置上使用無線網路。 某些連接功能（例如 Wi-Fi 感知）預設會停用。

鄰近性聯接和其他團隊聊天室功能都依賴藍牙。 不過，小組機房裝置上的藍牙實現不允許外部裝置連線至團隊聊天室裝置。 團隊室裝置上的藍牙技術使用目前僅限於廣告信標與提示近端連線。 在 `ADV_NONCONN_INT` 廣告信標中使用通訊協定資料單位 (PDU) 類型。 此 PDU 類型適用于不連接的裝置向接聽裝置公佈資訊的情況。 在這些功能中，沒有藍牙裝置配對。 您可以在 [藍牙 SIG 網站](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)上找到藍牙通訊協定的其他詳細資料。
