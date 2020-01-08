---
title: 設定媒體旁路全域設定以使用網站和區域資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="32b96-102">在 Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊</span><span class="sxs-lookup"><span data-stu-id="32b96-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32b96-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="32b96-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="32b96-104">本主題假設您已將來自中繼伺服器的任何干線連線的媒體旁路設定設為對等（公用交換電話網絡（PSTN）閘道、IP PBX，或網際網路電話語音的會話邊界控制器（SBC）您想要媒體略過轉送伺服器的特定網站或服務的提供者（ITSP）。</span><span class="sxs-lookup"><span data-stu-id="32b96-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="32b96-105">本主題也假設您已定義拓撲建立器中的所有中心網站和分支網站，符合在<A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 中建立或修改網路區域</A>、在 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 中建立或修改網路網站</A>中的步驟，以及在<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">lync server 2013 中將子網與網路網站建立關聯</A>的方式。</span><span class="sxs-lookup"><span data-stu-id="32b96-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="32b96-106">如果不相符，則媒體略過將無法成功。</span><span class="sxs-lookup"><span data-stu-id="32b96-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="32b96-107">除了為與對等相關聯的個別幹線連線啟用媒體旁路之外，您還必須設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="32b96-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="32b96-108">如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設下列其中一個或兩個情況會影響您的設定：</span><span class="sxs-lookup"><span data-stu-id="32b96-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="32b96-109">您在 Lync 伺服器端點與您在中繼連線中設定媒體旁路的任何對等的使用者之間，*都沒有良好的連線*性。</span><span class="sxs-lookup"><span data-stu-id="32b96-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="32b96-110">已啟用 [頻寬管理] 的通話許可控制（CAC）。</span><span class="sxs-lookup"><span data-stu-id="32b96-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="32b96-111">如需有關呼叫許可控制和媒體旁路考慮的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 的媒體旁路和轉送伺服器</A>中的 [呼叫 PSTN 連線的接入控制] 區段。</span><span class="sxs-lookup"><span data-stu-id="32b96-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="32b96-112">網路區域和網路網站資訊都是在 [呼叫許可控制] 中共用，當兩個專案都啟用時，媒體就會繞過高級企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="32b96-112">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="32b96-113">因此，如果您已設定 [通話許可控制]，則不需要您使用下列程式來編輯專門針對媒體旁路的網站和區域資訊。</span><span class="sxs-lookup"><span data-stu-id="32b96-113">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="32b96-114">如果您尚未設定 [通話許可控制] 的網路區域和網站，且您想要變更媒體旁路設定，請遵循此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="32b96-114">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="32b96-115">或者，如果您想要在進行回避決定時使用網站和區域資訊，但不想要啟用呼叫許可控制，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="32b96-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="32b96-116">在這種情況下，頻寬限制連結仍需要透過網路網站間原則來表示，如在[Lync Server 2013 中建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="32b96-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="32b96-117">在這種情況下，實際的頻寬限制並不重要，因為尚未啟用 [通話許可控制]。</span><span class="sxs-lookup"><span data-stu-id="32b96-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="32b96-118">相反地，這些連結是用來將子網劃分成分區，以指定那些沒有頻寬限制且可以使用媒體略過的專案。</span><span class="sxs-lookup"><span data-stu-id="32b96-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="32b96-119">請注意，當您同時啟用 [通話許可控制] 和 [媒體旁路] 時，也是如此。</span><span class="sxs-lookup"><span data-stu-id="32b96-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="32b96-120">此外，若要讓 [旁路] 正常運作，在拓撲建立器中定義的網站與在您設定網路區域和網路網站時所定義的網站而言，都必須是一致性。</span><span class="sxs-lookup"><span data-stu-id="32b96-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="32b96-121">例如，如果您在拓撲建立器中定義了一個已部署 PSTN 閘道的分支網站，則必須使用企業語音原則來設定分支網站，讓分支網站使用者能夠透過 PSTN 路由其 PSTN 通話分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="32b96-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="32b96-122">若要設定媒體旁路的網站和區域資訊</span><span class="sxs-lookup"><span data-stu-id="32b96-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="32b96-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="32b96-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="32b96-124">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="32b96-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="32b96-125">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="32b96-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="32b96-126">在資料表中按兩下**全域**配置。</span><span class="sxs-lookup"><span data-stu-id="32b96-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="32b96-127">在 [**編輯全域設定**] 頁面上，選取 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="32b96-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="32b96-128">按一下 [**使用網站和地區**設定]。</span><span class="sxs-lookup"><span data-stu-id="32b96-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="32b96-129">如有需要，請選取 [為**未對應的網站啟用旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="32b96-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="32b96-130">只有當您有一個或多個大型網站與不含頻寬限制（例如大型中央網站）的同一個區域相關聯時，才選取此核取方塊，但您還有一些與有頻寬的相同區域相關聯的分支網站限制.</span><span class="sxs-lookup"><span data-stu-id="32b96-130">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="32b96-131">當您針對未對應的網站啟用 [旁路] 時，系統會簡化配置，讓您只指定與分支網站相關聯的子網，而不需要指定與所有網站相關聯的所有子網。</span><span class="sxs-lookup"><span data-stu-id="32b96-131">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="32b96-132">如果已啟用 [通話許可控制]，建議您不要選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="32b96-132">We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="32b96-133">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32b96-133">Click **Commit**.</span></span>

<span data-ttu-id="32b96-134">接著，將子網新增至網路網站，如在[Lync Server 2013 中將子網與媒體旁路的網路網站相關聯](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)的說明。</span><span class="sxs-lookup"><span data-stu-id="32b96-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="32b96-135">（在[Lync Server 2013 中，將子網與網路網站相關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的實際程式將在 [與網路網站建立關聯] 中描述。）將所有子網與網路網站建立關聯之後，就會完成媒體略過部署。</span><span class="sxs-lookup"><span data-stu-id="32b96-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="32b96-136">如果您還沒有建立網路區域和網路網站，您必須先建立這些區域，才能繼續進行媒體旁路部署。</span><span class="sxs-lookup"><span data-stu-id="32b96-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="32b96-137">如需詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中建立或修改網路區域</A>，以及<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="32b96-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32b96-138">請參閱</span><span class="sxs-lookup"><span data-stu-id="32b96-138">See Also</span></span>


[<span data-ttu-id="32b96-139">在 Lync Server 2013 中將子網與網路網站進行媒體旁路</span><span class="sxs-lookup"><span data-stu-id="32b96-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

