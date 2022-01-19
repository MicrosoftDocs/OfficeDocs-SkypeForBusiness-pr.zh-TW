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
ms.openlocfilehash: 1af44c5e3962f89346cae166bf40efa6a8622338
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2022
ms.locfileid: "62065179"
---
# <a name="configure-sip-gateway"></a>設定 SIP 閘道

本文說明如何設定 SIP 閘道，讓貴組織能與系統使用相容的 SIP Microsoft Teams。 若要瞭解 SIP 閘道可針對貴組織執行哪些工作，以及貴組織需要哪些硬體、軟體及授權，請參閱 [SIP 閘道規劃](sip-gateway-plan.md)。

在您設定 SIP 閘道之前，請執行下列操作：

- **將 SIP 裝置重設為出廠預設值。** 您或貴組織的使用者必須將與 SIP 閘道一起使用的每個 SIP 裝置重設為出廠預設值。 若要瞭解如何執行這項操作，請參閱製造商的指示。

- **開啟防火牆以Microsoft 365 Teams。** 開啟網路的防火牆以Microsoft 365 Teams URL 和 IP 位址範圍Office 365[流量](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

- **請確定 SIP 裝置不在 Proxy 後面。** 請確保 HTTP/s 流量會忽略任何公司 HTTP/s Proxy。

- **開啟 UDP 埠。** 針對 IP 範圍 52.112.0.0.0/14 到 52.120.0.0/14，開啟範圍 49152 到 53247 的 UDP 埠。

- **開啟 TCP 埠。** 針對 IP 範圍 52.112.0.0/14 到 52.120.0.0/14 開啟 TCP 埠 5061。

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



下列各節說明您作為系統管理員必須執行哪些操作，才能設定 SIP 閘道。

- [確認貴組織可以使用 SIP 閘道](#verify-that-sip-gateway-is-available-for-your-organization)。

- [為貴組織的使用者](#enable-sip-gateway-for-the-users-in-your-organization)啟用 SIP 閘道。

- [設定 SIP 閘道設定伺服器 URL](#set-the-sip-gateway-provisioning-server-url)。

本文也會說明如何：

- [個別或批次註冊 SIP 裝置，以方便您使用](#provision-and-enroll-sip-devices-as-common-area-phones)。  


- [查看並監控 SIP 裝置。](#view-and-monitor-sip-devices)

- [啟用多語言使用者介面的支援。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>確認貴組織是否提供 SIP 閘道

1. 請Teams[系統管理中心](https://admin-teams.microsoft.com/)。

2. 在左側，選取 **Teams，** 並查看是否顯示 **SIP 裝置**。 如果是，則貴組織會啟用 SIP 閘道服務。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>為貴組織的使用者啟用 SIP 閘道

您可以使用兩種方式為貴組織啟用 SIP 閘道：使用 Teams管理中心，或使用 PowerShell Cmdlet。

### <a name="by-using-teams-admin-center"></a>使用 Teams系統管理中心

若要在系統管理中心Teams SIP 閘道，請遵循下列步驟：

1. 前往系統[管理Teams中心](https://admin.teams.microsoft.com/)

2. 在左側 **的語音下**，選取通話 **政策**。

3. 在 **右側管理原則** 下，選取指派給使用者的適當通話策略，或在必要時建立新通話策略，並將其指派給必要的使用者。

4. 選取 **管理原則**，選取一個策略， **然後選取編輯**。

5. 開啟 SIP **裝置可用於** 通話的設定，然後選取 **儲存**。


### <a name="by-using-powershell"></a>使用 PowerShell

您也可以使用 PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Cmdlet 啟用 SIP 閘道。 若要啟用 SIP 裝置的使用者，請選取一個策略，然後將 `-AllowSIPDevicesCalling` 屬性設定為 `True` 。 預設值為 ，因此除非您啟用，否則使用者將無法 `False` 使用他們的 SIP 裝置。


> [!NOTE]
> - 傳播策略最多可能需要 24 小時。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>設定 SIP 閘道設定伺服器 URL

您可以在動態主機設定通訊協定中設定 SIP 閘道設定伺服器的 URL， (DHCP) 伺服器。 遠端工作的使用者必須手動設定。

### <a name="using-dhcp"></a>使用 DHCP

針對每個 SIP 裝置，設定下列其中一個 SIP 閘道設定伺服器 URL： 

- EMEA： `http://emea.ipp.sdg.teams.microsoft.com`
- 美洲： `http://noam.ipp.sdg.teams.microsoft.com`
- 亞太： `http://apac.ipp.sdg.teams.microsoft.com`

在 DHCP 伺服器中Teams SIP 閘道置備伺服器 URL，將 SIP 裝置新增到貴組織。 若要深入瞭解 DHCP 伺服器，請參閱 [部署及管理 DHCP](/learn/modules/deploy-manage-dynamic-host-configuration-protocol)。 此外，您可以使用 DHCP 選項 42 指定網路時間通訊協定 (NTP) 伺服器，以及 DHCP 選項 2，以指定協調通用時間 (UTC) 的位移。 貴組織的裝置會路由至 SIP 閘道置備伺服器。 成功布備的 SIP 電話會顯示Teams標誌和用於登錄的柔和按鈕。

確保 SIP 裝置在最低支援的固件版本上，才能上機。 在上機期間，SIP 閘道會將預設組式和驗證使用者介面推送到裝置。 若要瞭解 SIP 裝置所需的固件版本，請參閱規劃 [SIP 閘道](sip-gateway-plan.md)。

### <a name="manually"></a>手動

遠端工作的使用者必須使用下列步驟，手動將伺服器 URL 設定為 SIP 裝置：

1. 在 **設定** 開啟裝置，並取得裝置 IP 位址。

2. 開啟瀏覽器視窗、輸入裝置 IP 位址、視需要登入 () ，以及設定裝置網頁公用程式中的部署伺服器的 URL。

3. 在 **設定** 或 **網頁** 公用程式上的進一步設定下，輸入上述的設定伺服器 URL。

> [!NOTE]
> - 只有相容的 SIP 裝置可以進入 SIP 閘道。 
> - Cisco IP 電話必須先閃爍至多平臺的固件，才能上手。 若要瞭解方法，請參閱 [Cisco 固件轉換指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)。
> - 對於 Yealink 手機，請使用選項 66。
> - 針對 Cisco、Poly 和 AudioCode 電話，請使用選項 160。 
> - 針對 Cisco 裝置，將 **/$PSN.xml** 附加至置備伺服器 URL。


## <a name="configure-conditional-access"></a>設定條件式存取

條件式存取是Azure Active Directory (Azure AD) 項功能，可協助確保存取您Microsoft 365資源的裝置獲得妥善管理及保護。 SIP 閘道會使用 Azure AD驗證 SIP 裝置，因此如果貴組織針對公司網路中的裝置使用條件式 Access，則應該排除下列 IP 位址：

- 北美：
    - 美國東部：52.170.38.140
    - 美國西部：40.112.144.212
-   EMEA 地區：
    - 北歐盟：40.112.71.149
    - 西歐：40.113.112.67
-   亞太地區：
    - 澳洲東部：20.92.120.71
    - 澳洲東南部：13.73.115.90

詳細資訊，請參閱 [IP 位址範圍](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)。


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>將 SIP 裝置置備及註冊為一般地區電話
> [!NOTE]
> SIP 裝置必須先進入 SIP 閘道，才能註冊。

若要簡化工作，您可以在系統管理中心Teams SIP 裝置，一次一個或批次註冊一個。 以下說明：

1. 登入系統管理 [**Teams中心**](https://admin.teams.microsoft.com)。

2. 選取 **Teams**  >  **SIP 裝置**。

3. 在右上角，選取 **動作**  >  **置備裝置**，然後遵循下列其中一個步驟：

  - **若要配置一個裝置：**

     a. 在 **等待啟用下****，選取** 新增 。

     b. 在新增 **MAC 位址窗格中**，輸入 **MAC** 位址和裝置的位置，然後選取 **Apply**。
     
     C。 在 **等待啟用下**，選取您剛剛新增的裝置，然後選取 產生 **驗證碼**。
     
     D。 在安裝 **裝置窗格** 的驗證 **碼下**，記下 SIP 裝置驗證碼。

   - **若要配置許多裝置：**

     a. 在 **正在等待啟用的** 右側，選取 (圖示Microsoft Excel匯出) 。
     
     b. 在顯示 **多個 MAC** 位址的 **Upload 窗格中**，選取下載 **範本**。
     
     C。 將 **Template_Provisioning.csv** 儲存到您的電腦，並填寫 **MAC 識別碼** 和 **位置** 欄位。
    
     D。 在顯示 **裝置窗格** 上，選取 **Upload多個 MAC 位址**。 

     e. 在 MAC 位址窗格的右側Upload選取一個檔案，然後選取 **Template_Provisioning.csv** 包含您資料的檔案。

     F。 On the **Provision devices** pane, under **Waiting on activation**, select a device and then select **Generate verification code** to generate a one-time verification code for each provisioned device. 請注意每個 SIP 裝置的驗證碼。

4. 在 SIP 裝置上，撥打註冊功能代碼，後面接著驗證碼。 在 SIP 裝置上，撥打 SIP 閘道用於註冊一次驗證碼驗證) 的註冊功能代碼 55* (，後面接著此特定裝置在 Teams 系統管理中心產生的驗證 \* 碼。 例如，如果驗證碼123456，請撥打 \* 55 \* 123456以註冊裝置。

5.  在顯示 **裝置窗格** 的等待 **登錄** 下，選取已 **登出**。

6. 在 **[登錄使用者>** 對話方塊中，複製或記下 SIP 裝置配對程式碼。

7. 前往 [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) ，然後在 **輸入程式碼** 下，輸入 SIP 裝置配對程式碼，然後選取下 **一步**。

8. 在 Microsoft **的登錄** 頁面上，在電子郵件 **或** 電話欄位中，輸入 SIP 裝置的電子郵件地址，然後選取下 **一步**。

9. 在密碼 **頁面上**，輸入 SIP 裝置電子郵件地址的密碼，然後選取

10. 在您 **嘗試在** SIP 裝置閘道Teams上，選取 **繼續**。

## <a name="how-to-sign-in-and-sign-out"></a>如何登錄和登出

使用者的個人裝置僅支援本地登錄。 若要從系統管理中心登出裝置，請遵循下列步驟：

1. 登入系統管理 [**Teams中心**](https://admin.teams.microsoft.com)。

2. 選取 **Teams**  >  **SIP 裝置**。

3. 在右側選取 SIP 裝置，然後 **選取登出**。


### <a name="user-pairing-and-sign-in"></a>使用者配對和登錄

若要在使用者使用公司認證進行驗證之後配對 SIP 裝置，使用者必須：

1. 在 **SIP 電話** 上按登錄以顯示驗證 URL 和配對代碼。 配對程式碼會區分時間。 如果到期，使用者必須在電話上按 **Back，** 然後再次啟動登錄程式。

2. 流覽至使用者桌面或行動瀏覽器中的驗證 URL，並使用公司認證登入。

3. 在 Web 驗證應用程式中輸入 SIP 電話上顯示的配對程式碼，將 SIP 電話與使用者帳戶配對。 如果成功登錄，可能需要一段時間，SIP 電話會顯示電話號碼和使用者名稱 ，如果裝置支援。

> [!NOTE]
> 在 Web 驗證應用程式上顯示Azure Active Directory的位置是裝置已連接的 SIP 閘道資料中心。 範圍中的 SIP 電話無法使用 OAuth，因此 SIP 閘道會透過 Web 驗證應用程式對使用者進行驗證，然後將裝置與使用者的認證配對。 請在這裡深入瞭解[：Microsoft 身分識別平臺和 OAuth 2.0 裝置授權授權流程](/azure/active-directory/develop/v2-oauth2-device-code)。

### <a name="sign-out"></a>登出

若要登出，裝置使用者可以：

- 在 **SIP 裝置** 上按登出，然後按照裝置上描述的步驟操作。 

若要在系統管理中心Teams登出裝置：

1. 登入系統管理 [**Teams中心**](https://admin.teams.microsoft.com)。

2. 選取 **Teams**  >  **SIP 裝置**。

3. 在右側 ，在 **SIP 裝置窗格中** ，選取裝置。

4. 在裝置之詳細資料窗格 **上**，選取詳細資料標籤，然後選取右上角的動作功能表，選取 **登出**。 


## <a name="view-and-monitor-sip-devices"></a>查看及監控 SIP 裝置

在裝置使用者至少登錄一次之後，Teams管理中心中查看及監控 SIP 裝置庫存。 以下說明：

1. 登入系統管理[Teams中心](https://admin.teams.microsoft.com/)。

2. 選取 **Teams**  >  **SIP 裝置**。 所有已登錄的 SIP 裝置都列在右側。

## <a name="restart-a-sip-device"></a>重新開機 SIP 裝置

1. 登入系統管理[Teams中心](https://admin.teams.microsoft.com)。

2. 選取 **Teams**  >  **SIP 裝置**。 

3. 在右側，選取要重新開機的 SIP 裝置，然後選取 **重新開機**。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>同步策略變更至 SIP 裝置以強制執行策略

當使用者登錄時，使用者詳細資料與政策會取至 SIP 裝置。 之後對已登錄使用者的任何政策變更，都會在一小時內同步到裝置。 裝置必須定期使用 SIP 閘道重新註冊。 SIP 電話取決於通話重新導向，因此系統管理員必須將 `AllowCallRedirect` 屬性設定為 `Set-CsTeamsCallingPolicy` `Enabled` 。


## <a name="set-a-sip-devices-ui-language"></a>設定 SIP 裝置 UI 語言

SIP 裝置通常可以顯示多種語言的資訊。 設定其 UI 語言會影響其介面，包括軟體金鑰和登錄/登出系統訊息。 設定 UI 語言是在設定伺服器、使用 DHCP 伺服器，或是在 URL 中手動附加代碼字串，如下列範例所示。

如何設定 Polycom、AudioCodes 和 Yealink 手機的德文：
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

如何設定 Cisco 電話的日文：
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
> - Yealink 不支援日文，而 Polycom VVX 也部分支援日文。
> - 如果 SIP 端點不支援選取的語言，系統會預設為英文。
> - 當 **lang_xx未** 透過設定 URL 設定時，會使用英文做為預設語言。
> - 如果 **無法** 將緊急電話文字翻譯成其他語言，則由於螢幕限制，在下列 IP 電話型號上按 Sign **In** 時，只會顯示英文縮寫版本：
>   - Poly VVX 150，VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - 由於字串長度的限制，Voice mail softkey 標籤會以 **適用于** Poly VVX 的所有語言之 VM 文字進行硬編碼。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams IPv6

SIP 閘道僅支援 IPv4。 Microsoft Teams和用戶端支援 IPv4 和 IPv6。 如果您想要控制通訊至Microsoft Teams，請使用 URL 和 IP 位址Microsoft 365 [IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

## <a name="emergency-calling"></a>緊急電話

SIP 閘道僅支援靜態的緊急位址 ，也稱為已登入位址。 目前，直接路由案例不支援已註冊的位址。 有關緊急電話詳細資訊，請參閱 [規劃及管理緊急電話](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。

## <a name="report-problems-to-microsoft"></a>向 Microsoft 報告問題

若要報告問題，請聯絡 [Microsoft 支援服務](https://support.microsoft.com)。
