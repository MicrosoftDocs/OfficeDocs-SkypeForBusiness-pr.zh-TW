---
title: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區
description: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e7e13ccd35a653d38174f55ace9dc6637ded04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554909"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="f6486-103">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f6486-103">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6486-104">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f6486-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f6486-105">如果在設定 Lync Server 同盟的 Edge 集區發生問題，則必須變更同盟使用不同的 Edge 集區，同盟才能運作。</span><span class="sxs-lookup"><span data-stu-id="f6486-105">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="f6486-106">容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f6486-106">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="f6486-p101">在前端伺服器上，開啟拓撲產生器。展開 **[Edge 集區]**，然後在目前設定用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="f6486-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="f6486-p102">在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]\*\*\*\*。按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6486-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="f6486-p103">展開 [Edge 集區]\*\*\*\*，然後在現在要用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 [編輯內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6486-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="f6486-p104">在 [編輯內容]\*\*\*\* 中，選取 [一般]\*\*\*\* 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6486-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="f6486-p105">按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f6486-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="f6486-p106">在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 **[安裝或更新 Lync Server 系統]**、**[安裝或移除 Lync Server 元件]**、**[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="f6486-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="f6486-p107">在 [安裝 Lync Server 元件] 中，按 **[下一步]**。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。按一下 **[完成]** 完成部署。</span><span class="sxs-lookup"><span data-stu-id="f6486-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="f6486-126">如果失敗 Edge 集區所在的網站包含仍在執行的前端伺服器，則必須更新在這些前端集區上的 Web 會議服務及 A/V 會議服務，以使用遠端網站上仍在執行的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="f6486-126">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="f6486-127">如需詳細資訊，請參閱 [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="f6486-127">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6486-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f6486-128">See Also</span></span>


[<span data-ttu-id="f6486-129">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f6486-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="f6486-130">在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f6486-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="f6486-131">Lync Server 2013 中的 Edge Server 災難性修復</span><span class="sxs-lookup"><span data-stu-id="f6486-131">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

