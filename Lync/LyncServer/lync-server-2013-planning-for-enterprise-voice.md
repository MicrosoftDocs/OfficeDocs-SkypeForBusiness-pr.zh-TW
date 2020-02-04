---
title: Lync Server 2013：規劃企業語音
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
ms.openlocfilehash: 83b0ec944ad857ffccb419cf9ed36fbca92306c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41753253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="026f9-102">在 Lync Server 2013 中規劃企業語音</span><span class="sxs-lookup"><span data-stu-id="026f9-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="026f9-103">_**主題上次修改日期：** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="026f9-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="026f9-104">企業語音的部署程式，取決於您現有的拓撲、基礎結構，以及您想要支援的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="026f9-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="026f9-105">所需的程式取決於您所選擇的功能，但是您必須在高層次進行其他規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="026f9-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="026f9-106">一般來說，請考慮您想要部署的網站類型及數量，以及它們的地理位置、每個網站的通話量、連接網站的網路連結類型，而無論您是否要為每個使用者提供語音功能的冗余與容錯移轉網站，以及您是否要使用現有的 PBX 裝置。</span><span class="sxs-lookup"><span data-stu-id="026f9-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="026f9-107">在您規劃 Lync Server 通訊軟體整體時，必須考慮一些考慮（例如高可用性）。</span><span class="sxs-lookup"><span data-stu-id="026f9-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="026f9-108">如有需要，我們將在本區段的主題中討論這些考慮。</span><span class="sxs-lookup"><span data-stu-id="026f9-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="026f9-109">規劃考慮</span><span class="sxs-lookup"><span data-stu-id="026f9-109">Planning Considerations</span></span>

<span data-ttu-id="026f9-110">針對特定企業語音功能或部署案例或元件的部署規劃決策，請參閱本節中的主題。</span><span class="sxs-lookup"><span data-stu-id="026f9-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="026f9-111">在 Lync Server 2013 中定義 Enterprise Voice 的需求</span><span class="sxs-lookup"><span data-stu-id="026f9-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="026f9-112">針對 Lync Server 2013 評估語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="026f9-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - <span data-ttu-id="026f9-113">[Lync Server 2013 中的 [高級企業語音功能] 的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="026f9-113">[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)</span></span>

  - [<span data-ttu-id="026f9-114">Lync Server 2013 中的企業語音所需元件</span><span class="sxs-lookup"><span data-stu-id="026f9-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="026f9-115">在 Lync Server 2013 中規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="026f9-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="026f9-116">在 Lync Server 2013 中規劃 Exchange Unified Messaging 整合</span><span class="sxs-lookup"><span data-stu-id="026f9-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="026f9-117">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="026f9-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="026f9-118">在 Lync Server 2013 中規劃緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="026f9-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="026f9-119">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="026f9-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="026f9-120">使用 Lync Server 2013 規劃私人電話線路</span><span class="sxs-lookup"><span data-stu-id="026f9-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="026f9-121">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="026f9-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="026f9-122">在 Lync Server 2013 中規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="026f9-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="026f9-123">Lync Server 2013 中 Enterprise Voice 的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="026f9-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="026f9-124">Lync Server 2013 中的企業語音部署程序概觀</span><span class="sxs-lookup"><span data-stu-id="026f9-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="026f9-125">在 Lync Server 2013 中將使用者移至企業語音</span><span class="sxs-lookup"><span data-stu-id="026f9-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="026f9-126">Lync Server 2013 中的 lync PreCall 診斷工具</span><span class="sxs-lookup"><span data-stu-id="026f9-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

