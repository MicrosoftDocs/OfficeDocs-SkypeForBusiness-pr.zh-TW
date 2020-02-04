---
title: Lync Server 2013：為 E9 設計 SIP 幹線-1-1
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
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="ae36e-102">在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="ae36e-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae36e-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ae36e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ae36e-104">Lync Server 會使用 SIP trunks，將緊急呼叫連線至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="ae36e-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="ae36e-105">您可以在一個中央網站、多個中央網站或每個分支網站上設定 E9-1-1 的緊急服務 SIP trunks。</span><span class="sxs-lookup"><span data-stu-id="ae36e-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="ae36e-106">不過，如果呼叫者的網站與託管緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則在斷開連接的網站上由使用者所撥的通話將需要使用者語音原則中的特殊電話使用記錄，將呼叫路由至ECRC 透過本機的公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="ae36e-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="ae36e-107">如果通話許可控制併發通話限制生效，就是如此。</span><span class="sxs-lookup"><span data-stu-id="ae36e-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae36e-108">在 Lync Server 環境中，有兩種方式可以實施 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="ae36e-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ae36e-109">使用多宿主的出局轉送伺服器，使用其向外公開路由介面與 SIP 中繼提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="ae36e-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="ae36e-110">使用內部部署會話邊界控制器（SBC），在中繼伺服器與 SIP 中繼提供者的服務之間提供安全的 demarcation 點。</span><span class="sxs-lookup"><span data-stu-id="ae36e-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="ae36e-111">如果您選擇後一個方法，請確定您所選擇的 SBC 與模型已獲認證，並且支援將目前狀態資訊資料格式位置物件（PIDF-LO）位置資料傳送成其 SIP 邀請的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae36e-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="ae36e-112">否則，來電將會在緊急服務服務提供者去除其位置資訊時收到。</span><span class="sxs-lookup"><span data-stu-id="ae36e-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="ae36e-113">如需有關驗證的 SBCs 的詳細資料，請參閱「Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>的基礎結構合格」。</span><span class="sxs-lookup"><span data-stu-id="ae36e-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="ae36e-114">E9-1-1 服務提供者會提供一組半形的存取權，以實現冗余。</span><span class="sxs-lookup"><span data-stu-id="ae36e-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="ae36e-115">您需要針對中繼伺服器拓撲和呼叫路由設定進行數個決策。</span><span class="sxs-lookup"><span data-stu-id="ae36e-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="ae36e-116">您會將 SBCs 視為同等對等，並使用迴圈式路由來進行呼叫，或是將一個 SBC 指派為主要的，另一個是副？</span><span class="sxs-lookup"><span data-stu-id="ae36e-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="ae36e-117">如需在 Lync Server 中部署 SIP 主幹的詳細資料，請參閱[如何在 Lync server 2013 中實現 sip 中繼？](lync-server-2013-how-do-i-implement-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="ae36e-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="ae36e-118">下列問題將協助您決定如何部署 E9 的 SIP trunks-1-1。</span><span class="sxs-lookup"><span data-stu-id="ae36e-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="ae36e-119">**您是否應該透過專用租使用者或共用的網際網路連線來部署 SIP 幹線？**</span><span class="sxs-lookup"><span data-stu-id="ae36e-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="ae36e-120">緊急通話永遠都是重要的。</span><span class="sxs-lookup"><span data-stu-id="ae36e-120">It is important that emergency calls always connect.</span></span> <span data-ttu-id="ae36e-121">專用線路提供的連線功能不會被網路上的其他流量搶佔，並可讓您實現服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="ae36e-121">A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS).</span></span> <span data-ttu-id="ae36e-122">請記住，如果您是透過公用網際網路連線到緊急服務服務提供者，而且您需要保證緊急通話的機密性，則需要進行 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="ae36e-122">Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="ae36e-123">**您的 E9-1-1 部署是否專為災難耐受性而設計？**</span><span class="sxs-lookup"><span data-stu-id="ae36e-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="ae36e-124">因為這是緊急解決方案，所以復原非常重要。</span><span class="sxs-lookup"><span data-stu-id="ae36e-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="ae36e-125">在災難容錯位置部署主要和次要轉送伺服器和 SIP trunks。</span><span class="sxs-lookup"><span data-stu-id="ae36e-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="ae36e-126">建議您部署最接近支援的使用者的主要轉送伺服器，並透過次要轉送伺服器（位於不同的地理位置）路由容錯移轉呼叫。</span><span class="sxs-lookup"><span data-stu-id="ae36e-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="ae36e-127">**您是否應該針對每個分支機搆部署個別的 SIP 幹線？**</span><span class="sxs-lookup"><span data-stu-id="ae36e-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="ae36e-128">Lync Server 提供幾項策略，可處理分支辦公室中的語音復原，包括：具備彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將呼叫推送到本機閘道。</span><span class="sxs-lookup"><span data-stu-id="ae36e-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="ae36e-129">如需詳細資訊，請參閱[Lync Server 2013 中的分支網站 SIP 中繼](lync-server-2013-branch-site-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="ae36e-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="ae36e-130">**已啟用呼叫許可控制（CAC）嗎？**</span><span class="sxs-lookup"><span data-stu-id="ae36e-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="ae36e-131">Lync Server 不會以任何不同于一般呼叫的方式來處理緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ae36e-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="ae36e-132">基於這個原因，頻寬管理或呼叫許可控制（CAC）會對 E9-1-1 設定造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="ae36e-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="ae36e-133">如果啟用了 CAC，緊急通話會遭到封鎖，或路由到本機 PSTN 閘道，且在路由緊急通話的連結上超過設定的限制。</span><span class="sxs-lookup"><span data-stu-id="ae36e-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="ae36e-134">如本主題前面所示，此類呼叫將沒有位置資料，必須手動路由至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="ae36e-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

