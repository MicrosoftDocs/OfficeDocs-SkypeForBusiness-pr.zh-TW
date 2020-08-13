---
title: Lync Server 2013 中型組織的參考拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10246ff2c6257376a0252cf2f9540007a1fc59ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>大中型組織中 Lync Server 2013 的參考拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

具有高可用性和單一資料中心的參考拓撲是專為具有一個中央網站的中小型組織所設計。 下圖中的實際拓撲是針對20000使用者的組織。

**中型組織的參考拓撲**

![單一資料中心圖表的參考拓撲](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "單一資料中心圖表的參考拓撲")

  - **新增多部前端伺服器以容納更多使用者。**    此圖中的實際拓撲有三部前端伺服器，可為20000使用者提供支援。 如果您有單一的中央網站和更多使用者，您只需要將多部前端伺服器新增至集區即可。 每個集區的使用者數目上限為80000，含十二部前端伺服器。
    
    不過，如果在網站再新增一個前端集區，則單一個網站拓撲可以支援更多使用者。

  - 可以**新增災難修復。**    針對此組織，其 Lync Server 服務的高可用性是必要的功能，但不會發生嚴重損壞修復。 其部署的前端伺服器集區提供高可用性。
    
    如果他們想要新增嚴重損壞復原能力，他們可能會考慮建立另一個資料中心，並在其中新增另一個前端集區，並將它與目前資料中心的前端集區配對。 然後，如果發生嚴重影響其主要集區的嚴重損壞，系統管理員可以將使用者容錯移轉至備份組區。

  - **後端伺服器已鏡像**    若要提供更高的基本使用者功能可用性，該組織已為每一個前端集區部署一組鏡像的後端伺服器。 這是 Lync Server 2013 的新拓撲選項，且是選用的。 您可以選擇改為部署單一後端伺服器。

  - **監控伺服器資料庫選項。**    此組織已部署監控，以確保 Enterprise Voice 通話的品質和 A/V 會議。 監控是部署于每一部前端伺服器上，而監視資料庫則是與後端伺服器組合。 我們也支援監控資料庫位於不同伺服器上的拓撲。

  - **Edge Server 高可用性**    在此範例中，有20000位使用者的組織，只有一部 Edge Server 足以獲得效能。 不過，已部署兩部 Edge Server 的集區以提供高可用性。

  - **分支網站部署選項。**    此拓撲中的組織已部署企業語音，成為其語音解決方案。 分支網站1沒有 Survivable WAN) 連結到中央網站的彈性廣域 (網路，因此它已部署分支裝置，以維護許多 Lync Server 功能，以防中央網站的 WAN 連結停止運作。 不過，分支網站 2 具有可恢復的 WAN 連結，因此只需要有公用交換電話網路 (PSTN) 閘道。 此網站部署的 PSTN 閘道支援媒體旁路，所以分支網站 2 不需要有中繼伺服器。 如需決定在分支網站上部署專案的詳細資訊，請參閱規劃檔中的[規劃 Lync Server 2013 中的 branch site voice 韌性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

  - **DNS 負載平衡。**    前端集區 andEdge 伺服器集區，具有部署 SIP 流量的 DNS 負載平衡。 如此一來，Edge Server 就不需要硬體負載平衡器，這樣可大幅減少為其他集區安裝和維護硬體負載平衡器的工作，因為只有 HTTP 流量才需要硬體負載平衡器。 如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

  - **Exchange UM 部署。** 此參考拓撲包含 Exchange 整合通訊 (UM) Server，它會執行 Microsoft Exchange Server，而不是 Lync Server。
    
    如需 Exchange UM 的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃 Exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[主控 Exchange 整合通訊2013整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps Server。** 建議您在使用 Web 會議的每家組織中部署 Office Web Apps Server 或 Office Web Apps Server 伺服器陣列。 Office Web Apps Server 可以在 Web 會議中呈現 Powerpoint 投影片。 如需詳細資訊，請參閱設定[Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **建議使用 Edge server。**    雖然不需要部署 Edge Server，但建議使用任何規模的部署。 您可以部署 Edge Server，將服務提供給目前組織防火牆以外的使用者，以達到最大的 Lync 伺服器投資。 優點包括下列各項：
    
      - 您組織的使用者可以使用 Lync Server 功能（如果他們在家中運作或是在旅途中外出）。
    
      - 您的使用者可以邀請外部使用者參與會議。
    
      - 如果您有也使用 Lync Server 的合作夥伴、廠商或客戶組織，您可以建立與該組織的同盟*關聯*。 然後，您的 Lync 伺服器部署會辨識來自該同盟組織的使用者，以改善合作。
    
      - 您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任何或所有專案： Windows Live、AOL、Yahoo \! 和 Google 交談。 使用這些服務的公用 IM 連線可能需要個別授權。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
        > <LI>
        > <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>

        
        </div>

  - **可以新增 director。**    如果此組織想要協助提高安全性以防範拒絕服務攻擊，也可以部署 Director 集區。 Director 是 Lync Server 中的個別非選用伺服器角色，不會家用使用者帳戶，也不會提供目前狀態或會議服務。 它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。 Director 對輸入要求進行預先驗證，並將它們重新導向至使用者的主集區或伺服器。 Director 的預先驗證可讓您從部署中未知的使用者帳戶中丟棄要求。 Director 可協助將前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。

  - **建議使用 System Center Operations Manager。**   建議您監視 Lync Server 部署的健康情況，以協助確保使用者的服務可用性。 您可以使用 Lync 的 System Center Operations Manager 管理元件（可免費從 Microsoft 下載）來監視 Lync。 透過 Lync 管理元件，您可以在發生問題時主動取得即時警示、執行綜合交易，以測試端對端的 Lync 功能、取得服務可用性的報告等等。 這可協助您在使用者體驗之前，主動回應部署的問題。

</div>

<span> </span>

</div>

</div>

</div>

