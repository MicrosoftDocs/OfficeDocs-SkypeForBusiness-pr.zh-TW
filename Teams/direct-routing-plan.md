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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解 Microsoft Phone 系統 Direct 路由如何讓您將支援的客戶提供的會話邊界控制器（SBC）連線至 Microsoft Phone 系統。
ms.openlocfilehash: bd221be2174a538956667e0b113d459f2293882f
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691229"
---
# <a name="plan-direct-routing"></a>規劃直接路由

> [!Tip]
> 請觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式：[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)

Microsoft Phone 系統直通路由可讓您將支援的客戶提供的會話邊界控制器（SBC）連線至 Microsoft Phone 系統。  例如，有了這項功能，您就可以設定與 Microsoft 團隊用戶端的內部部署公用電話網絡（PSTN）連線，如下圖所示： 

![顯示內部部署 PSTN 連線性配置的圖表](media/PlanDirectRouting1-PSTNwithTeams.png "與 Microsoft 團隊用戶端的內部部署 PSTN 連線能力")

  > [!NOTE]
  > 商務用 Skype Online 也能讓您與客戶提供的 SBC 搭配使用，但這需要一個內部部署商務用 Skype Server 部署，或是一個特殊版本的商務用 Skype （稱為雲端連接器），在 SBC 與 Microsoft 雲端之間。 這個案例稱為混合式語音。 相反地，直接路由可讓支援的 SBC 與 Microsoft 雲端之間的直接連接。 

透過直接路由，您可以將您的 SBC 連接到幾乎所有的電話幹線或與協力廠商 PSTN 裝置的互聯。 [直接佈線] 可讓您： 

- 在 Microsoft Phone 系統中使用幾乎任何 PSTN 幹線。 
- 在客戶擁有的電話語音裝置（例如協力廠商私人分支 exchange （PBX）、類比裝置和 Microsoft Phone 系統之間設定互通性。

Microsoft 也提供所有雲端語音解決方案，例如通話方案。 不過，在下列情況下，混合式語音方案可能最適合您的組織： 

- Microsoft 通話方案不適用於您的國家/地區。 
- 貴組織需要連線至協力廠商類比裝置、話務中心等。 
- 您的組織已擁有 PSTN 載波的現有合約。

直接路由還支援擁有 Microsoft 通話方案額外授權的使用者。 如需詳細資訊，請參閱[電話系統和通話方案](calling-plan-landing-page.md)。 

透過直接傳送，當使用者參與排程的會議時，Microsoft 音訊會議服務會提供撥入號碼，這需要正確的授權。  當您撥出時，Microsoft 音訊會議服務會使用線上通話功能（需要適當的授權）來放置通話。 （請注意，[撥出] 不會透過 [直接路由] 路由。）如需詳細資訊，請參閱[與團隊進行線上會議](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
規劃直接路由部署是成功實現的關鍵。 本文將說明基礎結構和授權需求，並提供 SBC 連線性的相關資訊： 

- [基礎結構需求](#infrastructure-requirements)
- [授權與其他需求](#licensing-and-other-requirements)
- [SBC 網功能變數名稱稱](#sbc-domain-names)
- [SBC 公開信任的憑證](#public-trusted-certificate-for-the-sbc)
- [SIP 信號： Fqdn](#sip-signaling-fqdns)
- [SIP 信號：埠](#sip-signaling-ports)
- [媒體流量：埠範圍](#media-traffic-port-ranges)
- [支援的會話邊界控制器（SBCs）](#supported-session-border-controllers-sbcs)

如需有關設定直接路由的詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基礎結構需求
下表列出支援的 SBCs、網域及其他網路連線需求之基礎結構需求：  

|**基礎結構需求**|**您需要下列各項**|
|:--- |:--- |
|會話邊界控制器（SBC）|受支援的 SBC。 如需詳細資訊，請參閱[支援的 SBCs](#supported-session-border-controllers-sbcs)。|
|連線至 SBC 的電話語音 trunks|一個或多個連線至 SBC 的電話 trunks。 在一端，SBC 透過直接路由連接到 Microsoft 手機系統。 SBC 也可以連接到協力廠商電話實體，例如 Pbx、類比電話卡等。 任何連接至 SBC 的 PSTN 連接選項都會正常運作。 （如需將 PSTN trunks 設定至 SBC，請參閱 SBC 廠商或主幹提供者）。|
|Microsoft 365 或 Office 365 組織|您用來將 Microsoft 團隊使用者用來家用的 Microsoft 365 或 Office 365 組織，以及 SBC 的設定與連接。|
|使用者註冊機構|使用者必須駐留在 Microsoft 365 或 Office 365 中。<br/>如果您的公司有內部部署商務用 Skype 或 Lync 環境，且其混合式連線至 Microsoft 365 或 Office 365，您就無法在小組中為使用者駐留內部部署的使用者啟用語音功能。<br/><br/>若要檢查使用者的註冊機構，請使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Cmdlet 的輸出應該會顯示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|定義域|新增至您的 Microsoft 365 或 Office 365 組織的一個或多個網域。<br/><br/>請注意，您無法使用 \* 針對您的租使用者自動建立的預設網域 onmicrosoft.com。<br/><br/>若要查看網域，您可以使用下列商務用 Skype Online PowerShell Cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>如需網域與 Microsoft 365 或 Office 365 組織的詳細資訊，請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公用 IP 位址|可用於連線至 SBC 的公用 IP 位址。 根據 SBC 的類型而定，SBC 可以使用 NAT。|
|SBC 的完整功能變數名稱（FQDN）|SBC 的 FQDN，其中 FQDN 的網域部分是您的 Microsoft 365 或 Office 365 組織中的註冊網域之一。 如需詳細資訊，請參閱[SBC 功能變數名稱](#sbc-domain-names)。|
|SBC 的公用 DNS 專案 |將 SBC FQDN 對應至公用 IP 位址的公用 DNS 專案。 |
|SBC 公開信任的憑證 |SBC 的憑證，用於與直接路由的所有通訊。 如需詳細資訊，請參閱[SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。|
|直接路由的連接點 |直接路由的連接點是下列三個 Fqdn：<br/><br/>`sip.pstnhub.microsoft.com`–必須先嘗試使用全域 FQDN。<br/>`sip2.pstnhub.microsoft.com`–次要 FQDN，地理位置對應至第二個優先順序區域。<br/>`sip3.pstnhub.microsoft.com`–三元 FQDN，地理位置對應至第三個優先順序區域。<br/><br/>如需設定需求的相關資訊，請參閱[SIP 信號： fqdn](#sip-signaling-fqdns)。|
|用於直接路由媒體的防火牆 IP 位址和埠 |SBC 會與雲端中的下列服務進行通訊：<br/><br/>負責處理信號的 SIP Proxy<br/>處理媒體的媒體處理器-除了媒體旁路<br/><br/>這兩個服務在 Microsoft 雲端中都有不同的 IP 位址，本文稍後會說明此檔。<br/><br/>如需詳細資訊，請參閱[url 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的[Microsoft 團隊區段](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 |
|媒體傳輸設定檔|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft 團隊媒體的防火牆 IP 位址和埠 |如需詳細資訊，請參閱[url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>授權與其他需求 

直接傳送的使用者必須具有下列在 Microsoft 365 或 Office 365 中指派的授權： 

- Microsoft Phone System。 
- Microsoft 團隊 + 商務用 Skype 方案2（如果包含在授權中）。
- Microsoft 音訊會議（如需有關授權的特定範例，請閱讀下列注意事項及以下段落）。

> [!NOTE]
> 商務用 Skype 方案不應從隨附的任何授權合約中移除。 


> [!IMPORTANT]
>  如果您想要將外部參與者新增至排程的會議，請撥打電話給他們，或提供撥入號碼，必須具備音訊會議授權。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>即席通話升級和音訊會議授權

團隊使用者可以啟動一對一團隊至 PSTN 或小組通話小組，並將 PSTN 參與者加入該小組。 這個案例稱為「ad hoc」會議。 呼叫所採取的路徑，取決於升級通話的使用者是否已指派 Microsoft 音訊會議授權：

- 如果升級通話的小組使用者已指派 Microsoft 音訊會議授權，則會透過 Microsoft 音訊會議服務進行升級。 受邀加入現有通話的遠端 PSTN 參與者會收到來電通知，並查看指派給啟動呈報之小組使用者的 Microsoft 橋接器號碼。
- 如果升級通話的小組使用者沒有指派 Microsoft 音訊會議授權，就會透過連線至直接路由介面的會話邊界控制器進行升級。 受邀接聽通話的遠端 PSTN 參與者會收到來電的通知，並查看已開始升級的小組使用者人數。 上報所用的特定 SBC 是由使用者的路由原則所定義。 


此外，您必須確認下列事項：
 
- CsOnlineVoiceRoutingPolicy 已指派給使用者。 
- 在 Microsoft 團隊的租使用者層級啟用 [允許私人通話]。 

直接路由還支援 Microsoft 通話方案授權的使用者。 含有通話方案的 Microsoft Phone 系統可以使用直接路由介面傳送一些通話。 不過，使用者的電話號碼必須是線上購買或移植至 Microsoft。  

針對相同的使用者混合通話方案和直接路由連線是選擇性的，但可能很有用（例如，當使用者指派 Microsoft 通話方案，但想要使用 SBC 路由進行一些呼叫）。 其中一個最常見的案例是呼叫協力廠商的 Pbx。  透過協力廠商 Pbx，所有通話（除了連接至該 Pbx 的電話除外）都是使用 Microsoft 通話方案進行路由，但連接至協力廠商 Pbx 的電話撥打電話給 SBC，因此，不會在商業網路中，也不是 PSTN。 

如需手機系統授權的詳細資訊，請參閱[充分利用 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)。 

如需手機系統授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 

## <a name="supported-end-points"></a>支援的端點 

您可以用做為終點：

- 任何團隊用戶端。 
- 常見的區域電話。 請參閱[設定 Microsoft 團隊的通用區域電話授權](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。 注意在使用直接傳送來設定一般的區域手機時，不需要通話方案授權。
- 商務用 Skype 3PIP 電話。 請參閱[Microsoft 團隊的商務用 Skype 電話（3PIP）支援](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 網功能變數名稱稱

SBC 網功能變數名稱稱必須來自于租使用者網域中註冊的其中一個名稱。 您無法 \* 針對 SBC 的 FQDN 名稱使用 onmicrosoft.com 租使用者。

下表顯示針對租使用者註冊的 DNS 名稱範例，無論該名稱是否可做為 SBC 的 FQDN，以及有效 FQDN 名稱的範例：

|**DNS 名稱**|**可用於 SBC FQDN**|**FQDN 名稱範例**|
|:--- |:--- |:--- |
contoso.com|是|**有效的名稱：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|SBC 名稱不支援使用 *. onmicrosoft.com 網域

假設您要使用新的功能變數名稱。 例如，您的租使用者有 contoso.com 做為在您的租使用者中註冊的功能變數名稱，而您想要使用 sbc1.sip.contoso.com。 您必須先在租使用者中的網域中註冊功能變數名稱 sip.contoso.com，才能將其與 name sbc1.sip.contoso.com 進行配對。 如果您在註冊功能變數名稱前嘗試搭配 sbc1.sip.contoso.com 進行配對，您會收到下列錯誤：「無法使用「sbc1.sip.contoso.com」網域，因為它未針對此租使用者進行設定。」
在您新增功能變數名稱之後，您也需要使用 UPN user@sip.contoso.com 建立使用者並指派小組授權。 在將功能變數名稱新增至租使用者的網域之後，最多可能需要24小時才能完全提供該功能變數名稱，並會建立一個具有新名稱的使用者，並指派授權給使用者。 

公司可能會在一個租使用者中有數個 SIP 位址空間。 例如，公司可能會將 contoso.com 做為 SIP 位址空間，並 fabrikam.com 為第二個 SIP 位址空間。 有些使用者有位址 user@contoso.com，而有些使用者則是位址 user@fabrikam.com。 

SBC 只需要一個 FQDN，而且可以從成對的租使用者中的任何位址空間來服務使用者。 例如，擁有 name sbc1.contoso.com 的 SBC 可以接收並傳送具有位址 user@contoso.com 和 user@fabrikam.com 之使用者的 PSTN 流量，只要這些 SIP 位址空間已在相同的租使用者中註冊。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 公開信任的憑證

Microsoft 建議您透過產生認證簽署要求（CSR）來要求 SBC 的憑證。 如需針對 SBC 產生 CSR 的特定指示，請參閱由您的 SBC 轉銷商提供的互連指示或檔。 

  > [!NOTE]
  > 大多數憑證授權單位（Ca）需要私密金鑰大小至少為2048。 產生 CSR 時，請記住這一點。

憑證在 subject 欄位中必須將 SBC FQDN 做為公用名（CN）。

或者，直接路由支援 SAN 中的萬用字元，而萬用字元必須符合[TLS 上標準 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)的要求。 \*在 SAN 中將會使用 contoso.com，這會與 SBC FQDN sbc.contoso.com 相符，但不會與 sbc.test.contoso.com 相符。

憑證需要由下列其中一個根憑證授權單位產生：

- AffirmTrust
- AddTrust 外部 CA 根目錄
- 巴爾的摩 CyberTrust 根
- Buypass
- Cybertrust
- Class 3 公用主要憑證授權單位
- Comodo 安全的根 CA
- 德國 Telekom 
- DigiCert 全域根 CA
- DigiCert 高確定性 EV 根 CA
- Entrust
- GlobalSign
- 移至 Go daddy
- GeoTrust
- Verisign，Inc。 
- SSL.com
- Starfield
- Microsoft 適用的 Symantec 企業行動裝置根 
- SwissSign
- Thawte 日戳 CA
- Trustwave
- TeliaSonera 
- T 系統國際 GmbH （德國 Telekom）
- QuoVadis

Microsoft 正在努力根據客戶要求新增其他認證機構。 

## <a name="sip-signaling-fqdns"></a>SIP 信號： Fqdn 

在下列環境中提供直接路由：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

深入瞭解[Office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（例如 GCC、gcc 高和 DoD）。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 及 Office 365 GCC 環境

直接路由的連接點是下列三個 Fqdn：

- **sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。 當 SBC 傳送要求來解析此名稱時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。 作業是以資料中心的效能指標，以及與 SBC 有關的地理位置為基礎。 傳回的 IP 位址會對應到主要 FQDN。
- **sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。
- **sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。

若要執行下列三個 Fqdn，必須進行下列動作：

- 提供最佳的使用體驗（在所指派的 SBC 資料中心較少且最接近的情況下，由查詢第一個 FQDN）。
- 提供從 SBC 連線到發生暫時問題的資料中心時的容錯移轉。 如需詳細資訊，請參閱下方的[容錯移轉機制](#failover-mechanism-for-sip-signaling)。  

Fqdn （sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）會解析成下列其中一個 IP 位址：

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。  如果您的防火牆支援 DNS 名稱，FQDN sip-all.pstnhub.microsoft.com 會解析為所有這些 IP 位址。 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

直接路由的連接點是下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。 因為 Office 365 DoD 環境僅存在於美國資料中心，所以沒有次要和第三個 Fqdn。

FQDN sip.pstnhub.dod.teams.microsoft.us 將解析成下列其中一個 IP 位址：

- 52.127.64.33
- 52.127.68.34

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

直接路由的連接點是下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。 由於 GCC 的高環境僅存在於美國資料中心，因此沒有副及三元 Fqdn。

FQDN sip.pstnhub.gov.teams.microsoft.us 將解析成下列其中一個 IP 位址：

- 52.127.88.59
- 52.127.92.64

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。

## <a name="sip-signaling-ports"></a>SIP 信號：埠

您必須在提供直接路由的 Microsoft 365 或 Office 365 環境中使用下列埠：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

|**頻寬**|**從**|**自**|**來源埠**|**目的地埠**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024–65535|在 SBC 上定義（必須使用 Office 365 GCC 高/DoD 專用埠5061）|
SIP/TLS|SBC|SIP Proxy|在 SBC 上定義|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 信號的容錯移轉機制

SBC 會進行 DNS 查詢來解析 sip.pstnhub.microsoft.com。 根據 SBC 位置和資料中心效能指標，選取主要資料中心。 如果主要資料中心遇到問題，SBC 將會嘗試可解析為第二個已指定資料中心的 sip2.pstnhub.microsoft.com，而且在兩個區域中的資料中心無法使用的極少數情況下，SBC 會重試最後一個 FQDN （sip3.pstnhub.microsoft.com），提供第三個資料中心 IP。

下表摘要列出主要、次要及三元資料中心之間的關聯：

|**如果主要資料中心是**|**中東**|**NOAM**|**太**|
|:--- |:--- |:--- |:--- |
|副資料中心（sip2.pstnhub.microsoft.com）|一下|歐洲|一下|
|第三個資料中心（sip3.pstnhub.microsoft.com）|太|太|歐洲|
|||||

## <a name="media-traffic-port-ranges"></a>媒體流量：埠範圍
請注意，如果您想要在不使用媒體的情況下部署直接路由，請套用下列需求。 如需媒體旁路的防火牆需求，請參閱[使用直接路由來規劃媒體旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。



媒體流量會流過 Microsoft 雲端中的個別服務。 媒體流量的 IP 位址範圍如下所示。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 及 Office 365 GCC 環境

- 52.112.0.0/14 （從52.112.0.1 到52.115.255.254 的 IP 位址）。
- 52.120.0.0/14 （從52.120.0.1 到52.123.255.254 的 IP 位址）。

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>埠範圍（適用于所有環境）
媒體處理器的埠範圍如下表所示： 

|**頻寬**|**從**|**自**|**來源埠**|**目的地埠**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒體處理器|SBC|3478-3481 與49152–53247|在 SBC 上定義|
|UDP/SRTP|SBC|媒體處理器|在 SBC 上定義|3478-3481 與49152–53247|

  > [!NOTE]
  > Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。


## <a name="media-traffic-media-processors-geography"></a>媒體流量：媒體處理器地理位置

媒體流量透過稱為媒體處理器的元件來流動。 媒體處理器與 SIP proxy 放在同一個資料中心。 此外，還有其他媒體處理器可優化媒體流程。 例如，我們目前沒有在澳大利亞（透過新加坡或香港）傳送 sip proxy 元件，但我們在澳大利亞有本機的媒體處理器。 在本機提供媒體處理器的需求是由我們透過傳送流量（例如從澳大利亞到新加坡或香港）來取得的延隔時間來決定。 雖然從澳大利亞到香港或新加坡的流量範例中的延遲，仍可保持良好的 SIP 流量通話品質，而不需要進行即時媒體流量。

媒體處理器的位置：

已部署 SIP proxy 和媒體處理器元件的位置：
- 我們（美國西部和東資料中心有兩個）
- 歐洲（阿姆斯特丹與都柏林資料中心）
- 亞洲（新加坡與香港資料中心）

只部署媒體處理器的位置（由上述最接近資料中心的 SIP 流程）：
- 日本（JP 東部和西部資料中心）
- 澳大利亞（AU 東和東南部資料中心）




## <a name="media-traffic-codecs"></a>媒體流量：編解碼器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>在 SBC 與雲端媒體處理器或 Microsoft 團隊用戶端之間的腿。
適用于媒體旁路大小寫和非旁路情況。

在會話邊界控制器和雲端媒體處理器（沒有媒體旁路）或團隊用戶端與 SBC （如果已啟用媒體旁路）之間，在腿的直接路由介面上，您可以使用下列編解碼器：

- 非媒體旁路（SBC 到雲端媒體處理器）：絞絲、711、722、G 729
- 媒體旁路（SBC 至團隊用戶端）：絞絲、711、729、722、G

您可以從優惠中排除不想要的編解碼器，以強制在會話邊界控制器上使用特定的編解碼器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft 團隊用戶端與雲端媒體處理器之間的腿
僅適用于非媒體旁路大小寫。 在媒體旁路的情況下，媒體會直接在團隊用戶端和 SBC 之間流動。

在雲端媒體處理器與 Microsoft 團隊用戶端之間的腿上，使用的是絞絲或722。 這個腿的編解碼器選擇是以 Microsoft 演算法為基礎，考慮了多個參數。 


## <a name="supported-session-border-controllers-sbcs"></a>支援的會話邊界控制器（SBCs）

Microsoft 只支援驗證的 SBCs 與直接路由配對。 因為企業語音對企業而言是很重要的，Microsoft 會以所選的 SBCs 來執行大量測試，並與 SBC 廠商搭配使用，以確保兩個系統相容。 

已驗證的裝置會列為 [團隊直接路由] 的 [認證者]。 認證的裝置在所有情況下都能保證正常運作。 

如需支援的 SBCs 的詳細資訊，請參閱[認證以直接路由的會話邊界控制器清單](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另請參閱

[設定直接路由](direct-routing-configure.md)
