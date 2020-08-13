---
title: Lync Server 2013 負載平衡需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54e1e8e130374e296d18680cf5d82001e55b68af
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="e6669-102">Lync Server 2013 的負載平衡需求</span><span class="sxs-lookup"><span data-stu-id="e6669-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6669-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e6669-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e6669-104">如果您有前端集區、Director 集區或 Edge Server 集區，則需要為這些集區部署負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="e6669-105">負載平衡會在集區中的伺服器之間分散流量。</span><span class="sxs-lookup"><span data-stu-id="e6669-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="e6669-106">Lync Server 2013 支援用戶端對伺服器流量的兩種負載平衡解決方案：網域名稱系統 (DNS) 負載平衡與硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="e6669-107">DNS 負載平衡提供數種優點，包括簡化管理、更有效率的疑難排解，以及隔離任何可能的「Lync Server」流量以避免任何可能的硬體負載平衡器問題的功能。</span><span class="sxs-lookup"><span data-stu-id="e6669-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="e6669-108">決定哪一種負載平衡解決方案適合您部署中的每個集區，請記住下列限制：</span><span class="sxs-lookup"><span data-stu-id="e6669-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="e6669-109">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-109">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="e6669-110">您無法在一個介面上使用 DNS 負載平衡，另一個在另一個介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-110">You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="e6669-111">某些類型的流量需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="e6669-111">Some types of traffic require a hardware load balancer.</span></span> <span data-ttu-id="e6669-112">例如，HTTP 流量需要硬體負載平衡器，而不是使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-112">For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing.</span></span> <span data-ttu-id="e6669-113">DNS 負載平衡無法搭配用戶端對伺服器的 web 流量使用。</span><span class="sxs-lookup"><span data-stu-id="e6669-113">DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="e6669-114">如需選擇硬體負載平衡器解決方案的詳細資訊，請參閱[Lync Server 2013 的硬體負載平衡器需求](lync-server-2013-hardware-load-balancer-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6669-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="e6669-115">如果您選擇針對集區使用 DNS 負載平衡，但仍需要針對流量（例如 HTTP 流量）執行硬體負載平衡器，則可大幅簡化硬體負載平衡器的管理。</span><span class="sxs-lookup"><span data-stu-id="e6669-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="e6669-116">例如，設定硬體負載平衡器會變得更簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都會透過 DNS 負載平衡來管理。</span><span class="sxs-lookup"><span data-stu-id="e6669-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="e6669-117">如需詳細資訊，請參閱[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="e6669-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="e6669-118">針對伺服器對伺服器流量，Lync Server 2013 使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="e6669-119">伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="e6669-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="e6669-120">管理員不需要設定或管理這種類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e6669-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="e6669-121">如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="e6669-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="e6669-122">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="e6669-122">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

