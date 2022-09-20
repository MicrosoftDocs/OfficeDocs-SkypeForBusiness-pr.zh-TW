---
title: 設定 SIP 閘道
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 瞭解如何設定 SIP 閘道。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f21ce36c1c44b14b80c9ae1684a65c6bd82b7d63
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808874"
---
# <a name="configure-sip-gateway"></a>設定 SIP 閘道

本文說明如何設定 SIP 閘道，讓貴組織能夠使用與 Microsoft Teams 相容的 SIP 裝置。 若要瞭解 SIP 閘道可為貴組織執行哪些工作，以及貴組織需要哪些硬體、軟體和授權，請閱讀 [規劃 SIP 閘道](sip-gateway-plan.md)。

設定 SIP 閘道之前，請執行下列動作：

- **將 SIP 裝置重設為原廠預設設定。** 您或貴組織的使用者必須將搭配 SIP 閘道使用的每個 SIP 裝置重設為原廠預設設定。 若要瞭解做法，請參閱製造商的指示。

- **開啟您的防火牆至 Microsoft 365 和 Teams。** 開啟網路防火牆至 Microsoft 365 和 Teams 流量[，如Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)中所述。 輸出流量只需要防火牆規則。

- **請確定 SIP 裝置不在 Proxy 之後。** 確定 HTTP/s 流量略過任何公司 HTTP/s Proxy。

- **開啟 UDP 埠。** 針對 IP 範圍 52.112.0.0.0/14 和 52.120.0.0/14，開啟範圍 49152 到 53247 中的 UDP 埠。

- **開啟 TCP 埠。** 開啟 IP 範圍為 52.112.0.0.14 和 52.120.0.0/14 的 TCP 埠 5061。

- **開啟下列 HTTPs 端點 (IP 位址和 URL) ：**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net


下列各節說明您必須以系統管理員身分執行哪些動作，才能設定 SIP 閘道。

- [確認您的組織可使用 SIP 閘道](#verify-that-sip-gateway-is-available-for-your-organization)。

- [為組織中的使用者啟用 SIP 閘道](#enable-sip-gateway-for-the-users-in-your-organization)。

- [設定 SIP 閘道布建伺服器 URL](#set-the-sip-gateway-provisioning-server-url)。

本文也說明如何：

- [為方便起見，請個別或分批註冊 SIP 裝置](#provision-and-enroll-sip-devices-as-common-area-phones)。  

- [檢視及監視您的 SIP 裝置。](#view-and-monitor-sip-devices)

- [啟用多語言使用者介面的支援。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>確認您的組織可使用 SIP 閘道

1. 登入 [Teams 系統管理中心](https://admin.teams.microsoft.com/)。

2. 在左側，選取 **[Teams 裝置** ]，並查看 **是否顯示 [SIP 裝置** ] 索引標籤。 如果是，表示您的組織已啟用 SIP 閘道服務。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>為組織中的使用者啟用 SIP 閘道

您可以透過下列兩種方式為貴組織啟用 SIP 閘道：使用 Teams 系統管理中心，或使用 PowerShell Cmdlet。

### <a name="by-using-teams-admin-center"></a>使用 Teams 系統管理中心

若要在 Teams 系統管理中心啟用 SIP 閘道，請遵循下列步驟：

1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com/)

2. 在左側的 [ **語音] 底** 下，選取 [ **通話原則]**。

3. 在右側的 [ **管理原則] 底** 下，選取指派給使用者的適當通話原則，或視需要建立新的通話原則，並將它指派給必要的使用者。

4. 選 **取 [管理原則**]，選取原則，然後選取 [ **編輯]**。

5. 開啟 **SIP 裝置的設定可用於通話**，然後選取 [ **儲存]**。


### <a name="by-using-powershell"></a>使用 PowerShell

您也可以使用 PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Cmdlet 來啟用 SIP 閘道。 若要啟用 SIP 裝置的使用者，請選取原則，並將屬性設 `-AllowSIPDevicesCalling` 為 `True` 。 預設值為 `False` ，因此除非您啟用，否則使用者將無法使用他們的 SIP 裝置。

> [!NOTE]
> - 原則傳播最多可能需要 24 小時。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>設定 SIP 閘道布建伺服器 URL

您可以在動態主機設定通訊協定 (DHCP) 伺服器中設定 SIP 閘道布建伺服器的 URL。 遠端工作的使用者必須手動設定。

### <a name="using-dhcp"></a>使用 DHCP

針對每個 SIP 裝置，設定下列其中一個 SIP 閘道布建伺服器 URL： 

- Emea： `http://emea.ipp.sdg.teams.microsoft.com`
- 美洲： `http://noam.ipp.sdg.teams.microsoft.com`
- 亞太： `http://apac.ipp.sdg.teams.microsoft.com`

在您的 DHCP 伺服器中設定上述 SIP 閘道布建伺服器 URL，將 SIP 裝置新增至您的 Teams 組織。 若要深入瞭解 DHCP 伺服器，請參閱 [部署和管理 DHCP](/training/modules/deploy-manage-dynamic-host-configuration-protocol)。 此外，您也可以使用 DHCP 選項 42 來指定網路時間通訊協定 (NTP) 伺服器，而 DHCP 選項 2 則可在幾秒內指定從協調通用時間 (UTC) 的位移。 貴組織中的裝置將會路由至 SIP 閘道布建伺服器。 已成功布建的 SIP 手機會顯示 Teams 標誌和用於登入的柔和按鈕。

確定 SIP 裝置在最低支援的韌體版本上進行上線。 在上線期間，SIP 閘道會將預設設定和驗證使用者介面推送到裝置。 若要瞭解 SIP 裝置所需的韌體版本，請參閱 [規劃 SIP 閘道](sip-gateway-plan.md)。

### <a name="manually"></a>手動

遠端工作的使用者必須使用下列步驟，在 SIP 裝置上手動設定布建伺服器 URL：

1. 開啟裝置上的 **[設定** ]，並取得裝置的 IP 位址。

2. 開啟瀏覽器視窗、輸入裝置的 IP 位址、必要時登入 () ，然後在裝置的 Web 公用程式中設定布建伺服器的 URL。

3. 在 [ **設定]** 或 [Web 公用程式的 **進階設定** ] 底下，輸入上述的布建伺服器 URL。

> [!NOTE]
> - 只有相容的 SIP 裝置可以登入 SIP 閘道。 
> - Cisco IP 手機必須閃爍為多重格式韌體，才能上線。 若要瞭解做法，請參閱 [Cisco 韌體轉換指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)。
> - 如果是 Yealink 手機，請使用選項 66。
> - 對於 Cisco、Poly 和 AudioCode 手機，請使用選項 160。 
> - 對於 Cisco 裝置，請在布建伺服器 URL **中附加 /$PSN.xml** 。


## <a name="configure-conditional-access"></a>設定條件式存取

條件式存取是 Azure Active Directory (Azure AD) 功能，可協助確保可正確管理且安全地管理存取 Microsoft 365 資源的裝置。 SIP 閘道會使用 Azure AD 驗證 SIP 裝置，因此如果您的組織針對公司網路中的裝置使用條件式存取，則應排除下列 IP 位址：

- 北美洲：
    - 美國東部：52.170.38.140
    - 美國西部：40.112.144.212
-   EMEA 地區：
    - 北歐盟：40.112.71.149
    - 歐盟西部：40.113.112.67
-   APAC 地區：
    - 澳洲東部：20.92.120.71
    - 澳大利亞東南亞：13.73.115.90

如需詳細資訊，請參閱 [IP 位址範圍](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)。

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>布建 SIP 裝置並註冊為常見區域電話

> [!NOTE]
> SIP 裝置必須先登入 SIP 閘道，才能註冊。

若要簡化您的工作，您可以在 Teams 系統管理中心一次或分批註冊 SIP 裝置。 方法如下：

1. 登入 [**Teams 系統管理中心**](https://admin.teams.microsoft.com)。

2. 選 **取 Teams 裝置**  >  **SIP 裝置**。

3. 在右上角，選取 **[動作**  >  **布建裝置**]，然後依照下列其中一個步驟執行：

  - **若要布建一部裝置：**

     a. 在 **[等待啟用] 底** 下，選取 [ **新增]**。

     b. 在 [ **新增 MAC 位址]** 窗格中，輸入 **MAC 位址** 和裝置 **的位置** ，然後選取 [ **套用]**。
     
     C。 在 **[等待啟用] 底** 下，選取您剛新增的裝置，然後選 **取 [產生驗證碼]**。
     
     D。 在 [ **布建裝置]** 窗格的 [ **驗證碼**] 底下，記下 SIP 裝置的驗證碼。

   - **若要布建許多裝置：**

     a. 在 **[等待啟用**] 底下的右側，選取 [ **導** 出 (Microsoft Excel 圖示) 。
     
     b. 在 [ **布建裝置]** 窗格的 [ **上傳多個 MAC 位址**] 底下，選 **取 [下載範本]**。
     
     C。 **將Template_Provisioning.csv** 儲存到您的電腦，並填入 **MAC 識別碼** 和 **[位置] 字** 段。
    
     D。 在 [ **布建裝置]** 窗格中，選取 **[上傳多個 MAC 位址]**。 

     e. 在 [ **上傳 MAC 位址** ] 窗格右側， **選取 [選取檔案**]，然後選取包含您資料 **的Template_Provisioning.csv** 檔案。

     F。 在 [ **布建裝置]** 窗格 **的 [等待啟用**] 底下，選取裝置，然後選取 [ **產生驗證碼** ]，為每個布建的裝置產生一次性驗證碼。 記下每個 SIP 裝置的驗證碼。

4. 在 SIP 裝置上，撥打註冊功能代碼，後面接著驗證碼。 在 SIP 裝置上，撥打 SIP 閘道用來註冊一次性驗證碼驗證) 的註冊功能代碼 \* 55* (，後面接著在 Teams 管理員 Center 針對此特定裝置產生的驗證碼。 例如，如果驗證碼123456，請撥打 \* 55 \* 123456註冊裝置。

5.  在 [ **布建裝置]** 窗格的 **[等待登入**] 底下，選取 [ **登出]**。

6. 在 [ **登入使用者** ] 對話方塊中，複製或記下 SIP 裝置的配對代碼。

7. 移至 [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) ，然後在 **[輸入代碼**] 底下，輸入 SIP 裝置的配對碼，然後選取 [ **下一步]**。

8. 在 [Microsoft **登入**] 頁面的 **[Email 或電話**] 欄位中，輸入 SIP 裝置的電子郵件地址，然後選取 [**下一步]**。

9. 在 [ **密碼]** 頁面上，輸入 SIP 裝置的電子郵件地址密碼，然後選取 [ **登入]**。

10. 在 **[您嘗試登入 Teams SIP 裝置閘道** 嗎？] 頁面上，選取 [ **繼續]**。

## <a name="how-to-sign-in-and-sign-out"></a>如何登入和登出

使用者的個人裝置僅支援本機登入。 若要從管理員中心登出裝置，請遵循下列步驟：

1. 登入 [**Teams 系統管理中心**](https://admin.teams.microsoft.com)。

2. 選 **取 Teams 裝置**  >  **SIP 裝置**。

3. 在右側選取 SIP 裝置，然後選取 [ **登出]**。


### <a name="user-pairing-and-sign-in"></a>使用者配對和登入

若要在使用者使用公司認證進行驗證後配對 SIP 裝置，使用者必須：

1. **在** SIP 手機上按下登入以顯示驗證 URL 和配對程式碼。 配對程式碼會區分時間。 如果過期，使用者必須在手機上按 **返回** ，然後再次開始登入程式。

2. 流覽至使用者桌面或行動瀏覽器上的驗證 URL，並使用公司認證登入。

3. 將 SIP 手機上顯示的配對代碼輸入 Web 驗證應用程式，將 SIP 手機與使用者的帳戶配對。 成功登入可能需要一些時間，如果裝置支援，SIP 手機將會顯示電話號碼和使用者名稱。

> [!NOTE]
> Azure Active Directory Web 驗證應用程式上顯示的裝置位置是裝置連線至的 SIP 閘道資料中心。 範圍內的 SIP 手機不支援 OAuth 功能，因此 SIP 閘道會透過 Web 驗證應用程式驗證使用者，然後將裝置與使用者的認證配對。 在這裡深入瞭解：[Microsoft 身分識別平臺和 OAuth 2.0 裝置授權授與流程](/azure/active-directory/develop/v2-oauth2-device-code)。

### <a name="sign-out"></a>登出

若要登出，裝置使用者可以：

- 在 SIP 裝置上按 [ **登出** ]，然後依照裝置上所述的步驟執行。 

若要在 Teams 系統管理中心登出裝置：

1. 登入 [**Teams 系統管理中心**](https://admin.teams.microsoft.com)。

2. 選 **取 Teams 裝置**  >  **SIP 裝置**。

3. 在右側 **的 [SIP 裝置** ] 窗格中，選取裝置。

4. 在裝置的 [ **詳細資料] 窗格** 中，選取 [ **詳細** 資料] 索引標籤，然後在 [ **動作** ] 功能表右上角選取 [ **登出]**。 

## <a name="view-and-monitor-sip-devices"></a>檢視及監視 SIP 裝置

在裝置使用者至少登入一次之後，您可以在 Teams 系統管理中心檢視及監控您的 SIP 裝置庫存。 方法如下：

1. 登入 [Teams 系統管理中心](https://admin.teams.microsoft.com/)。

2. 選 **取 Teams 裝置**  >  **SIP 裝置**。 所有已登入的 SIP 裝置都會列在右側。

## <a name="restart-a-sip-device"></a>重新開機 SIP 裝置

1. 登入 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

2. 選 **取 Teams 裝置**  >  **SIP 裝置**。 

3. 在右側，選取您要重新開機的 SIP 裝置，然後選取 [ **重新開機]**。


> [!NOTE]
> - Teams 系統管理中心目前無法從您的租使用者移除 SIP 裝置。 
> - 命令執行取決於裝置可用性，而且可能不符合 Teams 系統管理中心顯示的執行狀態。 如果您嘗試在不支援的裝置上啟用 SIP 閘道，將不會執行該命令。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>將原則變更同步至 SIP 裝置以強制執行原則

使用者登入時，使用者詳細資料和原則會擷取至 SIP 裝置。 此後，登入使用者的任何原則變更都會在一小時內同步處理到裝置。 裝置必須定期重新整理 SIP 閘道的註冊。 SIP 電話取決於通話重新導向，因此系統管理員必須將屬性設 `AllowCallRedirect` 為 `Set-CsTeamsCallingPolicy` `Enabled` 。


## <a name="set-a-sip-devices-ui-language"></a>設定 SIP 裝置的 UI 語言

SIP 裝置通常可以顯示多種語言的資訊。 設定 UI 語言會影響其介面，包括軟鍵和登入/登出系統訊息。 設定 UI 語言是在布建伺服器、使用 DHCP 伺服器，或手動在 URL 中附加程式碼字串來完成，如下列範例所示。

如何為 Polycom、AudioCodes 和 Yealink 手機設定德文：
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

如何設定 Cisco 手機的日文：
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>支援的語言

|語言名稱|語言代碼]
|-------------|-------------|
|英文 (預設) |en       |
|西班牙文      |es           |
|日語     |ja           |
|德語       |德           |
|法語       |fr           |
|葡萄牙文   |鉑           |

> [!Note]
> - Yealink 不支援日文，部分支援 Polycom VVX。
> - 如果 SIP 端點不支援選取的語言，系統會預設為英文。
> - 未透過布建 URL 設定 **lang_xx** 參數時，英文會做為預設語言。
> - 如果 **登入以撥打緊急電話** 的文字並未翻譯成其他語言，則只有英文的縮寫版本會在下列 IP 手機型號上 **按下 [登** 入] 顯示，因為螢幕大小限制：
>   - Poly VVX 150、VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - 針對 Poly VVX，語音信箱軟鍵標籤會以各種語言的 **VM** 文字硬編碼，因為字串長度有限制。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 和 IPv6

SIP 閘道僅支援 IPv4。 Microsoft Teams 服務和用戶端同時支援 IPv4 和 IPv6。 如果您想要控制與 Microsoft Teams 的通訊，請使用 [Microsoft 365 URL 和 IP 位址範圍中的 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

## <a name="emergency-calling"></a>緊急電話

SIP 閘道支援動態緊急呼叫 (動態 E911) ，適用于透過連接線共用網路屬性的相容 SIP 裝置。 這些屬性是在 Teams 系統管理中心中布建，可以結合本機 IP 和子網長度，或是底盤識別碼和網路埠號碼。 對於未共用位置屬性的裝置，或基於任何原因無法動態解析位置，SIP 閘道會繼續支援根據登錄位址的緊急通話。 目前，直接路由案例不支援已註冊的位址。 如需緊急電話的詳細資訊，請參閱 [規劃及管理緊急通話](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。

## <a name="report-problems-to-microsoft"></a>向 Microsoft 回報問題

若要回報問題，[請連絡Microsoft 支援服務](https://support.microsoft.com)。
