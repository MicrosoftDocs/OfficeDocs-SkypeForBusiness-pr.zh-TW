---
title: Lync Server 2013： SIP trunk 的元件和拓撲
description: Lync Server 2013： SIP trunk 的元件和拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549519"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2112f-103">Lync Server 2013 中 SIP 主幹的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="2112f-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2112f-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2112f-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2112f-105">下圖描述 Lync Server 中的 SIP 主幹拓撲。</span><span class="sxs-lookup"><span data-stu-id="2112f-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="2112f-106">**SIP 主幹拓撲**</span><span class="sxs-lookup"><span data-stu-id="2112f-106">**SIP trunking topology**</span></span>

<span data-ttu-id="2112f-107">![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")</span><span class="sxs-lookup"><span data-stu-id="2112f-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="2112f-108">如圖所示，在商業網路和公用交換電話網路 (PSTN) 服務提供者之間的連線中，會使用 IP 虛擬私人網路 (VPN) 。</span><span class="sxs-lookup"><span data-stu-id="2112f-108">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="2112f-109">此私人網路的目的在於提供 IP 連線功能、增強安全性，以及 (選擇性) 取得服務品質 (QoS) 保證。</span><span class="sxs-lookup"><span data-stu-id="2112f-109">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="2112f-110">由於 VPN 的性質，您不需要使用傳輸層安全性 (TLS) 以進行 SIP 信號流量或安全即時傳輸通訊協定 (SRTP) 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="2112f-110">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="2112f-111">企業和服務提供者之間的連線是由 SIP 和即時即時傳輸通訊協定的純 TCP 連線所組成 (RTP)  (透過 UDP) 透過 IP VPN 傳送媒體隧道。</span><span class="sxs-lookup"><span data-stu-id="2112f-111">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="2112f-112">確定所有 VPN 路由器間的防火牆皆已開啟埠，以允許 VPN 路由器通訊，而且 VPN 路由器外部邊緣的 IP 位址可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="2112f-112">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2112f-113">請與您的服務提供者聯繫，以判斷其是否提供高可用性支援（包括容錯移轉）。</span><span class="sxs-lookup"><span data-stu-id="2112f-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="2112f-114">如果是的話，您將需要決定設定的程式。</span><span class="sxs-lookup"><span data-stu-id="2112f-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="2112f-115">例如，您只需要在每個轉送伺服器上設定一個 IP 位址和一個 SIP 主幹，還是需要在每個轉送伺服器上設定多個 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="2112f-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="2112f-116">如果您有多部中央網站，也請詢問服務提供者是否有能力啟用與其他中央網站之間的連線。</span><span class="sxs-lookup"><span data-stu-id="2112f-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2112f-117">若為 SIP 主幹，強烈建議您部署獨立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="2112f-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="2112f-118">如需詳細資訊，請參閱部署檔中的部署中繼 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">伺服器及定義 Lync Server 2013 中的對等</A> 專案。</span><span class="sxs-lookup"><span data-stu-id="2112f-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="2112f-119">保護 SIP 中繼的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="2112f-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="2112f-120">基於安全性的考慮，您應該為兩個 VPN 路由器間的每個連線設定虛擬 LAN (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="2112f-120">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="2112f-121">安裝 VLAN 的實際程式會因不同的路由器製造商而異。</span><span class="sxs-lookup"><span data-stu-id="2112f-121">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="2112f-122">如需詳細資訊，請與您的路由器廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="2112f-122">For details, contact your router vendor.</span></span>

<span data-ttu-id="2112f-123">建議您遵循這些方針：</span><span class="sxs-lookup"><span data-stu-id="2112f-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2112f-124">在周邊網路中的轉送伺服器和 VPN 路由器之間設定虛擬 LAN (VLAN)  (也稱為 DMZ、隔離區域和遮罩式子網) 。</span><span class="sxs-lookup"><span data-stu-id="2112f-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="2112f-125">不允許從路由器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2112f-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="2112f-126">封鎖將流量從路由器路由傳送至任何地方（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="2112f-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="2112f-127">如果您使用 VPN 伺服器，我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="2112f-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2112f-128">在 VPN 伺服器與轉送伺服器之間設定 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2112f-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="2112f-129">不允許從 VPN 伺服器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2112f-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="2112f-130">封鎖將 VPN 伺服器流量路由傳送至任何無所不在（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="2112f-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="2112f-131">使用一般路由封裝 (GRE) ，加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="2112f-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

