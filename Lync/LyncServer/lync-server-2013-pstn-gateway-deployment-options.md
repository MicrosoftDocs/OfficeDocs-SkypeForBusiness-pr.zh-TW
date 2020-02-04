---
title: Lync Server 2013：PSTN 閘道部署選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="1947d-102">Lync Server 2013 中的 PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="1947d-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1947d-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1947d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="1947d-104">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="1947d-104">PSTN Gateways</span></span>

<span data-ttu-id="1947d-105">公用交換電話網絡（PSTN）閘道是協力廠商硬體元件，可直接或透過連線至 SIP trunks，在企業語音結構和 PSTN 之間轉換信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="1947d-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="1947d-106">在其中一個拓撲中，閘道會終止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="1947d-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="1947d-107">閘道會隔離在自己的子網中，並透過轉送伺服器連線到商業網路。</span><span class="sxs-lookup"><span data-stu-id="1947d-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="1947d-108">具有多個網站的企業通常會在每個網站上部署一個或多個閘道。</span><span class="sxs-lookup"><span data-stu-id="1947d-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="1947d-109">分支網站可以透過閘道或透過 Survivable 分支裝置連線到 PSTN，這會將閘道與伺服器結合在單一方塊中。</span><span class="sxs-lookup"><span data-stu-id="1947d-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="1947d-110">如果分支網站使用閘道，則會在網站上需要註冊機構和中繼伺服器，除非 WAN 連結是復原的。</span><span class="sxs-lookup"><span data-stu-id="1947d-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="1947d-111">一或多個在前端伺服器上 collocated 的中繼伺服器可以在每個網站上傳送一或多個閘道的呼叫。</span><span class="sxs-lookup"><span data-stu-id="1947d-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="1947d-112">我們建議您將網站上所需的註冊機構、中繼伺服器和閘道部署為 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="1947d-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="1947d-113">確定 PSTN 閘道的數目、大小及位置，可能是規劃企業語音基礎結構時必須做出的最重要且昂貴的決策。</span><span class="sxs-lookup"><span data-stu-id="1947d-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="1947d-114">以下是要考慮的主要問題。</span><span class="sxs-lookup"><span data-stu-id="1947d-114">Here are the main questions to consider.</span></span> <span data-ttu-id="1947d-115">請記住，這些問題的答案全都相互依賴</span><span class="sxs-lookup"><span data-stu-id="1947d-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="1947d-116">需要多少 PSTN 閘道？</span><span class="sxs-lookup"><span data-stu-id="1947d-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="1947d-117">答案取決於使用者數目、預期的同時通話數（流量負載），以及網站數量（每個網站需要一個）。</span><span class="sxs-lookup"><span data-stu-id="1947d-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="1947d-118">閘道應該是什麼大小？</span><span class="sxs-lookup"><span data-stu-id="1947d-118">What size should the gateways be?</span></span> <span data-ttu-id="1947d-119">答案視網站上的使用者數目和流量負荷而定。</span><span class="sxs-lookup"><span data-stu-id="1947d-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="1947d-120">閘道應該位於何處？</span><span class="sxs-lookup"><span data-stu-id="1947d-120">Where should the gateways be located?</span></span> <span data-ttu-id="1947d-121">答案是在拓撲的一部分，以及貴組織的地理位置分佈所組成。</span><span class="sxs-lookup"><span data-stu-id="1947d-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="1947d-122">您也應該考慮閘道拓朴選項（如需詳細資訊，請參閱本主題稍後的閘道拓撲）。</span><span class="sxs-lookup"><span data-stu-id="1947d-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="1947d-123">M:N 幹線支援</span><span class="sxs-lookup"><span data-stu-id="1947d-123">M:N Trunk Support</span></span>

<span data-ttu-id="1947d-124">中繼伺服器可透過多個閘道、網際網路電話服務提供者所提供的會話邊界控制器（SBCs），或這兩者的組合，路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="1947d-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="1947d-125">此外，池中的多個轉送伺服器可以與多個閘道互動。</span><span class="sxs-lookup"><span data-stu-id="1947d-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="1947d-126">在中繼伺服器和閘道之間定義的邏輯路由稱為*主幹*。</span><span class="sxs-lookup"><span data-stu-id="1947d-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="1947d-127">當內部使用者進行 PSTN 通話時，前端池上的輸出路由邏輯會選擇要路由超出所有可能可供路由該特定呼叫的組合。</span><span class="sxs-lookup"><span data-stu-id="1947d-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="1947d-128">使用 DNS 負載平衡時，如果由於池中的特定中繼伺服器問題而導致呼叫無法接通閘道，該呼叫將會重試至池中的備用轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="1947d-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="1947d-129">如需規劃多個閘道的詳細資料，請參閱[Lync Server 2013 中的 M:N 幹線](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="1947d-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="1947d-130">如需其他輸出路由增強功能的詳細資料，請參閱[Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="1947d-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="1947d-131">閘道拓撲</span><span class="sxs-lookup"><span data-stu-id="1947d-131">Gateway Topologies</span></span>

<span data-ttu-id="1947d-132">當您考慮閘道部署的基本問題時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1947d-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="1947d-133">使用企業語音來計算您想要提供 PSTN 連線性的網站數目。</span><span class="sxs-lookup"><span data-stu-id="1947d-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="1947d-134">估計每個網站的流量（使用者數及每個使用者每小時的平均通話數）。</span><span class="sxs-lookup"><span data-stu-id="1947d-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="1947d-135">在每個網站部署一或多個閘道，以處理預期的流量。</span><span class="sxs-lookup"><span data-stu-id="1947d-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="1947d-136">產生的分散式閘道拓撲如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="1947d-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="1947d-137">**分散式閘道拓朴**</span><span class="sxs-lookup"><span data-stu-id="1947d-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="1947d-138">![分散式閘道拓撲圖表](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分散式閘道拓撲圖表")</span><span class="sxs-lookup"><span data-stu-id="1947d-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="1947d-139">在這個拓朴中，每個網站的工作人員之間以及網站之間的呼叫都是在您的內部網路上路由。</span><span class="sxs-lookup"><span data-stu-id="1947d-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="1947d-140">對 PSTN 的呼叫會在企業 IP 網路上路由至最接近目的地號碼位置的閘道。但是，如果您的組織支援數十或幾百或甚至上千個以上的網站散佈在一或多個洲，那麼許多金融機構和其他大型企業都有這麼做？</span><span class="sxs-lookup"><span data-stu-id="1947d-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="1947d-141">在這種情況下，在每個網站上部署個別的閘道並不是不切實際的。</span><span class="sxs-lookup"><span data-stu-id="1947d-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="1947d-142">若要解決此問題，許多大型公司都想要部署一個或幾個大型電話中心網站，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="1947d-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="1947d-143">**電話中心網站拓撲**</span><span class="sxs-lookup"><span data-stu-id="1947d-143">**Telephony central site topology**</span></span>

<span data-ttu-id="1947d-144">![資料中心閘道拓撲](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "資料中心閘道拓撲")</span><span class="sxs-lookup"><span data-stu-id="1947d-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="1947d-145">在這個拓朴中，有幾個大型閘道足以容納預期的使用者負載，就是在每一個中央網站部署。</span><span class="sxs-lookup"><span data-stu-id="1947d-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="1947d-146">企業中的所有使用者呼叫都是由公司的電話服務提供者轉寄至中心網站。</span><span class="sxs-lookup"><span data-stu-id="1947d-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="1947d-147">中央網站上的路由邏輯可決定是否要在內部網路或 PSTN 路由通話。</span><span class="sxs-lookup"><span data-stu-id="1947d-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="1947d-148">閘道位置</span><span class="sxs-lookup"><span data-stu-id="1947d-148">Gateway Location</span></span>

<span data-ttu-id="1947d-149">閘道位置也可以決定您選擇的閘道類型，以及它們的設定方式。</span><span class="sxs-lookup"><span data-stu-id="1947d-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="1947d-150">有許多 PSTN 通訊協定，都不是世界標準。</span><span class="sxs-lookup"><span data-stu-id="1947d-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="1947d-151">如果您的所有閘道都位於單一的國家/地區，這不是問題，但如果您在多個國家/地區中找到閘道，則必須根據該國家/地區的 PSTN 標準進行設定。</span><span class="sxs-lookup"><span data-stu-id="1947d-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="1947d-152">此外，經認證的閘道（例如加拿大），可能無法在印度、巴西或歐盟進行認證。</span><span class="sxs-lookup"><span data-stu-id="1947d-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="1947d-153">閘道大小與數位</span><span class="sxs-lookup"><span data-stu-id="1947d-153">Gateway Size and Number</span></span>

<span data-ttu-id="1947d-154">大多陣列織都要考慮部署範圍的 PSTN 閘道，其大小必須是2到960埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="1947d-155">（甚至是更大的閘道，但主要是由電話服務提供者使用。）估計貴組織所需的埠數時，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="1947d-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="1947d-156">使用輕型電話使用的組織（每個小時每個使用者一個 PSTN 通話）應該為每15個使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="1947d-157">例如，如果您有20個使用者，就需要一個具有兩個埠的閘道。</span><span class="sxs-lookup"><span data-stu-id="1947d-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="1947d-158">具有中等電話使用方式（每個使用者每小時兩個 PSTN 通話）的組織應該為每10個使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="1947d-159">例如，如果您有100使用者，您將需要在一或多個閘道間分配10個埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="1947d-160">具有大量電話使用的組織（每小時每位使用者有三個或更多個 PSTN 通話）應該為每五位使用者指派一個埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="1947d-161">例如，如果您有47000使用者，您需要在至少10個大型閘道之間分配的9400埠總數。</span><span class="sxs-lookup"><span data-stu-id="1947d-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="1947d-162">在貴組織中的使用者數目或流量增加時，可以取得額外的埠。</span><span class="sxs-lookup"><span data-stu-id="1947d-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="1947d-163">針對您必須支援的任何特定使用者數，您可以選擇部署較少、較大的閘道或較小的閘道。</span><span class="sxs-lookup"><span data-stu-id="1947d-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="1947d-164">就規則而言，建議組織至少有兩個閘道，才能在一個閘道失敗時維持可用性。</span><span class="sxs-lookup"><span data-stu-id="1947d-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="1947d-165">您部署的每個 PSTN 閘道都必須至少有一個相對應的產生轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="1947d-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

