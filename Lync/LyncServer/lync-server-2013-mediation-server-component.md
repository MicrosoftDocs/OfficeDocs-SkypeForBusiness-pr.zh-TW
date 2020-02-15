---
title: Lync Server 2013： 中繼伺服器元件
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
ms.openlocfilehash: 82d540d37dee0de37d3986c02ac2243a95fe4404
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="3f2b9-102">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="3f2b9-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f2b9-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="3f2b9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3f2b9-104">如果您部署企業語音工作負載，您必須部署 Lync Server 2013 中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="3f2b9-105">本節說明基本功能、相依性、基本拓撲以及規劃指南。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="3f2b9-106">中繼伺服器及內容翻譯信號，在某些組態中，您內部 Lync Server 2013 Enterprise Voice 基礎結構與公用交換的電話網路 (PSTN) 閘道或工作階段初始通訊協定 (SIP) 主幹間的媒體。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="3f2b9-107">在 Lync Server 2013 端中繼伺服器同時接聽單一的相互 TLS (MTLS) 傳輸地址。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="3f2b9-108">在閘道端，中繼伺服器會在所有與＜拓撲＞文件中所定義之主幹相關聯的相關聆聽連接埠上聆聽。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="3f2b9-109">所有合格的閘道都必須支援 TLS，不過也可以一併啟用 TCP。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="3f2b9-110">不支援 TLS 的閘道，仍舊可以支援 TCP。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="3f2b9-111">如果您也會在您的環境中有現有的公用 Branch Exchange (PBX)，中繼伺服器會處理企業語音使用者與 PBX 之間的通話。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="3f2b9-112">如果您的 PBX 是 IP PBX，您可以建立中繼伺服器與 PBX 之間的直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="3f2b9-113">如果您 PBX 時間部門多工 (TDM) PBX，則也必須部署中繼伺服器和 PBX 間的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="3f2b9-114">根據預設，中繼伺服器已組合與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="3f2b9-115">中繼伺服器也可以部署在獨立的集區，基於效能考量，或如果您部署 SIP 主幹，這種情況的獨立集區強烈建議。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="3f2b9-116">如果您對支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="3f2b9-117">因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="3f2b9-118">我們也建議您，只要出現下列情形，如果您已經部署了 IP-PBX 或連線至網際網路電話服務提供者工作階段邊界控制器 (SBC) 時，請在前端集區上組合中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="3f2b9-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="3f2b9-119">IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="3f2b9-120">IP-PBX 不支援媒體旁路，但是主控中繼伺服器的前端集區可以處理語音轉碼要不適用媒體旁路的通話。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="3f2b9-121">您可以使用 Microsoft Lync Server 2013 規劃工具來評估是否想要組合的中繼伺服器的前端集區可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="3f2b9-122">如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="3f2b9-123">中繼伺服器的主要功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f2b9-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="3f2b9-124">加密與解密 SRTP Lync 伺服器端</span><span class="sxs-lookup"><span data-stu-id="3f2b9-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="3f2b9-125">將透過 TCP 的 SIP (對於不支援 TLS 的閘道) 轉譯為透過相互 TLS 的 SIP</span><span class="sxs-lookup"><span data-stu-id="3f2b9-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="3f2b9-126">轉譯 Lync 伺服器和中繼伺服器閘道對等之間的媒體資料流</span><span class="sxs-lookup"><span data-stu-id="3f2b9-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="3f2b9-127">將網路外部的用戶端連線到內部 ICE 元件，這些元件可以讓媒體周遊 NAT 與防火牆</span><span class="sxs-lookup"><span data-stu-id="3f2b9-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="3f2b9-128">做為閘道不支援，例如從 Enterprise Voice 用戶端上的遠端工作者的通話的通話流程媒介</span><span class="sxs-lookup"><span data-stu-id="3f2b9-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="3f2b9-129">在包含 SIP 主幹的部署中，搭配使用 SIP 主幹服務提供者可提供 PSTN 支援，如此便不需要 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="3f2b9-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="3f2b9-130">下圖顯示中繼伺服器與基本 PSTN 閘道及 Enterprise Voice 基礎結構進行通訊時所使用的訊號和媒體通訊協定。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="3f2b9-131">**中繼伺服器使用的訊號和媒體通訊協定**</span><span class="sxs-lookup"><span data-stu-id="3f2b9-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="3f2b9-132">![中繼伺服器通訊協定圖表](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中繼伺服器通訊協定圖表")</span><span class="sxs-lookup"><span data-stu-id="3f2b9-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f2b9-133">如果您在 PSTN 閘道與中繼伺服器之間的網路上使用 TCP 或 RTP/RTCP （而非 SRTP 或 SRTCP），我們建議您採取措施以協助確保安全性和隱私權的網路。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3f2b9-134">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3f2b9-134">In This Section</span></span>

  - [<span data-ttu-id="3f2b9-135">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="3f2b9-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="3f2b9-136">通話許可控制和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3f2b9-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="3f2b9-137">增強型的 9-1-1 (E9-1-1) 和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3f2b9-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="3f2b9-138">媒體旁路和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3f2b9-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="3f2b9-139">Lync Server 2013 中的中繼伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="3f2b9-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="3f2b9-140">Lync Server 2013 中的中繼伺服器的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="3f2b9-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

