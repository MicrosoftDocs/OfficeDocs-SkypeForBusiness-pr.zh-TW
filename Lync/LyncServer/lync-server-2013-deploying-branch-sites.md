---
title: Lync Server 2013：部署分支網站
description: Lync Server 2013：部署分支網站。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552639"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="3d81d-103">在 Lync Server 2013 中部署分支網站</span><span class="sxs-lookup"><span data-stu-id="3d81d-103">Deploying branch sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d81d-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3d81d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3d81d-105">分支網站使用者在分支網站相關聯的中央網站上，從該伺服器取得大多數的 Lync Server 2013 功能。</span><span class="sxs-lookup"><span data-stu-id="3d81d-105">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="3d81d-106">每個分支網站都恰與一個中央網站關聯。</span><span class="sxs-lookup"><span data-stu-id="3d81d-106">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="3d81d-107">若要與公用交換電話網路 (PSTN) 傳送通話，分支網站可能包含下列任一項：</span><span class="sxs-lookup"><span data-stu-id="3d81d-107">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="3d81d-108">PSTN 閘道，以及可能包含中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3d81d-108">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="3d81d-109">SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="3d81d-109">A SIP trunk</span></span>

  - <span data-ttu-id="3d81d-110">現有語音基礎結構搭配專用交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="3d81d-110">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="3d81d-111">Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="3d81d-111">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="3d81d-112">Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="3d81d-112">A Survivable Branch Server</span></span>

<span data-ttu-id="3d81d-113">使用 Survivable 分支裝置或 Survivable Branch 伺服器的分支網站，在廣域網路絡或中央網站發生故障的情況下，會比沒有這些解決方案的分支網站更具彈性。</span><span class="sxs-lookup"><span data-stu-id="3d81d-113">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="3d81d-114">例如，在已部署 Survivable 分支裝置或 Survivable Branch 伺服器的網站中，如果將分支網站連接到中央網站時，使用者仍可撥打和接收 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="3d81d-114">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="3d81d-115">若要達到分支網站恢復能力，另一種方式是使用 PSTN 閘道，或在分支網站使用具有完整層級 Lync Server 部署的 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="3d81d-115">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="3d81d-116">如需有關貴組織正確分支網站部署的詳細資訊，包括必要條件和其他規劃考慮，請參閱規劃檔中的規劃 lync server [2013 中的 PSTN](lync-server-2013-planning-for-pstn-connectivity.md) 連線和 [規劃分支網站語音2013彈性](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d81d-116">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d81d-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3d81d-117">In This Section</span></span>

  - [<span data-ttu-id="3d81d-118">在 Lync Server 2013 的分支網站提供 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="3d81d-118">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="3d81d-119">使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器</span><span class="sxs-lookup"><span data-stu-id="3d81d-119">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

