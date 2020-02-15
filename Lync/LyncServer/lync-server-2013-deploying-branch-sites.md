---
title: Lync Server 2013： 部署分支站台
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
ms.openlocfilehash: edacf70cf4a8b899857864c400fa92f78bb0d94b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="800ff-102">部署 Lync Server 2013 中的分支網站</span><span class="sxs-lookup"><span data-stu-id="800ff-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="800ff-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="800ff-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="800ff-104">分支網站使用者在分支網站相關聯的中央網站從伺服器取得它們大部分的 Lync Server 2013 功能。</span><span class="sxs-lookup"><span data-stu-id="800ff-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="800ff-105">每個分支網站都恰與一個中央網站關聯。</span><span class="sxs-lookup"><span data-stu-id="800ff-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="800ff-106">若要與公用交換電話網路 (PSTN) 傳送通話，分支網站可能包含下列任一項：</span><span class="sxs-lookup"><span data-stu-id="800ff-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="800ff-107">PSTN 閘道，以及可能包含中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="800ff-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="800ff-108">SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="800ff-108">A SIP trunk</span></span>

  - <span data-ttu-id="800ff-109">現有語音基礎結構搭配專用交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="800ff-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="800ff-110">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="800ff-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="800ff-111">Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="800ff-111">A Survivable Branch Server</span></span>

<span data-ttu-id="800ff-112">Survivable Branch Appliance 或 Survivable Branch Server 分支站台位於更有彈性廣域網路或中央站台失敗的次數超過分支網站，而這些解決方案的其中一個。</span><span class="sxs-lookup"><span data-stu-id="800ff-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="800ff-113">例如，在網站使用 Survivable Branch Appliance 或 Survivable Branch 伺服器部署中，使用者可以仍撥打及接聽 PSTN 通話如果網路連線至中央網站的分支站台不通。</span><span class="sxs-lookup"><span data-stu-id="800ff-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="800ff-114">以達到分支網站恢復的另一種方式是使用 PSTN 閘道或 SIP 主幹與分支網站的完整規模 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="800ff-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="800ff-115">如需詳細資訊需哪種分支網站部署最適合您的組織，包括先決條件和其他規劃考量，請參閱規劃文件中的[Planning for Lync Server 2013 中的 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md)」 和 「 [Lync Server 2013 中的分支網站語音恢復能力的計劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="800ff-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="800ff-116">本章節內容</span><span class="sxs-lookup"><span data-stu-id="800ff-116">In This Section</span></span>

  - [<span data-ttu-id="800ff-117">提供在分支網站 Lync Server 2013 中的 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="800ff-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="800ff-118">部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="800ff-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

