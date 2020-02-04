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
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="efdf0-102">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="efdf0-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efdf0-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="efdf0-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="efdf0-104">本節假設您已經發佈並設定至少一或多個轉送伺服器（如在 lync server 2013 的拓撲建立器中[定義轉送伺服器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)，並在 lync server [2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)，或在 Lync server 2013 中[定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)，並分別在部署檔中發佈[2013 拓撲](lync-server-2013-publish-the-topology.md)）。</span><span class="sxs-lookup"><span data-stu-id="efdf0-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="efdf0-105">本節也假設您已定義至少一個閘道對等來提供 PSTN 連線，如在[Lync Server 2013 的拓撲建立器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="efdf0-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="efdf0-106">如果您所連線的對等是 SIP 中繼提供者的 SBC，請確認提供者是合格的提供者，且提供者支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="efdf0-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="efdf0-107">例如，許多 SIP 中繼提供者將只允許其 SBC 接收來自中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="efdf0-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="efdf0-108">如果是，則不能針對有問題的主幹啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="efdf0-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="efdf0-109">此外，除非您的組織向 SIP 中繼提供者顯示其內部網路 IP 位址，否則您無法啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="efdf0-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="efdf0-110">媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="efdf0-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="efdf0-111">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="efdf0-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="efdf0-112">只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="efdf0-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="efdf0-113">本節說明如何啟用媒體旁路以減少進行轉送伺服器所需的處理。</span><span class="sxs-lookup"><span data-stu-id="efdf0-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="efdf0-114">在您啟用媒體旁路之前，請確定您的環境符合支援媒體旁路所需的條件，如在規劃檔中的[Lync Server 2013 規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="efdf0-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="efdf0-115">此外，請務必使用在[Lync server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)的資訊，決定是否要啟用媒體旁路全域設定，以避免在決定是否要繞過中繼伺服器時，一直略過中繼伺服器或使用網站和區域資訊。</span><span class="sxs-lookup"><span data-stu-id="efdf0-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="efdf0-116">如果您已經有選擇設定 [呼叫許可控制（CAC）]，另一個高級企業語音功能，請注意，通話許可控制所執行的頻寬保留不會套用到任何已使用媒體略過的呼叫。</span><span class="sxs-lookup"><span data-stu-id="efdf0-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="efdf0-117">驗證是否會先執行媒體略過，如果是採用媒體旁路，通話許可控制則不會用於通話;只有在媒體旁路檢查失敗時，才會執行 [通話許可控制] 的檢查。</span><span class="sxs-lookup"><span data-stu-id="efdf0-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="efdf0-118">因此，對於路由至 PSTN 的任何特定呼叫，這兩項功能都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="efdf0-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="efdf0-119">這是因為媒體旁路假設在通話中的媒體端點之間不存在頻寬限制;無法在頻寬限制的連結上執行媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="efdf0-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="efdf0-120">因此，下列其中一項將會套用至 PSTN 通話： a）媒體繞過中繼伺服器，且通話許可控制不會保留通話的頻寬;or b）通話許可控制將頻寬保留套用至通話，而媒體則由通話中所涉及的中繼伺服器來處理。</span><span class="sxs-lookup"><span data-stu-id="efdf0-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="efdf0-121">後續步驟：在主幹連線上啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="efdf0-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="efdf0-122">在設定 PSTN 連線（撥號方案、語音原則、PSTN 使用記錄、傳出通話路由及翻譯規則）的初始設定之後，請使用在[Lync Server 2013 中的 [使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)] 中的步驟開始啟用媒體旁路的程式。</span><span class="sxs-lookup"><span data-stu-id="efdf0-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efdf0-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="efdf0-123">See Also</span></span>


<span data-ttu-id="efdf0-124">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="efdf0-124">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  
[<span data-ttu-id="efdf0-125">在 Lync Server 2013 中設定媒體旁路，以永遠略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="efdf0-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="efdf0-126">在 Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊</span><span class="sxs-lookup"><span data-stu-id="efdf0-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="efdf0-127">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="efdf0-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="efdf0-128">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="efdf0-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

