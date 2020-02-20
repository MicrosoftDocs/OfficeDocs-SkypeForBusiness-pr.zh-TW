---
title: Lync Server 2013： 元件和的 SIP 主幹拓撲
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
ms.openlocfilehash: b81768fe055c28fb8643a267b74de4cc99bc0ff3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2d2e4-102">Lync Server 2013 中的 SIP 主幹的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="2d2e4-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d2e4-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="2d2e4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2d2e4-104">下圖說明 Lync Server 中的 SIP 主幹拓撲。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="2d2e4-105">**SIP 主幹拓撲**</span><span class="sxs-lookup"><span data-stu-id="2d2e4-105">**SIP trunking topology**</span></span>

<span data-ttu-id="2d2e4-106">![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")</span><span class="sxs-lookup"><span data-stu-id="2d2e4-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="2d2e4-107">如圖所示，IP 虛擬私人網路 (VPN) 適用於企業網路與公用交換的電話網路 (PSTN) 服務提供者之間的連線。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-107">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="2d2e4-108">此私人網路的用途是提供 IP 連線、 增強的安全性，以及 （選擇性） 取得服務品質 (QoS) 保證。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-108">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="2d2e4-109">VPN 的性質，因為您不需要使用傳輸層安全性 (TLS) 的 SIP 訊號流量或媒體流量的安全即時傳輸通訊協定 (SRTP)。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-109">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="2d2e4-110">企業與服務提供者之間的連線因此所組成的 SIP 和一般即時傳輸通訊協定 (RTP) （透過 UDP) 的通道透過 IP VPN 的媒體的純文字 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-110">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="2d2e4-111">請確定 VPN 路由器之間的所有防火牆都已開啟以允許 VPN 路由器，以進行通訊，連接埠和 IP 位址，在 [外部邊緣的 VPN 路由器上是可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-111">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d2e4-112">請連絡您的服務提供者，來判斷是否它提供支援的高可用性，包括容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="2d2e4-113">如果是的話，您必須決定及其設定的程序。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="2d2e4-114">例如，您需要在每個中繼伺服器上，設定只有一個 IP 位址和一個 SIP 主幹或您需要在每一部中繼伺服器上設定多個 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="2d2e4-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="2d2e4-115">如果您有多個中央網站，也請詢問服務提供者是否有能力啟用連線到及傳送自另一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2d2e4-116">SIP 主幹，我們強烈建議您部署獨立中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="2d2e4-117">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Lync Server 2013 中的定義同儕</A>。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="2d2e4-118">SIP 主幹保護中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="2d2e4-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="2d2e4-119">基於安全性考量，您應該設定設定虛擬 LAN (VLAN) 的每個連接兩個 VPN 路由器之間。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-119">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="2d2e4-120">實際的程序設定 VLAN 因一個路由器製造商的不同而異。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-120">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="2d2e4-121">如需詳細資訊，請連絡您的路由器供應商。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-121">For details, contact your router vendor.</span></span>

<span data-ttu-id="2d2e4-122">建議您遵循這些方針：</span><span class="sxs-lookup"><span data-stu-id="2d2e4-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2d2e4-123">設定設定虛擬 LAN (VLAN) 之間中繼伺服器和 VPN 路由器在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="2d2e4-124">不允許將廣播或多點傳送封包從路由器傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="2d2e4-125">封鎖任何從路由器 anywhere 的流量路由傳送的路由規則，但中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="2d2e4-126">如果您使用 VPN 伺服器，建議您遵循以下指導方針：</span><span class="sxs-lookup"><span data-stu-id="2d2e4-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2d2e4-127">設定 VPN 伺服器和中繼伺服器之間 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="2d2e4-128">不允許將廣播或多點傳送封包從 VPN 伺服器傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="2d2e4-129">封鎖任何將 VPN 伺服器流量路由傳送至任何位置的路由規則，但中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="2d2e4-130">藉由使用 generic routing encapsulation (GRE) 加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="2d2e4-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

