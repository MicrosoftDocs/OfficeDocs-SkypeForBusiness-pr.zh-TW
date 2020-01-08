---
title: Lync Server 2013：中繼伺服器元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="d19f0-102">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="d19f0-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d19f0-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d19f0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d19f0-104">如果您部署企業語音工作負載，您必須部署 Lync Server 2013 （中繼伺服器）。</span><span class="sxs-lookup"><span data-stu-id="d19f0-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="d19f0-105">本節說明基本功能、相依性、基本拓撲及規劃指導方針。</span><span class="sxs-lookup"><span data-stu-id="d19f0-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="d19f0-106">中繼伺服器會轉譯信號，並在部分設定中，在您內部 Lync Server 2013、企業語音結構和公用交換電話網絡（PSTN）閘道或會話初始通訊協定（SIP）幹線之間的媒體進行轉換。</span><span class="sxs-lookup"><span data-stu-id="d19f0-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="d19f0-107">在 Lync Server 2013 端，中繼伺服器會偵聽單一相互 TLS （MTLS）傳輸位址。</span><span class="sxs-lookup"><span data-stu-id="d19f0-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="d19f0-108">在閘道端，中繼伺服器會偵聽與拓撲檔中定義之 trunks 相關聯的所有關聯偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="d19f0-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="d19f0-109">所有合格的閘道都必須支援 TLS，但是也可以啟用 TCP。</span><span class="sxs-lookup"><span data-stu-id="d19f0-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="d19f0-110">對於不支援 TLS 的閘道，支援 TCP。</span><span class="sxs-lookup"><span data-stu-id="d19f0-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="d19f0-111">如果您的環境中也有現有的公用分支 Exchange （PBX），轉送伺服器會處理企業語音使用者與 PBX 之間的通話。</span><span class="sxs-lookup"><span data-stu-id="d19f0-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="d19f0-112">如果您的 PBX 是 IP PBX，您可以在 PBX 與中繼伺服器之間建立直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="d19f0-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="d19f0-113">如果您的 PBX 是時段分複用（TDM） PBX，您也必須在中繼伺服器與 PBX 之間部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d19f0-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="d19f0-114">中繼伺服器會根據預設，與前端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="d19f0-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="d19f0-115">您也可以將中繼伺服器部署在獨立的池中，以提高效能，或部署 SIP 中繼（在這種情況下，強烈建議使用獨立的池）。</span><span class="sxs-lookup"><span data-stu-id="d19f0-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="d19f0-116">如果您在支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署直接 SIP 連線，則不需要獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d19f0-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="d19f0-117">不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。</span><span class="sxs-lookup"><span data-stu-id="d19f0-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="d19f0-118">我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：</span><span class="sxs-lookup"><span data-stu-id="d19f0-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="d19f0-119">IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d19f0-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="d19f0-120">Ip-pbx 不支援媒體旁路，但是託管轉送伺服器的前端池可以處理語音轉換，以取得不需要媒體旁路的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d19f0-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="d19f0-121">您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="d19f0-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="d19f0-122">如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d19f0-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="d19f0-123">中繼伺服器的主要功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="d19f0-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="d19f0-124">在 Lync Server 端對 SRTP 進行加密和解密</span><span class="sxs-lookup"><span data-stu-id="d19f0-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="d19f0-125">將 SIP （適用于不支援 TLS 的閘道）轉換為經由相互 TLS 的 SIP</span><span class="sxs-lookup"><span data-stu-id="d19f0-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="d19f0-126">在 Lync Server 與中繼伺服器的閘道對等之間轉換媒體資料流程</span><span class="sxs-lookup"><span data-stu-id="d19f0-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="d19f0-127">將網路以外的用戶端連線到內部的 ICE 元件，讓介質能在 NAT 和防火牆間進行遍歷</span><span class="sxs-lookup"><span data-stu-id="d19f0-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="d19f0-128">充當閘道不支援的通話流程媒介，例如來自企業語音用戶端的遠端工作者呼叫</span><span class="sxs-lookup"><span data-stu-id="d19f0-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="d19f0-129">在包含 SIP 中繼的部署中，使用 SIP 中繼服務提供者來提供 PSTN 支援，從而消除 PSTN 閘道的需求</span><span class="sxs-lookup"><span data-stu-id="d19f0-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="d19f0-130">下圖顯示與基本 PSTN 閘道和企業語音基礎結構通訊時，中繼伺服器所使用的傳送信號和媒體通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d19f0-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="d19f0-131">**中繼伺服器所使用的信號和媒體通訊協定**</span><span class="sxs-lookup"><span data-stu-id="d19f0-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="d19f0-132">![中繼伺服器通訊協定](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "圖表")</span><span class="sxs-lookup"><span data-stu-id="d19f0-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d19f0-133">如果您使用的是 TCP 或 RTP/RTCP （而不是 SRTP 或 SRTCP），請在 PSTN 閘道與中繼伺服器之間的網路上進行測量，以協助確保網路的安全性與隱私權。</span><span class="sxs-lookup"><span data-stu-id="d19f0-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d19f0-134">本節內容</span><span class="sxs-lookup"><span data-stu-id="d19f0-134">In This Section</span></span>

  - [<span data-ttu-id="d19f0-135">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="d19f0-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="d19f0-136">Lync Server 2013 中的通話許可控制和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d19f0-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="d19f0-137">Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d19f0-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="d19f0-138">Lync Server 2013 中的媒體旁路和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d19f0-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="d19f0-139">Lync Server 2013 中之中繼伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="d19f0-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="d19f0-140">Lync Server 2013 中的中繼伺服器部署指導方針</span><span class="sxs-lookup"><span data-stu-id="d19f0-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

