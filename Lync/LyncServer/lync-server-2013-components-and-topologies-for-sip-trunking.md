---
title: Lync Server 2013：SIP 主幹連線的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d9bd8-102">Lync Server 2013 中的 SIP 主幹連線的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="d9bd8-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9bd8-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d9bd8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d9bd8-104">下圖描繪了 Lync Server 中的 SIP 中繼拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="d9bd8-105">**SIP 中繼拓撲**</span><span class="sxs-lookup"><span data-stu-id="d9bd8-105">**SIP trunking topology**</span></span>

<span data-ttu-id="d9bd8-106">![Sip 中繼拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 中繼拓撲")</span><span class="sxs-lookup"><span data-stu-id="d9bd8-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="d9bd8-107">如圖表中所示，IP 虛擬私人網路（VPN）是在商業網路與公用交換電話網絡（PSTN）服務提供者之間連線所使用。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-107">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="d9bd8-108">這個私人網路絡的用途是提供 IP 連線、加強安全性，以及（選擇）取得服務品質（QoS）保證。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-108">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="d9bd8-109">由於 VPN 的性質，您不需要針對媒體流量使用傳輸層安全性（TLS）來傳送 SIP 信號流量或安全即時傳輸通訊協定（SRTP）。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-109">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="d9bd8-110">企業與服務提供者之間的連線是由針對 SIP 的純 TCP 連線和純時間傳輸通訊協定（RTP）（透過 UDP），透過 IP VPN 傳送媒體隧道。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-110">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="d9bd8-111">確定 VPN 路由器之間的所有防火牆都已開啟埠，以允許 VPN 路由器進行通訊，以及 VPN 路由器外部邊緣的 IP 位址可公開路由。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-111">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9bd8-112">請與您的服務提供者聯繫，判斷它是否提供高可用性支援，包括容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="d9bd8-113">如果是這樣，您將需要判斷設定的程式。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="d9bd8-114">例如，您是否只需要在每個中繼伺服器上設定一個 IP 位址和一個 SIP 幹線，或者您是否需要在每個中繼伺服器上設定多個 SIP trunks？</span><span class="sxs-lookup"><span data-stu-id="d9bd8-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="d9bd8-115">如果您有多個中心網站，也會詢問服務提供者是否能夠啟用與其他中心網站的連線。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d9bd8-116">針對 SIP 中繼，我們強烈建議您部署獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="d9bd8-117">如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 中部署中繼伺服器和定義對等</A>。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="d9bd8-118">保護 SIP 中繼的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d9bd8-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="d9bd8-119">為安全起見，您應該針對兩個 VPN 路由器之間的每個連線設定虛擬 LAN （VLAN）。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-119">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="d9bd8-120">設定 VLAN 的實際處理常式會因路由器製造商而異。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-120">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="d9bd8-121">如需詳細資訊，請與您的路由器廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-121">For details, contact your router vendor.</span></span>

<span data-ttu-id="d9bd8-122">我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="d9bd8-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="d9bd8-123">在中繼伺服器與周邊網路中的 VPN 路由器（也稱為 DMZ、網路隔離區域及遮罩子網）之間設定虛擬 LAN （VLAN）。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="d9bd8-124">請勿允許將廣播或多播封包從路由器傳輸到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="d9bd8-125">封鎖任何路由規則，可將流量從路由器路由到任何位置，而不是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="d9bd8-126">如果您使用的是 VPN 伺服器，我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="d9bd8-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="d9bd8-127">在 VPN 伺服器與中繼伺服器之間設定 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="d9bd8-128">請勿允許從 VPN 伺服器傳送廣播或多播資料包至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="d9bd8-129">封鎖將 VPN 伺服器流量路由到任何位置的任何路由規則，而是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="d9bd8-130">使用一般路由封裝（GRE）來加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="d9bd8-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

