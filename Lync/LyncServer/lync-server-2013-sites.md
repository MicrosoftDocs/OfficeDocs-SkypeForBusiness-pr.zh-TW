---
title: Lync Server 2013 網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7193d657ad1e585b1a82ba8e934e5bf99d83e65b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519610"
---
# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="ca33a-102">Lync Server 2013 的 lync Server 網站</span><span class="sxs-lookup"><span data-stu-id="ca33a-102">Lync Server sites for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca33a-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="ca33a-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="ca33a-104">在 Lync Server 中，您可以在網路上定義包含 Lync Server 元件的 *網站* 。</span><span class="sxs-lookup"><span data-stu-id="ca33a-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="ca33a-105">網站是以高速、低延遲網路來妥善連線的一組電腦，例如單一區域網路 (LAN) 或以高速光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="ca33a-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="ca33a-106">請注意，Lync Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的不同概念。</span><span class="sxs-lookup"><span data-stu-id="ca33a-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="ca33a-107">您的 Lync 伺服器網站不需要對應至您的 Active Directory 網站。</span><span class="sxs-lookup"><span data-stu-id="ca33a-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="ca33a-108">網站類型</span><span class="sxs-lookup"><span data-stu-id="ca33a-108">Site Types</span></span>

<span data-ttu-id="ca33a-109">每個網站都是 *中央網站*（包含至少一個前端集區或 Standard Edition server），或是一個 *分支網站*。</span><span class="sxs-lookup"><span data-stu-id="ca33a-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="ca33a-110">每個分支網站都會與剛好一個中央網站產生關聯，而且分支網站的使用者可以從關聯的中央網站的伺服器取得大多數的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ca33a-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="ca33a-111">每一個分支網站都包含下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ca33a-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="ca33a-112">\*Survivable Branch 裝置 (SBA) \*，也就是具有 Lync Server 註冊機構的工業標準刀片式伺服器，以及在 Windows server 上執行的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ca33a-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="ca33a-113">Survivable Branch 裝置也包含公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="ca33a-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="ca33a-114">Survivable 分支裝置專為25到1000使用者之間的分支網站而設計。</span><span class="sxs-lookup"><span data-stu-id="ca33a-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="ca33a-115">\*Survivable Branch Server (SBS) \*，也就是執行 Windows Server 符合指定硬體需求，且已安裝 Lync Server 註冊機構和轉送伺服器軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ca33a-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="ca33a-116">該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="ca33a-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ca33a-117">Survivable Branch 伺服器特別針對具有 1000 至 5000 位用者的分支網站所設計。</span><span class="sxs-lookup"><span data-stu-id="ca33a-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="ca33a-118">PSTN 閘道和「中繼伺服器」\*\*(選用)。</span><span class="sxs-lookup"><span data-stu-id="ca33a-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="ca33a-119">如需此伺服器及其他伺服器角色的詳細資訊，請參閱 [Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ca33a-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="ca33a-120">具有中央網站的可恢復廣域網路 (WAN) 連結的分公司可以使用第三個選項，也就是 PSTN 閘道和中繼伺服器 (選用)。</span><span class="sxs-lookup"><span data-stu-id="ca33a-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="ca33a-121">具有較低彈性連結的分支 office 網站應該使用 Survivable 分支裝置或 Survivable 分支伺服器，這會在廣域網路絡失敗時提供恢復功能。</span><span class="sxs-lookup"><span data-stu-id="ca33a-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="ca33a-122">例如，在已部署 Survivable Branch 裝置或 Survivable Branch 伺服器的網站中，如果將分支網站連接至中央網站的 WAN，使用者仍可撥打及接收企業語音通話。</span><span class="sxs-lookup"><span data-stu-id="ca33a-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="ca33a-123">如需 Survivable 分支裝置、Survivable 分支伺服器及恢復功能的詳細資訊，請參閱規劃檔中的 [規劃 Lync server 2013 中的 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 。</span><span class="sxs-lookup"><span data-stu-id="ca33a-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="ca33a-124">網站拓撲</span><span class="sxs-lookup"><span data-stu-id="ca33a-124">Site Topologies</span></span>

<span data-ttu-id="ca33a-125">您的部署必須包含至少一個中央網站，並可以包含零到多個分支網站。</span><span class="sxs-lookup"><span data-stu-id="ca33a-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="ca33a-126">每一個分支網站均隸屬於一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="ca33a-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="ca33a-127">中央網站向分支網站提供 Lync Server 服務，該網站不會在分支網站上的本機主控，例如目前狀態和會議。</span><span class="sxs-lookup"><span data-stu-id="ca33a-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="ca33a-128">如果您有多個網站，您可以將不同網站的前端集區配對在一起，以啟用嚴重損壞修復功能。</span><span class="sxs-lookup"><span data-stu-id="ca33a-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="ca33a-129">如需詳細資訊，請參閱 [Lync Server 2013 中的高可用性和嚴重損壞修復支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)。</span><span class="sxs-lookup"><span data-stu-id="ca33a-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca33a-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ca33a-130">See Also</span></span>


[<span data-ttu-id="ca33a-131">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="ca33a-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="ca33a-132">Lync Server 2013 的高可用性和嚴重損壞修復支援</span><span class="sxs-lookup"><span data-stu-id="ca33a-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="ca33a-133">在 Lync Server 2013 中規劃 Enterprise Voice 韌性</span><span class="sxs-lookup"><span data-stu-id="ca33a-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

