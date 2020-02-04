---
title: Lync Server 2013 適用於中型組織的參考拓樸
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
ms.openlocfilehash: da4c29107a6ca3d33e76708be9eec07297eeaf93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>中型組織內 Lync Server 2013 的參考拓樸

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

具有高可用性與單一資料中心的參照拓撲是專為具有單一中心網站的中小型組織設計。 下圖中的確切拓撲是針對20000使用者的組織。

**中型組織的參考拓撲**

![單一資料中心圖表的參考拓撲](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "單一資料中心圖表的參考拓撲")

  - **新增更多前端伺服器以容納更多使用者。**   此圖中的確切拓撲包含三個前端伺服器來提供20000使用者的支援。 如果您有單一的中央網站及更多使用者，您可以直接在池中新增更多前端伺服器。 每個池的使用者數目上限為80000，且有十二個前端伺服器。
    
    不過，單一網站拓朴可將另一個 [前端] 池新增至網站，以支援更多使用者。

  - **您可以新增災害復原。**   針對此組織，其 Lync Server 服務的高可用性是必要的功能，但不需要災害復原。 其部署的前端伺服器池可提供高可用性。
    
    如果他們想要新增災害復原能力，他們可以考慮建立另一個資料中心，並在其中新增另一個 [前端] 池，並將它與目前資料中心的前端池配對。 然後，如果發生影響其主要池的災難，系統管理員可能會將使用者容錯移轉至備份池。

  - **後端伺服器會鏡像**   ，以提供更高的基本使用者功能可用性，組織已為每個前端池部署一個鏡像對後端伺服器。 這是 Lync Server 2013 的新拓撲選項，且是選擇性的。 您可以改為選擇部署單一後端伺服器。

  - **監視伺服器資料庫選項。**   此組織已部署監控，以確保企業語音通話品質及 A/V 會議品質。 監視是在每個前端伺服器上部署，而監視資料庫則與後端伺服器 collocated。 我們也支援監視資料庫位於個別伺服器上的拓撲。

  - **Edge 伺服器高可用性**    在這個範例組織中，有20000個使用者，只要有一個 Edge 伺服器就足以達到效能。 不過，已部署兩個 Edge 伺服器的池中，以提供高可用性。

  - **分支網站部署選項。**   此拓撲中的組織已將企業語音部署為其語音方案。 分支網站1沒有可復原的廣域網路（WAN）連結至中心網站，所以它擁有已部署來維護許多 Lync Server 功能的 Survivable 分支裝置，以便在指向中央網站的 WAN 連結關閉時使用。 分支網站2不過有彈性 WAN 連結，所以只需要公開的交換式電話網絡（PSTN）閘道。 部署的 PSTN 閘道支援媒體旁路，因此分支網站2不需要任何轉送伺服器。 如需決定要在分支網站上部署的內容的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

  - **DNS 負載平衡。**   前端池 andEdge 伺服器池，具有部署 SIP 流量的 DNS 負載平衡。 這消除了邊緣伺服器的硬體負載平衡器需求，並大大減少了其他池的硬體負載平衡器的設定和維護，因為只有 HTTP 流量需要硬體負載平衡器。 如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

  - **Exchange UM 部署。** 這個參照拓撲包含 Exchange 整合通訊（UM）伺服器，該伺服器會執行 Microsoft Exchange Server，而不是 Lync Server。
    
    如需有關 Exchange UM 的詳細資訊，請參閱規劃檔中的 lync server [2013 中的 Exchange 整合訊息整合規劃](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)（ [lync server 2013 中的託管 exchange](lync-server-2013-hosted-exchange-unified-messaging-integration.md)整合訊息整合）。

  - **Office Web Apps 伺服器。** 我們建議您在使用 Web 會議的每一個組織中部署 Office Web Apps Server 或 Office Web Apps 伺服器群。 Office Web Apps 伺服器可讓 Powerpoint 投影片呈現在網路會議中。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **建議使用 Edge 伺服器。**   雖然不需要部署 Edge 伺服器，但我們建議將它用於任何部署大小。 您可以部署 Edge 伺服器來將您的 Lync 伺服器投資最大化，為目前組織防火牆以外的使用者提供服務。 其優點包括下列各項：
    
      - 貴組織的使用者可以使用 Lync Server 的功能（如果他們在家中或在路上）。
    
      - 您的使用者可以邀請外部使用者參與會議。
    
      - 如果您有合作夥伴、廠商或客戶組織，且使用 Lync Server，您可以建立與該組織的*聯盟關聯*。 接著，您的 Lync Server 部署會辨識來自該同盟組織的使用者，以更好的方式共同作業。
    
      - 您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任一或所有專案： Windows Live、AOL、Yahoo\!和 Google 交談。 您可能需要使用這些服務的公用 IM 連線的個別授權。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
        > <LI>
        > <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>

        
        </div>

  - **您可以新增控制器。**   如果此組織想要協助加強抵禦拒絕服務攻擊的安全性，也可以部署一個控制器池。 Director 是 Lync Server 中不是家用使用者帳戶的個別、選擇性的伺服器角色，或提供目前狀態或會議服務。 它是一種內部的下一個躍點伺服器，可讓邊緣伺服器路由發往內部伺服器的入站 SIP 流量。 主管對輸入要求進行預驗證，並將它們重新導向至使用者的主區或伺服器。 在主管中進行預驗證，可在部署時丟棄使用者帳戶的要求。 控制器可協助將前端伺服器與惡意流量（例如拒絕服務（DoS）攻擊）隔離。 如果網路充斥在攻擊中的無效外部通信量，通信量就會結束在 Director 上。

  - **建議使用 System Center Operations Manager。**  我們建議您監視 Lync Server 部署的健康情況，以協助確保終端使用者的服務可用性。 您可以使用可從 Microsoft 免費下載的 Lync 系統中心作業管理員管理套件來監視 Lync。 在 Lync 管理套件中，您可以在發生問題時，主動取得即時通知、執行綜合交易，以測試端對端 Lync 功能、取得服務可用性的報告等。 這可協助您在最終使用者體驗到您的部署之前，提前回應您的部署問題。

</div>

<span> </span>

</div>

</div>

</div>

