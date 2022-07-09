---
title: 規劃混合式連線|商務用 Skype Server和 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: 規劃透過設定混合式模式，在 商務用 Skype Server 和 Teams 之間實作混合式連線商務用 Skype。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695046"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>規劃商務用 Skype Server與 Teams 之間的混合式連線

> [!Important]
> 雖然 商務用 Skype Online 自 2021 年起已淘汰，但仍支援內部部署產品 商務用 Skype Server 2019、商務用 Skype Server 2015 和 Lync Server 2013。 此外，Microsoft 支援這些內部部署產品與 Microsoft Teams 之間的混合式環境。 這可讓具有這些內部部署的組織將其使用者移轉至 TeamsOnly。  最後，不再支援 Cloud Connector 版本的 商務用 Skype Server。 需要內部部署 PSTN 連線的客戶應該使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)。


閱讀本主題以瞭解如何規劃 商務用 Skype Server 或 Lync Server 2013 與 Teams 之間的混合式連線。 設定混合式連線能力是將內部部署環境移至雲端中僅限 Microsoft Teams 環境的第一個步驟。

在商務用 Skype Server的內部部署中，商務用 Skype的使用者也可以使用 Teams，但並非所有 Teams 功能都可供這類使用者使用，只要他們設定為使用內部部署商務用 Skype Server部署即可。 這些使用者稱為「常用」內部部署，而當這些使用者位於內部部署時，某些 Teams 功能無法使用，例如：

- 無法透過使用者的 Teams 用戶端與其他組織中的使用者進行同盟通話和聊天
- 透過使用者的 Teams 用戶端與組織中使用商務用 Skype用戶端的其他使用者進行 Interop 通訊。
- 如果使用者獲指派電話系統授權) ，則 PSTN 通話功能 (。

若要取得完整的 Teams 功能，這些使用者必須從內部部署商務用 Skype移至雲端，此時使用者會變成 TeamsOnly。 將使用者從內部部署移至雲端的動作，會將使用者的共同存在模式設定為 TeamsOnly。 一旦使用者移至雲端和 TeamsOnly，所有連入聊天和通話都會進入其 Teams 用戶端 (不同于 Teams) 的並存使用方式。  如需詳細資訊，請參閱[Teams 與商務用 Skype共存和移](/microsoftteams/coexistence-chat-calls-presence)轉，以及[搭配使用 Teams 與商務用 Skype之組織的互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

在內部部署與雲端中的 TeamsOnly 之間移動使用者需要設定商務用 Skype混合模式。 此外，在解除委任內部部署商務用 Skype部署會將所有使用者從內部部署移至雲端。   設定混合式連線後，您可以根據您的排程和業務需求，選擇將使用者移至雲端。  使用直接路由，您可以在移至雲端時以及在完成移轉之後，運用您的內部部署語音基礎結構。

本主題說明在現有的內部部署商務用 Skype Server部署與 Teams 之間設定混合式連線所需的基礎結構和系統需求。

閱讀本主題並準備好設定混合式連線之後，請參閱設定[商務用 Skype Server與 Teams 之間的混合式連線](configure-hybrid-connectivity.md)。 設定主題提供在內部部署與 Teams 之間設定混合式連線的逐步指引。


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>商務用 Skype Online 淘汰的影響
請務必記住，在 商務用 Skype Online 淘汰之前和之後，位於內部部署商務用 Skype Server使用者都可以使用 Teams，但不能是 TeamsOnly。  (內部部署使用者預設為離島模式，且獲指派 TeamsOnly) 以外的任何模式。 使用者只能體驗 Teams 的完整優點，特別是同盟、PSTN 支援，以及保證所有輸入聊天和通話在 Teams 處於 TeamsOnly 模式之後才會進入 Teams。 

商務用 Skype Online 的淘汰不會影響 商務用 Skype Server 或 Lync Server 2013 的現有支援生命週期。  不過，商務用 Skype Online 的淘汰確實會影響 *使用者如何轉換至雲* 端，並在具有內部部署商務用 Skype Server或 Lync Server 2013 的組織中成為 TeamsOnly 的特定層面，包括現有的混合式組織。 使用混合式作為從內部部署轉換至雲端的必要組態 (例如 TeamsOnly) 維持不變。

在淘汰 商務用 Skype Online 之前，混合式組織可以包含三種基本類型的使用者： 
- 內部部署使用者 (誰可以或可能不會使用 Teams，但不能在僅限 Teams 模式中)  
- 具有 TeamsOnly 以外的任何共存模式的線上使用者
- TeamsOnly 使用者。

不過，在 商務用 Skype Online 淘汰之後，混合式組織只能由兩種基本類型的使用者組成： 
- 內部部署使用者 (誰可以或可能不會使用 Teams，但不能在 TeamsOnly 模式中) 
- 僅限 Teams 使用者。 

若要讓組織從 商務用 Skype Server 或 Lync Server 2013 移至 Teams，仍必須使用相同的工具組來設定混合式，*與淘汰前完全相同*。 將使用者從內部部署移至 TeamsOnly 時，不再需要在 中 `Move-CsUser` 指定 `-MoveToTeams` 參數。 先前，如果未指定此參數，則使用者會從內部部署商務用 Skype Server的住家轉換為 商務用 Skype Online，且其模式會保持不變。 不過，由於 Skype Business Online 已淘汰，因此使用 將使用者從內部部署移至雲 `Move-CsUser` 端會 *自動* 指派 TeamsOnly 模式，並起始將其會議從內部部署轉換為 Teams 會議，而不論是否 `-MoveToTeams` 已指定切換。 這也表示具有 Lync Server 2013 且從未進行過切換的 `MoveToTeams` 組織，可以將使用者從內部部署直接移至 TeamsOnly。 

同樣地，如果直接在 Microsoft 365 而不是內部部署中建立新使用者，該使用者將自動擁有僅限 Teams 模式，而不論租使用者的模式為何。 請記住，在至少具有一個內部部署使用者的混合式組織中，應該在內部部署的 Active Directory (中建立新使用者，然後同步處理到 Microsoft 365) ，而不是直接在 Microsoft 365 中建立使用者，以確保 *即使您想要讓新使用者成為雲* 端使用者，內部部署使用者仍可路由傳送至新使用者。 在內部部署目錄中建立之後，這些新使用者必須在內部部署商務用 Skype部署 *中* 啟用 sip，然後視需要移至雲端成為 TeamsOnly。 

商務用 Skype Online 淘汰之後，共存模式會繼續存在。 和之前一樣，具有位於內部部署商務用 Skype Server帳戶的使用者，可以獲指派 TeamsOnly 以外的任何共存模式。 不過，在停用之後，線上的使用者只能是 TeamsOnly。 您無法再將 TeamsOnly 以外的模式指派給線上的使用者。


> [!Important]
> 現有混合式組織，其使用者位於 商務用 Skype Online，而這些使用者不是 TeamsOnly，應儘快專注于將這些使用者升級至僅限 Teams 模式。 如果您的組織仍有使用者位於 商務用 Skype *Online* 中，而這些使用者不是 TeamsOnly，您將會被排程進行 Microsoft 協助升級，以將這些使用者轉換至 TeamsOnly。 **Microsoft 輔助升級不會影響位於內部部署商務用 Skype Server使用者。** 在這些線上非 TeamsOnly 使用者升級至 Teams 之前，排程通知會事先傳送給位於 商務用 Skype Online 的使用者的混合式客戶。

## <a name="about-shared-sip-address-space-functionality"></a>關於共用 SIP 位址空間功能

<a name="BKMK_Overview"> </a>

在內部部署商務用 Skype Server與 Teams 之間設定混合式連線能力後，您可以讓一些使用者在內部部署和部分使用者上線。

這種類型的設定依賴共用 SIP 位址空間功能，有時稱為「分割網域」，這表示網域的使用者，例如 contoso.com，會在內部部署和 Teams 上使用商務用 Skype Server來分割，如下圖所示：

![商務用 Skype 混合式連線 - 分割網域。](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

設定共用 SIP 位址空間時：

- Azure Active Directory Connect 可用來同步處理內部部署目錄與 Microsoft 365。
- 位於內部部署的使用者會與內部部署商務用 Skype伺服器互動。
- 在線上的使用者會與 Teams 互動。
- 來自這兩個環境的使用者可以彼此通訊。
- 內部部署的 Active Directory具有權威性。 所有使用者都應該先在內部部署的 Active Directory中建立，然後同步處理至 Azure AD。 即使您想要讓使用者上線，您也必須先在內部部署環境中建立使用者，然後將使用者移至線上，以確保內部部署使用者可以探索使用者。

使用者必須先獲指派 Teams 授權，以及 商務用 Skype Online (方案 2) ，才能將使用者移至線上。 **即使在 商務用 Skype Online 淘汰之後，仍需要指派 商務用 Skype Online 授權。** 如果您的使用者想要利用其他線上功能，例如音訊會議或電話系統，您需要在 Microsoft 365 中為其指派適當的授權。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>混合式連線基礎結構需求

<a name="BKMK_Infrastructure"> </a>

若要實作內部部署環境與 Microsoft 365 通訊服務之間的混合式連線，您需要符合下列基礎結構需求：

- 在支援的拓撲中部署商務用 Skype Server或 Lync Server 的單一內部部署。 請參閱本主題中的 [拓撲需求](plan-hybrid-connectivity.md#BKMK_Topology) 。

- 具有 Teams 的 Microsoft 365 組織。
    > [!NOTE]
    > 您只能將單一租使用者用於內部部署的混合式組態。
    
- Azure Active Directory Connect 以同步處理您的內部部署目錄與 Microsoft 365。 如需詳細資訊，請參閱 [[Azure AD Connect: 帳戶和權限]](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- 商務用 Skype Server管理工具。 這些是將使用者從內部部署移至雲端的必要專案。 這些工具必須安裝在可存取內部部署和網際網路的伺服器上。
- 線上系統管理工具。 您可以使用 Teams 系統管理中心或Windows PowerShell來管理 Teams。 若要使用 PowerShell 來管理 Teams，請下載並安裝 Teams PowerShell 模組。  (商務用 Skype Online Connector 已淘汰) 。
- 必須啟用共用 SIP 位址空間，而且您的內部部署必須設定為使用 Microsoft 365 作為主機提供者。 如需設定混合式連線所需步驟的詳細資訊，請參閱設定 [混合式連線](configure-hybrid-connectivity.md)能力。

設定混合式連線之後，您可以將使用者移至 Teams。 如需詳細資訊，請 [參閱將使用者從內部部署移至 Teams](move-users-from-on-premises-to-teams.md)。

## <a name="server-version-requirements"></a>伺服器版本需求

<a name="BKMK_Topology"> </a>

若要設定與 **Teams** 混合的部署，您需要有下列其中一個支援的拓撲：

- 含所有執行商務用 Skype 伺服器 2019 之伺服器的商務用 Skype 伺服器 2019 部署。
- 含所有執行商務用 Skype 伺服器 2015 之伺服器的商務用 Skype 伺服器 2015 部署。
- 含所有執行 Lync Server 2013 之伺服器的 Lync Server 2013 部署。  不過，如果需要混合式語音連線，您必須使用混合版本拓撲，如下所述。
- 具有最多 2 個不同伺服器版本的部署，如下所示：
  - 商務用 Skype 伺服器 2015 和商務用 Skype 伺服器 2019
  - Lync Server 2013 和商務用 Skype 伺服器 2019
  - Lync Server 2013 和商務用 Skype 伺服器 2015
- 自 2022 年 7 月 31 日起，若要在內部部署與雲端之間移動使用者，您必須使用下列最低版本的 商務用 Skype Server 或 Lync Server：
</br>

|內部部署產品|必要的最低版本|必要的最小組建|
|---|---|---|
|商務用 Skype Server 2019| CU6 |7.0.2046.385|
|商務用 Skype Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 搭配 Hotfix 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Teams 不支援 Lync Server 2010。


## <a name="multi-forest-support"></a>多樹系支援

<a name="BKMK_MultiForest"> </a>

Microsoft 支援下列多樹系混合式案例類型：

- **資源樹系拓撲。** 在這種拓撲中，有一個樹系裝載商務用 Skype Server (資源樹系) ，而且有一或多個額外的樹系裝載帳戶身分識別，可存取資源樹系中的商務用 Skype Server。 一般而言，如果符合下列需求，使用者就可以存取另一個樹系中的商務用 Skype 功能：
  - 使用者會正確同步處理至代管商務用 Skype 的樹系。 在混合式組態中，這表示使用者必須同步為停用的使用者物件。
  - 代管商務用 Skype 的樹系必須信任包含使用者的樹系。
    如需資源樹系混合式案例的詳細資訊，請[參閱部署混合式商務用 Skype的資源樹系拓撲](configure-a-multi-forest-environment-for-hybrid.md)。

- **在多個樹系中部署多個商務用 Skype Server。** 此設定可能是因為合併和收購案例，以及更複雜的企業所導致。 只要符合下列重要需求，任何具有多個商務用 Skype部署的組織都可以在單一 Microsoft 365 組織中將所有使用者從內部部署整合到雲端：
  - 最多必須涉及一個 Microsoft 365 組織。 不支援在具有多個組織的案例中進行匯總。
  - 任何時候，只有一個內部部署商務用 Skype 樹系可以處於混合模式 (共用 SIP 位址空間)。 所有其他內部部署商務用 Skype樹系必須完全保留在內部部署 (，而且必須彼此同盟) 。 請注意，如果需要，這些其他內部部署組織可以使用新功能來同步至 AAD，以停用 2018 年 12 月起可用的 [線上 SIP 網域](/powershell/module/skype/disable-csonlinesipdomain) 。

    在多個樹系中部署商務用 Skype的客戶必須使用分割網域 (共用 SIP 位址空間) 功能，將每個商務用 Skype樹系個別完全移轉至 Microsoft 365 組織。 樹系移轉完成之後，客戶必須先停用混合式內部部署，再繼續移轉下一個內部部署商務用 Skype部署。 此外，在移轉至雲端之前，內部部署使用者會與未在相同使用者內部部署目錄中表示的任何使用者保持同盟狀態。 如需詳細資訊，請參閱[Teams 和 商務用 Skype 的雲端匯總](cloud-consolidation.md)。

## <a name="federation-requirements"></a>同盟需求

<a name="BKMK_Federation"> </a>

設定商務用 Skype混合模式時，您必須確定內部部署和線上環境可以彼此同盟。  線上環境預設會開啟同盟;根據預設，內部部署環境通常會關閉同盟。  

必須符合下列需求，才能成功設定混合式部署：

- 您的內部部署和 Microsoft 365 組織必須設定相同的網域比對。 如果在內部部署上啟用合作夥伴探索，則必須為您的線上組織設定開啟同盟。 如果未啟用合作夥伴探索，則必須為您的線上組織設定已關閉的同盟。
- 內部部署中的 [封鎖的網域] 清單必須完全符合線上租使用者的 [封鎖的網域] 清單。
- 內部部署中的 [允許的網域] 清單必須完全符合線上租使用者的 [允許的網域] 清單。
- 必須針對線上租使用者的外部通訊啟用同盟。

## <a name="network-considerations"></a>網路考量

下列各節說明下列專案的考慮：

- DNS 設定
- 防火牆考慮

### <a name="dns-settings-for-hybrid-deployments"></a>混合式部署的 DNS 設定

<a name="BKMK_DNS"> </a>

建立混合式部署的 DNS 記錄時，所有商務用 Skype 外部 DNS 記錄都應該指向內部部署基礎結構。 如需所需 DNS 記錄的詳細資訊，請參閱[商務用 Skype Server的 DNS 需求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，您必須確保下表所述的 DNS 解析可在您的內部部署中運作。 (如果您已針對內部部署設定同盟，則很可能已經有這些。)

|DNS 記錄  <br/> |可解決者  <br/> |DNS 需求  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp 的 DNS SRV 記錄。\<sipdomain.com\> 針對解析為 Access Edge 外部 IP (的所有支援 SIP 網域)   <br/> |Edge Server  <br/> |在混合式設定中啟用同盟通訊。 Edge Server 必須知道要在何處路由傳送內部部署和線上之間分割之 SIP 網域的同盟流量。  <br/> 必須在使用者名稱中的網域與 SRV 記錄之間使用嚴格的 DNS 名稱比對。  <br/> |
|DNS A 記錄 (Edge Web 會議服務 FQDN 的) ，例如 webcon.contoso.com 解析為 Web Conferencing Edge 外部 IP (的)   <br/> |內部公司網路連線使用者的電腦  <br/> |讓線上使用者在內部部署託管的會議中呈現或檢視內容。 內容包括 PowerPoint 檔案、白板、投票和共用筆記。  <br/> |

根據您組織中的 DNS 設定方式，您可能需要將這些記錄新增至內部裝載的 DNS 區域，以便對應的 SIP 網域可提供這些記錄的內部 DNS 解析。

### <a name="firewall-considerations-for-hybrid-deployments"></a>混合式部署的防火牆考慮

<a name="BKMK_Firewall"> </a>

您網路上的電腦必須能夠執行標準網際網路 DNS 查詢。 若這些電腦可以搜尋標準網際網路網站，表示您的網路符合此需求。

根據 Microsoft Online Services 資料中心的位置，您也必須將網路防火牆裝置設定為接受以萬用字元功能變數名稱為基礎的連線 (例如，來自 \* .outlook.com) 的所有流量。 如果您組織的防火牆不支援萬用字元名稱設定，您必須手動判斷您想要允許的 IP 位址範圍和指定的埠。

如需詳細資訊，包括埠和通訊協定需求的詳細資料，請參閱 [Microsoft 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)。
