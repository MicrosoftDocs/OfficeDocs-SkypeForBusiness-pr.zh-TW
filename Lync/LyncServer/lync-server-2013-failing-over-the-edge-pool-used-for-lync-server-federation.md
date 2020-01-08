---
title: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="deea5-102">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="deea5-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deea5-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="deea5-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="deea5-104">如果您已將 Lync Server federation 的邊緣池設定為 down，您必須將同盟變更為使用不同的邊緣池才能運作。</span><span class="sxs-lookup"><span data-stu-id="deea5-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="deea5-105">針對 Lync Server Federation 所用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="deea5-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="deea5-106">在前端伺服器上，開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="deea5-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="deea5-107">展開 [**邊緣池**]，然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="deea5-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="deea5-108">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="deea5-109">在 [**編輯屬性**] 底下的 **[一般**] 底下，清除 **[針對此 Edge 池啟用同盟（埠5061）**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="deea5-110">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deea5-110">Click **OK**.</span></span>

3.  <span data-ttu-id="deea5-111">展開 [**邊緣池**]，然後以滑鼠右鍵按一下您要用於同盟的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="deea5-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="deea5-112">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="deea5-113">在 [**編輯屬性**] 底下的 **[一般**] 底下，選取 **[針對此 Edge 池啟用同盟（埠5061）**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="deea5-114">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deea5-114">Click **OK**.</span></span>

5.  <span data-ttu-id="deea5-115">按一下 [**動作**]，選取 [**拓撲**]，選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="deea5-116">**發佈拓撲**時出現提示時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="deea5-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="deea5-117">發佈完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="deea5-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="deea5-118">在邊緣伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="deea5-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="deea5-119">按一下 [**安裝或更新 Lync Server 系統**]，然後按一下 [**設定] 或 [移除 Lync server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="deea5-120">再次按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="deea5-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="deea5-121">在安裝程式 Lync Server 元件上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="deea5-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="deea5-122">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="deea5-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="deea5-123">完成部署之後，按一下 [**查看記錄**] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="deea5-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="deea5-124">按一下 **[完成]** 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="deea5-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="deea5-125">如果包含失敗的邊緣池的網站包含仍在執行的前端伺服器，您必須更新這些前端池的 Web 會議服務和 A/V 會議服務，才能在仍在執行的遠端網站中使用 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="deea5-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="deea5-126">如需詳細資訊，請參閱[在 Lync Server 2013 中變更與前端池相關聯的邊緣池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="deea5-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="deea5-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="deea5-127">See Also</span></span>


[<span data-ttu-id="deea5-128">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="deea5-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="deea5-129">在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="deea5-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="deea5-130">Lync Server 2013 中的 Edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="deea5-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

