---
title: 將試驗集區連接到舊版 Edge Server
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
ms.openlocfilehash: cc9213dbf5d75b80ccbfc67d03cfb3c02ef87145
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8e960-102">將試驗集區連接到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="8e960-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e960-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="8e960-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8e960-104">部署 Lync Server 2013 之後, 您要設定您的站台同盟路由。</span><span class="sxs-lookup"><span data-stu-id="8e960-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="8e960-105">若要使用 Lync Server 2010 正在使用的同盟的路由，Lync Server 2013 必須設定為使用此路由。</span><span class="sxs-lookup"><span data-stu-id="8e960-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="8e960-106">若要啟用 Lync Server 2013 站台能夠使用 Lync Server 2010 部署的 Edge Server 與 Director，請使用拓撲產生器建立舊版 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="8e960-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8e960-107">使用拓撲產生器來與舊版 Edge 集區建立關聯</span><span class="sxs-lookup"><span data-stu-id="8e960-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="8e960-108">開啟**拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="8e960-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="8e960-109">選取您的網站，也就是 [ **Lync Server** ] 節點的正下方。</span><span class="sxs-lookup"><span data-stu-id="8e960-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="8e960-110">在 [動作]\*\*\*\* 功能表上，按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e960-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8e960-111">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="8e960-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="8e960-112">在 [**站台同盟路由指派**]，選取 [**啟用 SIP 同盟**]，然後選取 [Lync Server 2010 Director 或 Lync Server 2010 Edge Server，如果未列出 Director。</span><span class="sxs-lookup"><span data-stu-id="8e960-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="8e960-113">![編輯同盟路由] 頁面上的屬性](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "編輯同盟路由] 頁面上的屬性")</span><span class="sxs-lookup"><span data-stu-id="8e960-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="8e960-114">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="8e960-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="8e960-115">在拓撲產生器] 下 [Lync Server 2013] 節點中，瀏覽至 [ **Standard Edition server** ] 或 [ **Enterprise Edition 前端集區**以滑鼠右鍵按一下集區，，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="8e960-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="8e960-116">在 [關聯]\*\*\*\* 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8e960-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="8e960-117">從清單中，選取舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="8e960-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="8e960-118">![編輯內容] 對話方塊中，選取舊版 Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "編輯內容] 對話方塊中，選取舊版 Edge")</span><span class="sxs-lookup"><span data-stu-id="8e960-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="8e960-119">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="8e960-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="8e960-120">在 [**拓撲產生器中**，選取最頂端的節點 [ **Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="8e960-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="8e960-121">從 [**動作**] 功能表中，[**發行拓撲**]，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e960-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="8e960-122">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e960-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

