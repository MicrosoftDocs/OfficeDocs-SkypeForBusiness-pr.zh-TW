---
title: Lync Server 2013： SIP trunk 的元件和拓撲
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
ms.openlocfilehash: 08961982f382e5b5c670f6a1640884a4540a4c20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502490"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="60284-102">Lync Server 2013 中 SIP 主幹的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="60284-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60284-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="60284-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="60284-104">下圖描述 Lync Server 中的 SIP 主幹拓撲。</span><span class="sxs-lookup"><span data-stu-id="60284-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="60284-105">**SIP 主幹拓撲**</span><span class="sxs-lookup"><span data-stu-id="60284-105">**SIP trunking topology**</span></span>

<span data-ttu-id="60284-106">![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")</span><span class="sxs-lookup"><span data-stu-id="60284-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="60284-107">如圖所示，在商業網路和公用交換電話網路 (PSTN) 服務提供者之間的連線中，會使用 IP 虛擬私人網路 (VPN) 。</span><span class="sxs-lookup"><span data-stu-id="60284-107">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="60284-108">此私人網路的目的在於提供 IP 連線功能、增強安全性，以及 (選擇性) 取得服務品質 (QoS) 保證。</span><span class="sxs-lookup"><span data-stu-id="60284-108">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="60284-109">由於 VPN 的性質，您不需要使用傳輸層安全性 (TLS) 以進行 SIP 信號流量或安全即時傳輸通訊協定 (SRTP) 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="60284-109">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="60284-110">企業和服務提供者之間的連線是由 SIP 和即時即時傳輸通訊協定的純 TCP 連線所組成 (RTP)  (透過 UDP) 透過 IP VPN 傳送媒體隧道。</span><span class="sxs-lookup"><span data-stu-id="60284-110">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="60284-111">確定所有 VPN 路由器間的防火牆皆已開啟埠，以允許 VPN 路由器通訊，而且 VPN 路由器外部邊緣的 IP 位址可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="60284-111">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60284-112">請與您的服務提供者聯繫，以判斷其是否提供高可用性支援（包括容錯移轉）。</span><span class="sxs-lookup"><span data-stu-id="60284-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="60284-113">如果是的話，您將需要決定設定的程式。</span><span class="sxs-lookup"><span data-stu-id="60284-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="60284-114">例如，您只需要在每個轉送伺服器上設定一個 IP 位址和一個 SIP 主幹，還是需要在每個轉送伺服器上設定多個 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="60284-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="60284-115">如果您有多部中央網站，也請詢問服務提供者是否有能力啟用與其他中央網站之間的連線。</span><span class="sxs-lookup"><span data-stu-id="60284-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="60284-116">若為 SIP 主幹，強烈建議您部署獨立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="60284-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="60284-117">如需詳細資訊，請參閱部署檔中的部署中繼 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">伺服器及定義 Lync Server 2013 中的對等</A> 專案。</span><span class="sxs-lookup"><span data-stu-id="60284-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="60284-118">保護 SIP 中繼的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="60284-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="60284-119">基於安全性的考慮，您應該為兩個 VPN 路由器間的每個連線設定虛擬 LAN (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="60284-119">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="60284-120">安裝 VLAN 的實際程式會因不同的路由器製造商而異。</span><span class="sxs-lookup"><span data-stu-id="60284-120">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="60284-121">如需詳細資訊，請與您的路由器廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="60284-121">For details, contact your router vendor.</span></span>

<span data-ttu-id="60284-122">建議您遵循這些方針：</span><span class="sxs-lookup"><span data-stu-id="60284-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="60284-123">在周邊網路中的轉送伺服器和 VPN 路由器之間設定虛擬 LAN (VLAN)  (也稱為 DMZ、隔離區域和遮罩式子網) 。</span><span class="sxs-lookup"><span data-stu-id="60284-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="60284-124">不允許從路由器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="60284-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="60284-125">封鎖將流量從路由器路由傳送至任何地方（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="60284-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="60284-126">如果您使用 VPN 伺服器，我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="60284-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="60284-127">在 VPN 伺服器與轉送伺服器之間設定 VLAN。</span><span class="sxs-lookup"><span data-stu-id="60284-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="60284-128">不允許從 VPN 伺服器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="60284-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="60284-129">封鎖將 VPN 伺服器流量路由傳送至任何無所不在（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="60284-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="60284-130">使用一般路由封裝 (GRE) ，加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="60284-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

