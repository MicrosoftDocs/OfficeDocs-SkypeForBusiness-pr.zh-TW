---
title: 規劃直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解 Microsoft Phone System Direct Routing 如何讓您將支援的客戶提供的會話邊界控制器 (SBC) Microsoft Phone System。
ms.openlocfilehash: 858d57fb210765a1223a68527b0aa1b37bf7800b
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836990"
---
# <a name="plan-direct-routing"></a>規劃直接路由

> [!Tip]
> 觀看下列會話以瞭解直接路由的好處、如何規劃，以及如何部署[：Microsoft Teams](https://aka.ms/teams-direct-routing)中的直接路由

Microsoft Phone System Direct Routing 可讓您將支援、客戶提供的會話邊界控制器 (SBC) Microsoft Phone System。  例如，有了這項功能，您可以設定內部部署公用交換電話網絡 (PSTN) Microsoft Teams 用戶端的) ，如下圖所示： 

![顯示內部部署 PSTN 連接配置的圖表](media/PlanDirectRouting1-PSTNwithTeams.png "與 Microsoft Teams 用戶端內部部署 PSTN 連接的配置")

  > [!NOTE]
  > 商務用 Skype Online 也可讓您配對客戶提供的 SBC，但這需要在 SBC 和 Microsoft Cloud 之間部署內部部署商務用 Skype Server 或稱為雲端連接器的特殊版商務用 Skype。 此案例稱為混合式語音。 相反地，直接路由允許在支援的 SBC 和 Microsoft Cloud 之間直接連接。

> [!Important]
> 雲端連接器版將于 2021 年 7 月 31 日與商務用 Skype Online 一起淘汰。 您的組織升級至 Teams 之後，瞭解如何使用直接路由將您的內部部署電話網路連接到[Teams。](direct-routing-landing-page.md) 

使用直接路由，您可以將 SBC 連接到幾乎任何電話主幹，或和協力廠商 PSTN 設備進行互連。 直接路由可讓您： 

- 使用幾乎任何 PSTN 主幹與 Microsoft Phone System。 
- 設定客戶擁有的電話設備之間的互通性，例如 PBX (、類比裝置和 Microsoft Phone System 的協力廠商私人分支交換) 。.

Microsoft 也提供全雲端語音解決方案，例如通話方案。 不過，如果： 

- 您的國家/地區沒有 Microsoft 通話方案。 
- 貴組織需要連接到協力廠商類比裝置、通話中心等。 
- 貴組織與 PSTN 電信公司有現有的合約。

直接路由也支援擁有 Microsoft 通話方案額外授權的使用者。 詳細資訊，請參閱 [電話系統與通話方案](calling-plan-landing-page.md)。 

使用直接路由時，當使用者參與排定的會議時，電話撥入號碼是由 Microsoft 音訊會議服務提供，需要適當的授權。  撥出時，Microsoft 音訊會議服務會使用線上通話功能撥打電話，這需要適當的授權。  (請注意，如果使用者沒有 Microsoft 音訊會議授權，通話會透過直接路由路由。) 請參閱 Teams 的線上 [會議](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
規劃直接路由的部署是成功執行的關鍵。 本文將說明基礎結構和授權需求，並提供有關 SBC 連接的資訊： 

- [基礎結構需求](#infrastructure-requirements)
- [授權和其他需求](#licensing-and-other-requirements)
- [SBC 功能變數名稱](#sbc-domain-names)
- [SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)
- [SIP 訊號：FQDNs](#sip-signaling-fqdns)
- [SIP 訊號：埠](#sip-signaling-ports)
- [媒體流量：埠範圍](#media-traffic-port-ranges)
- [支援會話邊界控制器 (SBC) ](#supported-session-border-controllers-sbcs)

有關設定直接路由的詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基礎結構需求
下表列出部署直接路由的支援 SBC、網域和其他網路連接需求之基礎結構需求：  

|基礎結構需求|您需要下列專案|
|:--- |:--- |
|會話邊界控制器 (SBC) |支援的 SBC。 詳細資訊，請參閱支援的 [SBCs](#supported-session-border-controllers-sbcs)。|
|連接到 SBC 的電話主幹|一或多個連接到 SBC 的電話主幹。 在一端，SBC 會透過直接路由連接到 Microsoft Phone 系統。 SBC 也可以連接到協力廠商電話實體，例如 PBX、類比電話轉接器等。 任何連接至 SBC 的 PSTN 連接選項都會使用。  (如需將 PSTN 主幹組至 SBC，請參閱 SBC 廠商或主幹提供者。) |
|Microsoft 365 或 Office 365 組織|您用於支援 Microsoft Teams 使用者的 Microsoft 365 或 Office 365 組織，以及 SBC 的組建和連接。|
|使用者註冊機構|使用者必須是 Microsoft 365 或 Office 365 的首頁。<br/>如果您的公司內部部署商務用 Skype 或 Lync 環境與 Microsoft 365 或 Office 365 的混合式連接，您無法為內部部署使用者啟用 Teams 中的語音。<br/><br/>若要檢查使用者的註冊機構，請使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Cmdlet 的輸出應該會顯示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|新增到 Microsoft 365 或 Office 365 組織的一或多個網域。<br/><br/>請注意，您無法使用為租使用者 onmicrosoft.com 建立的預設網 \* 域 .onmicrosoft.com。<br/><br/>若要查看網域，您可以使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有關網域和 Microsoft 365 或 Office 365 組織的資訊，請參閱 [網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公用 IP 位址|可用來連接到 SBC 的公用 IP 位址。 根據 SBC 類型，SBC 可以使用 NAT。|
|適用于 SBC (FQDN) 功能變數名稱|SBC 的 FQDN，其中 FQDN 的網域部分是 Microsoft 365 或 Office 365 組織中已註冊的網域之一。 詳細資訊，請參閱 [SBC 功能變數名稱](#sbc-domain-names)。|
|SBC 的公用 DNS 專案 |將 SBC FQDN 與公用 IP 位址的公用 DNS 專案。 |
|SBC 的公用信任憑證 |SBC 的憑證，用於使用直接路由進行所有通訊。 詳細資訊，請參閱 [SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。|
|直接路由的連接點 |直接路由的連接點如下三個 FQDNs：<br/><br/>`sip.pstnhub.microsoft.com` – 必須先嘗試全域 FQDN。<br/>`sip2.pstnhub.microsoft.com` – 次要 FQDN，地理上會繪製至第二個優先順序區域。<br/>`sip3.pstnhub.microsoft.com` – 三級 FQDN，地理分佈到第三個優先順序區域。<br/><br/>有關組組需求的資訊，請參閱 [SIP 訊號：FQDNs](#sip-signaling-fqdns)。|
|直接路由媒體的防火牆 IP 位址和埠 |SBC 會與雲端中的下列服務通訊：<br/><br/>SIP Proxy，可處理訊號<br/>媒體處理器，可處理媒體 -除非媒體旁路已啟用<br/><br/>這兩個服務在 Microsoft Cloud 中分別有 IP 位址，本檔稍後會說明。<br/><br/>詳細資訊請參閱 URL 和 IP 位址範圍的 [Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [一節](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|媒體傳輸設定檔|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 媒體的防火牆 IP 位址和埠 |詳細資訊，請參閱 [URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>授權和其他需求 

直接路由的使用者必須在 Microsoft 365 或 Office 365 中指派下列授權： 

- Microsoft Phone System。 
- Microsoft Teams + 商務用 Skype 方案 2 ，如果包含在授權中。
- Microsoft 音訊會議 (請參閱下列筆記和段落，以瞭解何時需要授權) 。

> [!NOTE]
> 商務用 Skype 方案不應從包含之任何授權合約中移除。 
> 
> [!IMPORTANT]
> GCC High 和 DoD 使用者應停用 G5 中包含的任何音訊會議授權，並等待啟用任何音訊會議，直到直接路由完全完成配置。 在啟用音訊會議授權之前，使用者應該已配置電話撥入電話號碼和可工作的撥號鍵台。 請參閱使用 GCC High 和 [DoD 直接路由的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-with-direct-routing-for-gcch-and-dod) ，以進一步瞭解詳細資料。


> [!IMPORTANT]
>  若要新增外部參與者至排定的會議，請撥電話給他們，或提供撥入號碼，則您需要音訊會議授權。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>臨時通話升級和音訊會議授權

Teams 使用者可以啟動一對一 Teams 到 PSTN 或 Teams 到 Teams 通話，並新增 PSTN 參與者。 此案例稱為臨時會議。 通話路徑取決於升級通話的使用者是否已指派 Microsoft 音訊會議授權：

- 如果升級通話的 Teams 使用者已指派 Microsoft 音訊會議授權，則升級會透過 Microsoft 音訊會議服務進行。 受邀加入現有通話的遠端 PSTN 參與者會收到來電通知，並查看指派給啟動升級的 Teams 使用者的 Microsoft 橋接器號碼。
- 如果升級通話的 Teams 使用者未指派 Microsoft 音訊會議授權，則升級會透過連接至直接路由介面的會話邊界控制器進行。 受邀加入通話的遠端 PSTN 參與者會收到來電通知，並查看啟動升級的 Teams 使用者數目。 升級時所使用的特定 SBC 是由使用者的路由策略定義。 


此外，您必須確保下列各項：
 
- CsOnlineVoiceRoutingPolicy 已指派給使用者。 
- Microsoft Teams 的租使用者層級已啟用允許私人通話。 

直接路由也支援擁有 Microsoft 通話方案授權的使用者。 具有通話計畫的 Microsoft Phone System 可以使用直接路由介面路由部分通話。 不過，使用者的電話號碼必須線上取得或移植到 Microsoft。  

為同一個使用者混合通話方案與直接路由連接是選擇性的，但可能很有用 (例如，當使用者被指派 Microsoft 通話方案，但想要使用 SBC 電話) 。 最常見的案例之一是撥打協力廠商 PBX。  使用協力廠商 PBX 時，除了連接到該 PBX 的電話以外，所有通話都是使用 Microsoft 通話方案路由，但連至協力廠商 PBX 的電話會傳送到 SBC，因此會留在商業網路內，而不是 PSTN。 

有關電話系統授權的詳細資訊，請參閱從 Office 和方案選項[取得](https://products.office.com/compare-all-microsoft-office-products?tab=2)[最大使用。](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

有關電話系統授權詳細資訊，請參閱 Microsoft [Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。 

## <a name="supported-end-points"></a>支援的結束點 

您可以使用做為終點：

- 任何 Teams 用戶端。 
- 一般地區電話。 請參閱設定 Microsoft [Teams 的公用區域電話授權](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。 請注意，設定使用直接路由的公用地區電話時，不需要通話方案授權。
- 商務用 Skype 3PIP 手機。 請參閱 [商務用 Skype 手機 (3PIP) Microsoft Teams 支援](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 功能變數名稱

SBC 功能變數名稱必須來自在租使用者網域中註冊的其中一個名稱。 您無法將 \* .onmicrosoft.com 租使用者用於 SBC 的 FQDN 名稱。

下表顯示為租使用者註冊的 DNS 名稱範例、該名稱是否可以做為 SBC 的 FQDN，以及有效的 FQDN 名稱範例：

|DNS 名稱|可用於 SBC FQDN|FQDN 名稱範例|
|:--- |:--- |:--- |
contoso.com|是|**有效的名稱：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|SBC onmicrosoft.com 不支援使用 *.onmicrosoft.com 網域

假設您要使用新的功能變數名稱。 例如，您的租使用者 contoso.com 在租使用者中註冊的功能變數名稱，而您想要使用 sbc1.sip.contoso.com。 在將 SBC 與名稱配對 sbc1.sip.contoso.com，您必須在租使用者 sip.contoso.com 網域中註冊功能變數名稱。 如果您在註冊功能變數名稱之前嘗試將 SBC 與 sbc1.sip.contoso.com 配對，將會收到下列錯誤：「無法使用 「sbc1.sip.contoso.com」網域，因為它未為此租使用者所配置」。
新增功能變數名稱之後，您也需要使用 UPN 帳戶建立使用者，user@sip.contoso.com Teams 授權。 將功能變數名稱新加入租使用者網域、建立具有新名稱的使用者，以及指派授權給使用者之後，最多可能需要 24 小時的時間才能完整配置功能變數名稱。 

一家公司在一個租使用者中可能有幾個 SIP 位址空間。 例如，公司可能 contoso.com SIP 位址空間，fabrikam.com 作為第二個 SIP 位址空間。 有些使用者有位址 user@contoso.com，有些使用者有位址 user@fabrikam.com。 

SBC 只需要一個 FQDN，而且可以從配對租使用者的任何位址空間為使用者提供服務。 例如，名稱為 sbc1.contoso.com 的 SBC 可以接收及傳送位址為 user@contoso.com 和 user@fabrikam.com 的使用者的 PSTN 流量，只要這些 SIP 位址空間是在同一個租使用者中註冊。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的公用信任憑證

Microsoft 建議您針對 SBC 要求憑證，在CSR (中) 。 有關產生 SBC 的CSR 的特定指示，請參閱 SBC 廠商提供的互連指示或檔。 

  > [!NOTE]
  > 大部分的憑證頒發 (CA) 要求私密金鑰大小至少為 2048。 產生CSR 時，請記住這一點。

憑證必須具有 SBC FQDN 做為 CN (的公用名稱) 或 SAN (的) 名稱。 憑證應直接從憑證授權單位發出，而不是從中間提供者發出。

或者，直接路由支援 CN 和/或 SAN 中的萬用字元，而萬用字元必須符合標準的[RFC HTTP Over TLS。](https://tools.ietf.org/html/rfc2818#section-3.1) 例如，使用 \* .contoso.com 會符合 SBC FQDN sbc.contoso.com，但與 sbc.test.contoso.com。

憑證必須由下列其中一個根憑證授權單位產生：

- 確認信任
- AddTrust 外部 CA 根目錄
- 巴的摩網路根信任*
- Buypass
- 網路信任
- 第 3 類公用主要憑證授權單位
- Com正統安全根 CA
- Deutsche Telekom 
- DigiCert 全域根 CA
- DigiCert 高保證 EV 根 CA
- 委託
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign， Inc. 
- SSL.com
- Starfield
- Microsoft 版 Symantec Enterprise Mobile Root 
- SwissSign
- 解說時間戳記 CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom) 
- 仲裁Vadis

針對 Office 365 GCCH 和 DoD 環境中的直接路由，憑證必須由下列其中一個根憑證授權單位產生：
- DigiCert 全域根 CA
- DigiCert 高保證 EV 根 CA

> [!NOTE]
> *如果共同 TLS (MTLS) 支援已啟用 SBC 上的 Teams 連接，則您必須在 Teams TLS 上下文的 SBC 根信任存放區中安裝Baltimore CyberTrust 根憑證。  (這是因為 Microsoft 服務憑證使用Baltimore 根憑證。) 若要下載巴的摩根憑證，請參閱 [Office 365 加密鏈](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)。

Microsoft 正在根據客戶要求新增其他憑證授權單位。 

## <a name="sip-signaling-fqdns"></a>SIP 訊號：FQDNs 

直接路由提供于下列環境：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

深入瞭解 [Office 365 和](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 美國政府環境，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

直接路由的連接點如下三個 FQDNs：

- **sip.pstnhub.microsoft.com** 全域 FQDN - 必須先嘗試。 當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會返回指向指派給 SBC 的主要 Azure 資料中心的 IP 位址。 此工作分派是根據資料中心的績效度量，以及 SBC 的地理位置鄰近度。 所退回的 IP 位址會對應到主要 FQDN。
- **sip2.pstnhub.microsoft.com** - 次要 FQDN - 地理上會繪製至第二個優先順序區域。
- **sip3.pstnhub.microsoft.com** - 三級 FQDN – 地理上可繪製至第三個優先順序區域。

若要將這三個 FQDNs 排序，必須：

- 查詢第一個 FQDN (，提供較不載入且最接近 SBC 資料中心的最佳) 。
- 當從 SBC 建立與遇到暫時問題的資料中心的連接時，提供容錯移轉。 詳細資訊，請參閱 [下方的容錯移轉](#failover-mechanism-for-sip-signaling) 機制。  

FQNS -sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com sip3.pstnhub.microsoft.com -會解析為下列其中一個 IP 位址：

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。  如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 解析為所有這些 IP 位址。 

> [!IMPORTANT]
>  作為 Teams Direct 路由擴充和服務改進的一部分，我們已在澳大利亞部署直接路由基礎結構的新實例。 這反映在兩個額外的 IP 位址 (52.114.16.74 和 52.114.20.29) 以下 FQNS 將針對澳洲客戶解決 ： sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com。 您必須將這兩個 IP 位址 (52.114.16.74 和 52.114.20.29) 新加到您的 IP 存取控制清單 (ACL) ，並開啟防火牆中所有這些 IP 位址的埠，以便接收和傳出流量，以便接收和從位址發出通知。

### <a name="office-365-gcch-and-dod-environment"></a>Office 365 GCCH 和 DoD 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全域 FQDN。 由於 Office 365 DoD 環境僅存在於美國資料中心，因此沒有次要和三級 FQNS。

FQDN sip.pstnhub.dod.teams.microsoft.us 會解析為下列其中一個 IP 位址：

- 52.127.64.33
- 52.127.68.34

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全域 FQDN。 由於 GCC High 環境僅存在於美國資料中心，因此沒有次要和三級 FQNS。

FQDN sip.pstnhub.gov.teams.microsoft.us 會解析為下列其中一個 IP 位址：

- 52.127.88.59
- 52.127.92.64

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。 如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.gov.teams.microsoft.us** 解析為所有這些 IP 位址。 此 FQDN 也可以做為用於傳入通話分類的聯邦 FQDN。

## <a name="sip-signaling-ports"></a>SIP 訊號：埠

您必須針對提供直接路由的 Microsoft 365 或 Office 365 環境使用下列埠：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|交通|從|自|來源埠|目的地埠|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|Sbc|1024 – 65535|在 SBC 上定義 (Office 365 GCC High/DoD 僅埠 5061 必須使用) |
SIP/TLS|Sbc|SIP Proxy|在 SBC 上定義|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 訊號的容錯移轉機制

SBC 會進行 DNS 查詢來解決 sip.pstnhub.microsoft.com。 根據 SBC 位置和資料中心的績效度量，已選取主資料中心。 如果主要資料中心遇到問題，SBC 會嘗試 sip2.pstnhub.microsoft.com，這可解決至第二個指派的資料中心，而且，在兩個區域的資料中心無法使用的情況下，SBC 會重試最後一個 FQDN (sip3.pstnhub.microsoft.com) ，提供第三級資料中心 IP。

下表摘要列出主要、次要和三級資料中心之間的關係：

|如果主要資料中心是|Emea|NOAM|亞洲|
|:--- |:--- |:--- |:--- |
|次要資料中心 (sip2.pstnhub.microsoft.com) |我們|歐盟|我們|
|第三級資料中心 (sip3.pstnhub.microsoft.com) |亞洲|亞洲|歐盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒體流量：埠範圍
請注意，如果您想要部署不含媒體旁路的直接路由，則適用下列需求。 如需媒體旁路的防火牆需求，請參閱使用直接路由 [規劃媒體旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。



媒體流量會往來于 Microsoft Cloud 中的個別服務。 媒體流量的 IP 位址範圍如下。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

- 52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) 。
- 52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) 。

### <a name="office-365-dod-environment"></a>Office 365 DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>埠範圍 (適用于所有環境) 
媒體處理器的埠範圍如下表所示： 

|交通|從|自|來源埠|目的地埠|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒體處理器|Sbc|3478-3481 和 49152 – 53247|在 SBC 上定義|
|UDP/SRTP|Sbc|媒體處理器|在 SBC 上定義|3478-3481 和 49152 – 53247|

  > [!NOTE]
  > Microsoft 建議 SBC 上每個同時通話至少兩個埠。


## <a name="media-traffic-media-processors-geography"></a>媒體流量：媒體處理器地理位置

媒體流量會透過稱為媒體處理器的元件而流量。 媒體處理器會置於與 SIP 代理相同的資料中心。 此外，還有其他媒體處理器可優化媒體流程。 例如，我們目前在澳大利亞沒有 SIP proxy 元件 (SIP 經由新加坡或香港) 但我們在澳洲當地有媒體處理器。 本地媒體處理器的需要是由我們傳送長途流量的延遲所決定，例如從澳洲傳送至新加坡或香港。 雖然從澳洲到香港或新加坡的流量範例中的延遲是可接受的，可維持 SIP 流量的通話品質，但即時媒體流量則不允許。

媒體處理器的位置：

SIP Proxy 和媒體處理器元件部署的位置：
- 美國 (美國西部和東部資料中心有兩個) 
- 位於 (和伯林達的歐洲資料中心) 
- 亞洲 (新加坡和香港資料中心) 

只有媒體處理器部署在 SIP (經由上述最近的資料中心) ：
- 日本 (JP East 和 West 資料中心) 
- 澳大利亞 (東部和東南亞資料中心) 




## <a name="media-traffic-codecs"></a>媒體流量：編解碼器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>在 SBC 和雲端媒體處理器或 Microsoft Teams 用戶端之間移動。
適用于媒體旁路案例和非旁路案例。

在會話邊界控制器和雲端媒體處理器之間 (沒有媒體旁路) 或 Teams 用戶端與 SBC (如果已啟用媒體旁路) 之間的直接路由介面可以使用下列編解碼器：

- 將 SBC (雲端媒體處理器) ：SILK、G.711、G.722、G.729
- 將 SBC (到 Teams 用戶端的媒體) ：SILK、G.711、G.722、G.729

您可以強制使用會話邊界控制器上的特定編解碼器，從優惠中排除不想要的編解碼器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 用戶端與雲端媒體處理器之間的腳
僅適用于非媒體旁路案例。 使用媒體旁路，媒體會直接在 Teams 用戶端和 SBC 之間流動。

在雲端媒體處理器和 Microsoft Teams 用戶端之間使用 SILK 或 G.722。 此支腳上的編解碼器選項是以 Microsoft 演算法為基礎，其中會考慮多個參數。 


## <a name="supported-session-border-controllers-sbcs"></a>支援會話邊界控制器 (SBC) 

Microsoft 僅支援經過認證的 SBCs 與直接路由配對。 由於企業語音對於企業至關重要，因此 Microsoft 會與選取的 SBC 執行大量測試，並且與 SBC 廠商合作，以確保兩個系統相容。 

已驗證的裝置會列為 Teams 直接路由認證。 所有案例都保證認證裝置能夠使用。 

有關支援的 SBCs 詳細資訊，請參閱通過直接路由認證的會話 [邊界控制器清單](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另請參閱

[設定直接路由](direct-routing-configure.md)
