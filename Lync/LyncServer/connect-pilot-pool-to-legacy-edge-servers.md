---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="df04e-102">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="df04e-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df04e-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="df04e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="df04e-104">部署 Lync Server 2013 之後，您必須為您的網站設定同盟路由。</span><span class="sxs-lookup"><span data-stu-id="df04e-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="df04e-105">若要使用 Lync Server 2010 所使用的同盟路由，Lync Server 2013 必須設定為使用這個路由。</span><span class="sxs-lookup"><span data-stu-id="df04e-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="df04e-106">若要讓 Lync Server 2013 網站使用 Lync Server 2010 部署的控制器與邊緣伺服器，請使用拓撲建立器來關聯舊版 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="df04e-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="df04e-107">使用拓撲建立器關聯舊版 Edge 池</span><span class="sxs-lookup"><span data-stu-id="df04e-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="df04e-108">開啟**拓撲**建立器。</span><span class="sxs-lookup"><span data-stu-id="df04e-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="df04e-109">選取您的網站，這會直接位於**Lync Server**節點的正下方。</span><span class="sxs-lookup"><span data-stu-id="df04e-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="df04e-110">在 [**動作**] 功能表上，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="df04e-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="df04e-111">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="df04e-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="df04e-112">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [lync server 2010 控制器]，或 [Lync server 2010 Edge 伺服器（如果沒有列出主管）]。</span><span class="sxs-lookup"><span data-stu-id="df04e-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="df04e-113">![編輯內容，[同盟路由] 頁面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "編輯內容，[同盟路由] 頁面")</span><span class="sxs-lookup"><span data-stu-id="df04e-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="df04e-114">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="df04e-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="df04e-115">在 [拓撲建立器] 中，在 [Lync Server 2013] 節點底下，流覽至 [**標準版] 伺服器**或 [**企業版] 前端池**，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="df04e-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="df04e-116">在 [**關聯**性] 底下，選取 [關聯邊緣池] 旁的核取方塊 **（適用于媒體元件）**。</span><span class="sxs-lookup"><span data-stu-id="df04e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="df04e-117">從清單中選取舊版邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="df04e-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="df04e-118">![[編輯內容] 對話方塊，選取舊版 Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "[編輯內容] 對話方塊，選取舊版 Edge")</span><span class="sxs-lookup"><span data-stu-id="df04e-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="df04e-119">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="df04e-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="df04e-120">在 [**拓撲**建立器] 中，選取最頂端的節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="df04e-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="df04e-121">在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df04e-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="df04e-122">**發佈嚮導**完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="df04e-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

