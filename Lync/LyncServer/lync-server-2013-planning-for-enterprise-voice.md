---
title: 'Lync Server 2013: Planning for Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e629946d0db408e83ea12313507787df233bcbc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3b7dd-102">規劃 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3b7dd-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b7dd-103">_**上次修改主題：** 2013年-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b7dd-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="3b7dd-104">Enterprise Voice 的部署程序取決於您現有的拓樸、 基礎結構，以及您想要支援的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="3b7dd-105">必要的程序將取決於哪些功能選擇，但您必須進行高層級的其他規劃考量。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="3b7dd-106">一般而言，請考慮類型及數目您想要部署的網站和其地理位置、 各網站通話數、 的連線網站的網路連結類型是否要為每個語音功能提供備援和容錯移轉網站，以及是否要使用現有的 PBX 設備。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="3b7dd-107">有某些注意事項，例如，您應該考慮當您規劃整體的 Lync Server 通訊軟體的高可用性。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="3b7dd-108">視需要在此區段中，整個主題中討論這些考量。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="3b7dd-109">規劃考量</span><span class="sxs-lookup"><span data-stu-id="3b7dd-109">Planning Considerations</span></span>

<span data-ttu-id="3b7dd-110">規劃決策資訊適用於特定的 Enterprise Voice 功能或是部署案例或元件的部署，請參閱本節中的主題。</span><span class="sxs-lookup"><span data-stu-id="3b7dd-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="3b7dd-111">定義 Lync Server 2013 中的 Enterprise Voice 的需求</span><span class="sxs-lookup"><span data-stu-id="3b7dd-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="3b7dd-112">評估語音使用方式和 Lync Server 2013 的流量</span><span class="sxs-lookup"><span data-stu-id="3b7dd-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="3b7dd-113">Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="3b7dd-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="3b7dd-114">所需的 Lync Server 2013 中的企業語音元件</span><span class="sxs-lookup"><span data-stu-id="3b7dd-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="3b7dd-115">規劃 Lync Server 2013 中的企業語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="3b7dd-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="3b7dd-116">規劃 Lync Server 2013 中的 Exchange Unified Messaging 整合</span><span class="sxs-lookup"><span data-stu-id="3b7dd-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="3b7dd-117">規劃 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="3b7dd-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="3b7dd-118">規劃 Lync Server 2013 中的緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="3b7dd-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="3b7dd-119">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3b7dd-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="3b7dd-120">規劃與 Lync Server 2013 的私人電話線</span><span class="sxs-lookup"><span data-stu-id="3b7dd-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="3b7dd-121">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="3b7dd-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="3b7dd-122">規劃 Lync Server 2013 中的企業語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="3b7dd-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="3b7dd-123">Lync Server 2013 中的 Enterprise voice 的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="3b7dd-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="3b7dd-124">Lync Server 2013 中的 Enterprise voice 的部署程序概觀</span><span class="sxs-lookup"><span data-stu-id="3b7dd-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="3b7dd-125">將使用者移至 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3b7dd-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="3b7dd-126">Lync Server 2013 中的 Lync PreCall 診斷工具</span><span class="sxs-lookup"><span data-stu-id="3b7dd-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

