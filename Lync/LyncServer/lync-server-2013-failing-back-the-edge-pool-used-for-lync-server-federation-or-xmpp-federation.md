---
title: 容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2fc24adb8808eae3d3152b74e29426b2facecfb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530990"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="27dd2-102">在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="27dd2-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27dd2-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="27dd2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="27dd2-104">在用來主控同盟的失敗 Edge 集區回到線上後，請使用此程式來容錯回復 Lync Server 同盟路由和/或 XMPP 同盟路由，以再次使用此還原的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="27dd2-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="27dd2-105">將同盟回復至還原的 Edge 集區失敗</span><span class="sxs-lookup"><span data-stu-id="27dd2-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="27dd2-106">在現在可以使用的 Edge 集區上，啟動 Edge Services。</span><span class="sxs-lookup"><span data-stu-id="27dd2-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="27dd2-107">如果您想要容錯回復 Lync Server 同盟路由以使用還原的 Edge Server，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="27dd2-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="27dd2-p101">在前端伺服器上，開啟拓撲產生器。展開 **[Edge 集區]**，然後在目前設定用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="27dd2-p102">在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]\*\*\*\*。按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="27dd2-113">展開 [ **Edge**集區]，然後以滑鼠右鍵按一下原始 Edge Server 或 Edge server 集區，以供同盟使用。</span><span class="sxs-lookup"><span data-stu-id="27dd2-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="27dd2-114">選取 [編輯內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27dd2-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="27dd2-p104">在 [編輯內容]\*\*\*\* 中，選取 [一般]\*\*\*\* 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="27dd2-p105">按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="27dd2-p106">在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 **[安裝或更新 Lync Server 系統]**、**[安裝或移除 Lync Server 元件]**、**[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="27dd2-p107">在 [安裝 Lync Server 元件] 中，按 **[下一步]**。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。按一下 **[完成]** 完成部署。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="27dd2-127">如果您想要容錯回復 XMPP 同盟路由以使用還原的 Edge Server，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="27dd2-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="27dd2-128">執行下列 Cmdlet，將 XMPP 同盟路由 repoint 至 Edge 集區，該集區現在會主控 XMPP 同盟 (在此範例中，EdgeServer1) ：</span><span class="sxs-lookup"><span data-stu-id="27dd2-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="27dd2-129">在此範例中，Site1 是包含 Edge 集區的網站，它現在會主控 XMPP 同盟路由，而且 EdgeServer1.contoso.com 是該集區中 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="27dd2-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="27dd2-p108">如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。</span><span class="sxs-lookup"><span data-stu-id="27dd2-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="27dd2-132">在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="27dd2-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="27dd2-133">確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。</span><span class="sxs-lookup"><span data-stu-id="27dd2-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="27dd2-134">如果前端集區仍在包含失敗且已還原之 Edge 集區的網站中執行，您應該更新這些前端集區上的 Web 會議服務和 A/V 會議服務，以再次使用本機網站上的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="27dd2-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="27dd2-135">如需詳細資訊，請參閱 [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="27dd2-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="27dd2-136">如果與失敗 Edge 集區位於相同網站的前端集區也失敗，您現在可以使用 Invoke–CsPoolFailback 來容錯回前端集區。</span><span class="sxs-lookup"><span data-stu-id="27dd2-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27dd2-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="27dd2-137">See Also</span></span>


[<span data-ttu-id="27dd2-138">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="27dd2-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="27dd2-139">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="27dd2-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="27dd2-140">Lync Server 2013 中的 Edge Server 災難性修復</span><span class="sxs-lookup"><span data-stu-id="27dd2-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

