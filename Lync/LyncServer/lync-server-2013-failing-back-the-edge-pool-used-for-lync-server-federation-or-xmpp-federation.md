---
title: 容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="36797-102">在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="36797-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36797-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="36797-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="36797-104">當您用來主持同盟的邊緣池已重新連線之後，請使用此程式來容錯回復 Lync Server 同盟路由和/或 XMPP 同盟路由，以再次使用此已還原的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="36797-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="36797-105">無法將同盟切回已還原的邊緣池</span><span class="sxs-lookup"><span data-stu-id="36797-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="36797-106">在現在可以再次使用的邊緣池中，啟動 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="36797-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="36797-107">如果您想要將 Lync Server 同盟路由容錯回復到使用已還原的邊緣伺服器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="36797-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="36797-108">在前端伺服器上，開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="36797-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="36797-109">展開 [**邊緣池**]，然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="36797-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="36797-110">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="36797-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="36797-111">在 [**編輯屬性**] 底下的 **[一般**] 底下，清除 **[針對此 Edge 池啟用同盟（埠5061）**]。</span><span class="sxs-lookup"><span data-stu-id="36797-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="36797-112">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="36797-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="36797-113">展開 [**邊緣池**]，然後以滑鼠右鍵按一下您想要用於同盟的原始邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="36797-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="36797-114">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="36797-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="36797-115">在 [**編輯屬性**] 底下的 **[一般**] 底下，選取 **[針對此 Edge 池啟用同盟（埠5061）**]。</span><span class="sxs-lookup"><span data-stu-id="36797-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="36797-116">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="36797-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="36797-117">按一下 [**動作**]，選取 [**拓撲**]，選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="36797-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="36797-118">**發佈拓撲**時出現提示時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36797-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="36797-119">發佈完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="36797-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="36797-120">在邊緣伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="36797-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="36797-121">按一下 [**安裝或更新 Lync Server 系統**]，然後按一下 [**設定] 或 [移除 Lync server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="36797-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="36797-122">再次按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="36797-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="36797-123">在安裝程式 Lync Server 元件上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36797-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="36797-124">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="36797-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="36797-125">完成部署之後，按一下 [**查看記錄**] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="36797-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="36797-126">按一下 **[完成]** 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="36797-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="36797-127">如果您想要將 XMPP 同盟路由容錯回復到使用已還原的邊緣伺服器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="36797-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="36797-128">執行下列 Cmdlet，將 XMPP 同盟路由 repoint 到 Edge 池中，這將會立即託管 XMPP 同盟（在此範例中為 EdgeServer1）：</span><span class="sxs-lookup"><span data-stu-id="36797-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="36797-129">在這個範例中，Site1 是包含邊緣池的網站，現在將託管 XMPP 同盟路由，而 EdgeServer1.contoso.com 是該池中的邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="36797-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="36797-130">如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄，而該內容現在將託管 XMPP 同盟，您必須新增該記錄，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="36797-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="36797-131">這個 SRV 記錄的埠值必須是5269。</span><span class="sxs-lookup"><span data-stu-id="36797-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="36797-132">在外部 DNS 伺服器上，將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="36797-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="36797-133">確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。</span><span class="sxs-lookup"><span data-stu-id="36797-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="36797-134">如果前端池仍在包含已失敗且已還原的邊緣池的網站中執行，您應該在這些前端池上更新網路會議服務和 A/V 會議服務，以再次使用其本機網站上的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="36797-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="36797-135">如需詳細資訊，請參閱[在 Lync Server 2013 中變更與前端池相關聯的邊緣池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="36797-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="36797-136">如果與失敗的邊緣池位於同一網站的前端池也失敗，您現在可以使用 Invoke-CsPoolFailback 來容錯回復前端池。</span><span class="sxs-lookup"><span data-stu-id="36797-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36797-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="36797-137">See Also</span></span>


[<span data-ttu-id="36797-138">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="36797-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="36797-139">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="36797-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="36797-140">Lync Server 2013 中的 Edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="36797-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

