---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="e2576-102">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e2576-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2576-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e2576-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e2576-104">在部署 Lync Server 2013 之後，未設定此網站的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="e2576-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="e2576-105">為了使用 Office 通訊伺服器 2007 R2 所使用的同盟路由，Lync Server 2013 必須設定成使用此路由。</span><span class="sxs-lookup"><span data-stu-id="e2576-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="e2576-106">若要讓 Lync Server 2013 網站使用 BackCompatSite 的 Director 和 Edge Server，請使用拓撲產生器建立與舊版 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="e2576-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="e2576-107">使用拓撲產生器來與舊版 Edge 集區建立關聯</span><span class="sxs-lookup"><span data-stu-id="e2576-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="e2576-108">在拓撲產生器中開啟試驗集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="e2576-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="e2576-109">選取您的 Lync Server 2013 網站。</span><span class="sxs-lookup"><span data-stu-id="e2576-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="e2576-110">在 [**動作**] 功能表上，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e2576-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="e2576-111">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [Office 通訊伺服器 2007 r2 Director]，或 Office 通訊伺服器 2007 r2 Edge Server （如果未列出 Director）。</span><span class="sxs-lookup"><span data-stu-id="e2576-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="e2576-112">![[編輯屬性] 對話方塊，[同盟路由] 頁面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[編輯屬性] 對話方塊，[同盟路由] 頁面")</span><span class="sxs-lookup"><span data-stu-id="e2576-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="e2576-113">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="e2576-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="e2576-114">在 [拓撲產生器] 的 [Lync Server 2013] 節點下，流覽至 [ **Standard edition server** ] 或 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e2576-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="e2576-115">在 [關聯]\*\*\*\* 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e2576-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="e2576-116">從清單中，選取 BackCompatSite 的 Edge Server 介面。</span><span class="sxs-lookup"><span data-stu-id="e2576-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="e2576-117">![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="e2576-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="e2576-118">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="e2576-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="e2576-119">在 [**拓撲**產生器] 中，選取最頂端的節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="e2576-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="e2576-120">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e2576-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="e2576-121">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2576-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

