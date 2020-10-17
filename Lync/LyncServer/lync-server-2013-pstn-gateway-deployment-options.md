---
title: Lync Server 2013： PSTN 閘道部署選項
description: Lync Server 2013： PSTN 閘道部署選項。
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
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565589"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="5cee4-103">Lync Server 2013 中的 PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="5cee4-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cee4-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5cee4-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="5cee4-105">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="5cee4-105">PSTN Gateways</span></span>

<span data-ttu-id="5cee4-106">公用交換電話網路 (PSTN) 閘道是協力廠商硬體元件，可直接或透過連接至 SIP 主幹，在企業語音基礎結構與 PSTN 之間轉譯信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="5cee4-106">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="5cee4-107">在任一拓撲中，閘道會終止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="5cee4-107">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="5cee4-108">閘道會隔離在其自己的子網中，並透過轉送伺服器連線至商業網路。</span><span class="sxs-lookup"><span data-stu-id="5cee4-108">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="5cee4-109">具有多個網站的企業通常會在每個網站上部署一或多個閘道。</span><span class="sxs-lookup"><span data-stu-id="5cee4-109">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="5cee4-110">分支網站可以透過閘道或透過 Survivable 分支裝置連接至 PSTN，此裝置會將閘道和伺服器結合到單一方塊中。</span><span class="sxs-lookup"><span data-stu-id="5cee4-110">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="5cee4-111">如果分支網站使用閘道，則網站上必須有註冊機構和轉送伺服器，除非 WAN 連結可復原。</span><span class="sxs-lookup"><span data-stu-id="5cee4-111">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="5cee4-112">在前端伺服器上組合的一或多個轉送伺服器，可在每個網站上路由傳送一或多個閘道的來電。</span><span class="sxs-lookup"><span data-stu-id="5cee4-112">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="5cee4-113">建議將網站上的註冊機構、轉送伺服器和閘道部署為 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="5cee4-113">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="5cee4-114">決定 PSTN 閘道的數量、大小和位置可能是規劃企業語音基礎結構時必須進行的最重要且昂貴的決策。</span><span class="sxs-lookup"><span data-stu-id="5cee4-114">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="5cee4-115">以下是需要考慮的主要問題。</span><span class="sxs-lookup"><span data-stu-id="5cee4-115">Here are the main questions to consider.</span></span> <span data-ttu-id="5cee4-116">請記住，這些問題的答案都是相互依賴的</span><span class="sxs-lookup"><span data-stu-id="5cee4-116">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="5cee4-117">需要多少 PSTN 閘道？</span><span class="sxs-lookup"><span data-stu-id="5cee4-117">How many PSTN gateways are needed?</span></span> <span data-ttu-id="5cee4-118">其答案取決於使用者數目、預期同時通話的數目 (流量負載) ，以及每個網站 (的網站數目) 一個。</span><span class="sxs-lookup"><span data-stu-id="5cee4-118">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="5cee4-119">閘道應該是什麼大小？</span><span class="sxs-lookup"><span data-stu-id="5cee4-119">What size should the gateways be?</span></span> <span data-ttu-id="5cee4-120">其答案取決於網站上的使用者人數及流量負載。</span><span class="sxs-lookup"><span data-stu-id="5cee4-120">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="5cee4-121">閘道應位於何處？</span><span class="sxs-lookup"><span data-stu-id="5cee4-121">Where should the gateways be located?</span></span> <span data-ttu-id="5cee4-122">其答案部分取決於拓撲，以及組織地理位置發佈的部分。</span><span class="sxs-lookup"><span data-stu-id="5cee4-122">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="5cee4-123">您也應該考慮閘道拓撲選項 (如需詳細資訊，請參閱本主題稍後的閘道拓撲) 。</span><span class="sxs-lookup"><span data-stu-id="5cee4-123">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="5cee4-124">M:N 主幹支援</span><span class="sxs-lookup"><span data-stu-id="5cee4-124">M:N Trunk Support</span></span>

<span data-ttu-id="5cee4-125">轉送伺服器可以透過多個閘道、會話邊界控制器 (SBCs) Internet 電話語音服務提供者所提供的電話，或是二者的組合，進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="5cee4-125">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="5cee4-126">此外，集區中的多個轉送伺服器可以與多個閘道互動。</span><span class="sxs-lookup"><span data-stu-id="5cee4-126">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="5cee4-127">在轉送伺服器與閘道之間定義的邏輯路由稱為 *主幹*。</span><span class="sxs-lookup"><span data-stu-id="5cee4-127">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="5cee4-128">當內部使用者加入 PSTN 通話時，前端集區上的輸出路由邏輯會選擇哪一個主幹可路由傳送該特定通話的所有可能可使用的組合。</span><span class="sxs-lookup"><span data-stu-id="5cee4-128">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="5cee4-129">使用 DNS 負載平衡，如果呼叫因集區中的特定轉送伺服器問題而無法抵達閘道，則會將此呼叫重試至集區中的替代轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="5cee4-129">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="5cee4-130">如需規劃多個閘道的詳細資訊，請參閱 [M:N 主幹 In Lync Server 2013](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="5cee4-130">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="5cee4-131">如需其他輸出路由增強功能的詳細資訊，請參閱 [Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="5cee4-131">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="5cee4-132">閘道拓撲</span><span class="sxs-lookup"><span data-stu-id="5cee4-132">Gateway Topologies</span></span>

<span data-ttu-id="5cee4-133">當您考慮閘道部署的基本問題時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5cee4-133">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="5cee4-134">使用 Enterprise Voice，計算您想要提供 PSTN 連線的網站數目。</span><span class="sxs-lookup"><span data-stu-id="5cee4-134">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="5cee4-135">評估每個網站的流量 (使用者數目，以及每個使用者) 每小時平均通話數目。</span><span class="sxs-lookup"><span data-stu-id="5cee4-135">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="5cee4-136">在每個網站部署一或多個閘道，以處理預期的流量。</span><span class="sxs-lookup"><span data-stu-id="5cee4-136">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="5cee4-137">產生的分散式閘道拓撲如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="5cee4-137">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="5cee4-138">**分散式閘道拓撲**</span><span class="sxs-lookup"><span data-stu-id="5cee4-138">**Distributed gateway topology**</span></span>

<span data-ttu-id="5cee4-139">![分散式閘道拓撲圖表](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分散式閘道拓撲圖表")</span><span class="sxs-lookup"><span data-stu-id="5cee4-139">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="5cee4-140">透過此拓撲，每個網站和兩個網站之間的工作人員間的通話都會透過您的內部網路進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="5cee4-140">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="5cee4-141">對 PSTN 所進行的呼叫會透過企業 IP 網路路由傳送至最接近目的地號碼位置的閘道。不過，如果您的組織支援數十或數百甚至數千部的網站分散于一或多個洲，那麼許多金融機構和其他大型企業會這麼做？</span><span class="sxs-lookup"><span data-stu-id="5cee4-141">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="5cee4-142">在這種情況下，在每個網站部署個別的閘道是不可行的。</span><span class="sxs-lookup"><span data-stu-id="5cee4-142">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="5cee4-143">若要解決此問題，許多大型公司喜歡部署一個或幾個大型電話語音中央網站，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="5cee4-143">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="5cee4-144">**電話語音中央網站拓撲**</span><span class="sxs-lookup"><span data-stu-id="5cee4-144">**Telephony central site topology**</span></span>

<span data-ttu-id="5cee4-145">![資料中心閘道拓撲](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "資料中心閘道拓撲")</span><span class="sxs-lookup"><span data-stu-id="5cee4-145">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="5cee4-146">在此拓撲中，會在每個中央網站上部署數個足以容納預期使用者負載的大型閘道。</span><span class="sxs-lookup"><span data-stu-id="5cee4-146">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="5cee4-147">企業的所有呼叫都是由公司的電話服務提供者轉接至中央網站。</span><span class="sxs-lookup"><span data-stu-id="5cee4-147">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="5cee4-148">中央網站的路由邏輯會決定是否要透過內部網路或 PSTN 路由傳送呼叫。</span><span class="sxs-lookup"><span data-stu-id="5cee4-148">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="5cee4-149">閘道位置</span><span class="sxs-lookup"><span data-stu-id="5cee4-149">Gateway Location</span></span>

<span data-ttu-id="5cee4-150">閘道位置也可以決定您選擇的閘道類型及設定方式。</span><span class="sxs-lookup"><span data-stu-id="5cee4-150">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="5cee4-151">有許多 PSTN 通訊協定，都不是全球標準。</span><span class="sxs-lookup"><span data-stu-id="5cee4-151">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="5cee4-152">如果您的所有閘道都位於單一國家/地區內，這不是問題，但是如果您在多個國家/地區內找到閘道，則每個國家/地區都必須根據該國家/地區的 PSTN 標準進行設定。</span><span class="sxs-lookup"><span data-stu-id="5cee4-152">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="5cee4-153">此外，認證于中運作的閘道（例如，加拿大）可能無法在印度、巴西或歐盟進行認證。</span><span class="sxs-lookup"><span data-stu-id="5cee4-153">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="5cee4-154">閘道大小和數目</span><span class="sxs-lookup"><span data-stu-id="5cee4-154">Gateway Size and Number</span></span>

<span data-ttu-id="5cee4-155">大多陣列織會考慮採用從2到高達960埠的大小部署範圍的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="5cee4-155">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="5cee4-156"> (甚至更大的閘道，但是主要是由電話服務提供者使用。 ) 當您的組織需要的埠數目進行估計時，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="5cee4-156">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="5cee4-157">每位使用者每小時一次 PSTN 通話的組織 (每小時一次 PSTN 通話) 應該為每15位使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="5cee4-157">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="5cee4-158">例如，如果您有20位使用者，則需要有兩個埠的閘道。</span><span class="sxs-lookup"><span data-stu-id="5cee4-158">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="5cee4-159">組織使用適中的電話語音流量 (每個使用者每小時兩個 PSTN 通話) 每10位使用者都應該為一個埠指派。</span><span class="sxs-lookup"><span data-stu-id="5cee4-159">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="5cee4-160">例如，如果您有100位使用者，則需要在一或多個閘道間分攤10個埠。</span><span class="sxs-lookup"><span data-stu-id="5cee4-160">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="5cee4-161">使用大量電話語音使用的組織 (每位使用者每小時三個或更多 PSTN 通話) 應該為每五位使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="5cee4-161">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="5cee4-162">例如，如果您有47000位使用者，則需要至少10個大型閘道中所分配的9400埠總數。</span><span class="sxs-lookup"><span data-stu-id="5cee4-162">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="5cee4-163">當您組織中的使用者人數或流量量增加時，可以取得額外的埠。</span><span class="sxs-lookup"><span data-stu-id="5cee4-163">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="5cee4-164">針對您必須支援的任何特定使用者數目，您可以選擇部署較少、更大的閘道或較小的閘道。</span><span class="sxs-lookup"><span data-stu-id="5cee4-164">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="5cee4-165">一般來說，如果一個閘道失敗時，建議至少有兩個組織閘道可維護可用性。</span><span class="sxs-lookup"><span data-stu-id="5cee4-165">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="5cee4-166">您部署的每個 PSTN 閘道都必須至少有一個對應的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="5cee4-166">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

