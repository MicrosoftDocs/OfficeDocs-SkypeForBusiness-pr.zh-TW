---
title: Lync Server 2013 負載平衡需求
description: Lync Server 2013 負載平衡需求。
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
ms.openlocfilehash: a768b2cbfe444e6915c932835d3cc2abaf6a98c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550029"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="8a321-103">Lync Server 2013 的負載平衡需求</span><span class="sxs-lookup"><span data-stu-id="8a321-103">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a321-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8a321-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8a321-105">如果您有前端集區、Director 集區或 Edge Server 集區，則需要為這些集區部署負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-105">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="8a321-106">負載平衡會在集區中的伺服器之間分散流量。</span><span class="sxs-lookup"><span data-stu-id="8a321-106">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="8a321-107">Lync Server 2013 支援用戶端對伺服器流量的兩種負載平衡解決方案：網域名稱系統 (DNS) 負載平衡與硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-107">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="8a321-108">DNS 負載平衡提供數種優點，包括簡化管理、更有效率的疑難排解，以及隔離任何可能的「Lync Server」流量以避免任何可能的硬體負載平衡器問題的功能。</span><span class="sxs-lookup"><span data-stu-id="8a321-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="8a321-109">決定哪一種負載平衡解決方案適合您部署中的每個集區，請記住下列限制：</span><span class="sxs-lookup"><span data-stu-id="8a321-109">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="8a321-110">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-110">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="8a321-111">您無法在一個介面上使用 DNS 負載平衡，另一個在另一個介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-111">You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="8a321-112">某些類型的流量需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="8a321-112">Some types of traffic require a hardware load balancer.</span></span> <span data-ttu-id="8a321-113">例如，HTTP 流量需要硬體負載平衡器，而不是使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-113">For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing.</span></span> <span data-ttu-id="8a321-114">DNS 負載平衡無法搭配用戶端對伺服器的 web 流量使用。</span><span class="sxs-lookup"><span data-stu-id="8a321-114">DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="8a321-115">如需選擇硬體負載平衡器解決方案的詳細資訊，請參閱 [Lync Server 2013 的硬體負載平衡器需求](lync-server-2013-hardware-load-balancer-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a321-115">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="8a321-116">如果您選擇針對集區使用 DNS 負載平衡，但仍需要針對流量（例如 HTTP 流量）執行硬體負載平衡器，則可大幅簡化硬體負載平衡器的管理。</span><span class="sxs-lookup"><span data-stu-id="8a321-116">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="8a321-117">例如，設定硬體負載平衡器會變得更簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都會透過 DNS 負載平衡來管理。</span><span class="sxs-lookup"><span data-stu-id="8a321-117">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="8a321-118">如需詳細資訊，請參閱 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="8a321-118">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="8a321-119">針對伺服器對伺服器流量，Lync Server 2013 使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-119">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="8a321-120">伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="8a321-120">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="8a321-121">管理員不需要設定或管理這種類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8a321-121">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="8a321-122">如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="8a321-122">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="8a321-123">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="8a321-123">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

