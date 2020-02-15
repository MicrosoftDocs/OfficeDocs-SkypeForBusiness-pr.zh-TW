---
title: SIP 主幹連線的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="b55b8-102">Lync Server 2013 中的 SIP 主幹連線概觀</span><span class="sxs-lookup"><span data-stu-id="b55b8-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b55b8-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="b55b8-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b55b8-p101">部署 SIP 主幹可以大幅簡化組織的電信通訊，並可利用最新的即時通訊增強功能。SIP 主幹最重要的優點之一，是可將組織連線合併至中央網站的公用交換電話網路 (PSTN)，而其前身分時多工 (TDM) 主幹卻通常需要每個分支網站各一個主幹。</span><span class="sxs-lookup"><span data-stu-id="b55b8-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="b55b8-106">Lync Server 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="b55b8-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="b55b8-107">Lync Server 2013 SIP 主幹功能可讓下列：</span><span class="sxs-lookup"><span data-stu-id="b55b8-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="b55b8-108">公司防火牆內外的企業使用者皆可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。</span><span class="sxs-lookup"><span data-stu-id="b55b8-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="b55b8-109">任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。</span><span class="sxs-lookup"><span data-stu-id="b55b8-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="b55b8-110">節省成本</span><span class="sxs-lookup"><span data-stu-id="b55b8-110">Cost Savings</span></span>

<span data-ttu-id="b55b8-111">SIP 主幹相關聯的成本節省可能相當可觀：</span><span class="sxs-lookup"><span data-stu-id="b55b8-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="b55b8-112">撥打的長途電話通常更省錢透過 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="b55b8-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="b55b8-113">您可以管理成本，並降低部署複雜性。</span><span class="sxs-lookup"><span data-stu-id="b55b8-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="b55b8-114">如果您的 SIP 主幹直接連線到在大幅降低成本 ITSP 可以消除基本速率介面 (BRI) 與主要 rate interface (PRI) 費用。</span><span class="sxs-lookup"><span data-stu-id="b55b8-114">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="b55b8-115">中 TDM 主幹服務提供者的呼叫依收費分鐘。</span><span class="sxs-lookup"><span data-stu-id="b55b8-115">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="b55b8-116">SIP 主幹的成本可能會根據您可以購買較小，更經濟增量的頻寬用量。</span><span class="sxs-lookup"><span data-stu-id="b55b8-116">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="b55b8-117">（實際成本取決於您選擇 ITSP 的服務模型）。</span><span class="sxs-lookup"><span data-stu-id="b55b8-117">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="b55b8-118">相對於 PSTN 閘道或 IP PBX 主控的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="b55b8-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="b55b8-119">SIP 主幹直接連接到服務供應商，因為您可以省去您 PSTN 閘道、 其管理成本和複雜度。</span><span class="sxs-lookup"><span data-stu-id="b55b8-119">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="b55b8-120">使用 SIP 主幹可能會導致大量成本節省透過減少的維護和管理。</span><span class="sxs-lookup"><span data-stu-id="b55b8-120">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="b55b8-121">擴充的 VoIP 服務</span><span class="sxs-lookup"><span data-stu-id="b55b8-121">Expanded VoIP Services</span></span>

<span data-ttu-id="b55b8-122">語音功能通常會部署 SIP 主幹的主要動機但語音支援只是第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="b55b8-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="b55b8-123">使用 SIP 主幹，您可以擴充 VoIP 功能，並啟用 Lync Server 2013 提供一組更豐富的服務。</span><span class="sxs-lookup"><span data-stu-id="b55b8-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="b55b8-124">例如：</span><span class="sxs-lookup"><span data-stu-id="b55b8-124">For example:</span></span>

  - <span data-ttu-id="b55b8-125">增強型目前狀態偵測未執行 Lync Server 2013 的裝置可以更密切整合與行動電話，讓您查看使用者在行動電話上時。</span><span class="sxs-lookup"><span data-stu-id="b55b8-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="b55b8-126">E9-1-1 緊急通話可讓人員接聽 911 通話至判斷他/她的電話號碼的來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="b55b8-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b55b8-127">請連絡 ITSP 並索取他們支援您的組織可以啟用的服務的清單。</span><span class="sxs-lookup"><span data-stu-id="b55b8-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

