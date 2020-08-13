---
title: Lync Server 2013：設計 E9-1-1 的 SIP 主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="c454f-102">在 Lync Server 2013 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="c454f-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c454f-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c454f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c454f-104">Lync Server 使用 SIP 主幹將緊急通話連接至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="c454f-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="c454f-105">您可以在一個中央網台、多個中央網台或每個分支網站上設定 E9-1-1 的緊急服務 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="c454f-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="c454f-106">不過，如果來電者網站與主控緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，由中斷連線網站上的使用者所撥打的電話在使用者語音原則中，需要有特殊的電話使用方式記錄來指定透過本機公用交換電話網路 (PSTN) 閘道，將電話路由至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="c454f-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="c454f-107">如果通話許可控制並行通話限制有效，則有同樣的需求。</span><span class="sxs-lookup"><span data-stu-id="c454f-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c454f-108">在 Lync Server 環境中執行 SIP 主幹的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="c454f-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c454f-109">使用多宿主的轉送伺服器，利用其向外公開路由的介面與 SIP 主幹提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="c454f-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="c454f-110">使用內部部署會話邊界控制器 (SBC) ，以在轉送伺服器和 SIP 主幹提供者的服務之間提供安全的分割點。</span><span class="sxs-lookup"><span data-stu-id="c454f-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="c454f-111">如果您選擇後者，請確定您所選擇的 SBC 品牌與型號已取得認證，並且支援傳遞「目前狀態資訊資料格式位置物件」(PIDF-LO) 位置資料做為其 SIP INVITE 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c454f-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="c454f-112">否則電話將會送達去除其位置資訊的緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="c454f-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="c454f-113">如需認證 SBCs 的詳細資訊，請參閱「Microsoft Lync 的基礎結構合格」 <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> 。</span><span class="sxs-lookup"><span data-stu-id="c454f-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="c454f-114">E9-1-1 服務提供者為您提供一組 SBC 的存取做為後備之用。</span><span class="sxs-lookup"><span data-stu-id="c454f-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="c454f-115">您需要對轉送伺服器拓撲及通話路由設定進行幾項決策。</span><span class="sxs-lookup"><span data-stu-id="c454f-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="c454f-116">您是要將兩台 SBC 視為對等，並對它們之間的通話使用循環配置資源路由；或是要將一個 SBC 指派為主要，而另一個指派為次要呢？</span><span class="sxs-lookup"><span data-stu-id="c454f-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="c454f-117">如需在 Lync Server 中部署 SIP 主幹的詳細資訊，請參閱[如何在 Lync server 2013？中執行 sip 中繼](lync-server-2013-how-do-i-implement-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="c454f-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="c454f-118">為了協助決定如何部署 E9-1-1 的 SIP 主幹，您應該先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="c454f-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="c454f-119">**您應該在專用的租用網際網路連線上還是共用的網際網路連線上部署 SIP 主幹？**</span><span class="sxs-lookup"><span data-stu-id="c454f-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="c454f-p105">重點是一定要能夠接通緊急通話。專用線路可提供不被網路上其他流量佔用的連線，並讓您能夠實作服務品質 (QoS)。請記住，如果您透過公用網際網路連線至緊急服務服務提供者，而且需要保證緊急電話的機密性，則需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="c454f-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="c454f-123">**您的 E9-1-1 部署是針對嚴重損壞而設計嗎？**</span><span class="sxs-lookup"><span data-stu-id="c454f-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="c454f-124">因為這是緊急解決方案，所以恢復能力很重要。</span><span class="sxs-lookup"><span data-stu-id="c454f-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="c454f-125">在災難容錯位置部署主要和次要轉送伺服器和 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="c454f-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="c454f-126">最好是部署最接近其支援之使用者的主要轉送伺服器，並將容錯移轉呼叫路由傳送至位於不同地理位置) 中的次要轉送伺服器 (。</span><span class="sxs-lookup"><span data-stu-id="c454f-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="c454f-127">**您是否應該為每個分公司部署個別的 SIP 主幹？**</span><span class="sxs-lookup"><span data-stu-id="c454f-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="c454f-128">Lync Server 提供數個策略，可處理分支辦公室中的語音恢復作業，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將呼叫推出至本機閘道。</span><span class="sxs-lookup"><span data-stu-id="c454f-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="c454f-129">如需詳細資訊，請參閱[Lync Server 2013 中的分支網站 SIP trunk](lync-server-2013-branch-site-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="c454f-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="c454f-130">**是否啟用通話許可控制 (CAC)?**</span><span class="sxs-lookup"><span data-stu-id="c454f-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="c454f-131">Lync Server 不會處理與一般通話不同的緊急通話。</span><span class="sxs-lookup"><span data-stu-id="c454f-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="c454f-132">因此，頻寬管理或通話許可控制 (CAC) 可能對 E9-1-1 組態有負面影響。</span><span class="sxs-lookup"><span data-stu-id="c454f-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="c454f-133">如果啟用 CAC，且在路由緊急通話的連結上的流量超出設定的限制，則緊急通話可能會被封鎖或路由至本機 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c454f-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="c454f-134">如同本主題稍早所述，這類通話將會沒有位置資料，並且必須以手動方式路由至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="c454f-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

