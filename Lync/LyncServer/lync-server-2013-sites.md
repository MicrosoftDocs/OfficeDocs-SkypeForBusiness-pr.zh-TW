---
title: Lync Server 2013 網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="4e122-102">Lync Server 2013 的 Lync Server 網站</span><span class="sxs-lookup"><span data-stu-id="4e122-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e122-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4e122-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4e122-104">在 Lync Server 中，您會在網路上定義包含 Lync Server 元件的*網站*。</span><span class="sxs-lookup"><span data-stu-id="4e122-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="4e122-105">網站是一組由高速、低延遲網路連接的電腦，例如單一局域網（LAN），或由高速光纖光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="4e122-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="4e122-106">請注意，Lync Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的個別概念。</span><span class="sxs-lookup"><span data-stu-id="4e122-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="4e122-107">您的 Lync Server 網站不需要與 Active Directory 網站相對應。</span><span class="sxs-lookup"><span data-stu-id="4e122-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="4e122-108">網站類型</span><span class="sxs-lookup"><span data-stu-id="4e122-108">Site Types</span></span>

<span data-ttu-id="4e122-109">每個網站都是*中央網站*，其中包含至少一個前端池或標準版伺服器，或*分支網站*。</span><span class="sxs-lookup"><span data-stu-id="4e122-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="4e122-110">每個分支網站都只會與一個中心網站建立關聯，而分支網站上的使用者就能從關聯的中央網站從伺服器取得大多數的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="4e122-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="4e122-111">每個分支網站都包含下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4e122-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="4e122-112">*Survivable 分支裝置（SBA）* 是一種工業標準刀片伺服器，其中包含 Lync Server 註冊機構，以及在 Windows server 上執行的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="4e122-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="4e122-113">Survivable 分支裝置也包含公用的交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="4e122-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="4e122-114">Survivable 分支裝置專為25與1000使用者之間的分支網站而設計。</span><span class="sxs-lookup"><span data-stu-id="4e122-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="4e122-115">*Survivable 分支伺服器（SBS）* 是一種執行 Windows Server 且符合指定硬體需求的伺服器，且已在其中安裝 Lync Server 註冊機構和轉送伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="4e122-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="4e122-116">它必須連線至 PSTN 閘道或 SIP 幹線給電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="4e122-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="4e122-117">Survivable 分支伺服器是針對1000與5000使用者之間的分支網站而設計。</span><span class="sxs-lookup"><span data-stu-id="4e122-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="4e122-118">PSTN 閘道，也可以選擇使用*中繼伺服器*。</span><span class="sxs-lookup"><span data-stu-id="4e122-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="4e122-119">如需此與其他伺服器角色的詳細資料，請參閱[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4e122-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="4e122-120">有彈性廣域網路（WAN）連結至中心網站的分支機搆可以使用第三個選項： PSTN 閘道，以及其他中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="4e122-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="4e122-121">具有較低彈性連結的分支機搆網站應該使用 Survivable 分支裝置或 Survivable 分支伺服器，這會提供廣域網路絡故障的復原時間。</span><span class="sxs-lookup"><span data-stu-id="4e122-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="4e122-122">例如，在已部署 Survivable 分支裝置或 Survivable 分支伺服器的網站中，如果將分支網站連接至中心網站的 WAN，使用者仍然可以撥打及接聽企業語音通話。</span><span class="sxs-lookup"><span data-stu-id="4e122-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="4e122-123">如需 Survivable 分支裝置的詳細資料，請 Survivable [分支伺服器] 和 [復原]，請參閱規劃檔中的[Lync server 2013 規劃企業語音復原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="4e122-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="4e122-124">網站拓撲</span><span class="sxs-lookup"><span data-stu-id="4e122-124">Site Topologies</span></span>

<span data-ttu-id="4e122-125">您的部署必須包含至少一個中央網站，而且可以包含零到多個分支網站。</span><span class="sxs-lookup"><span data-stu-id="4e122-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="4e122-126">每個分支網站都隸屬于一個中心網站。</span><span class="sxs-lookup"><span data-stu-id="4e122-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="4e122-127">中央網站將 Lync Server services 提供給分支網站，而該網站不是在本機主機（例如目前狀態與會議）中託管。</span><span class="sxs-lookup"><span data-stu-id="4e122-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="4e122-128">如果您有多個網站，您可以將前端池放在不同的網站，以啟用災害復原能力。</span><span class="sxs-lookup"><span data-stu-id="4e122-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="4e122-129">如需詳細資訊，請參閱[Lync Server 2013 中的高可用性與災害復原支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)。</span><span class="sxs-lookup"><span data-stu-id="4e122-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e122-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="4e122-130">See Also</span></span>


[<span data-ttu-id="4e122-131">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="4e122-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="4e122-132">Lync Server 2013 中的高可用性和災害復原支援</span><span class="sxs-lookup"><span data-stu-id="4e122-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="4e122-133">在 Lync Server 2013 中規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="4e122-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

