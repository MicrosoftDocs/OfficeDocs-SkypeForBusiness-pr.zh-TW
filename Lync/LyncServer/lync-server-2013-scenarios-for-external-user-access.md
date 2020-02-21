---
title: 外部使用者存取的 Lync Server 2013： 案例
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
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6a0ec-102">Lync Server 2013 中的外部使用者存取的案例</span><span class="sxs-lookup"><span data-stu-id="6a0ec-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a0ec-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="6a0ec-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6a0ec-104">提供 Lync Server 2013 的外部使用者存取需要您先部署在周邊網路中，至少有一部 Edge Server 和一個反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="6a0ec-105">或者，您可以在其中部署 Director 或 Director 集區中您的內部網路。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="6a0ec-106">如果您需要更多的容量，比可以提供單一 Edge Server，或如果您需要為 Edge Server 部署高可用性，您可以設定負載平衡功能和部署多部 Edge Server 的負載平衡集區中。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="6a0ec-107">如果組織有多個資料中心，您可以有多個位置的 Edge Server 或 Edge 集區部署。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="6a0ec-108">不過，只有其中一個 Edge Server 部署可以指定作為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="6a0ec-109">本節定義 Edge Server 部署案例，並將對應的可能案例規劃章節。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="6a0ec-110">例如，如果您的部署需要高可用性，以可延伸訊息和目前狀態 (XMPP) 的連絡人，以及 Lync mobility 同盟選取相符的項目會滿足這些需求，使用下列表格中下列流程圖所示，請參考規劃的各節，以定義您的部署。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="6a0ec-111">**Edge Server 部署案例選擇程序**</span><span class="sxs-lookup"><span data-stu-id="6a0ec-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="6a0ec-112">![範例部署流程圖](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "範例部署流程圖")</span><span class="sxs-lookup"><span data-stu-id="6a0ec-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="6a0ec-113">藉由使用此程序，您可以規劃及文件的所有潛在的功能，您想要部署為您的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="6a0ec-114">不過，您可以新增同盟和行動服務後您已部署 Edge Server 並確認正確的操作，才能新增其他功能。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="6a0ec-115">將功能新增至現有的 Edge Server 部署的程序涵蓋在 [部署] 區段中。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="6a0ec-116">如需部署的詳細資訊，請參閱[部署外部使用者存取 Lync Server 2013 中](lync-server-2013-deploying-external-user-access.md)藉由包括在初始的規劃程序期間進行規劃的這些功能，您可以準備 DNS、 防火牆和憑證需求的新增功能，可讓您取得憑證並設定 DNS 和連接埠/通訊協定需求事先。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6a0ec-117">如果您計劃要安裝 Edge Server 和反向 proxy，然後新增功能更新版本 （例如，同盟和行動），決定您需要的所有服務之後部署何種憑證。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="6a0ec-118">規劃並了解取得憑證，事先，所有功能的初始部署或沒看到，請儲存您不必順序新的憑證，以滿足需求的同盟 (亦即在 Edge Server 上) 或反向 proxy (也就是行動服務）。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6a0ec-119">在每部 Edge Server 上執行所有 edge 服務。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="6a0ec-120">服務無法兩個不同的 Edge 伺服器之間分割。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="6a0ec-121">如果您部署的延展性的 Edge 集區，在集區中每個 Edge Server 上要部署的所有 edge 服務。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="6a0ec-122">XMPP 同盟、 Office Communications Server 及 Lync Server 同盟、 公用 IM 連線能力和用戶端行動性是您已部署您的第一個 Edge Server 或 Edge 集區之後，可以部署的其他服務。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="6a0ec-123">Mobility Service 是一種使用反向 Proxy 的功能。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="6a0ec-124">安裝行動服務不將功能加入您的 Edge Server，但需要重新設定您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="6a0ec-125">列出這些功能的<STRONG>安裝目標</STRONG>欄同時規劃要部署 Edge Server 已安裝並設定當這些功能提供相關聯的資料行下<STRONG>Edge Server 規劃] 區段中或各節</STRONG>中的規劃指引。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="6a0ec-126">識別並對應您的部署目標</span><span class="sxs-lookup"><span data-stu-id="6a0ec-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a0ec-127">安裝目標</span><span class="sxs-lookup"><span data-stu-id="6a0ec-127">Installation goal</span></span></th>
<th><span data-ttu-id="6a0ec-128">Edge Server 規劃文件</span><span class="sxs-lookup"><span data-stu-id="6a0ec-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a0ec-p107">您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="6a0ec-131">使用此計劃] 區段中，如果您在您的周邊中部署單一 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="6a0ec-132">您將部署 Edge Server 與私人 IP 位址指派給 Edge Server，並將使用 NAT 網際網路上的外部使用者提供的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">私人 IP 位址及 NAT Lync Server 2013 中的單一合併的 edge</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ec-p109">您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用公用 IP 位址來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="6a0ec-136">使用此計劃] 區段中，如果您在您的周邊中部署單一 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="6a0ec-137">您會使用公用 IP 位址指派給 Edge Server 部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="6a0ec-138">而不是 NAT，您會使用此案例中的路由。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="6a0ec-139">Edge Server 的實際公用 IP 位址是供外部使用者的連線數目。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">與 Lync Server 2013 中的公用 IP 位址的單一合併的 edge</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ec-p111">您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="6a0ec-143">使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="6a0ec-144">您將部署 Edge Server 與私人 IP 位址指派給 Edge Server，使用 DNS 負載平衡集區上散佈的通訊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="6a0ec-145">您將使用 NAT 來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ec-147">您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="6a0ec-148">您也想要用於網際網路 Edge Server 外部介面公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="6a0ec-149">使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="6a0ec-150">您將部署 Edge Server 與公用 IP 位址指派給 Edge Server，使用 DNS 負載平衡集區上散佈的通訊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="6a0ec-151">您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ec-153">您已決定 Edge service 的高可用性是重要給您的使用者，而您將部署兩部，或者使用硬體此集區中的更多 Edge Server 負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="6a0ec-154">使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="6a0ec-155">您將部署 Edge Server 與公用 IP 位址指派給 Edge Server，使用硬體負載平衡器集區上散佈的通訊。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="6a0ec-156">您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中調整式合併的邊緣搭配硬體負載平衡器</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ec-158">您可使用同盟案例來規劃可擴充與使用者進行通訊之協力廠商類型的功能。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="6a0ec-159">Lync Server 同盟</span><span class="sxs-lookup"><span data-stu-id="6a0ec-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="6a0ec-160">Office Communications Server 同盟</span><span class="sxs-lookup"><span data-stu-id="6a0ec-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="6a0ec-161">公共 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6a0ec-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="6a0ec-162">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="6a0ec-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a0ec-163">規劃同盟案例</span><span class="sxs-lookup"><span data-stu-id="6a0ec-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="6a0ec-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 與 Office Communications Server 同盟</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="6a0ec-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">規劃 Lync Server 2013 中的 public instant messaging 連線</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="6a0ec-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中規劃</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ec-167">行動服務提供通過反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="6a0ec-168">服務，可以讓外部使用者的行動性部署上的前端伺服器或前端集區。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="6a0ec-169">您建立或修改現有的發佈規則，以便為外部使用者的行動服務反向 proxy 上。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="6a0ec-170"><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 中的行動規劃</a></span><span class="sxs-lookup"><span data-stu-id="6a0ec-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="6a0ec-171">在下列案例中章節的某些參考架構、 範例 DNS、 連接埠/通訊協定定義和憑證需求。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="6a0ec-172">也包含圖表用於您的 DNS，連接埠/通訊協定定義，而且需要憑證。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="6a0ec-173">圖表會提供您填寫並散發至其他小組 （例如，貴組織的網路小組、 公用金鑰基礎結構小組和伺服器部署小組） 的範本。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="6a0ec-174">圖表的目標是增強的通訊，並確保成功通訊所需的 Edge Server 組態元件會執行實際的人員時組態工作。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="6a0ec-175">我們建議您使用的圖表和相關聯的參考架構規劃您的部署。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

