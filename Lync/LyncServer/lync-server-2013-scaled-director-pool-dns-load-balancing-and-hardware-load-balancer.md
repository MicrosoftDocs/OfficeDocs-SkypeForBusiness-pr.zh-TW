---
title: 調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc2d23fb2dac39ed568fb4aab6ab49f9e6213cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="ee0f2-102">調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee0f2-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee0f2-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="ee0f2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ee0f2-104">調整式的 Director 集區，其中有一個以上的 Director 部署處理更大的容量，並提供高可用性，需要負載平衡來發佈至的集區的所有成員的用戶端和伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="ee0f2-105">Director 主機 web 服務非常類似的前端集區。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="ee0f2-106">若要提供負載平衡，您可以使用任一硬體負載平衡或網域名稱系統 (DNS) 負載平衡與硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="ee0f2-107">硬體負載平衡需要的 web 服務，且 DNS 負載平衡單獨不提供的 web 服務所需的功能。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="ee0f2-108">下列主題說明部署 Director 集區使用 DNS 負載平衡搭配硬體負載平衡的規劃考量。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="ee0f2-109">如果您想要使用硬體負載平衡，但不是 DNS 負載平衡 Director 集區，請參閱[調整式 Director 集區-硬體負載平衡器 Lync Server 2013 中](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)的主題會說明該拓撲的規劃需求。</span><span class="sxs-lookup"><span data-stu-id="ee0f2-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="ee0f2-110">![調整式 Director 集區](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "調整式 Director 集區")</span><span class="sxs-lookup"><span data-stu-id="ee0f2-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee0f2-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ee0f2-111">In This Section</span></span>

  - [<span data-ttu-id="ee0f2-112">憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="ee0f2-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="ee0f2-113">Lync Server 2013 中的連接埠摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="ee0f2-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="ee0f2-114">Lync Server 2013 中的 DNS 摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="ee0f2-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

