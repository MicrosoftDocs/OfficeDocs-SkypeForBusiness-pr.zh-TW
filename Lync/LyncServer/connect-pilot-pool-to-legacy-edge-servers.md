---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 313d2201be5f5919aeec37087a02bf7f400d7ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="6b057-102">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="6b057-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b057-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="6b057-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="6b057-104">在部署 Lync Server 2013 之後，您必須為您的網站設定同盟路由。</span><span class="sxs-lookup"><span data-stu-id="6b057-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="6b057-105">為了使用 Lync Server 2010 所使用的同盟路由，Lync Server 2013 必須設定為使用此路由。</span><span class="sxs-lookup"><span data-stu-id="6b057-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="6b057-106">若要讓 Lync Server 2013 網站使用 Lync Server 2010 部署的 Director 和 Edge Server，請使用拓撲產生器建立與舊版 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="6b057-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="6b057-107">使用拓撲產生器來與舊版 Edge 集區建立關聯</span><span class="sxs-lookup"><span data-stu-id="6b057-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="6b057-108">開啟**拓撲**產生器。</span><span class="sxs-lookup"><span data-stu-id="6b057-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="6b057-109">選取您的網站，它會直接在**Lync Server**節點底下。</span><span class="sxs-lookup"><span data-stu-id="6b057-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="6b057-110">在 [動作]\*\*\*\* 功能表上，按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6b057-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="6b057-111">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="6b057-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="6b057-112">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [lync server 2010 Director] 或 [Lync server 2010 Edge Server （如果未列出 Director）]。</span><span class="sxs-lookup"><span data-stu-id="6b057-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="6b057-113">![編輯屬性、同盟路由頁面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "編輯屬性、同盟路由頁面")</span><span class="sxs-lookup"><span data-stu-id="6b057-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="6b057-114">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="6b057-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="6b057-115">在 [拓撲產生器] 的 [Lync Server 2013] 節點下，流覽至 [ **Standard edition server** ] 或 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6b057-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="6b057-116">在 [關聯]\*\*\*\* 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6b057-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="6b057-117">從清單中，選取舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6b057-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="6b057-118">![[編輯屬性] 對話方塊，選取舊版 Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "[編輯屬性] 對話方塊，選取舊版 Edge")</span><span class="sxs-lookup"><span data-stu-id="6b057-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="6b057-119">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="6b057-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="6b057-120">在 [**拓撲**產生器] 中，選取最頂端的節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="6b057-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="6b057-121">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6b057-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="6b057-122">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6b057-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

