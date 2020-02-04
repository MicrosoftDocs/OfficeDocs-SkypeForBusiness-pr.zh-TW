---
title: 針對具有多個資料中心的大型組織提供的 Lync Server 2013 參考拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d9edde5ab097f3244919d6dd2c572b4a1dc112
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>具有多個資料中心的大型組織中的 Lync Server 2013 參考拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

具有多個資料中心支援的大型組織的參照拓撲，是針對有一個以上的中心網站的組織規模。 下圖中的確切拓撲是針對50000使用者的組織，在中央網站 A 上有20000個使用者，並在中央網站 B 進行20000，以及在中央網站 C 和分支網站上的10000總計。 此圖表中顯示的拓撲類型可容納擁有任何數量使用者的組織。

除了由前端伺服器池所提供的高可用性之外，此拓朴還新增災害復原支援。 中央站台 A 和 B 的前端池是成對搭配。 如果其中一個池出現停機，系統管理員可以將受影響之使用者的服務移至未受影響網站的配對池。

此拓朴會顯示在多個圖表中，並先進行概要，然後再按中央網站的詳細視圖。

**具有多個資料中心之大型組織的參照拓撲概覽**

![多個資料中心的參考拓撲](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "多個資料中心的參考拓撲")

**大型組織的參考拓撲：中央網站 A 的詳細視圖**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**大型組織的參考拓撲：中央網站 B 的詳細視圖**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**大型組織的參考拓撲：中央網站 C 的詳細視圖**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **前端池已配對以啟用災害復原。**   [網站 A] 和 [網站 B] 的前端池會彼此配對，以提供災害復原支援。 如果一個網站上的池發生故障，系統管理員可以將該網站的使用者容錯移轉到另一個網站上的成對的前端池，且使用者的服務中斷最低。 這兩個前端池中的每一個都有六個伺服器，對於在容錯移轉時，兩個池中的所有40000使用者都足夠。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **後端伺服器會鏡像**   ，以提供更高的基本使用者功能可用性，組織已為每個前端池部署一個鏡像對後端伺服器。 這是選擇性拓撲，您可以選擇部署單一後端伺服器。

  - **在分支網站使用標準版伺服器。**   此組織會將網站 C 視為分支網站，因為它只有600員工。 不過，使用者本身之間有許多 A/V 會議。 如果它是在 Lync Server 中部署為分支網站，這些會議的媒體將會跨廣域網路（WAN）執行，並從已部署前端伺服器的中央網站進行。 為了避免這種可能的頻寬載入，他們已在此網站上安裝一對標準版伺服器，這會主持這些會議。 而且因為標準版伺服器已安裝于其中，所以 Lync Server 依定義將它視為中央網站，而且在拓撲建立器和規劃工具中會被視為如此。
    
    只要有一個標準版伺服器的效能，就能達到此目的，但組織已將兩個和成對的專案部署在一起，以在一個伺服器停機時提供高可用性。
    
    雖然網站 C 被視為中心網站，但您不需要在其中部署邊緣伺服器。 在這個範例中，Site C 會使用在網站 A 部署的邊緣伺服器。

  - **監視及**   封存此組織已部署監視與封存。 當您部署監視或封存時，它會在每個前端伺服器上執行。 這些功能的資料庫可與後端資料庫 collocated，或位於另一個伺服器上。 此組織已將這些資料庫放在與後端伺服器（位於中央網站 B）之外的伺服器上。[資料庫] 中的資料庫會從所有網站中的前端伺服器接收監控及歸檔資料。

  - **分支網站部署選項。**   這個組織實際上有超過50個分支網站，其中只有三個會顯示在詳細圖表中。 分支網站1和3沒有指向中央網站的彈性 WAN 連結，因此他們已部署 Survivable 分支裝置來提供電話語音，以防 WAN 連結指向中央網站。 分支網站2不過有一個彈性 WAN 連結，因此您只需要一個公用的交換電話網絡（PSTN）閘道。 部署的 PSTN 閘道支援媒體旁路，因此分支網站 B 不需要任何轉送伺服器。如需決定要在分支網站上安裝哪些內容的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的企業語音復原規劃](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

  - **SIP 中繼和中繼伺服器。**   請注意，在中央網站 B，中繼伺服器無法與前端伺服器 collocated。 這是因為對於使用 SIP 中繼的網站，我們建議使用獨立的中繼伺服器。 在大多數其他情況下，我們建議您 collocate 中繼伺服器與前端伺服器。 如需有關中繼伺服器拓撲的詳細資料，請參閱規劃檔中的[Lync server 2013 中的中繼伺服器元件與拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。

  - **已部署持續聊天。**   此組織已部署啟用持續聊天所需的伺服器。 它已部署多個持續聊天前端伺服器，以處理池中的使用者數目的負荷，並提供高可用性。 它也已部署持續性聊天的相容性，並在個別的伺服器上，找到永久聊天存放區和持續交談合規性存放區。 這些存儲可以是 collocated，甚至可以與後端伺服器 collocated，但此組織已選擇將它們分開，以提供更佳的效能。

  - **DNS 負載平衡。**   [前端] 池和 [邊緣伺服器] 池。 這就消除了邊緣伺服器內部介面的硬體負載平衡器需求，而且大大減少了在設定和維護其他池之硬體負載平衡器（例如硬體載入）時所花費的時間量。平衡器僅在 HTTP 流量中需要。 如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

  - **Exchange UM 部署。**  Lync Server 可搭配 Exchange 整合訊息（UM）與*託管*Exchange UM 的*內部*部署部署使用。 中央網站 A 包含 Exchange 整合通訊（UM）伺服器，該伺服器會執行 Microsoft Exchange Server，而不是 Lync Server。 Lync Server 的 Exchange UM 功能會在前端池上執行。
    
    中央網站 B 使用託管 Exchange，因此也會託管 Exchange UM 伺服器功能。
    
    如需有關 Exchange UM 的詳細資訊，請參閱規劃檔中的 lync server [2013 中的 Exchange 整合訊息整合規劃](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)（ [lync server 2013 中的託管 exchange](lync-server-2013-hosted-exchange-unified-messaging-integration.md)整合訊息整合）。

  - **Office Web Apps 伺服器。**   我們建議您在使用 Web 會議的每一個組織中部署 Office Web Apps Server 或 Office Web Apps 伺服器群。 您可以在一個網站中部署單一的 Office Web Apps 伺服器群，以提供來自所有網站的流量，或在每個網站上部署。 Office Web Apps 伺服器可讓 Powerpoint 投影片呈現在網路會議中。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **您可以新增控制器。**  如果此組織想要加強抵禦拒絕服務攻擊的安全性，也可以部署一個控制器池。 Director 是 Lync Server 中不是家用使用者帳戶的個別、選擇性的伺服器角色，或提供目前狀態或會議服務。 它是一種內部的下一個躍點伺服器，可讓邊緣伺服器路由發往內部伺服器的入站 SIP 流量。 主管對輸入要求進行預驗證，並將它們重新導向至使用者的主區或伺服器。 在主管中進行預驗證，可在部署時丟棄使用者帳戶的要求。 控制器可協助將前端伺服器與惡意流量（例如拒絕服務（DoS）攻擊）隔離。 如果網路充斥在攻擊中的無效外部通信量，通信量就會結束在 Director 上。

  - **系統中心作業管理員已部署。**  我們建議您監視 Lync Server 部署的健康情況，以確保終端使用者的服務可用性。 您可以使用可從 Microsoft 免費下載的 Lync 系統中心作業管理員管理套件來監視 Lync。 在 Lync 管理套件中，您可以在發生問題時，主動取得即時通知、執行綜合交易，以測試端對端 Lync 功能、取得服務可用性的報告等。 這可協助您在最終使用者體驗到您的部署之前，提前回應您的部署問題。
    
    此組織已在每個中央網站中部署 System Center Operations Manager 伺服器。

</div>

<span> </span>

</div>

</div>

</div>

