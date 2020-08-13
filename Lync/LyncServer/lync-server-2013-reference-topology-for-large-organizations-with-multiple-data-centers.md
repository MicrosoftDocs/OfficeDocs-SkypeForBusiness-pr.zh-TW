---
title: 具有多個資料中心的大型組織的 Lync Server 2013 參考拓撲
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
ms.openlocfilehash: a596276361183bc31b2503aceacb064f1f45ec1f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>具有多個資料中心的大型組織中的 Lync Server 2013 參考拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

具有多個資料中心支援之大型組織的參考拓撲，適用于具有多部中央網站的組織規模。 下圖中的實際拓撲是針對50000使用者的組織，其中的20000使用者在中央網站 A，20000位於中央網站 B。中央網站 C 和分支網站上的總10000。 此圖表所顯示的拓撲類型可容納具有任意數目使用者的組織。

除了前端伺服器集區所提供的高可用性之外，此拓撲還會新增嚴重損壞修復支援。 中央網站 A 和 B 的前端集區會成對搭配。 如果其中一個集區中斷，系統管理員可以將受影響使用者的服務移至未受影響之網站的配對集區。

這種拓撲會顯示在多個圖表中，並優先于中央網站的詳細視圖。

**具有多個資料中心之大型組織的參考拓撲概述**

![多個資料中心的參考拓撲](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "多個資料中心的參考拓撲")

**大型組織的參考拓撲：中央網站 A 的詳細視圖**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**大型組織的參考拓撲：中央網站 B 的詳細視圖**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**大型組織的參考拓撲：中央網站 C 的詳細視圖**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **前端集區配對以啟用嚴重損壞修復。**    網站 A 和網站 B 的前端集區彼此配對，以提供嚴重損壞修復支援。 如果某個網站上的集區失敗，系統管理員可以從該網站將使用者容錯移轉至另一個網站的配對前端集區，並為使用者最低的服務中斷。 這兩個前端集區共有六部伺服器，也足以用於兩個集區中的所有40000使用者，以防容錯移轉。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **後端伺服器已鏡像**    若要提供更高的基本使用者功能可用性，該組織已為每一個前端集區部署一組鏡像的後端伺服器。 這是選用的拓撲，而您可以選擇部署單一後端伺服器。

  - **在分支網站上使用 Standard Edition server。**    此組織會將網站 C 視為分支網站，因為它只有600名員工。 不過，使用者彼此之間有許多 A/V 會議。 如果它是部署在 Lync Server 中作為分支網站，則這些會議的媒體會在廣域網路絡上執行 (WAN) 與已部署前端伺服器的中央網站。 為了避免這種可能的頻寬負載，使用者已在此網站上安裝一對 Standard Edition 伺服器，這會主控這些會議。 而且由於已安裝 Standard Edition server，依定義的 Lync Server 會將它視為中央網站，而拓撲產生器和規劃工具會將其視為類似。
    
    在這裡，只要一部 Standard Edition server 會有足夠的效能，但是該組織已部署兩個搭配搭配，以提供高可用性，以防一部伺服器宕機。
    
    雖然網站 C 被視為中央網站，但您不需要在此部署 Edge Server。 在此範例中，Site C 會使用部署于網站 A 的 Edge Server。

  - **監視與**     封存此組織已同時部署監控與封存。 當您部署監控或封存時，它會在每一部前端伺服器上執行。 這些功能的資料庫可以與後端資料庫組合，也可以位於不同的伺服器上。 此組織已將這些資料庫放在與後端伺服器不同的伺服器上（位於中央網站 B）。資料庫這裡會從所有網站中的前端伺服器接收監控和封存資料。

  - **分支網站部署選項。**    此組織實際上具有超過50個分支網站，詳細資訊圖中只顯示三個分支網站。 分支網站1和3不具備中央網站的彈性 WAN 連結，因此他們已部署 Survivable 分支裝置以提供電話語音，以防中央網站的 WAN 連結停止使用。 分支網站2不過具有彈性 WAN 連結，所以您只需要公用交換電話網路 (PSTN) 閘道。 部署的 PSTN 閘道支援媒體旁路，所以分支網站 B 不需要轉送伺服器。如需決定在分支網站安裝之專案的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 。

  - **SIP 主幹和轉送伺服器。**    請注意，在中央網站 B 上，轉送伺服器不會與前端伺服器組合。 這是因為針對使用 SIP 主幹的網站，建議使用獨立的轉送伺服器。 在其他大多數的情況下，我們建議您組合轉送伺服器與前端伺服器。 如需有關轉送伺服器拓撲的詳細資訊，請參閱規劃檔中的 Lync Server 2013 中的「中繼」 [伺服器元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md) 。

  - **部署持續性聊天。**    此組織已部署啟用持續性聊天所需的伺服器。 它已部署多個持續性聊天前端伺服器來處理集區中使用者數目的負載，並提供高可用性。 它也部署了持續性聊天的相容性，並已在不同的伺服器上找到 Persistent chat Store 和 Persistent Chat 規範存放區。 這些存放區可能是組合，甚至可以與後端伺服器組合，但這項組織已選擇將其分開，以提供更好的效能。

  - **DNS 負載平衡。**    前端集區和 Edge Server 集區，。 這樣就不需要對 Edge Server 的內部介面進行硬體負載平衡器，也能大幅減少對其他集區的硬體負載平衡器進行設定與維護所需花費的時間，因為只有 HTTP 流量需要硬體負載平衡器。 如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。

  - **EXCHANGE UM 部署。**   Lync Server 搭配 Exchange 整合通訊 (UM) 和*主控*exchange UM 的*內部*部署使用。 中央網站 A 包含 Exchange 整合通訊 (UM) Server，它會執行 Microsoft Exchange Server，而不是 Lync Server。 Lync Server 的 Exchange UM 功能會在前端集區上執行。
    
    中央網站 B 使用託管 Exchange，因此也會主控 Exchange UM 伺服器功能。
    
    如需 Exchange UM 的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃 Exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [主控 Exchange 整合通訊2013整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。

  - **Office Web Apps Server。**   建議您在使用 Web 會議的每家組織中部署 Office Web Apps Server 或 Office Web Apps Server 伺服器陣列。 您可以在一個網站中部署單一的 Office Web Apps Server 伺服器陣列，以便從所有網站提供流量，或是在每個網站中部署。 Office Web Apps Server 可以在 Web 會議中呈現 Powerpoint 投影片。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **可以新增 director。**   如果此組織想要提高安全性以防範拒絕服務攻擊，也可以部署 Director 集區。 Director 是 Lync Server 中的個別非選用伺服器角色，不會家用使用者帳戶，也不會提供目前狀態或會議服務。 它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。 Director 對輸入要求進行預先驗證，並將它們重新導向至使用者的主集區或伺服器。 Director 的預先驗證可讓您從部署中未知的使用者帳戶中丟棄要求。 Director 可協助將前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。

  - **已部署 System Center Operations Manager。**   建議您監視 Lync Server 部署的健康情況，以確保使用者的服務可用性。 您可以使用 Lync 的 System Center Operations Manager 管理元件（可免費從 Microsoft 下載）來監視 Lync。 透過 Lync 管理元件，您可以在發生問題時主動取得即時警示、執行綜合交易，以測試端對端的 Lync 功能、取得服務可用性的報告等等。 這可協助您在使用者體驗之前，主動回應部署的問題。
    
    此組織已在每個中央網站中部署 System Center Operations Manager 伺服器。

</div>

<span> </span>

</div>

</div>

</div>

