---
title: Lync Server 2013： [高級企業語音功能] 的網路設定
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
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="f9079-102">Lync Server 2013 中的 [高級企業語音功能] 的網路設定</span><span class="sxs-lookup"><span data-stu-id="f9079-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9079-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f9079-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f9079-104">Lync Server 有三個高級企業語音功能： [呼叫許可控制] （CAC）、緊急服務（E9-1-1），以及 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="f9079-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="f9079-105">這些功能會在 Lync 伺服器拓撲中與網路網站共用網路區域、網路網站和每個子閘道聯的特定設定需求。</span><span class="sxs-lookup"><span data-stu-id="f9079-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="f9079-106">如需規劃部署這些功能的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="f9079-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="f9079-107">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="f9079-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="f9079-108">在 Lync Server 2013 中規劃緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="f9079-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="f9079-109">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="f9079-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="f9079-110">如需有關部署這些功能的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署高級企業語音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9079-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f9079-111">本主題概述所有三個高級企業語音功能通用的配置需求。</span><span class="sxs-lookup"><span data-stu-id="f9079-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="f9079-112">網路區域</span><span class="sxs-lookup"><span data-stu-id="f9079-112">Network Regions</span></span>

<span data-ttu-id="f9079-113">網路區域是網路中樞或網路骨幹，只能在通話許可控制（CAC）、E9-1 及媒體旁路設定中使用。</span><span class="sxs-lookup"><span data-stu-id="f9079-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9079-114">網路區域與 Lync Server 電話撥入式會議區域不同，必須將電話撥入式會議存取號碼與一或多個 Lync Server 撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f9079-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="f9079-115">如需電話撥入式會議區域的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</A>。</span><span class="sxs-lookup"><span data-stu-id="f9079-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="f9079-116">CAC 需要每個網路區域都有一個相關聯的 Lync Server 中央網站，可管理該區域內的媒體流量（亦即根據已設定的原則作出決策，關於是否有即時音訊或視頻會話可以建立）。</span><span class="sxs-lookup"><span data-stu-id="f9079-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="f9079-117">Lync Server 中央網站不代表地理位置，而是設定為一個池或一組池的邏輯伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="f9079-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="f9079-118">如需中心網站的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9079-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="f9079-119">另請參閱可支援性檔中的[Lync Server 2013 支援的拓撲](lync-server-2013-supported-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9079-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f9079-120">若要設定網路區域，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段上的 [**區域**] 索引標籤，或執行**新的 CsNetworkRegion**或**CsNetworkRegion 的**Lync server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9079-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="f9079-121">如需相關指示，請參閱在部署檔中的[Lync server 2013 中建立或修改網路區域](lync-server-2013-create-or-modify-a-network-region.md)，或參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="f9079-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="f9079-122">所有三個高級企業語音功能都將共用相同的網路區域定義。</span><span class="sxs-lookup"><span data-stu-id="f9079-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="f9079-123">如果您已經為一個功能建立了網路區域，就不需要為其他功能建立新的網路區域。</span><span class="sxs-lookup"><span data-stu-id="f9079-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="f9079-124">不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="f9079-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f9079-125">例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），且稍後您要部署 [呼叫許可控制]，則您必須修改每個網路區域定義，才能指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="f9079-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="f9079-126">若要將 Lync Server 中央網站與網路區域建立關聯，您可以指定中心網站名稱，方法是使用 Lync Server [控制台] 的 [**網路**設定] 區段，或執行**新的 CsNetworkRegion**或**CsNetworkRegion** Lync server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9079-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="f9079-127">如需相關指示，請參閱在部署檔中的[Lync server 2013 中建立或修改網路區域](lync-server-2013-create-or-modify-a-network-region.md)，或參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="f9079-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="f9079-128">網路網站</span><span class="sxs-lookup"><span data-stu-id="f9079-128">Network Sites</span></span>

<span data-ttu-id="f9079-129">Network 網站代表地理位置，例如分支機搆、地區辦事處或主辦公室。</span><span class="sxs-lookup"><span data-stu-id="f9079-129">A network site represents a geographical location, such as a branch office, a regional office, or a main office.</span></span> <span data-ttu-id="f9079-130">每個網路網站都必須與特定的網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f9079-130">Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9079-131">網路網站只能由高級企業語音功能使用。</span><span class="sxs-lookup"><span data-stu-id="f9079-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="f9079-132">它們與您在 Lync Server 拓撲結構中設定的分支網站不同。</span><span class="sxs-lookup"><span data-stu-id="f9079-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="f9079-133">如需分支網站的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的參考拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="f9079-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="f9079-134">另請參閱可支援性檔中的<A href="lync-server-2013-supported-topologies.md">Lync Server 2013 支援的拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="f9079-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="f9079-135">若要設定網路網站並將它與網路區域建立關聯，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段，或執行 Lync Server Management Shell **CsNetworkSite**或**CsNetworkSite** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9079-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="f9079-136">如需詳細資訊，請參閱在部署檔中的[Lync server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)，或參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="f9079-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="f9079-137">識別 IP 子網</span><span class="sxs-lookup"><span data-stu-id="f9079-137">Identify IP Subnets</span></span>

<span data-ttu-id="f9079-138">針對每個網路網站，您必須與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="f9079-138">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="f9079-139">如果您的網路系統管理員已經將 IP 子網組織到網路區域和網路網站，您的工作會明顯簡化。</span><span class="sxs-lookup"><span data-stu-id="f9079-139">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="f9079-140">例如，您可以將下列 IP 子網指派給北美地區的紐約網站： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="f9079-140">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="f9079-141">如果 Bob 通常是在底特律中運作，在紐約辦公室進行訓練，然後開啟他的電腦並聯機到網路上，他的電腦將會取得 IP 位址，並在為紐約所指派的四個範圍中的其中一個，例如172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="f9079-141">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f9079-142">在伺服器的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確地用於媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="f9079-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="f9079-143">Lync 用戶端會採用其本機 IP 位址，並使用相關聯的子網路遮罩來遮罩 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f9079-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="f9079-144">在判斷與每個用戶端相關的旁路識別碼時，註冊機構會將與每個網路網站相關聯的 IP 子網清單與用戶端提供的子網進行比較，以取得完全相符的專案。</span><span class="sxs-lookup"><span data-stu-id="f9079-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="f9079-145">基於這個原因，在伺服器的網路設定期間輸入的子網很重要，而不是虛擬子網。</span><span class="sxs-lookup"><span data-stu-id="f9079-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="f9079-146">（如果您部署 [呼叫許可控制]，但無法使用 [媒體旁路]，即使您設定虛擬子網，也能正常使用通話許可控制功能。）</span><span class="sxs-lookup"><span data-stu-id="f9079-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="f9079-147">例如，如果 Lync 用戶端在 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，則會要求與子網172.29.81.0 相關聯的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="f9079-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="f9079-148">如果子網是定義為 172.29.0.0/16，雖然用戶端屬於虛擬子網，但註冊機構不會認為這個相符，因為註冊機構特別想要尋找子網172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="f9079-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="f9079-149">因此，系統管理員必須完全按照 Lync 用戶端所提供的方式輸入子網（無論是靜態或由動態主機設定通訊協定（DHCP），都能在網路設定期間由子網進行設定。）</span><span class="sxs-lookup"><span data-stu-id="f9079-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="f9079-150">將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="f9079-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="f9079-151">商業網路中的每個子網都必須與網路網站相關聯（也就是說，每個子網上都需要與地理位置相關聯）。</span><span class="sxs-lookup"><span data-stu-id="f9079-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="f9079-152">這個子網的關聯性能讓 [高級企業語音] 功能在地理位置找到端點。</span><span class="sxs-lookup"><span data-stu-id="f9079-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="f9079-153">例如，找出端點可讓 CAC 從網路網站傳送即時音訊及視頻資料的流程。</span><span class="sxs-lookup"><span data-stu-id="f9079-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="f9079-154">若要將子網與網路網站建立關聯，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段，或者您可以使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="f9079-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="f9079-155">如需相關指示，請參閱在部署檔中[將子網與 Lync server 2013 中的網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)，或參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="f9079-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9079-156">請參閱</span><span class="sxs-lookup"><span data-stu-id="f9079-156">See Also</span></span>


[<span data-ttu-id="f9079-157">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="f9079-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="f9079-158">在 Lync Server 2013 中規劃緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="f9079-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="f9079-159">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="f9079-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

