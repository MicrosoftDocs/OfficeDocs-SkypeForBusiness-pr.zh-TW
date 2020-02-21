---
title: Lync Server 2013： 設定媒體旁路
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
ms.openlocfilehash: 93fe9bb93ad32c0871dd51d3818d2ca788327dc5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="3c3d6-102">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3c3d6-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c3d6-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="3c3d6-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="3c3d6-104">本節假設您有已發佈且設定至少一個或多個中繼伺服器 (如[Define a Mediation Server，在 Lync Server 2013 中的拓撲產生器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)和[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)，或中所述[定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)和[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)，分別部署文件中的所有)。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="3c3d6-105">本章節也假設您已定義至少一個閘道對等，提供 PSTN 連線能力，[定義在 Lync Server 2013 中的拓撲產生器的閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)所述。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="3c3d6-106">如果您連線到對等 SBC 的 SIP 主幹提供者，請確定提供者是完整的提供者，而且提供者支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="3c3d6-107">例如，許多 SIP 主幹提供者將只會允許其 SBC 接收來自中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="3c3d6-108">如果是的話，然後略過必須不啟用主幹有問題。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="3c3d6-109">此外，您無法啟用媒體旁路，除非您的組織可以找到好幾它內部網路的 IP 位址至 SIP 主幹提供者。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c3d6-110">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3c3d6-111">Microsoft 已測試一組的 PSTN 閘道與 Sbc 與認證合作夥伴，並已執行一些測試與 Cisco Ip-pbx。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3c3d6-112">媒體旁路只支援的產品和版本列在 Unified Communications Open Interoperability Program – 在 Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="3c3d6-113">本節說明如何啟用媒體旁路以減少所需的中繼伺服器處理。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="3c3d6-114">在啟用之前媒體略過，請確定您的環境符合條件才能支援媒體旁路中, 所述的[規劃媒體旁路 Lync Server 2013 中](lync-server-2013-planning-for-media-bypass.md)規劃文件。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="3c3d6-115">也請確定在[規劃媒體旁路 Lync Server 2013 中](lync-server-2013-planning-for-media-bypass.md)使用的資訊，決定是否要啟用媒體旁路以始終略過中繼伺服器，或若要判斷是否略過中繼伺服器時，使用網站與地區資訊的全域設定。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="3c3d6-116">如果您已經選擇性地設定通話許可控制 (CAC)，另一個進階 Enterprise Voice 功能，請注意，通話許可控制所執行的頻寬保留項目不會套用到哪些媒體任何通話採用略過]。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="3c3d6-117">首先，執行是否要使用媒體旁路的驗證，且通話許可控制如果採用媒體旁路，不會用於通話;媒體旁路檢查失敗時，才會執行檢查通話許可控制的。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="3c3d6-118">因此所是互斥的任何特定的通話路由傳送至 PSTN 的兩個功能。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="3c3d6-119">這是邏輯，因為媒體旁路假設上呼叫; 媒體端點之間並不存在的頻寬限制無法在連結限制頻寬與執行媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="3c3d6-120">As a result，其中一項將會套用至 PSTN 通話：) 的媒體略過中繼伺服器和通話許可控制不會保留通話; 頻寬或 b） 通話許可控制套用至來電的頻寬保留項目和媒體處理的呼叫中的相關中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="3c3d6-121">後續步驟： 啟用媒體旁路的主幹連線</span><span class="sxs-lookup"><span data-stu-id="3c3d6-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="3c3d6-122">之後初始設定 PSTN 連線能力 （撥號對應表、 語音原則、 PSTN 使用方式記錄、 撥出電話路由和轉譯規則），開始程序啟用媒體旁路的使用中[設定主幹，且媒體旁路 Lync Server 2013 中](lync-server-2013-configure-a-trunk-with-media-bypass.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="3c3d6-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c3d6-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3c3d6-123">See Also</span></span>


[<span data-ttu-id="3c3d6-124">設定與 Lync Server 2013 中的媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="3c3d6-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="3c3d6-125">設定媒體旁路以始終略過中繼伺服器的 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="3c3d6-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="3c3d6-126">若要使用網站與地區資訊的 Lync Server 2013 中設定媒體旁路全域設定</span><span class="sxs-lookup"><span data-stu-id="3c3d6-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="3c3d6-127">通用媒體旁路 Lync Server 2013 中的選項</span><span class="sxs-lookup"><span data-stu-id="3c3d6-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="3c3d6-128">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3c3d6-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

