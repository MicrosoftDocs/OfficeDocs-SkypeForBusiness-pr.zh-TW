---
title: 規劃直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解 Microsoft 直接路由如何讓您將受支援的客戶提供的會話框線控制器 (SBC) 連線至電話系統。
ms.openlocfilehash: dd3b9ef6517c1a4c63fe12f7b7eeba4078df8ddd
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823062"
---
# <a name="plan-direct-routing"></a>規劃直接路由

> [!Tip]
> 請觀看下列會話，以瞭解直接路由的優點、規劃方式，以及部署方式：[Microsoft Teams中的直接路由](https://aka.ms/teams-direct-routing)

直接路由可讓您將客戶提供的會話框線控制器 (SBC) 連線至電話系統。 使用這項功能，您可以設定內部部署的公用交換電話網路 (PSTN) 與Microsoft Teams用戶端的連線能力，如下圖所示： 

![顯示內部部署 PSTN 連線能力設定的圖表。](media/PlanDirectRouting1-PSTNwithTeams.png "設定與Microsoft Teams用戶端的內部部署 PSTN 連線")

  > [!NOTE]
  > 商務用 Skype Online 也可讓您配對客戶提供的 SBC，但這需要在 SBC 與 Microsoft Cloud 之間進行內部部署商務用 Skype Server部署或稱為雲端連接器的特殊版本 商務用 Skype。 此案例稱為混合式語音。 相反地，直接路由可讓支援的 SBC 和 Microsoft Cloud 之間直接連線。

> [!Important]
> 雲端連接器版本將于 2021 年 7 月 31 日與 商務用 Skype Online 一起淘汰。 一旦貴組織升級至 Teams，請瞭解如何使用[直接](direct-routing-landing-page.md)路由將內部部署電話語音網路連線至Teams。 

透過直接路由，您可以將 SBC 連接到幾乎任何電話語音主幹或與協力廠商 PSTN 設備相互連線。 直接路由可讓您： 

- 使用幾乎任何 PSTN 主幹搭配電話系統。 

- 在客戶擁有的電話語音設備之間設定互通性，例如協力廠商專用分公司交換 (PBX) 、類比裝置和Teams。

Microsoft 也提供全雲語音解決方案，例如通話方案。 不過，混合式語音解決方案在下列情況中可能最適合您的組織： 

- 您所在的國家/地區不提供 Microsoft 通話方案。 

- 您的組織需要連線至協力廠商類比裝置、通話中心等。 

- 貴組織已與 PSTN 電信業者簽訂合約。

直接路由也支援擁有 Microsoft 通話方案額外授權的使用者。 如需詳細資訊，請參[閱電話系統和通話方案](calling-plan-landing-page.md)。 

透過直接路由，當使用者參與排定的會議時，撥入號碼是由 Microsoft 音訊會議 服務提供，需要適當的授權。  撥出時，Microsoft 音訊會議服務會使用需要適當授權的線上通話功能撥打通話。  (請注意，如果使用者沒有 Microsoft 音訊會議 授權，通話會透過 Direct Routing.) 路由進行，如需詳細資訊，請參閱[Teams線上會議](https://www.microsoft.com/en-us/microsoft-teams/online-meetings)。 
 
規劃部署直接路由是成功實作的關鍵。 本文說明基礎結構與授權需求，並提供 SBC 連線的相關資訊： 

- [基礎結構需求](#infrastructure-requirements)
- [授權和其他需求](#licensing-and-other-requirements)
- [SBC 功能變數名稱](#sbc-domain-names)
- [SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)
- [SIP 訊號：FQDN](#sip-signaling-fqdns)
- [SIP 訊號：埠](#sip-signaling-ports)
- [媒體流量：埠範圍](#media-traffic-port-ranges)
- [支援的會話框線控制器 (SBC) ](#supported-session-border-controllers-sbcs)

如需設定直接路由的詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基礎結構需求
下表列出支援 SBC、網域及其他部署直接路由之網路連線需求的基礎結構需求：  

|基礎結構需求|您需要下列專案|
|:--- |:--- |
|會話框線控制器 (SBC) |支援的 SBC。 如需詳細資訊，請參閱 [支援的 SBC](#supported-session-border-controllers-sbcs)。|
|連接至 SBC 的電話語音主幹|連接至 SBC 的一或多個電話語音主幹。 在一端，SBC 會透過直接路由連接到電話系統。 SBC 也可以連線至協力廠商電話語音實體，例如 PBX、類比電話語音介面卡等。 任何連線到 SBC 的 PSTN 連線選項都可運作。  (若要設定 SBC 的 PSTN 主幹，請參閱 SBC 廠商或主幹提供者。) |
|Microsoft 365組織|您用來將Microsoft Teams使用者設為家的Microsoft 365組織，以及 SBC 的設定和連線。|
|使用者註冊機構|使用者必須住Microsoft 365。<br/>如果您公司的內部部署商務用 Skype或 Lync 環境具有Microsoft 365的混合式連線能力，您就無法為內部部署使用者啟用Teams語音功能。<br/><br/>若要檢查使用者的註冊機構，請使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Cmdlet 的輸出應該會顯示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|新增到Microsoft 365或Office 365組織的一或多個網域。<br/><br/>請注意，您無法使用自動為租使用者建立的預設網域 \* .onmicrosoft.com。<br/><br/>若要檢視網域，您可以使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>如需網域和Microsoft 365或Office 365組織的詳細資訊，請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公用 IP 位址|可用來連線至 SBC 的公用 IP 位址。 根據 SBC 的類型，SBC 可以使用 NAT。|
|SBC 的完整功能變數名稱 (FQDN) |SBC 的 FQDN，其中 FQDN 的網域部分是您Microsoft 365或Office 365組織中的其中一個註冊網域。 如需詳細資訊，請參閱 [SBC 功能變數名稱](#sbc-domain-names)。|
|SBC 的公用 DNS 專案 |將 SBC FQDN 對應到公用 IP 位址的公用 DNS 專案。 |
|SBC 的公用信任憑證 |SBC 的憑證，用於所有具有直接路由的通訊。 如需詳細資訊，請參閱 [SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。|
|直接路由的連接點 |直接路由的連接點為下列三個 FQDN：<br/><br/>`sip.pstnhub.microsoft.com` – 必須先試用全球 FQDN。<br/>`sip2.pstnhub.microsoft.com` – 次要 FQDN，地理位置對應到第二優先順序區域。<br/>`sip3.pstnhub.microsoft.com` – 從地理位置對應到第三優先順序區域的 FQDN。<br/><br/>如需設定需求的相關資訊，請參閱 [SIP 訊號：FQDN](#sip-signaling-fqdns)。|
|直接路由媒體的防火牆 IP 位址和埠 |SBC 會在雲端中與下列服務通訊：<br/><br/>SIP Proxy，可處理訊號<br/>處理媒體的媒體處理器 -除了開啟媒體旁路時<br/><br/>這兩個服務在 Microsoft Cloud 中有個別的 IP 位址，如本文稍後所述。<br/><br/>如需詳細資訊，請參閱[URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)中的[Microsoft Teams一節](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 |
|媒體傳輸設定檔|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams媒體的防火牆 IP 位址和埠 |如需詳細資訊，請參閱 [URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>授權和其他需求 

直接路由使用者必須在 Microsoft 365 中指派下列授權： 

- Microsoft 電話系統]
- Microsoft Teams + 商務用 Skype方案 2，如果包含在授權中
- Microsoft 音訊會議 (閱讀下方的備忘稿和段落，瞭解何時需要此授權的特定範例。) 

> [!NOTE]
> 商務用 Skype方案不應從包含此合約的任何授權合約中移除。 
> 
> [!IMPORTANT]
> GCC High 和 DoD 使用者應停用 G5 中包含的任何音訊會議授權，並等候啟用任何音訊會議，直到直接路由完全設定完成為止。 使用者在啟用音訊會議授權之前，應先設定撥入電話號碼和有效的撥號鍵台。 如需詳細資訊，請參閱[使用 GCC High 和 DoD 的直接路由音訊會議](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)。


> [!IMPORTANT]
>  如果您想要將外部參與者新增至排定的會議，請透過撥出電話或提供撥入號碼的方式，即需要音訊會議授權。
> 對於 GCC High 和 DoD，請勿為 G5 使用者指派音訊會議授權。 對於 G3 使用者，在直接路由完全設定且使用者有有效的撥號鍵台之前，請勿指派音訊會議授權。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>臨時通話升級和音訊會議授權

Teams使用者可以啟動一對一Teams對 PSTN 或Teams對Teams通話，並在其中新增 PSTN 參與者。 此案例稱為臨時會議。 通話所採用的路徑取決於升級通話的使用者是否已指派 Microsoft 音訊會議授權：

- **如果升級通話的Teams使用者已指派 Microsoft 音訊會議 授權**，則會透過 Microsoft 音訊會議 服務升級。 受邀參與現有通話的遠端 PSTN 參與者會收到關於來電的通知，並看到指派給啟動升級之Teams使用者的 Microsoft 橋接器號碼。

- **如果升級通話的Teams使用者沒有指派 Microsoft 音訊會議 授權**，則升級會透過連接至直接路由介面的會話框線控制器進行升級。 受邀參與通話的遠端 PSTN 參與者會收到關於來電的通知，並看到啟動升級的Teams使用者人數。 用於升級的特定 SBC 是由使用者的路由原則所定義。 

您必須確定下列事項：
 
- CsOnlineVoiceRoutingPolicy 已指派給使用者。 

- 允許私人通話會在租使用者層級啟用Microsoft Teams。 

直接路由也支援具有 Microsoft 通話方案授權的使用者。 電話系統使用通話方案可以使用直接路由介面路由一些來電。 不過，使用者的電話號碼必須先在線上取得，或是移轉至 Microsoft。  

混合同一個使用者的通話方案和直接路由連線是選用的，但可能很有用。 例如，當使用者獲派 Microsoft 通話方案，但想要使用 SBC 路由一些通話時。 其中一個最常見的案例是呼叫協力廠商 PBX。  使用協力廠商 PBX 時，除了撥打到連線至該 PBX 的電話外，所有通話都是使用 Microsoft 通話方案路由，但連接到協力廠商 PBX 之電話的電話會移至 SBC，因此會留在商業網路內，而非 PSTN。 

如需電話系統授權的詳細資訊，請參閱[充分利用Office](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[方案選項](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)[及Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 

## <a name="supported-end-points"></a>支援的端點 

您可以做為終點：

- 任何Teams用戶端。 

- 常見的區域電話。 請參閱[為 Microsoft Teams 設定通用區域電話](./set-up-common-area-phones.md)。 使用直接路由設定通用區域電話時，您不需要通話方案授權。

- 商務用 Skype 3PIP 手機。 使用[Microsoft Teams 查看商務用 Skype手機 (3PIP) 支援](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 功能變數名稱

SBC 功能變數名稱必須來自租使用者網域中註冊的其中一個名稱。 您無法使用 \* .onmicrosoft.com 租使用者做為 SBC 的 FQDN 名稱。

下表顯示為租使用者註冊的 DNS 名稱範例、該名稱是否可以做為 SBC 的 FQDN，以及有效的 FQDN 名稱範例：

|DNS 名稱|可用於 SBC FQDN|FQDN 名稱的範例|
|:--- |:--- |:--- |
contoso.com|是|**有效的名稱：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|SBC 名稱不支援使用 *.onmicrosoft.com 網域

假設您想要使用新的功能變數名稱。 例如，您的租使用者 contoso.com 為在租使用者中註冊的功能變數名稱，而您想要使用 sbc1.sip.contoso.com。 您必須先在租使用者的網域中註冊功能變數名稱 sip.contoso.com，才能將 SBC 與名稱 sbc1.sip.contoso.com 配對。 如果您在註冊功能變數名稱前先嘗試將 SBC 與 sbc1.sip.contoso.com 配對，您會收到下列錯誤：「無法使用「sbc1.sip.contoso.com」網域，因為它尚未為此租使用者設定。」
新增功能變數名稱之後，您也需要使用 UPN user@sip.contoso.com 建立使用者，並指派Teams授權。 將功能變數名稱新增至租使用者的網域後，最多可能需要 24 小時才能完整布建功能變數名稱、建立有新名稱的使用者，以及指派授權給使用者。 

有可能是公司在一個租使用者中有幾個 SIP 位址空間。 例如，公司可能會將 contoso.com 為 SIP 位址空間，fabrikam.com 做為第二個 SIP 位址空間。 有些使用者有位址 user@contoso.com，有些使用者有位址 user@fabrikam.com。 

SBC 只需要一個 FQDN，而且可以從配對租使用者中的任何位址空間為使用者提供服務。 例如，名稱 sbc1.contoso.com 的 SBC 可以接收並傳送位址 user@contoso.com 使用者的 PSTN 流量，只要這些 SIP 位址空間是在同一個租使用者中登錄，user@fabrikam.com。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的公用信任憑證

Microsoft 建議您產生認證簽署要求 (CSR) ，以要求 SBC 的憑證。 如需有關為 SBC 產生 CSR 的特定指示，請參閱 SBC 廠商提供的相互連接指示或檔。 

> [!NOTE]
> 大部分憑證授權單位單位 (CAs) 需要至少 2048 個私密金鑰大小。 產生 CSR 時請記住這點。

憑證必須將 SBC FQDN 做為 CN () 常用名稱或主旨替代名稱 (SAN) 欄位。

或者，直接路由支援 CN 和/或 SAN 中的萬用字元，萬用字元必須符合標準 [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)。 例如，使用 \* .contoso.com 會符合 SBC FQDN sbc.contoso.com，但與 sbc.test.contoso.com 不相符。

直接路由 SIP 介面只會信任由憑證授權單位單位 (CAs 簽署的憑證，) 屬於 Microsoft 信任的根憑證計畫。 請確定您的 SBC 憑證是由屬於該程式一部分的 CA 簽署，且憑證的擴充 (EKU) 副檔名包含伺服器驗證。
深入瞭解： [計畫需求 - Microsoft 根信任計畫](/security/trusted-root/program-requirements)
  
[隨附的 CA 憑證清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 對於 Office 365 GCCH 和 DoD 環境中的直接路由，憑證必須由下列其中一個跟憑證授權單位單位產生：

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> 如果在 SBC 上啟用了共同 TLS (MTLS) 支援Teams連線，則您必須在 SBC Trusted Root Microsoft Store Teams TLS 內容的 SBC Trusted Root Microsoft Store中安裝[該共性 TLS Root] 和 DigiCert Global Root G2 憑證。  (這是因為 Microsoft 服務憑證使用這兩種根憑證的其中之一。) 若要下載這些根憑證，請[參閱Office 365加密鏈。](/microsoft-365/compliance/encryption-office-365-certificate-chains) 如需詳細資料，[請參閱 TLS 憑證變更Office](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes)。

## <a name="sip-signaling-fqdns"></a>SIP 訊號：FQDN 

在下列環境中提供直接路由：

- Microsoft 365或Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

深入瞭解[Office 365及美國政府環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365和Office 365 GCC環境

直接路由的連接點為下列三個 FQDN：

- **sip.pstnhub.microsoft.com** – 全球 FQDN – 必須先試用。 當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 的主要 Azure 資料中心之 IP 位址。 作業是根據資料中心的效能指派，以及與 SBC 的地理鄰近度。 傳回的 IP 位址會對應到主要的 FQDN。

- **sip2.pstnhub.microsoft.com** – 次要 FQDN – 地理位置對應到第二優先順序地區。

- **sip3.pstnhub.microsoft.com** – 新式 FQDN – 地理位置對應到第三優先順序地區。

將這三個 FQDN 順序排列為：

- 透過查詢第一個 FQDN) ，提供 (載入較少且最接近指派的 SBC 資料中心的最佳體驗。

- 從 SBC 連線到發生暫時性問題的資料中心時，提供容錯移轉。 如需詳細資訊，請參閱下方 [的容錯移轉機制](#failover-mechanism-for-sip-signaling) 。  

FQDN - sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com – 將解析為來自下列子網的 IP 位址：

- 52.112.0.0/14
- 52.120.0.0/14

您必須在防火牆中開啟所有這些 IP 位址範圍的埠，以允許內送和外寄流量從位址進入和移出訊號。

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** – 全球 FQDN。 由於Office 365 DoD 環境僅存在於美國資料中心，因此沒有次要和次要 FQDN。

FQDN sip.pstnhub.dod.teams.microsoft.us 將從下列子網解析為 IP 位址：

- 52.127.64.0/21

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許內送和外寄流量從位址進入和移出訊號。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** – 全球 FQDN。 由於「GCC High」環境只存在於美國資料中心，因此沒有次要和次要 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 將從下列子網解析為 IP 位址：

- 52.127.88.0/21

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許內送和外寄流量從位址進入和移出訊號。

## <a name="sip-signaling-ports"></a>SIP 訊號：埠

對於提供直接路由的Microsoft 365或Office 365環境，您必須使用下列埠：

- Microsoft 365或Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|交通|從|自|來源埠|目的地埠|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|定義于 SBC (對於 Office 365 GCC High/DoD，必須只使用埠 5061) |
SIP/TLS|SBC|SIP Proxy|定義于 SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 訊號的容錯移轉機制

SBC 會建立 DNS 查詢來解決 sip.pstnhub.microsoft.com。 根據 SBC 位置和資料中心效能指標，選取了主要資料中心。 如果主要資料中心發生問題，SBC 會嘗試 sip2.pstnhub.microsoft.com，此 sip2.pstnhub.microsoft.com 會解析到第二個指派的資料中心，而在兩個區域的資料中心無法使用的情況下，SBC 會重新發佈最後一個 FQDN (sip3.pstnhub.microsoft.com) ，這會提供儲存的資料中心 IP。

下表摘要說明主要、次要和次要資料中心之間的關聯性：

|如果主要資料中心是|EMEA|NOAM|亞洲|
|:--- |:--- |:--- |:--- |
|次要資料中心 (sip2.pstnhub.microsoft.com) |我們|歐盟|我們|
|集中的資料中心 (sip3.pstnhub.microsoft.com) |亞洲|亞洲|歐盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒體流量：埠範圍
請注意，如果您想要部署沒有媒體旁路的直接路由，下列需求適用。 如需 Media Bypass 的防火牆需求，請參閱 [使用直接路由規劃媒體略過](./direct-routing-plan-media-bypass.md)。

媒體流量會流經 Microsoft Cloud 中不同服務的往來。 媒體流量的 IP 位址範圍如下所示。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365和Office 365 GCC環境

- 52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) 。
- 52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) 。

### <a name="office-365-dod-environment"></a>Office 365 DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>適用于所有環境的埠範圍 () 
媒體處理器的埠範圍如下表所示： 

|交通|從|自|來源埠|目的地埠|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒體處理器|SBC|3478-3481 和 49152 – 53247|定義于 SBC|
|UDP/SRTP|SBC|媒體處理器|定義于 SBC|3478-3481 和 49152 – 53247|

  > [!NOTE]
  > Microsoft 建議至少在 SBC 上同時通話兩個埠。


## <a name="media-traffic-media-processors-geography"></a>媒體流量：媒體處理器地理位置

媒體流量會透過稱為媒體處理器的元件流經。 媒體處理器與 SIP Proxy 位於同一個資料中心：

- NOAM (美國中南部，兩個位于美國西部和美國東部資料中心) 
- 歐洲 (英國南部、法國中央、阿姆斯特丹和都柏林資料中心) 
- Asia (Singapore 資料中心) 
- 日本 (JP 東部和西部資料中心) 
- 澳大利亞 (AU 東部和東南亞資料中心) 
- 拉坦 (巴西南) 
- 非洲 (南非北) 

## <a name="media-traffic-codecs"></a>媒體流量：編解碼器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC 和雲端媒體處理器或Microsoft Teams用戶端之間的長段

同時適用于媒體略過案例和非略過案例。

如果啟) 用了 Media Bypass，則會話框線控制器和雲端媒體處理器之間段落上的直接路由介面 (沒有媒體略過) ，或在Teams用戶端和 SBC (之間使用下列編解碼器：

- 非媒體略過 (SBC 轉雲端媒體處理器) ：SILK、G.711、G.722、G.729
- 媒體略過將 SBC (Teams用戶端) ：SILK、G.711、G.722、G.729

您可以排除優惠中不常用的編解碼器，藉此強制使用會話框線控制器上的特定編解碼器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams用戶端和雲端媒體處理器之間的長段

僅適用于非媒體略過案例。 使用 Media Bypass，媒體會直接在Teams用戶端和 SBC 之間延伸。

在雲端媒體處理器和Microsoft Teams用戶端之間的腿上，會使用 SILK 或 G.722。 此長段上的編解碼器選擇是以 Microsoft 演算法為基礎，並考慮多個參數。 


## <a name="supported-session-border-controllers-sbcs"></a>支援的會話框線控制器 (SBC) 

Microsoft 僅支援通過認證的 SB 與直接路由配對。 由於企業語音對企業而言至關重要，因此 Microsoft 會針對選取的 SBC 執行密集測試，並與 SBC 廠商合作以確保兩種系統相容。 

已驗證的裝置列為「Teams直接路由認證」。 認證的裝置可在所有案例中都能正常運作。 

如需支援的 SBC 的詳細資訊，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另請參閱

[設定直接路由](direct-routing-configure.md)
