---
title: Lync Server 2013： PSTN 連接元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="31079-102">Lync Server 2013 中的 PSTN 連接元件</span><span class="sxs-lookup"><span data-stu-id="31079-102">PSTN connectivity components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31079-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="31079-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="31079-104">企業級 VoIP 解決方案必須提供呼叫及從公開的交換電話網絡（PSTN）撥打電話，而不會拒絕服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="31079-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="31079-105">此外，使用者在撥打及接聽電話時，不應知道基礎技術。</span><span class="sxs-lookup"><span data-stu-id="31079-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="31079-106">從使用者的角度來看，企業語音結構和 PSTN 之間的通話看起來應該就像是另一個 SIP 會話。</span><span class="sxs-lookup"><span data-stu-id="31079-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="31079-107">針對 PSTN 連線，您可以部署 SIP 幹線或 PSTN 閘道（使用 PBX，也稱為直接 SIP 連結，或沒有 PBX）。</span><span class="sxs-lookup"><span data-stu-id="31079-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="31079-108">SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="31079-108">SIP Trunking</span></span>

<span data-ttu-id="31079-109">除了使用 PSTN 閘道之外，您還可以使用 SIP 中繼將企業語音方案連線至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="31079-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="31079-110">SIP 中繼可啟用下列案例：</span><span class="sxs-lookup"><span data-stu-id="31079-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="31079-111">公司防火牆內部或外部的企業使用者可以撥打以164為規範之服務提供者的服務，在 PSTN 上終止的本地或長途號碼。</span><span class="sxs-lookup"><span data-stu-id="31079-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="31079-112">任何 PSTN 訂閱者都可以撥打與該企業使用者相關聯的直接向內撥號（已連線）號碼，與公司防火牆內部或外部的企業使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="31079-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="31079-113">使用此部署方案需要 SIP 中繼服務提供者。</span><span class="sxs-lookup"><span data-stu-id="31079-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="31079-114">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="31079-114">PSTN gateways</span></span>

<span data-ttu-id="31079-115">PSTN 閘道是協力廠商裝置，可在企業語音結構和 PSTN 或 PBX 之間轉換信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="31079-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="31079-116">PSTN 閘道與中繼伺服器搭配使用，以向企業語音用戶端出示 PSTN 或 PBX 通話。</span><span class="sxs-lookup"><span data-stu-id="31079-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="31079-117">中繼伺服器也會將來自企業語音用戶端的呼叫提供給 pstn 閘道，以用於路由至 PSTN 或 PBX。</span><span class="sxs-lookup"><span data-stu-id="31079-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="31079-118">如需與 Microsoft 合作以提供搭配 Lync Server 使用之裝置的合作夥伴清單，請參閱 Microsoft 整合通訊合作夥伴網站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。</span><span class="sxs-lookup"><span data-stu-id="31079-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="31079-119">私人分支交換</span><span class="sxs-lookup"><span data-stu-id="31079-119">Private Branch Exchanges</span></span>

<span data-ttu-id="31079-120">如果您的現有語音結構使用的是私人分支 exchange （PBX），您可以將 PBX 搭配 Lync Server 企業語音使用。</span><span class="sxs-lookup"><span data-stu-id="31079-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="31079-121">支援的企業語音 PBX 整合案例如下所示：</span><span class="sxs-lookup"><span data-stu-id="31079-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="31079-122">支援媒體旁路的 IP PBX （含轉送伺服器）。</span><span class="sxs-lookup"><span data-stu-id="31079-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="31079-123">需要獨立 PSTN 閘道的 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="31079-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="31079-124">含獨立 PSTN 閘道的時間分段複用（TDM） PBX。</span><span class="sxs-lookup"><span data-stu-id="31079-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31079-125">媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="31079-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="31079-126">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="31079-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="31079-127">只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="31079-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="31079-128">如需提供企業語音方案之合作夥伴的詳細資訊，請參閱 Microsoft 整合通訊合作夥伴[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)網站。</span><span class="sxs-lookup"><span data-stu-id="31079-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="31079-129">如需提供企業語音硬體方案（包括 PSTN 閘道）合作夥伴的詳細資訊，請參閱 Microsoft 整合[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)通訊合作夥伴網站。</span><span class="sxs-lookup"><span data-stu-id="31079-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

