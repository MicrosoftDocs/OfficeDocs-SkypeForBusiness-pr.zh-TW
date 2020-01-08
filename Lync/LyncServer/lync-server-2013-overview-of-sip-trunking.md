---
title: Lync Server 2013：SIP 主幹連線概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d029d-102">Lync Server 2013 中的 SIP 主幹連線概觀</span><span class="sxs-lookup"><span data-stu-id="d029d-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d029d-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d029d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d029d-104">部署 SIP 中繼可能是簡化貴組織的電訊，並準備最新的即時通訊功能的重要步驟。</span><span class="sxs-lookup"><span data-stu-id="d029d-104">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="d029d-105">SIP 中繼的主要優點之一是，您可以將貴組織的連線到中央網站的公用交換電話網絡（PSTN），而不是其前置任務、時間單位複用（TDM）中繼（通常是需要來自每個分支網站的個別幹線。</span><span class="sxs-lookup"><span data-stu-id="d029d-105">One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="d029d-106">Lync Server 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="d029d-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="d029d-107">Lync Server 2013 SIP 中繼功能可讓您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d029d-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="d029d-108">企業使用者（無論是在公司防火牆內部或外部），都可以撥打由 E. 在 PSTN 上終止的以164為規範之服務提供者的服務所指定的本機通話或長途通話。</span><span class="sxs-lookup"><span data-stu-id="d029d-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="d029d-109">任何 PSTN 訂閱者都可以撥打與該企業使用者相關聯的直接向內撥號（已連線）號碼，與公司防火牆內部或外部的企業使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="d029d-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="d029d-110">成本節約</span><span class="sxs-lookup"><span data-stu-id="d029d-110">Cost Savings</span></span>

<span data-ttu-id="d029d-111">與 SIP 中繼相關的成本節約可能相當重要：</span><span class="sxs-lookup"><span data-stu-id="d029d-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="d029d-112">遠距離通話通常會透過 SIP 幹線降低成本。</span><span class="sxs-lookup"><span data-stu-id="d029d-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="d029d-113">您可以削減易管理性成本，並減少部署的複雜性。</span><span class="sxs-lookup"><span data-stu-id="d029d-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="d029d-114">如果您將 SIP 主幹直接連線至 ITSP，成本較低，就可以消除基本比率介面（BRI）和主要比率介面（PRI）費用。</span><span class="sxs-lookup"><span data-stu-id="d029d-114">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="d029d-115">在 TDM 中繼中，服務提供者會以分鐘為通話付費。</span><span class="sxs-lookup"><span data-stu-id="d029d-115">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="d029d-116">SIP 中繼的成本可能是以頻寬使用量為基礎，您可以使用較小的增量來購買。</span><span class="sxs-lookup"><span data-stu-id="d029d-116">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="d029d-117">（實際成本取決於您所選擇之 ITSP 的服務模型。）</span><span class="sxs-lookup"><span data-stu-id="d029d-117">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="d029d-118">SIP 中繼與託管 PSTN 閘道或 IP PBX</span><span class="sxs-lookup"><span data-stu-id="d029d-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="d029d-119">因為 SIP trunks 直接連線至您的服務提供者，所以您可以消除 PSTN 閘道及其管理成本與複雜性。</span><span class="sxs-lookup"><span data-stu-id="d029d-119">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="d029d-120">使用 SIP 幹線，只需要減少維護與管理，即可帶來巨大的成本節約。</span><span class="sxs-lookup"><span data-stu-id="d029d-120">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="d029d-121">擴充的 VoIP 服務</span><span class="sxs-lookup"><span data-stu-id="d029d-121">Expanded VoIP Services</span></span>

<span data-ttu-id="d029d-122">語音功能通常是部署 SIP 中繼的主要動機，但語音支援只是第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="d029d-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="d029d-123">使用 SIP 中繼，您可以延伸 VoIP 功能並啟用 Lync Server 2013，以提供一組更豐富的服務。</span><span class="sxs-lookup"><span data-stu-id="d029d-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="d029d-124">例如：</span><span class="sxs-lookup"><span data-stu-id="d029d-124">For example:</span></span>

  - <span data-ttu-id="d029d-125">針對未執行 Lync Server 2013 的裝置，增強的目前狀態偵測功能可提供與行動電話的更佳整合，讓您可以查看使用者何時在行動電話上通話。</span><span class="sxs-lookup"><span data-stu-id="d029d-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="d029d-126">E9-1-1 緊急通話可讓您接聽911通話的主管機構，判斷來電者與其電話號碼的位置。</span><span class="sxs-lookup"><span data-stu-id="d029d-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d029d-127">請與您的 ITSP 取得他們支援並可供您組織使用的服務清單。</span><span class="sxs-lookup"><span data-stu-id="d029d-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

