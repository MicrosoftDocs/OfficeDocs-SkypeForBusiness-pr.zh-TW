---
title: Lync Server 2013：中繼伺服器的元件和拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="cc135-102">Lync Server 2013 中之中繼伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="cc135-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc135-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cc135-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cc135-104">本主題描述的是中繼伺服器所依賴的元件，以及可在其中部署中繼伺服器的拓撲</span><span class="sxs-lookup"><span data-stu-id="cc135-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="cc135-105">因素</span><span class="sxs-lookup"><span data-stu-id="cc135-105">Dependencies</span></span>

<span data-ttu-id="cc135-106">中繼伺服器具有下列相依性：</span><span class="sxs-lookup"><span data-stu-id="cc135-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="cc135-107">**註冊機構.**</span><span class="sxs-lookup"><span data-stu-id="cc135-107">**Registrar.**</span></span> <span data-ttu-id="cc135-108">必填。</span><span class="sxs-lookup"><span data-stu-id="cc135-108">Required.</span></span> <span data-ttu-id="cc135-109">註冊機構是在與 Lync Server 2013 網路進行中繼伺服器互動時的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="cc135-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="cc135-110">請注意，除了在僅包含轉送伺服器的獨立池中安裝外，還可以在前端伺服器與註冊機構 collocated 的情況下，進行中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc135-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="cc135-111">註冊機構是在 Survivable 分支裝置上使用中繼伺服器和 PSTN 閘道進行 collocated。</span><span class="sxs-lookup"><span data-stu-id="cc135-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="cc135-112">**監視伺服器。**</span><span class="sxs-lookup"><span data-stu-id="cc135-112">**Monitoring Server.**</span></span> <span data-ttu-id="cc135-113">選擇性，但強烈建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="cc135-113">Optional but highly recommended.</span></span> <span data-ttu-id="cc135-114">監視伺服器可讓中繼伺服器記錄與其媒體會話相關聯的品質指標。</span><span class="sxs-lookup"><span data-stu-id="cc135-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="cc135-115">**Edge 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="cc135-115">**Edge Server.**</span></span> <span data-ttu-id="cc135-116">外部使用者支援所需。</span><span class="sxs-lookup"><span data-stu-id="cc135-116">Required for external user support.</span></span> <span data-ttu-id="cc135-117">Edge 伺服器可讓中繼伺服器與位於 NAT 或防火牆背後的使用者進行互動。</span><span class="sxs-lookup"><span data-stu-id="cc135-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="cc135-118">形</span><span class="sxs-lookup"><span data-stu-id="cc135-118">Topologies</span></span>

<span data-ttu-id="cc135-119">Lync Server 2013 的中繼伺服器是預設的 collocated，其中包含標準版 Server、前端池或 Survivable 分支裝置上的註冊機構實例。</span><span class="sxs-lookup"><span data-stu-id="cc135-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="cc135-120">前端池中的所有中繼伺服器都必須設定相同的配置。</span><span class="sxs-lookup"><span data-stu-id="cc135-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="cc135-121">在發生效能問題的情況下，最好是在專用獨立的池中部署一或多個轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc135-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="cc135-122">或者，如果您要部署 SIP 中繼，我們建議您部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="cc135-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="cc135-123">如果您在支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署直接 SIP 連線，則不需要獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="cc135-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="cc135-124">不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。</span><span class="sxs-lookup"><span data-stu-id="cc135-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="cc135-125">我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：</span><span class="sxs-lookup"><span data-stu-id="cc135-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="cc135-126">IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc135-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="cc135-127">Ip-pbx 不支援媒體旁路，但是託管轉送伺服器的前端池可以處理語音轉換，以取得不需要媒體旁路的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc135-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="cc135-128">您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="cc135-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="cc135-129">如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="cc135-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="cc135-130">如需部署何種拓撲的詳細資料，請參閱[Lync server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cc135-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="cc135-131">下圖顯示由 WAN 連結所連接的兩個網站所組成的簡單拓撲。</span><span class="sxs-lookup"><span data-stu-id="cc135-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="cc135-132">在網站1上，將 collocated 伺服器與前端池中的註冊機構進行。</span><span class="sxs-lookup"><span data-stu-id="cc135-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="cc135-133">網站1的中繼伺服器控制網站1的 PSTN 閘道和網站2的閘道。</span><span class="sxs-lookup"><span data-stu-id="cc135-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="cc135-134">在此拓朴中，會使用 [媒體旁路] 來全域性地使用網站和區域資訊，而每個 PSTN 閘道的 trunks （GW1 和 GW2）都已啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="cc135-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="cc135-135">**在 site 1 與網站2上的中繼伺服器連線之 WAN 連結的網站範例**</span><span class="sxs-lookup"><span data-stu-id="cc135-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="cc135-136">使用仲介(images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "伺服器 Wan 閘道")的 [![中繼伺服器 wan 閘道]] 語音拓撲的語音拓撲</span><span class="sxs-lookup"><span data-stu-id="cc135-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="cc135-137">下圖顯示的是一種簡單的拓撲，其中的中繼伺服器是與位於 Site 1 之前端池的註冊機構 collocated，並與 Site 1 的 IP PBX 具有直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="cc135-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="cc135-138">在此圖中，中繼伺服器也會控制網站2的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="cc135-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="cc135-139">假設 Lync 使用者同時存在於網站1和2。</span><span class="sxs-lookup"><span data-stu-id="cc135-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="cc135-140">另外，假設 IP PBX 有一個相關聯的媒體處理器，必須由所有源自 Lync 端點的媒體來遍歷，然後才能傳送到由 IP PBX 控制的媒體端點。</span><span class="sxs-lookup"><span data-stu-id="cc135-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="cc135-141">在此拓朴中，會使用 [媒體旁路] 來全域啟用網站和區域資訊，而 PBX 和 PSTN 閘道的 trunks 已啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="cc135-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="cc135-142">**在 site 1 和 PBX 伺服器上，由 WAN 連結與在 site 2 上的中繼伺服器連線的網站範例**</span><span class="sxs-lookup"><span data-stu-id="cc135-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="cc135-143">![語音拓撲中繼伺服器 WAN pbx](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "語音拓撲中繼伺服器 wan pbx")</span><span class="sxs-lookup"><span data-stu-id="cc135-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="cc135-144">如需有關 PBX 拓朴規劃的詳細資訊，請參閱 lync server [2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)和[lync server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)。</span><span class="sxs-lookup"><span data-stu-id="cc135-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="cc135-145">本主題中的最後一個圖表顯示的是將中繼伺服器連線至網際網路電話服務提供者之 SBC 的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cc135-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="cc135-146">如需 SIP 中繼拓撲的詳細資料，請參閱[Lync Server 2013 中的 sip 中繼](lync-server-2013-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="cc135-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

