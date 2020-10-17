---
title: Lync Server 2013：設定媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6153be57ec60e58b404370ece2c2214ae33083c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520626"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0ecf9-102">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0ecf9-102">Configure media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ecf9-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0ecf9-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="0ecf9-104">本節假設您已發佈和設定至少一部或多部轉送伺服器 (如在 Lync server 2013 的 [拓撲](lync-server-2013-define-a-mediation-server-in-topology-builder.md) 產生器中定義轉送伺服器和在 lync server [2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)，或是在 lync server 2013 中的 [ [定義及設定前端集區或 Standard Edition Server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) ] 中所述，然後在 [部署] 檔) 中分別 [發行2013拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="0ecf9-105">本節也假設您已定義至少一個閘道對等提供 PSTN 連線，如在 [Lync Server 2013 的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)所述。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="0ecf9-106">如果您所連接的對等是 SIP 主幹提供者的 SBC，請確定提供者是合格的提供者，而且提供者支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="0ecf9-107">例如，許多 SIP 主幹提供者只會允許其 SBC 從轉送伺服器接收流量。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="0ecf9-108">如果是的話，則不能針對有問題的主幹啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="0ecf9-109">此外，除非您的組織對 SIP 主幹提供者顯示其內部網路 IP 位址，否則您無法啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ecf9-110">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="0ecf9-111">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0ecf9-112">只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="0ecf9-113">本節說明如何啟用媒體旁路，以減少轉送伺服器所需的處理。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="0ecf9-114">在您啟用媒體旁路之前，請確定您的環境符合支援媒體旁路所需的條件，如規劃檔中的在 [Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 中所述。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="0ecf9-115">此外，請確定您已使用在 [Lync server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 的資訊，決定是否要啟用媒體旁路全域設定，以在決定是否略過轉送伺服器時，永遠略過轉送伺服器或使用網站與地區資訊。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="0ecf9-116">如果您已選擇性設定通話許可控制 (CAC) ，另一種高級 Enterprise Voice 功能，請注意，「通話許可控制」所執行的頻寬保留不會套用到使用媒體旁路的任何呼叫。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="0ecf9-117">驗證是否要使用媒體旁路，以及是否採用媒體旁路，通話許可控制不會用於通話;只有在媒體旁路檢查失敗時，才會為通話許可控制執行支票。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="0ecf9-118">針對路由傳送至 PSTN 的任何特殊呼叫，這兩種功能都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="0ecf9-119">這是因為媒體旁路假設在通話上的媒體端點之間不存在頻寬限制，所以此邏輯為此邏輯。媒體旁路無法在限制頻寬的連結上執行。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="0ecf9-120">因此，下列其中一項會套用至 PSTN 通話：) 媒體略過轉送伺服器，而通話許可控制並未保留通話的頻寬;or b) 通話許可控制會將頻寬保留套用至通話，並由通話所涉及的轉送伺服器處理媒體。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="0ecf9-121">後續步驟：在主幹連線上啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0ecf9-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="0ecf9-122">在設定 PSTN 連線的初始設定之後 (撥號對應表、語音原則、PSTN 使用方式記錄、撥出電話路由和轉譯規則) ，使用在 [Lync Server 2013 中設定具有媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟開始，以啟用媒體旁路的處理常式。</span><span class="sxs-lookup"><span data-stu-id="0ecf9-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ecf9-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ecf9-123">See Also</span></span>


[<span data-ttu-id="0ecf9-124">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="0ecf9-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="0ecf9-125">在 Lync Server 2013 中設定媒體旁路，以永遠略過轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="0ecf9-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="0ecf9-126">在 Lync Server 2013 中設定媒體旁路全域設定，以使用網站與地區資訊</span><span class="sxs-lookup"><span data-stu-id="0ecf9-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="0ecf9-127">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="0ecf9-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="0ecf9-128">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0ecf9-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

