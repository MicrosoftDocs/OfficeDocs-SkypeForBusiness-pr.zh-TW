---
title: 規劃混合式連接 |商務用 Skype Server 2019 和 Microsoft 365 或 Office 365 整合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 透過設定商務用 Skype 混合模式，規劃在商務用 Skype Server 和團隊或商務用 skype Online 之間實施混合式連線。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 856172d5fba3df96b2456f0ceca1c661120e84e4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878577"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線

閱讀此主題以瞭解如何規劃商務用 Skype Server 和團隊或商務用 Skype Online 之間的混合式連線。 設定混和式連線是將內部部署環境移至雲端的第一步。

如果是使用 Teams (並存) 之內部部署的商務用 Skype 使用者，將無法從 Teams 用戶端與商務用 Skype 使用者互通，也無法從 Teams 用戶端與同盟組織中的使用者進行通訊。 若要取得 Teams 中的這項功能，這些使用者必須從商務用 Skype 內部部署移至雲端，而此動作需要設定商務用 Skype 混合式模式。 此外，為了獲得最佳的體驗，這些使用者應是「僅限小組」的模式，可確保使用者的團隊用戶端中所有使用者土地的來電和聊天。

在解除您的內部部署商務用 Skype之前，還必須設定混合式連線並將所有使用者移至雲端。  設定混合式連線後，您可以根據您的排程和業務需求，選擇將使用者移至雲端。 使用直接路由，您可以在移至雲端時以及在完成移轉之後，運用您的內部部署語音基礎結構。

本主題說明在您現有的內部部署商務用 Skype Server 部署與團隊或商務用 Skype Online 之間設定混合式連線時，所需的基礎結構和系統需求。

閱讀本主題並準備好設定混合式連線後，請參閱 [設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合](configure-hybrid-connectivity.md)式連線。 設定主題為設定內部部署與小組或商務用 Skype Online 之間設定混合式連線的逐步指引。

> [!Important]
> 在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。  瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

## <a name="about-shared-sip-address-space-functionality"></a>關於共用 SIP 位址空間功能

<a name="BKMK_Overview"> </a>

 在內部部署商務用 Skype Server 和團隊或商務用 Skype Online 之間設定混合式連線，您可以讓某些使用者位於內部部署，而某些使用者則位於線上。

這種類型的設定取決於共用 SIP 位址空間功能，有時也稱為「分割網域」--表示網域的使用者（如 contoso.com）是在內部部署和小組或商務用 Skype Online 上使用商務用 Skype 伺服器進行分割，如下圖所示：

![商務用 Skype 混合式連線功能-分割網域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

設定共用 SIP 位址空間時：

- Azure Active Directory Connect 是用於同步處理內部部署目錄與 Microsoft 365 或 Office 365。
- 位於內部部署的使用者會與內部部署商務用 Skype 伺服器互動。
- 位於線上的使用者可能會與商務用 Skype Online 或小組服務互動。
- 這兩種環境中的使用者都可以相互通訊。
- 內部部署 Active Directory 具有權威性。 所有使用者都應該先在內部部署 Active Directory 中建立，然後同步處理至 Azure AD。 即使您想要讓使用者進入線上狀態，您還是必須先在內部部署環境中建立使用者，然後將使用者移至線上，以確保內部部署使用者可以發現使用者。

使用者必須已獲指派商務用 Skype Online (方案 2) 授權，使用者才能線上移動。 如果使用者使用的是小組，也必須為使用者指派小組授權 (，商務用 Skype 授權必須保持啟用) 。 如果您的使用者想要利用其他線上功能（例如音訊會議或電話系統），您必須在 Microsoft 365 或 Office 365 中指派適當的授權。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>混合式連接基礎結構需求

<a name="BKMK_Infrastructure"> </a>

若要在您的內部部署環境與 Microsoft 365 或 Office 365 通訊服務之間執行混合式連線，您必須符合下列基礎結構需求：

- 在支援的拓撲中部署的商務用 Skype Server 或 Lync Server 的單一內部部署。 請參閱本主題中的 [拓撲需求](plan-hybrid-connectivity.md#BKMK_Topology) 。

- 啟用啟用商務用 Skype Online 的 Microsoft 365 或 Office 365 組織。
    > [!NOTE]
    > 您可以使用單一租使用者進行混合式設定與您的內部部署。
    
- Azure Active Directory Connect 以將您的內部部署目錄與 Microsoft 365 或 Office 365 同步。 如需詳細資訊，請參閱 [AZURE AD Connect：帳戶和許可權](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- 商務用 Skype Server 系統管理工具。 這些是將使用者從內部部署移至雲端的必要條件。 這些工具必須安裝在具有內部部署和網際網路存取權的伺服器上。
- 線上系統管理工具。 您可以使用團隊系統管理中心或 Windows PowerShell 來管理團隊和商務用 Skype Online。 若要使用 PowerShell 管理小組或商務用 Skype Online，請下載並安裝商務用 Skype Online 連接器。
- 必須啟用共用 SIP 位址空間，而且您的內部部署部署必須設定為使用 Microsoft 365 或 Office 365 作為主機服務提供者。 如需設定混合式連線所需步驟的詳細資訊，請參閱 [設定混合](configure-hybrid-connectivity.md)式連線。

設定混合式連線後，您可以將使用者移至小組或商務用 Skype Online。 如需詳細資訊，請參閱 [將使用者從內部部署移至小組](move-users-from-on-premises-to-teams.md) ，以及 [將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。

## <a name="server-version-requirements"></a>伺服器版本需求

<a name="BKMK_Topology"> </a>

若要設定部署以搭配 **小組或商務用 Skype Online** 進行混合，您必須具備下列其中一種支援的拓撲：

- 商務用 Skype Server 2019 部署，包含所有執行商務用 Skype Server 2019 的伺服器。
- 商務用 Skype Server 2015 部署，包含所有執行商務用 Skype Server 2015 的伺服器。
- Lync Server 2013 部署，包含所有執行 Lync Server 2013 的伺服器。  不過，如果需要混合式語音連線，您必須使用混合版本拓撲，如下所述。
- 最多有2個不同伺服器版本的部署，如下所示：
  - 商務用 skype Server 2015 和商務用 Skype Server 2019
  - Lync Server 2013 和商務用 Skype Server 2019
  - Lync Server 2013 和商務用 Skype Server 2015

*如果任何拓撲中需要混合式語音* ，則指定為同盟 edge 的 edge server 以及與 SIP 同盟關聯的集區，都必須執行商務用 Skype 2015 或更新版本。 使用者可以保留在 Lync 2013 集區（如果有的話）。 如需詳細資訊，請參閱 [Plan Phone System WITH PSTN Connectivity In 商務用 Skype Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。

下列包括 Lync Server 2010 的拓撲支援立即訊息和會議的 **商務用 Skype Online** 。 **混合式語音或小組不支援包含 Lync Server 2010** 的拓撲。

- 混合的 Lync Server 2010 和商務用 Skype Server 2015 部署
- 混合的 Lync Server 2010 和 Lync Server 2013 部署
- Lync Server 2010 部署，其中包含所有執行 Lync Server 2010 的伺服器及最新的累計更新。

同盟 edge server 與下一個躍點伺服器的同盟 Edge server 必須執行 Lync Server 2010 及最新的累計更新。 商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須至少安裝在一部伺服器或管理工作站上。

## <a name="multi-forest-support"></a>多樹系支援

<a name="BKMK_MultiForest"> </a>

Microsoft 支援下列多樹系混合式案例類型：

- **資源樹系拓撲。** 在這種拓撲中，有一個樹系主控商務用 Skype Server (資源樹系) ，而且還有一或多個其他樹系主控帳戶身分識別，可在資源樹系中存取商務用 Skype 伺服器。 一般來說，如果符合下列需求，使用者就可以在另一個樹系中存取商務用 Skype 功能：
  - 使用者可正確地同步處理到主控商務用 Skype 的樹系中。 在混合式設定中，這表示使用者必須同步處理成停用的使用者物件。
  - 主控商務用 Skype 的樹系必須信任包含使用者的樹系。
    如需資源樹系混合式案例的詳細資訊，請參閱 [部署混合式商務用 Skype 的資源樹系拓撲](configure-a-multi-forest-environment-for-hybrid.md)。

- **多個樹系中商務用 Skype Server 的多個部署。** 這項設定會因合併和收購案例，以及更複雜的企業而產生。 若有多個商務用 Skype 部署的組織，您可以在單一 Microsoft 365 或 Office 365 組織中，將所有使用者從內部部署整合至雲端，但前提是符合下列主要需求：
  - 最多隻能有一個 Microsoft 365 或 Office 365 組織參與。 不支援在具有多個組織之案例中進行合併。
  - 在任何指定時間，只有一個內部部署商務用 Skype 樹系可以在混合模式中 (共用 SIP 位址空間) 。 其他所有的內部部署商務用 Skype 樹系都必須完全在內部部署中 (，並將每個其他) 的同盟。 請注意，如有需要，這些其他內部部署組織可以與 AAD 同步處理，以停用於12月2018的 [線上 SIP 網域](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 。

    在多個樹系中部署商務用 Skype 的客戶，必須透過分割網域 (共用 SIP 位址空間) 功能，將每個商務用 skype 樹系完全遷移到 Microsoft 365 或 Office 365 組織中，然後再停用內部部署的混合式，再繼續遷移下一個內部部署商務用 Skype 部署。 此外，在遷移至雲端之前，內部部署使用者仍保持同盟狀態，而不是在相同使用者的內部部署目錄中呈現任何使用者。 如需詳細資訊，請參閱 [Cloud 整合小組和商務用 Skype](cloud-consolidation.md)。

## <a name="federation-requirements"></a>同盟需求

<a name="BKMK_Federation"> </a>

設定商務用 Skype 混合模式時，您必須確定內部部署和線上環境可以彼此同盟。  根據預設，線上環境具有開啟的同盟;根據預設，內部部署環境通常會有關閉的同盟。  

若要成功設定混合式部署，必須符合下列需求：

- 您的內部部署和您的 Microsoft 365 或 Office 365 組織必須設定符合網域的功能。 如果已在內部部署上啟用夥伴探索，則必須為您的線上組織設定開啟同盟。 若未啟用夥伴探索，則必須為您的線上組織設定關閉的同盟。
- 內部部署部署中的封鎖網域清單必須完全符合您線上租使用者的封鎖網域清單。
- 內部部署部署中的允許網域清單必須完全符合您線上租使用者的允許網域清單。
- 必須針對線上承租人的外部通訊啟用同盟。

## <a name="network-considerations"></a>網路考量

下列各節說明下列事項：

- DNS 設定
- 防火牆考慮

### <a name="dns-settings-for-hybrid-deployments"></a>混合式部署的 DNS 設定

<a name="BKMK_DNS"> </a>

在建立混合部署的 DNS 記錄時，所有商務用 Skype 外部 DNS 記錄都應該指向內部部署基礎結構。 如需必要 DNS 記錄的詳細資訊，請參閱 [商務用 Skype Server 的 DNS 需求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，您必須確定下表中所述的 DNS 解析度可在您的內部部署中運作。  (如果您已經為內部部署設定同盟，您很可能已經有這些。 ) 

|DNS 記錄  <br/> |可解析的  <br/> |DNS 需求  <br/> |
|:-----|:-----|:-----|
|_Tcp 的 _sipfederationtls DNS SRV 記錄。\<sipdomain.com\> 針對所有支援的 SIP 網域，解析為存取 Edge 外部 IP (s)   <br/> |Edge server (s)   <br/> |在混合式設定中啟用同盟通訊。 Edge Server 需要知道如何路由傳送內部部署和線上間的 SIP 網域的同盟流量。  <br/> 必須使用使用者名稱和 SRV 記錄中網域的嚴格 DNS 名稱相符。  <br/> |
|DNS A 記錄 (s) Edge Web 會議服務 FQDN，例如 webcon.contoso.com 解析為 Web 會議 Edge 外部 IP (s)   <br/> |連線使用者電腦的內部公司網路  <br/> |讓線上使用者可以在內部部署主控會議中呈現或查看內容。 內容包括 PowerPoint 檔案、白板、投票和共用附注。  <br/> |

根據組織中設定 DNS 的方式，您可能需要將這些記錄新增至對應 SIP 網域的內部主控 DNS 區域， (s) 以提供對這些記錄的內部 DNS 解析。

### <a name="firewall-considerations-for-hybrid-deployments"></a>混合式部署的防火牆考慮

<a name="BKMK_Firewall"> </a>

網路上的電腦必須能夠執行標準網際網路 DNS 查閱。 若這些電腦可以搜尋標準網際網路網站，表示您的網路符合此需求。

根據您的 Microsoft 線上服務資料中心的位置，您也必須設定網路防火牆裝置，以接受以萬用字元功能變數名稱為基礎的連線 (例如，所有來自 \* outlook.com) 的流量。 如果您組織的防火牆不支援萬用字元名稱設定，您必須手動判斷您要允許的 IP 位址範圍和指定的埠。

如需詳細資訊，包括埠和通訊協定需求的詳細資訊，請參閱 [Microsoft 365 和 Office 365 URLs 及 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkId=252942)。
