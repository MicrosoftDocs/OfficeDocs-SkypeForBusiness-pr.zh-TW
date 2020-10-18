---
title: Lync Server 2013： SIP trunk 的簡介
description: Lync Server 2013： SIP 主幹的簡介。
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
ms.openlocfilehash: 6132cc16d8aaeee4b27355ea8676672a0a5df93d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577259"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="75a26-103">Lync Server 2013 中的 SIP 主幹概述</span><span class="sxs-lookup"><span data-stu-id="75a26-103">Overview of SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a26-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="75a26-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="75a26-p101">部署 SIP 主幹可以大幅簡化組織的電信通訊，並可利用最新的即時通訊增強功能。SIP 主幹最重要的優點之一，是可將組織連線合併至中央網站的公用交換電話網路 (PSTN)，而其前身分時多工 (TDM) 主幹卻通常需要每個分支網站各一個主幹。</span><span class="sxs-lookup"><span data-stu-id="75a26-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="75a26-107">Lync Server 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="75a26-107">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="75a26-108">Lync Server 2013 SIP 主幹功能可讓下列專案：</span><span class="sxs-lookup"><span data-stu-id="75a26-108">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="75a26-109">公司防火牆內外的企業使用者皆可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。</span><span class="sxs-lookup"><span data-stu-id="75a26-109">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="75a26-110">任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。</span><span class="sxs-lookup"><span data-stu-id="75a26-110">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="75a26-111">節省成本</span><span class="sxs-lookup"><span data-stu-id="75a26-111">Cost Savings</span></span>

<span data-ttu-id="75a26-112">與 SIP 主幹相關聯的成本節約可能相當大：</span><span class="sxs-lookup"><span data-stu-id="75a26-112">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="75a26-113">長途通話通常會透過 SIP 主幹降低成本。</span><span class="sxs-lookup"><span data-stu-id="75a26-113">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="75a26-114">您可以削減管理成本，並降低部署的複雜度。</span><span class="sxs-lookup"><span data-stu-id="75a26-114">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="75a26-115">基本速率介面 (BRI) 和主要速率介面 (PRI) 費用，可在您將 SIP 主幹直接連接至您的 ITSP 時，降低成本。</span><span class="sxs-lookup"><span data-stu-id="75a26-115">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="75a26-116">在 TDM trunk 中，服務提供者會在一分鐘內收取通話的費用。</span><span class="sxs-lookup"><span data-stu-id="75a26-116">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="75a26-117">SIP 主幹的成本可能是根據頻寬使用量而定，您可以更小、更經濟的增量購買。</span><span class="sxs-lookup"><span data-stu-id="75a26-117">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="75a26-118"> (實際成本取決於您所選擇之 ITSP 的服務模型。 ) </span><span class="sxs-lookup"><span data-stu-id="75a26-118">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="75a26-119">與裝載 PSTN 閘道或 IP-PBX 的 SIP Trunk</span><span class="sxs-lookup"><span data-stu-id="75a26-119">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="75a26-120">由於 SIP 主幹直接連線至您的服務提供者，所以您可以省去您的 PSTN 閘道及其管理成本和複雜性。</span><span class="sxs-lookup"><span data-stu-id="75a26-120">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="75a26-121">使用 SIP 主幹可縮短維護和管理，從而導致大量成本節約。</span><span class="sxs-lookup"><span data-stu-id="75a26-121">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="75a26-122">擴充的 VoIP 服務</span><span class="sxs-lookup"><span data-stu-id="75a26-122">Expanded VoIP Services</span></span>

<span data-ttu-id="75a26-123">語音功能常常是部署 SIP 主幹的主要動機，但語音支援只是第一步。</span><span class="sxs-lookup"><span data-stu-id="75a26-123">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="75a26-124">透過 SIP trunk，您可以擴充 VoIP 功能，並讓 Lync Server 2013 提供一組更豐富的服務。</span><span class="sxs-lookup"><span data-stu-id="75a26-124">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="75a26-125">例如：</span><span class="sxs-lookup"><span data-stu-id="75a26-125">For example:</span></span>

  - <span data-ttu-id="75a26-126">未執行 Lync Server 2013 之裝置的增強顯示狀態偵測，可提供與行動電話的更好整合，讓您能看到使用者何時接聽行動電話。</span><span class="sxs-lookup"><span data-stu-id="75a26-126">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="75a26-127">E9-1-1 緊急電話可讓接聽911呼叫的授權者判斷來電者的電話號碼的位置。</span><span class="sxs-lookup"><span data-stu-id="75a26-127">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75a26-128">請與您的 ITSP 取得支援的服務清單，並可為您的組織啟用這些服務。</span><span class="sxs-lookup"><span data-stu-id="75a26-128">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

