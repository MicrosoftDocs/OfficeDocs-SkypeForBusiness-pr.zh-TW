---
title: Lync Server 2013：轉送伺服器的元件和拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6c824da8eccaec0cb48450b0d81dddcc60f99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="0565d-102">Lync Server 2013 中轉送伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="0565d-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0565d-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0565d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0565d-104">本主題說明轉送伺服器相依的元件，以及可部署轉送伺服器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="0565d-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="0565d-105">相依性</span><span class="sxs-lookup"><span data-stu-id="0565d-105">Dependencies</span></span>

<span data-ttu-id="0565d-106">轉送伺服器具有下列相依性：</span><span class="sxs-lookup"><span data-stu-id="0565d-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="0565d-107">**處長。**</span><span class="sxs-lookup"><span data-stu-id="0565d-107">**Registrar.**</span></span> <span data-ttu-id="0565d-108">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="0565d-108">Required.</span></span> <span data-ttu-id="0565d-109">在與 Lync Server 2013 網路進行轉送伺服器互動時，註冊機構是下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="0565d-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="0565d-110">請注意，除了只包含轉送伺服器的獨立集區之外，也可以在前端伺服器上組合轉送伺服器和註冊機構。</span><span class="sxs-lookup"><span data-stu-id="0565d-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="0565d-111">註冊機構是透過 Survivable Branch 裝置上的轉送伺服器和 PSTN 閘道來組合。</span><span class="sxs-lookup"><span data-stu-id="0565d-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="0565d-112">**監控伺服器。**</span><span class="sxs-lookup"><span data-stu-id="0565d-112">**Monitoring Server.**</span></span> <span data-ttu-id="0565d-113">選用但是強烈建議。</span><span class="sxs-lookup"><span data-stu-id="0565d-113">Optional but highly recommended.</span></span> <span data-ttu-id="0565d-114">監控伺服器可讓轉送伺服器記錄與其媒體會話相關聯的品質計量。</span><span class="sxs-lookup"><span data-stu-id="0565d-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="0565d-115">**Edge Server。**</span><span class="sxs-lookup"><span data-stu-id="0565d-115">**Edge Server.**</span></span> <span data-ttu-id="0565d-116">外部使用者支援所需。</span><span class="sxs-lookup"><span data-stu-id="0565d-116">Required for external user support.</span></span> <span data-ttu-id="0565d-117">Edge Server 可讓轉送伺服器與位於 NAT 或防火牆後面的使用者進行互動。</span><span class="sxs-lookup"><span data-stu-id="0565d-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="0565d-118">拓撲</span><span class="sxs-lookup"><span data-stu-id="0565d-118">Topologies</span></span>

<span data-ttu-id="0565d-119">使用 Standard Edition server、前端集區或 Survivable Branch 裝置上的報名者實例，Lync Server 2013 （轉送伺服器）預設為組合。</span><span class="sxs-lookup"><span data-stu-id="0565d-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="0565d-120">前端集區中的所有轉送伺服器都必須設定相同的。</span><span class="sxs-lookup"><span data-stu-id="0565d-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="0565d-121">在效能問題的情況下，在專用獨立集區中部署一或多個轉送伺服器可能會比較可取。</span><span class="sxs-lookup"><span data-stu-id="0565d-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="0565d-122">或者，如果您要部署 SIP 主幹，我們建議您部署獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="0565d-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="0565d-123">如果您對支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="0565d-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="0565d-124">因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="0565d-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="0565d-125">我們也建議您，只要出現下列情形，如果您已經部署了 IP-PBX 或連線至網際網路電話服務提供者工作階段邊界控制器 (SBC) 時，請在前端集區上組合中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="0565d-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="0565d-126">IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。</span><span class="sxs-lookup"><span data-stu-id="0565d-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="0565d-127">IP-PBX 不支援媒體旁路，但主控轉送伺服器的前端集區可以處理不適用媒體旁路的呼叫語音轉碼。</span><span class="sxs-lookup"><span data-stu-id="0565d-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="0565d-128">您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="0565d-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="0565d-129">如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="0565d-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="0565d-130">如需部署哪些拓撲的詳細資訊，請參閱 [Lync server 2013 中的轉送伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0565d-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="0565d-131">下圖顯示由兩個透過 WAN 連結所連線的網站所組成的簡易拓撲。</span><span class="sxs-lookup"><span data-stu-id="0565d-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="0565d-132">轉送伺服器是使用位於網站1之前端集區上的註冊機構組合。</span><span class="sxs-lookup"><span data-stu-id="0565d-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="0565d-133">網站1上的轉送伺服器會控制網站1上的 PSTN 閘道和 Site 2 上的閘道。</span><span class="sxs-lookup"><span data-stu-id="0565d-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="0565d-134">在此拓撲中，會以全域方式啟用媒體旁路，以使用網站與地區資訊，並將主幹至每個 PSTN 閘道 (GW1 和 GW2) 已啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="0565d-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="0565d-135">**透過 WAN 連結所連線的網站範例，其中網站1上有轉送伺服器和 Site 2 上的 PSTN 閘道**</span><span class="sxs-lookup"><span data-stu-id="0565d-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="0565d-136">![轉送伺服器 WAN 閘道的語音拓撲](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "轉送伺服器 WAN 閘道的語音拓撲")</span><span class="sxs-lookup"><span data-stu-id="0565d-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="0565d-137">下圖顯示一種簡單的拓撲，其中的轉送伺服器是與網站1之前端集區上的註冊機構組合，且具有 Site 1 上的 IP-PBX 的直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="0565d-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="0565d-138">在此圖中，轉送伺服器也會控制網站2上的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0565d-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="0565d-139">假設 Lync 使用者同時存在於網站1和2。</span><span class="sxs-lookup"><span data-stu-id="0565d-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="0565d-140">此外，假設 IP-PBX 有一個相關聯的媒體處理器，必須透過來自 Lync 端點的所有媒體進行遍歷，然後才會將其傳送至 IP-PBX 所控制的媒體端點。</span><span class="sxs-lookup"><span data-stu-id="0565d-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="0565d-141">在此拓撲中，會以全域方式啟用媒體旁路，以使用網站與地區資訊，並將主幹至 PBX 和 PSTN 閘道以啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0565d-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="0565d-142">**透過 WAN 連結所連線的網站範例，其中網站1上的轉送伺服器與 Site 2 上的 PBX**</span><span class="sxs-lookup"><span data-stu-id="0565d-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="0565d-143">![語音拓撲轉送伺服器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "語音拓撲轉送伺服器 WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="0565d-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="0565d-144">如需有關規劃 PBX 拓撲的詳細資訊，請參閱 lync server 2013 的中繼 [伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md) 和 [lync server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)。</span><span class="sxs-lookup"><span data-stu-id="0565d-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="0565d-145">本主題的最後一個圖顯示的拓撲，轉送伺服器會連線至網際網路電話語音服務提供者的 SBC。</span><span class="sxs-lookup"><span data-stu-id="0565d-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="0565d-146">如需 SIP 主幹拓撲的詳細資訊，請參閱 [Lync Server 2013 中的 SIP](lync-server-2013-sip-trunking.md)主幹。</span><span class="sxs-lookup"><span data-stu-id="0565d-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

