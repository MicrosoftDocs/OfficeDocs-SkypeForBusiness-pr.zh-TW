---
title: Lync Server 2013：規劃通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7c101ab49d16b01dd35d4fc498f002747cd31cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497810"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2ad2d-102">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="2ad2d-102">Planning for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ad2d-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2ad2d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2ad2d-104">針對整合通訊 (UC) 以 IP 為基礎的應用程式（例如電話語音、影片和應用程式共用），通常不會將商業網路的可用頻寬視為 LAN 環境中的限制因素。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="2ad2d-105">不過，您可以在互連網站的 WAN 連結上限制網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="2ad2d-106">當網路流量的 influx oversubscribes WAN 連結時，會使用目前的機制（例如佇列、緩衝和封包放置）來解析擁塞。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="2ad2d-107">額外的流量通常會延緩，直到網路擁塞越好，否則會中斷流量（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="2ad2d-108">針對傳統的資料流量，在這種情況下，接收用戶端可以復原。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="2ad2d-109">針對即時流量（如整合通訊），無法以這種方式解決網路擁塞問題，因為整合通訊流量對延遲和封包遺失都很重要。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="2ad2d-110">WAN 上的擁塞可能會導致使用者 (QoE) 的經驗品質不良。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="2ad2d-111">針對擁塞狀況中的即時流量，拒絕呼叫比提供品質不良的連線要好。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="2ad2d-112">通話許可控制 (CAC) 會判斷是否有足夠的網路頻寬，可建立可接受品質的即時會話。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="2ad2d-113">在 Lync Server 2013 中，CAC 只會控制音訊和影片的即時流量，但不會影響資料流量。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="2ad2d-114">如果預設 WAN 路徑不具備必要的頻寬，CAC 可以嘗試透過網際網路路徑或公用交換電話網路 (PSTN) 來路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="2ad2d-115">CAC 只能在 Lync Server 中使用。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="2ad2d-116">本節說明通話許可控制功能，並說明如何規劃 CAC。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ad2d-117">Lync Server 具有三個高級 Enterprise Voice 功能：通話許可控制 (CAC) 、緊急服務 (E9-1-1) 和媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="2ad2d-118">如需所有三種功能共同使用的規劃資訊，請參閱 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的「高級 Enterprise Voice 功能」網路設定</A>。</span><span class="sxs-lookup"><span data-stu-id="2ad2d-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2ad2d-119">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2ad2d-119">In This Section</span></span>

  - [<span data-ttu-id="2ad2d-120">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="2ad2d-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="2ad2d-121">在 Lync Server 2013 中定義通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="2ad2d-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="2ad2d-122">範例：在 Lync Server 2013 中收集通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="2ad2d-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="2ad2d-123">Lync Server 2013 中 CAC 的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="2ad2d-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="2ad2d-124">Lync Server 2013 中通話許可控制的最佳作法</span><span class="sxs-lookup"><span data-stu-id="2ad2d-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="2ad2d-125">Lync Server 2013 中的通話許可控制的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="2ad2d-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

