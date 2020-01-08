---
title: Lync Server 2013：外部使用者存取案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="97a54-102">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="97a54-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97a54-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="97a54-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="97a54-104">提供 Lync Server 2013 的外部使用者存取需要您在周邊網路中至少部署一個 Edge 伺服器與一個反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="97a54-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="97a54-105">您也可以選擇在內部網路中部署控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="97a54-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="97a54-106">如果您需要比單一邊緣伺服器更大的容量，或者如果您的 Edge 伺服器部署需要高可用性，您可以在負載均衡的池中設定負載平衡與部署多個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97a54-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="97a54-107">如果您的組織有多個資料中心，您可以在一個以上的位置進行 Edge 伺服器或邊緣池部署。</span><span class="sxs-lookup"><span data-stu-id="97a54-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="97a54-108">不過，只有其中一個 Edge 伺服器部署可以指定為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="97a54-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="97a54-109">本節定義 Edge 伺服器部署的案例，並將規劃區段對應至可能的案例。</span><span class="sxs-lookup"><span data-stu-id="97a54-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="97a54-110">例如，如果您的部署需要高可用性、具有可擴展訊息和目前狀態（XMPP）連絡人的同盟，以及 Lync 行動性，您可以在下表中選取符合這些需求的相符專案，並使用參照規劃區段來定義您的部署，如以下流程圖所示。</span><span class="sxs-lookup"><span data-stu-id="97a54-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="97a54-111">**Edge 伺服器部署案例選取流程**</span><span class="sxs-lookup"><span data-stu-id="97a54-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="97a54-112">部署![流程圖範例](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "部署流程圖")</span><span class="sxs-lookup"><span data-stu-id="97a54-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="97a54-113">您可以使用此程式來規劃並記錄您想要為使用者部署的所有可能功能的設定。</span><span class="sxs-lookup"><span data-stu-id="97a54-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="97a54-114">不過，您可以在部署 Edge 伺服器之後新增同盟與行動服務，並在新增其他功能之前確認正確的操作。</span><span class="sxs-lookup"><span data-stu-id="97a54-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="97a54-115">在現有的邊緣伺服器部署中新增功能的套裝程式含在 [部署] 區段中。</span><span class="sxs-lookup"><span data-stu-id="97a54-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="97a54-116">如需有關部署的詳細資料，請參閱在初次規劃程式期間，在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)，您可以為新增功能準備 dns、防火牆和憑證需求，這可讓您提前取得證書並設定 dns 和埠/通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="97a54-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="97a54-117">如果您打算安裝 Edge 伺服器和反向 proxy，然後在稍後新增功能（例如，同盟與行動行動），請判斷部署之後所有服務所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="97a54-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="97a54-118">預先規劃及取得所有功能的憑證（初次部署），讓您不必定購新的憑證，就能滿足同盟的需求（也就是在 Edge 伺服器上），或是反向 proxy （也就是移動性的方式）。服務）。</span><span class="sxs-lookup"><span data-stu-id="97a54-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="97a54-119">所有 edge 服務都在每個 Edge 伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="97a54-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="97a54-120">無法在兩個不同的邊緣伺服器間分割服務。</span><span class="sxs-lookup"><span data-stu-id="97a54-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="97a54-121">如果您部署邊緣池以實現可伸縮性，則所有 edge 服務都會部署在該池中的每個 Edge 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="97a54-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="97a54-122">XMPP 同盟、Office 通訊伺服器和 Lync Server 同盟、公用 IM 連線與客戶行動，也是部署第一個邊緣伺服器或 Edge 池之後可以部署的其他服務。</span><span class="sxs-lookup"><span data-stu-id="97a54-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="97a54-123">行動服務是使用反向 proxy 的功能。</span><span class="sxs-lookup"><span data-stu-id="97a54-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="97a54-124">安裝行動服務不會將功能新增到 Edge 伺服器，但需要重新配置您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="97a54-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="97a54-125">列出這些功能的 [<STRONG>安裝目標</STRONG>] 欄會在 [ <STRONG>edge 伺服器規劃] 區段</STRONG>下的關聯欄中提供規劃指導方針，或按一下章節，在安裝及設定邊緣伺服器時，同時規劃要部署的這些功能。</span><span class="sxs-lookup"><span data-stu-id="97a54-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="97a54-126">識別及對應您的部署目標</span><span class="sxs-lookup"><span data-stu-id="97a54-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97a54-127">安裝目標</span><span class="sxs-lookup"><span data-stu-id="97a54-127">Installation goal</span></span></th>
<th><span data-ttu-id="97a54-128">Edge 伺服器規劃檔</span><span class="sxs-lookup"><span data-stu-id="97a54-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97a54-129">您已決定單一伺服器足以在您的基礎結構中提供 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="97a54-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="97a54-130">您也想要將使用 NAT 的邊緣伺服器外部介面的私人 IP 位址用於網際網路。</span><span class="sxs-lookup"><span data-stu-id="97a54-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="97a54-131">如果您要在您的周長部署單一邊緣伺服器，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="97a54-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="97a54-132">您將會部署邊緣伺服器，並將私人 IP 位址指派給 Edge 伺服器，並將使用 NAT 為網際網路上的外部使用者提供公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="97a54-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中的單一合併 Edge (利用私人 IP 位址及 NAT)</a></span><span class="sxs-lookup"><span data-stu-id="97a54-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a54-134">您已決定單一伺服器足以在您的基礎結構中提供 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="97a54-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="97a54-135">您也想要將邊緣伺服器外部介面的公用 IP 位址用於網際網路。</span><span class="sxs-lookup"><span data-stu-id="97a54-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="97a54-136">如果您要在您的周長部署單一邊緣伺服器，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="97a54-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="97a54-137">您將會部署邊緣伺服器，並將公用 IP 位址指派給 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97a54-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="97a54-138">在這種情況下，您將不會使用 NAT，而是使用路由。</span><span class="sxs-lookup"><span data-stu-id="97a54-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="97a54-139">外部使用者連線會提供邊緣伺服器的實際公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="97a54-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)</a></span><span class="sxs-lookup"><span data-stu-id="97a54-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a54-141">您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會在這個池中部署兩個或多個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97a54-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="97a54-142">您也想要將使用 NAT 的邊緣伺服器外部介面的私人 IP 位址用於網際網路。</span><span class="sxs-lookup"><span data-stu-id="97a54-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="97a54-143">如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="97a54-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="97a54-144">您將使用 DNS 負載平衡來在整個池中散佈通訊，將邊緣伺服器部署成已指派給 Edge 伺服器的私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="97a54-145">您將會使用 NAT，為網際網路上的外部使用者提供公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="97a54-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</a></span><span class="sxs-lookup"><span data-stu-id="97a54-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a54-147">您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會在這個池中部署兩個或多個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97a54-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="97a54-148">您也想要將邊緣伺服器外部介面的公用 IP 位址用於網際網路。</span><span class="sxs-lookup"><span data-stu-id="97a54-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="97a54-149">如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="97a54-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="97a54-150">您將使用 DNS 負載平衡來在整個池中散佈通訊，將邊緣伺服器部署成指派給 Edge 伺服器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="97a54-151">您會使用路由來為網際網路上的外部使用者提供公用 IP 位址（而不是 NAT）。</span><span class="sxs-lookup"><span data-stu-id="97a54-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="97a54-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)</a></span><span class="sxs-lookup"><span data-stu-id="97a54-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a54-153">您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會使用硬體負載平衡器在這個池中部署兩個或多個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97a54-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="97a54-154">如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="97a54-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="97a54-155">您將使用硬體負載平衡器在整個池中散佈通訊，將邊緣伺服器部署成指派給 Edge 伺服器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97a54-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="97a54-156">您會使用路由來為網際網路上的外部使用者提供公用 IP 位址（而不是 NAT）。</span><span class="sxs-lookup"><span data-stu-id="97a54-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="97a54-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge</a></span><span class="sxs-lookup"><span data-stu-id="97a54-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a54-158">同盟案例可讓您規劃可延伸您的使用者可與之通訊之合作夥伴類型的功能。</span><span class="sxs-lookup"><span data-stu-id="97a54-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="97a54-159">Lync Server 同盟</span><span class="sxs-lookup"><span data-stu-id="97a54-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="97a54-160">Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="97a54-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="97a54-161">公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="97a54-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="97a54-162">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="97a54-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97a54-163">規劃同盟案例</span><span class="sxs-lookup"><span data-stu-id="97a54-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="97a54-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 與 Office 通訊伺服器同盟</a></span><span class="sxs-lookup"><span data-stu-id="97a54-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="97a54-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">規劃 Lync Server 2013 中的公用立即訊息連線能力</a></span><span class="sxs-lookup"><span data-stu-id="97a54-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="97a54-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中規劃可擴展訊息和目前狀態通訊協定（XMPP）同盟</a></span><span class="sxs-lookup"><span data-stu-id="97a54-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a54-167">行動服務是透過反向 proxy 提供。</span><span class="sxs-lookup"><span data-stu-id="97a54-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="97a54-168">針對外部使用者啟用行動性的服務會部署在前端伺服器或頂層池。</span><span class="sxs-lookup"><span data-stu-id="97a54-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="97a54-169">您可以在反向 proxy 上建立或修改現有的發佈規則，為您的外部使用者啟用行動服務。</span><span class="sxs-lookup"><span data-stu-id="97a54-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="97a54-170"><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 中的行動規劃</a></span><span class="sxs-lookup"><span data-stu-id="97a54-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="97a54-171">在下列案例區段中，是參考體系結構、範例 DNS、埠/通訊協定定義及證書需求。</span><span class="sxs-lookup"><span data-stu-id="97a54-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="97a54-172">也包含您的 DNS、埠/通訊協定定義及證書需求的圖表。</span><span class="sxs-lookup"><span data-stu-id="97a54-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="97a54-173">圖表會提供範本供您填入並散佈給其他小組（例如，貴組織的網路小組、公開金鑰基礎結構小組和伺服器部署小組）。</span><span class="sxs-lookup"><span data-stu-id="97a54-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="97a54-174">圖表的目標是加強溝通，並確保將必要的邊緣伺服器設定元素傳達給將執行實際設定工作的人員時，取得成功。</span><span class="sxs-lookup"><span data-stu-id="97a54-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="97a54-175">建議您使用圖表與關聯的參考體系結構來規劃您的部署。</span><span class="sxs-lookup"><span data-stu-id="97a54-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

