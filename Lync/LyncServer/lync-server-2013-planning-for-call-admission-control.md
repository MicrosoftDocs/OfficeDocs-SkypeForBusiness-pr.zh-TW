---
title: Lync Server 2013：規劃通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7214e-102">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="7214e-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7214e-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7214e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7214e-104">針對以 IP 為基礎（例如電話、影片和應用程式共用）的整合通訊（UC）應用程式，商業網路的可用頻寬通常不會被視為在局域網環境中的限制因素。</span><span class="sxs-lookup"><span data-stu-id="7214e-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="7214e-105">不過，在互連網站的 WAN 連結上，網路頻寬可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="7214e-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="7214e-106">當 influx 網路流量 oversubscribes WAN 連結時，會使用目前的機制（例如排隊、緩衝及資料包刪除）來解決擁塞問題。</span><span class="sxs-lookup"><span data-stu-id="7214e-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="7214e-107">額外的流量通常會延遲到網路擁塞，或如有必要，通信量遭到中斷。</span><span class="sxs-lookup"><span data-stu-id="7214e-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="7214e-108">針對傳統的資料流量，在這種情況下，接收用戶端可以復原。</span><span class="sxs-lookup"><span data-stu-id="7214e-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="7214e-109">針對即時流量（例如整合通訊），網路擁塞無法以這種方式解決，因為整合通訊流量對延遲與資料包遺失都是敏感的。</span><span class="sxs-lookup"><span data-stu-id="7214e-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="7214e-110">WAN 上的擁塞可能會導致使用者的體驗品質不佳（QoE）。</span><span class="sxs-lookup"><span data-stu-id="7214e-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="7214e-111">針對在擁塞情況下的即時流量，最好是拒絕呼叫，而不是提供品質欠佳的連接。</span><span class="sxs-lookup"><span data-stu-id="7214e-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="7214e-112">通話許可控制（CAC）會判斷是否有足夠的網路頻寬來建立可接受品質的即時會話。</span><span class="sxs-lookup"><span data-stu-id="7214e-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="7214e-113">在 Lync Server 2013 中，CAC 只會控制音訊和影片的即時流量，但不會影響資料流量。</span><span class="sxs-lookup"><span data-stu-id="7214e-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="7214e-114">如果預設 WAN 路徑沒有所需的頻寬，CAC 可以嘗試透過網際網路路徑或公用的交換電話網絡（PSTN）傳送通話。</span><span class="sxs-lookup"><span data-stu-id="7214e-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="7214e-115">CAC 只適用于 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="7214e-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="7214e-116">本節說明呼叫許可控制功能，並說明如何規劃 CAC。</span><span class="sxs-lookup"><span data-stu-id="7214e-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7214e-117">Lync Server 有三個高級企業語音功能： [呼叫許可控制] （CAC）、緊急服務（E9-1-1），以及 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="7214e-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="7214e-118">如需所有這三項功能共有的規劃資訊的概覽，請參閱<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的 [高級企業語音功能] 的網路設定</A>。</span><span class="sxs-lookup"><span data-stu-id="7214e-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7214e-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="7214e-119">In This Section</span></span>

  - [<span data-ttu-id="7214e-120">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="7214e-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="7214e-121">在 Lync Server 2013 中定義通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="7214e-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="7214e-122">範例：在 Lync Server 2013 中收集您對通話許可控制的需求</span><span class="sxs-lookup"><span data-stu-id="7214e-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="7214e-123">Lync Server 2013 中 CAC 的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="7214e-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="7214e-124">Lync Server 2013 中通話許可控制的最佳做法</span><span class="sxs-lookup"><span data-stu-id="7214e-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="7214e-125">Lync Server 2013 中的通話許可控制的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="7214e-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

