---
title: Lync Server 2013 會議使用者模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="3917a-102">Lync Server 2013 中的會議使用者模型</span><span class="sxs-lookup"><span data-stu-id="3917a-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3917a-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3917a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3917a-104">Lync Server 會議使用者模型的重要部分是會議大小。</span><span class="sxs-lookup"><span data-stu-id="3917a-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="3917a-105">從多個資料點收集資料之後（如下一節所述），我們已決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="3917a-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="3917a-106">大多數的會議實際上都是小型共同作業會議，平均需要四個到六個參與者</span><span class="sxs-lookup"><span data-stu-id="3917a-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="3917a-107">大約80% 的會議人數少於20名參與者。</span><span class="sxs-lookup"><span data-stu-id="3917a-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="3917a-108">99.98% 的會議人數少於100個參與者。</span><span class="sxs-lookup"><span data-stu-id="3917a-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="3917a-109">除了會議大小以外，會議使用者模型也會考慮多種不同的因素，例如：</span><span class="sxs-lookup"><span data-stu-id="3917a-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="3917a-110">**同時**在會議上有多少使用者想要同時參與會議？   </span><span class="sxs-lookup"><span data-stu-id="3917a-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="3917a-111">**媒體混合**   使用哪些類型的媒體，且預期會供會議中的使用者使用？</span><span class="sxs-lookup"><span data-stu-id="3917a-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="3917a-112">**使用者類型**   是使用者內部使用者、遠端使用者、聯盟使用者或匿名使用者？</span><span class="sxs-lookup"><span data-stu-id="3917a-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="3917a-113">**會議加速**   會議的所有使用者加入會議需要多少時間？</span><span class="sxs-lookup"><span data-stu-id="3917a-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="3917a-114">如需使用者模型的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="3917a-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="3917a-115">若要決定用來測試的會議和使用者數量，我們已執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3917a-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="3917a-116">佔用組織中的使用者總數（例如，80000的使用者），並將其乘以會議併發費率（例如，5% 的所有使用者）來判斷會議中預期的使用者總數（在此範例中為、4000使用者）。</span><span class="sxs-lookup"><span data-stu-id="3917a-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="3917a-117">依部署中的 Lync Server 2013、前端伺服器數（例如，8個伺服器），以判斷每個前端伺服器的會議參與者估計人數（在此範例中為每個前端伺服器的500使用者）。</span><span class="sxs-lookup"><span data-stu-id="3917a-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="3917a-118">以平均會議大小（例如4個使用者）劃分每個前端伺服器的使用者數目，以判斷每個前臺伺服器估計的平均會議數（在這個範例中，每個前端伺服器的125會議）。</span><span class="sxs-lookup"><span data-stu-id="3917a-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="3917a-119">若要在每個前端伺服器上取得每個媒體負載，我們會估計媒體組合。</span><span class="sxs-lookup"><span data-stu-id="3917a-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="3917a-120">例如，假設75% 的會議不只需要音訊支援，而這些會議的50% 需要應用程式共用，平均47會議和188使用者都連線到每個前端伺服器以進行應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="3917a-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="3917a-121">已測試各種會議大小（根據我們在共用池中最多250個使用者的使用者模型），以確保伺服器的可伸縮性。</span><span class="sxs-lookup"><span data-stu-id="3917a-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

