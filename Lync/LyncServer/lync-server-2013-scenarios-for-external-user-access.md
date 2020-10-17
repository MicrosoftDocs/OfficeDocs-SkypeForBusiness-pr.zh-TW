---
title: Lync Server 2013：外部使用者存取的案例
description: Lync Server 2013：外部使用者存取的案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547639"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="1c27b-103">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="1c27b-103">Scenarios for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c27b-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1c27b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1c27b-105">提供外部使用者存取的 Lync Server 2013 時，需要在周邊網路中至少部署一個 Edge Server 與一個反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="1c27b-105">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="1c27b-106">您也可以選擇性地在內部網路中部署 Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="1c27b-106">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="1c27b-107">如果您需要的容量大於單一 Edge Server 所能提供的容量，或如果您需要 Edge Server 部署的高可用性，您可以在負載平衡集區中設定負載平衡及部署多部 Edge server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-107">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="1c27b-108">如果您的組織有多個資料中心，您可以讓 Edge Server 或 Edge 集區部署位於一個以上的位置。</span><span class="sxs-lookup"><span data-stu-id="1c27b-108">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="1c27b-109">不過，只有其中一個 Edge Server 部署可以指定為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="1c27b-109">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="1c27b-110">本節定義 Edge Server 部署的案例，並將規劃區段對應至可能的案例。</span><span class="sxs-lookup"><span data-stu-id="1c27b-110">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="1c27b-111">例如，如果您的部署需要高可用性、具有可延伸訊息和顯示狀態的同盟 (XMPP) 連絡人和 Lync 行動性，請選取下表中符合這些需求的相符專案，並使用參考的規劃區段來定義您的部署，如下流程圖所示。</span><span class="sxs-lookup"><span data-stu-id="1c27b-111">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="1c27b-112">**Edge Server 部署案例選擇程序**</span><span class="sxs-lookup"><span data-stu-id="1c27b-112">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="1c27b-113">![範例部署流程圖](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "範例部署流程圖")</span><span class="sxs-lookup"><span data-stu-id="1c27b-113">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="1c27b-114">使用此程式，您可以規劃及記錄您要為使用者部署的所有潛在功能設定。</span><span class="sxs-lookup"><span data-stu-id="1c27b-114">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="1c27b-115">不過，您可以在部署 Edge Server 後新增同盟及行動性服務，並在新增其他功能之前確認正確的操作。</span><span class="sxs-lookup"><span data-stu-id="1c27b-115">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="1c27b-116">在 [部署] 區段中涵蓋將功能新增至現有 Edge Server 部署的程式。</span><span class="sxs-lookup"><span data-stu-id="1c27b-116">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="1c27b-117">如需有關部署的詳細資訊，請參閱在初次規劃程式期間， [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md) ，您可以為新增的功能準備 dns、防火牆和憑證需求，這樣可讓您預先取得憑證及設定 dns 及埠/通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="1c27b-117">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1c27b-118">如果您打算安裝 Edge Server 和反向 proxy，然後在稍後新增功能 (例如，同盟與行動性) ，請決定部署後所有服務所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="1c27b-118">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="1c27b-119">預先規劃及取得所有功能的憑證，最初部署的憑證，可讓您不必定購新的憑證，以滿足同盟 (的需求，也就是在 Edge Server 上) 或反向 proxy (也是針對行動服務) 。</span><span class="sxs-lookup"><span data-stu-id="1c27b-119">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1c27b-120">在每一部 Edge Server 上執行所有 edge 服務。</span><span class="sxs-lookup"><span data-stu-id="1c27b-120">All edge services run on each Edge Server.</span></span> <span data-ttu-id="1c27b-121">無法在兩個不同的 Edge Server 之間分割服務。</span><span class="sxs-lookup"><span data-stu-id="1c27b-121">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="1c27b-122">如果您部署 Edge 集區以取得可擴充性，所有 edge service 都會部署在集區中的每一部 Edge Server 上。</span><span class="sxs-lookup"><span data-stu-id="1c27b-122">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="1c27b-123">XMPP 同盟、Office 通訊伺服器和 Lync Server 同盟、公用 IM 連線和用戶端行動是在您部署第一部 Edge Server 或 Edge 集區之後，可以部署的其他服務。</span><span class="sxs-lookup"><span data-stu-id="1c27b-123">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="1c27b-124">Mobility Service 是一種使用反向 Proxy 的功能。</span><span class="sxs-lookup"><span data-stu-id="1c27b-124">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="1c27b-125">安裝行動服務不會將功能新增至 Edge Server，但需要重新配置反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="1c27b-125">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="1c27b-126">列出這些功能的 <STRONG>安裝目標</STRONG> 欄，會在 edge <STRONG>Server 計畫區段</STRONG> 底下的相關欄中提供規劃指導方針，以在安裝及設定 edge server 時同時規劃要部署的這些功能。</span><span class="sxs-lookup"><span data-stu-id="1c27b-126">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="1c27b-127">識別並對應您的部署目標</span><span class="sxs-lookup"><span data-stu-id="1c27b-127">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c27b-128">安裝目標</span><span class="sxs-lookup"><span data-stu-id="1c27b-128">Installation goal</span></span></th>
<th><span data-ttu-id="1c27b-129">Edge Server 規劃文件</span><span class="sxs-lookup"><span data-stu-id="1c27b-129">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c27b-p107">您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="1c27b-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1c27b-132">如果您要在周邊環境中部署單一 Edge Server，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="1c27b-132">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1c27b-133">您將使用指派給 Edge Server 的私人 IP 位址部署 Edge Server，並使用 NAT 為網際網路上的外部使用者提供公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c27b-133">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中的單一合併 edge （利用私人 IP 位址及 NAT）</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c27b-p109">您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用公用 IP 位址來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="1c27b-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1c27b-137">如果您要在周邊環境中部署單一 Edge Server，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="1c27b-137">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1c27b-138">您將使用指派給 Edge Server 的公用 IP 位址，部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-138">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="1c27b-139">在此案例中，您將使用路由取代 NAT。</span><span class="sxs-lookup"><span data-stu-id="1c27b-139">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="1c27b-140">Edge Server 的實際公用 IP 位址可供外部使用者連線使用。</span><span class="sxs-lookup"><span data-stu-id="1c27b-140">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c27b-p111">您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="1c27b-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1c27b-144">如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="1c27b-144">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1c27b-145">您將使用 DNS 負載平衡來散佈整個集區中的通訊，以部署具有指派給 Edge Server 之私人 IP 位址的 Edge server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-145">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1c27b-146">您將使用 NAT 來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c27b-146">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c27b-148">您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-148">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="1c27b-149">您也想要對網際網路使用 Edge Server 外部介面的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c27b-149">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1c27b-150">如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="1c27b-150">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1c27b-151">您將使用 DNS 負載平衡來散佈整個集區中的通訊，以部署具有指派給 Edge Server 之公用 IP 位址的 Edge server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-151">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1c27b-152">您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c27b-152">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c27b-154">您已決定 Edge service 的高可用性對您的使用者來說很重要，且您將使用硬體負載平衡器在此集區中部署兩部以上的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-154">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="1c27b-155">如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。</span><span class="sxs-lookup"><span data-stu-id="1c27b-155">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1c27b-156">您將使用硬體負載平衡器來散佈跨集區的通訊，以指派給 Edge Server 的公用 IP 位址，來部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="1c27b-156">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="1c27b-157">您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c27b-157">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c27b-159">您可使用同盟案例來規劃可擴充與使用者進行通訊之協力廠商類型的功能。</span><span class="sxs-lookup"><span data-stu-id="1c27b-159">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="1c27b-160">Lync Server 同盟</span><span class="sxs-lookup"><span data-stu-id="1c27b-160">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="1c27b-161">Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="1c27b-161">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="1c27b-162">公共 IM 連線</span><span class="sxs-lookup"><span data-stu-id="1c27b-162">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="1c27b-163">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="1c27b-163">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1c27b-164">規劃同盟案例</span><span class="sxs-lookup"><span data-stu-id="1c27b-164">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="1c27b-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 和 Office 通訊伺服器同盟</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="1c27b-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">在 Lync Server 2013 中規劃公用立即訊息連線</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="1c27b-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c27b-168">行動性服務是透過反向 proxy 提供。</span><span class="sxs-lookup"><span data-stu-id="1c27b-168">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="1c27b-169">對外部使用者啟用行動性的服務會部署在前端伺服器或前端集區上。</span><span class="sxs-lookup"><span data-stu-id="1c27b-169">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="1c27b-170">您可以在反向 proxy 上建立或修改現有的發行規則，為外部使用者啟用行動服務。</span><span class="sxs-lookup"><span data-stu-id="1c27b-170">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="1c27b-171"><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動性</a></span><span class="sxs-lookup"><span data-stu-id="1c27b-171"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="1c27b-172">在下列案例區段中，為參考架構、範例 DNS、埠/通訊協定定義和憑證需求。</span><span class="sxs-lookup"><span data-stu-id="1c27b-172">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="1c27b-173">此外，也包含您的 DNS、埠/通訊協定定義和憑證需求的圖表。</span><span class="sxs-lookup"><span data-stu-id="1c27b-173">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="1c27b-174">圖表會提供範本，供您用來填入或散佈至其他小組 (例如，組織的網路小組、公開金鑰基礎結構小組和伺服器部署小組) 。</span><span class="sxs-lookup"><span data-stu-id="1c27b-174">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="1c27b-175">圖表的目的是為了加強通訊，並在將必要的 Edge Server 設定元素傳遞給將執行實際設定工作的人員時，確保成功。</span><span class="sxs-lookup"><span data-stu-id="1c27b-175">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="1c27b-176">建議您使用圖表和相關的參考架構規劃您的部署。</span><span class="sxs-lookup"><span data-stu-id="1c27b-176">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

