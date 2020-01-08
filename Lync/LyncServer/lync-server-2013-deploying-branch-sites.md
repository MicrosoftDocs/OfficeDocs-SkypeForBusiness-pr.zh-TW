---
title: Lync Server 2013：部署分支網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="72ba3-102">在 Lync Server 2013 中部署分支網站</span><span class="sxs-lookup"><span data-stu-id="72ba3-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72ba3-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="72ba3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="72ba3-104">分支網站使用者在分支網站所關聯的中央網站上，從伺服器取得最大部分的 Lync Server 2013 功能。</span><span class="sxs-lookup"><span data-stu-id="72ba3-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="72ba3-105">每個分支網站都只與一個中央網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="72ba3-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="72ba3-106">若要提供與公眾交換電話網絡（PSTN）的呼叫和來源，分支網站可能會包含下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="72ba3-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="72ba3-107">PSTN 閘道和可能是 Meditation 伺服器</span><span class="sxs-lookup"><span data-stu-id="72ba3-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="72ba3-108">SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="72ba3-108">A SIP trunk</span></span>

  - <span data-ttu-id="72ba3-109">具有私人分支 exchange （PBX）的現有語音結構</span><span class="sxs-lookup"><span data-stu-id="72ba3-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="72ba3-110">Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="72ba3-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="72ba3-111">Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="72ba3-111">A Survivable Branch Server</span></span>

<span data-ttu-id="72ba3-112">使用 Survivable 分支裝置或 Survivable 分支伺服器的分支網站，比不含下列其中一種解決方案的分支網站的廣域網路或中央網站故障更具彈性。</span><span class="sxs-lookup"><span data-stu-id="72ba3-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="72ba3-113">例如，在已部署 Survivable 分支裝置或 Survivable 分支伺服器的網站中，如果將分支網站連線到中央網站的網路，使用者仍然可以撥打和接聽 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="72ba3-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="72ba3-114">若要實現分支網站復原，另一種方式是在分支網站上使用 PSTN 閘道或 SIP 幹線進行完整的 Lync 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="72ba3-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="72ba3-115">如需有關哪個分支網站部署適合您組織的詳細資料（包括先決條件及其他規劃考慮），請參閱規劃檔中的 lync server [2013 規劃](lync-server-2013-planning-for-pstn-connectivity.md)，以及在[lync Server 2013 中規劃分支網站語音復原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="72ba3-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72ba3-116">本節內容</span><span class="sxs-lookup"><span data-stu-id="72ba3-116">In This Section</span></span>

  - [<span data-ttu-id="72ba3-117">使用 Lync Server 2013 在分支網站提供 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="72ba3-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="72ba3-118">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="72ba3-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

