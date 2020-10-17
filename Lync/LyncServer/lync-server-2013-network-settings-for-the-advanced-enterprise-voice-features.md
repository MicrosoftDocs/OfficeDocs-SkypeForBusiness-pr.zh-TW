---
title: Lync Server 2013：高級 Enterprise Voice 功能的網路設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8096f9dbce6e5e807cc806a5d87df7558f38a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505480"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="98152-102">Lync Server 2013 中的高級 Enterprise Voice 功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="98152-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98152-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="98152-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="98152-104">Lync Server 具有三個高級 Enterprise Voice 功能：通話許可控制 (CAC) 、緊急服務 (E9-1-1) 和媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="98152-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="98152-105">這些功能會在 Lync Server 拓撲中，共用網路地區、網路網站及每個子網與網路網站關聯的特定設定需求。</span><span class="sxs-lookup"><span data-stu-id="98152-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="98152-106">如需這些功能之部署規劃的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="98152-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="98152-107">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="98152-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="98152-108">在 Lync Server 2013 中規劃緊急服務 (E9-1-1) </span><span class="sxs-lookup"><span data-stu-id="98152-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="98152-109">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="98152-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="98152-110">如需有關部署上述各項功能的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中部署 Advanced Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="98152-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="98152-111">本主題概要說明所有三種高級 Enterprise Voice 功能的常見設定需求。</span><span class="sxs-lookup"><span data-stu-id="98152-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="98152-112">網路地區</span><span class="sxs-lookup"><span data-stu-id="98152-112">Network Regions</span></span>

<span data-ttu-id="98152-113">網路地區是一種網路中樞或網路骨幹，只有在通話許可控制 (CAC)、E9-1-1 和媒體旁路的組態中才會使用。</span><span class="sxs-lookup"><span data-stu-id="98152-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98152-114">網路地區與 Lync Server 電話撥入式會議地區不同，後者與一或多部 Lync Server 撥號對應表建立電話撥入式會議存取號碼的要求。</span><span class="sxs-lookup"><span data-stu-id="98152-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="98152-115">如需電話撥入式會議區域的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="98152-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="98152-116">CAC 需要每個網路地區都有相關聯的 Lync Server 中央網站，它會管理地區內的媒體流量 (也就是說，它會根據您設定的原則進行決策，有關是否可以) 建立即時音訊或視頻會話。</span><span class="sxs-lookup"><span data-stu-id="98152-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="98152-117">Lync Server 中央網站不代表地理位置，而是設定為集區或集區集區的邏輯群組。</span><span class="sxs-lookup"><span data-stu-id="98152-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="98152-118">如需中央網站的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md) 。</span><span class="sxs-lookup"><span data-stu-id="98152-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="98152-119">另請參閱支援檔中的 [Lync Server 2013 中支援的拓撲](lync-server-2013-supported-topologies.md) 。</span><span class="sxs-lookup"><span data-stu-id="98152-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="98152-120">若要設定網路地區，您可以使用 Lync Server 控制台的 [**網路**設定] 區段中的 [**區域**] 索引標籤，或執行**New-CsNetworkRegion**或**Set-CsNetworkRegion** Lync server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98152-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="98152-121">如需相關指示，請參閱部署檔中的在 [Lync server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md) ，或參考 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="98152-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="98152-122">所有三個高級 Enterprise Voice 功能都會共用相同的網路地區定義。</span><span class="sxs-lookup"><span data-stu-id="98152-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="98152-123">如果您已為其中一項功能建立網路地區，即無須再為其他功能建立新的網路地區。</span><span class="sxs-lookup"><span data-stu-id="98152-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="98152-124">但您可能需要修改現有的網路地區定義，以套用功能特有的設定。</span><span class="sxs-lookup"><span data-stu-id="98152-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="98152-125">例如，如果您為 E9-1-1 (不需要有相關聯的中央網站) 建立網路地區後，又部署了通話許可控制，則必須修改每個網路地區定義以指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="98152-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="98152-126">若要將 Lync Server 中央網站與網路地區產生關聯，您可以使用 Lync Server 控制台的 [ **網路** 設定] 區段，或是執行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion** Lync server 管理命令介面 Cmdlet 來指定中央網站名稱。</span><span class="sxs-lookup"><span data-stu-id="98152-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="98152-127">如需相關指示，請參閱部署檔中的在 [Lync server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md) ，或參考 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="98152-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="98152-128">網站</span><span class="sxs-lookup"><span data-stu-id="98152-128">Network Sites</span></span>

<span data-ttu-id="98152-p107">網路網站代表地理位置，例如分公司、地區辦事處或總公司。每個網路網站都必須與某個網路地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="98152-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98152-131">只有「高級 Enterprise Voice」功能才能使用網路網站。</span><span class="sxs-lookup"><span data-stu-id="98152-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="98152-132">它們不同于您在 Lync Server 拓撲中設定的分支網站。</span><span class="sxs-lookup"><span data-stu-id="98152-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="98152-133">如需有關分支網站的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的參考拓撲</A> 。</span><span class="sxs-lookup"><span data-stu-id="98152-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="98152-134">另請參閱支援檔中的 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013 中支援的拓撲</A> 。</span><span class="sxs-lookup"><span data-stu-id="98152-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="98152-135">若要設定網路網站，並將其與網路地區產生關聯，您可以使用 Lync Server 控制台的 [ **網路** 設定] 區段，或執行 Lync Server 管理命令介面 **New-CsNetworkSite** 或 **Set-CsNetworkSite** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98152-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="98152-136">如需詳細資訊，請參閱部署檔中的 [建立或修改 Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) 中的網站，或參考 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="98152-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="98152-137">識別 IP 子網路</span><span class="sxs-lookup"><span data-stu-id="98152-137">Identify IP Subnets</span></span>

<span data-ttu-id="98152-p110">對於每一個網站，您需要和網路管理員一同決定要指派給每一個網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網站的 IP 子網路，您的工作將會大幅簡化。</span><span class="sxs-lookup"><span data-stu-id="98152-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="98152-p111">例如，可以將指派以下 IP 子網路給北美洲區域內的紐約網站：172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. 假設平常在 Detroit 工作的 Bob 要到 New York 分公司受訓。當他開啟自己的電腦並連線至網路時，他的電腦會取得分配給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="98152-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="98152-142">在伺服器上的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確用於媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="98152-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="98152-143">Lync 用戶端會採用其本機 IP 位址，並以關聯的子網路遮罩遮罩 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="98152-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="98152-144">決定與每一位用戶端相關聯的旁路識別碼時，註冊機構會比較與用戶端所提供之子網相關聯的 IP 子網清單，以取得完全相符的專案。</span><span class="sxs-lookup"><span data-stu-id="98152-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="98152-145">因此，在伺服器上的網路設定期間輸入的子網，必須是實際的子網，而不是虛擬子網，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="98152-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="98152-146"> (如果您部署通話許可控制，但沒有媒體旁路，則即使您設定虛擬子網，通話許可控制也會正常運作。 ) </span><span class="sxs-lookup"><span data-stu-id="98152-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="98152-147">例如，如果 Lync 用戶端在其 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，則會要求與子網172.29.81.0 相關聯的旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="98152-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="98152-148">如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="98152-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="98152-149">因此，管理員必須嚴格依照 Lync 用戶端所提供的方式輸入子網， (會在網路設定期間（靜態或透過動態主機設定通訊協定 (DHCP) ）輸入子網。 ) </span><span class="sxs-lookup"><span data-stu-id="98152-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="98152-150">建立子網路與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="98152-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="98152-151">企業網路中的每個子網路都必須與某個網路網站相關聯 (亦即，每個子網路都必須與某個地理位置相關聯)。</span><span class="sxs-lookup"><span data-stu-id="98152-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="98152-152">這個子閘道聯可讓高級 Enterprise Voice 功能找到地理位置的端點。</span><span class="sxs-lookup"><span data-stu-id="98152-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="98152-153">例如，找出端點位置後，CAC 可以調節進出該網路網站的即時音訊與視訊資料流量。</span><span class="sxs-lookup"><span data-stu-id="98152-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="98152-154">若要將子網與網站產生關聯，您可以使用 Lync Server 控制台的 [ **網路** 設定] 區段，也可以使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="98152-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="98152-155">如需相關指示，請參閱部署檔中的在 [Lync server 2013 中建立子網與網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md) ，或參考 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="98152-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98152-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="98152-156">See Also</span></span>


[<span data-ttu-id="98152-157">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="98152-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="98152-158">在 Lync Server 2013 中規劃緊急服務 (E9-1-1) </span><span class="sxs-lookup"><span data-stu-id="98152-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="98152-159">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="98152-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

