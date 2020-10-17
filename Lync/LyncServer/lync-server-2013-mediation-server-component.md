---
title: Lync Server 2013：轉送伺服器元件
description: Lync Server 2013：轉送伺服器元件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568639"
---
# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="df672-103">Lync Server 2013 中的轉送伺服器元件</span><span class="sxs-lookup"><span data-stu-id="df672-103">Mediation Server component in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df672-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="df672-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="df672-105">您必須部署 Lync Server 2013，轉送伺服器（如果您部署企業語音工作負載）。</span><span class="sxs-lookup"><span data-stu-id="df672-105">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="df672-106">本節說明基本功能、相依性、基本拓撲以及規劃指南。</span><span class="sxs-lookup"><span data-stu-id="df672-106">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="df672-107">轉送伺服器會在您的內部 Lync Server 2013、企業語音基礎結構和公用交換電話網路 (PSTN) 閘道或會話初始通訊協定 (SIP) 主幹之間，轉譯信號，並在某些設定中使用媒體。</span><span class="sxs-lookup"><span data-stu-id="df672-107">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="df672-108">在 Lync Server 2013 端上，轉送伺服器會接聽單一相互 TLS (MTLS) transport address。</span><span class="sxs-lookup"><span data-stu-id="df672-108">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="df672-109">在閘道端，中繼伺服器會在所有與＜拓撲＞文件中所定義之主幹相關聯的相關聆聽連接埠上聆聽。</span><span class="sxs-lookup"><span data-stu-id="df672-109">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="df672-110">所有合格的閘道都必須支援 TLS，不過也可以一併啟用 TCP。</span><span class="sxs-lookup"><span data-stu-id="df672-110">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="df672-111">不支援 TLS 的閘道，仍舊可以支援 TCP。</span><span class="sxs-lookup"><span data-stu-id="df672-111">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="df672-112">如果您的環境中也有現有的公用分支 Exchange (PBX) ，轉送伺服器會處理 Enterprise Voice 使用者和 PBX 之間的呼叫。</span><span class="sxs-lookup"><span data-stu-id="df672-112">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="df672-113">如果您的 PBX 為 IP-PBX，您可以在 PBX 和轉送伺服器之間建立直接的 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="df672-113">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="df672-114">如果您的 PBX 為分多工 (TDM) PBX，您也必須在轉送伺服器和 PBX 之間部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="df672-114">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="df672-115">根據預設，轉送伺服器會與前端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="df672-115">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="df672-116">轉送伺服器也可以部署在獨立集區中以取得效能原因，或者，如果您要部署 SIP 主幹，強烈建議使用獨立集區。</span><span class="sxs-lookup"><span data-stu-id="df672-116">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="df672-117">如果您對支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="df672-117">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="df672-118">因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="df672-118">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="df672-119">我們也建議您，只要出現下列情形，如果您已經部署了 IP-PBX 或連線至網際網路電話服務提供者工作階段邊界控制器 (SBC) 時，請在前端集區上組合中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="df672-119">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="df672-120">IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。</span><span class="sxs-lookup"><span data-stu-id="df672-120">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="df672-121">IP-PBX 不支援媒體旁路，但主控轉送伺服器的前端集區可以處理不適用媒體旁路的呼叫語音轉碼。</span><span class="sxs-lookup"><span data-stu-id="df672-121">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="df672-122">您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="df672-122">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="df672-123">如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="df672-123">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="df672-124">轉送伺服器的主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="df672-124">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="df672-125">在 Lync Server 端加密及解密 SRTP</span><span class="sxs-lookup"><span data-stu-id="df672-125">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="df672-126">將透過 TCP 的 SIP (對於不支援 TLS 的閘道) 轉譯為透過相互 TLS 的 SIP</span><span class="sxs-lookup"><span data-stu-id="df672-126">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="df672-127">在 Lync Server 與轉送伺服器的閘道對等之間轉譯媒體資料流程</span><span class="sxs-lookup"><span data-stu-id="df672-127">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="df672-128">將網路外部的用戶端連線到內部 ICE 元件，這些元件可以讓媒體周遊 NAT 與防火牆</span><span class="sxs-lookup"><span data-stu-id="df672-128">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="df672-129">充當閘道不支援的通話流程媒介，例如從 Enterprise Voice 用戶端遠端工作者撥打的電話</span><span class="sxs-lookup"><span data-stu-id="df672-129">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="df672-130">在包含 SIP 主幹的部署中，搭配使用 SIP 主幹服務提供者可提供 PSTN 支援，如此便不需要 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="df672-130">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="df672-131">下圖顯示與基本 PSTN 閘道和企業語音基礎結構通訊時，轉送伺服器所使用的信號和媒體通訊協定。</span><span class="sxs-lookup"><span data-stu-id="df672-131">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="df672-132">**中繼伺服器使用的訊號和媒體通訊協定**</span><span class="sxs-lookup"><span data-stu-id="df672-132">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="df672-133">![轉送伺服器通訊協定圖表](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "轉送伺服器通訊協定圖表")</span><span class="sxs-lookup"><span data-stu-id="df672-133">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df672-134">如果您使用 TCP 或 RTP/RTCP (，而不是在 PSTN 閘道和轉送伺服器之間的網路上) SRTP 或 SRTCP，我們建議您採取措施，以協助確保網路的安全性和隱私權。</span><span class="sxs-lookup"><span data-stu-id="df672-134">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df672-135">本章節內容</span><span class="sxs-lookup"><span data-stu-id="df672-135">In This Section</span></span>

  - [<span data-ttu-id="df672-136">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="df672-136">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="df672-137">Lync Server 2013 中的通話許可控制和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="df672-137">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="df672-138">Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="df672-138">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="df672-139">Lync Server 2013 中的媒體旁路和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="df672-139">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="df672-140">Lync Server 2013 中轉送伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="df672-140">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="df672-141">Lync Server 2013 中轉送伺服器的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="df672-141">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

