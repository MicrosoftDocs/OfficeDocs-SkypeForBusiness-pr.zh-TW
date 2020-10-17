---
title: 設定媒體旁路通用設定以使用網站與地區資訊
description: 設定媒體旁路全域設定以使用網站與地區資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559799"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="94f3c-103">在 Lync Server 2013 中設定媒體旁路全域設定，以使用網站與地區資訊</span><span class="sxs-lookup"><span data-stu-id="94f3c-103">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94f3c-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94f3c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="94f3c-105">本主題假設您已經針對您希望媒體略過中繼伺服器的特定網站或服務，對於從中繼伺服器至對等 (網際網路電話語音服務提供者 (ITSP) 的公用交換電話網路 (PSTN) 閘道、IP-PBX 或工作階段界限控制器 (SBC)) 的任何主幹連線設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="94f3c-105">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="94f3c-106">本主題也假設您已在拓撲產生器中定義所有的中央網站和分支網站，使其符合您依照在 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 中建立或修改網路地區</A>的步驟，在 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 中建立或修改網路網站</A>，以及 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 lync server 2013 中建立子網與網路網站的關聯</A>，都符合您執行的網路地區、網路網站及子網設定。</span><span class="sxs-lookup"><span data-stu-id="94f3c-106">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="94f3c-107">如果不符合，則媒體旁路會失敗。</span><span class="sxs-lookup"><span data-stu-id="94f3c-107">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="94f3c-p102">除了針對與對等關聯的個別主幹連線啟用媒體旁路以外，您也必須設定全域設定。如果您使用本主題中的步驟來設定媒體旁路的全域設定，則假設下列其中一種或兩種情況會影響您的設定：</span><span class="sxs-lookup"><span data-stu-id="94f3c-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="94f3c-110">您沒有在 Lync Server 端點和您在主幹連線上設定媒體旁路的任何對等專案之間取得 *良好的連線* 能力。</span><span class="sxs-lookup"><span data-stu-id="94f3c-110">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="94f3c-111">已啟用頻寬管理的通話許可控制 (CAC)。</span><span class="sxs-lookup"><span data-stu-id="94f3c-111">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="94f3c-112">如需通話許可控制和媒體旁路考慮的詳細資訊，請參閱規劃檔中的「 <A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 中的媒體旁路和轉送伺服器</A> 」一節中的「呼叫許可控制 PSTN 連線」一節。</span><span class="sxs-lookup"><span data-stu-id="94f3c-112">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="94f3c-p103">若已啟用通話許可控制與媒體旁路進階 Enterprise Voice 功能，則網路地區和網路網站資訊會由這兩項功能共用。因此，如果您已經設定通話許可控制，則不需要使用下列程序特別針對媒體旁路來編輯網站與地區資訊。如果您尚未設定通話許可控制的網路地區和網站，而想要變更媒體旁路設定，請遵循此程序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="94f3c-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="94f3c-116">或者，如果您想要使用網站與地區資訊進行旁路決策，但無意啟用通話許可控制，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="94f3c-116">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="94f3c-117">在這種情況下，頻寬限制連結仍必須透過網路網站間原則來表示，如在 [Lync Server 2013 中建立網路站策略中](lync-server-2013-create-network-intersite-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="94f3c-117">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="94f3c-118">因為尚未啟用通話許可控制，所以在此情況下實際頻寬限制沒那麼重要。</span><span class="sxs-lookup"><span data-stu-id="94f3c-118">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="94f3c-119">這些連結會用來分割子網路，以指定沒有頻寬限制，因而可運用媒體旁路的子網路。</span><span class="sxs-lookup"><span data-stu-id="94f3c-119">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="94f3c-120">請注意，若已同時啟用通話許可控制和媒體旁路，情形也是如此。</span><span class="sxs-lookup"><span data-stu-id="94f3c-120">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="94f3c-121">此外，為了讓旁路能夠正常運作，在拓撲產生器中所定義的網站與設定網路地區和網站時所定義的網站之間，必須是一致的一致性。</span><span class="sxs-lookup"><span data-stu-id="94f3c-121">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="94f3c-122">例如，如果您已在拓撲產生器中定義的分支網站，只部署了 PSTN 閘道，則該分支網站必須設定企業語音原則，讓分支網站使用者能夠透過分支網站的 PSTN 閘道路由傳送 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="94f3c-122">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="94f3c-123">設定媒體旁路的網站與地區資訊</span><span class="sxs-lookup"><span data-stu-id="94f3c-123">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="94f3c-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="94f3c-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94f3c-125">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="94f3c-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="94f3c-126">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="94f3c-126">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="94f3c-127">連按兩下表格中的 **[全域]** 組態。</span><span class="sxs-lookup"><span data-stu-id="94f3c-127">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="94f3c-128">在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="94f3c-128">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="94f3c-129">按一下 **[使用網站和地區設定]**。</span><span class="sxs-lookup"><span data-stu-id="94f3c-129">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="94f3c-130">如有必要，請選取 **[啟用非對應網站的旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="94f3c-130">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="94f3c-p107">如果您有一或多個與相同區域關聯的大型網站沒有頻寬限制 (例如，大型中央網站)，但也有一些與相同區域關聯的分支網站具有頻寬限制，請選取此核取方塊。當您啟用非對應網站的旁路時，設定作業比較精簡，因為您只需指定與分支網站關聯的子網路，而不需指定與所有網站關聯的所有子網路。如果已啟用通話許可控制，則建議您不要選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="94f3c-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="94f3c-134">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="94f3c-134">Click **Commit**.</span></span>

<span data-ttu-id="94f3c-135">接下來，將子網新增至網站，如在 [Lync Server 2013 中關聯子網與媒體旁路的網路網站](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)所述。</span><span class="sxs-lookup"><span data-stu-id="94f3c-135">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="94f3c-136"> (將子網與網路網站相關聯的實際程式，會在 [ [將子網與 Lync Server 2013 中的網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)] 中說明。 ) 將所有子網與網站關聯之後，媒體旁路部署即完成。</span><span class="sxs-lookup"><span data-stu-id="94f3c-136">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="94f3c-137">如果您尚未建立網路地區和網路網站，您必須先予以建立，才能繼續進行媒體旁路部署。</span><span class="sxs-lookup"><span data-stu-id="94f3c-137">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="94f3c-138">如需詳細資訊，請參閱在 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 中建立或修改網路地區</A> ，以及 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="94f3c-138">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94f3c-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="94f3c-139">See Also</span></span>


[<span data-ttu-id="94f3c-140">在 Lync Server 2013 中將子網與媒體旁路的網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="94f3c-140">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

