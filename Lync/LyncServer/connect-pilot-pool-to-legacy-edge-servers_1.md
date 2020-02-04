---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09858b03c787af034790c94bcbf12ca6ea7ceecf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="ced33-102">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ced33-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ced33-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ced33-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ced33-104">部署 Lync Server 2013 之後，未設定此網站的同盟路線。</span><span class="sxs-lookup"><span data-stu-id="ced33-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="ced33-105">若要使用由 Office 通訊伺服器 2007 R2 使用的聯盟路由，必須將 Lync Server 2013 設定為使用此路由。</span><span class="sxs-lookup"><span data-stu-id="ced33-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="ced33-106">若要讓 Lync Server 2013 網站使用 BackCompatSite 的控制器和邊緣伺服器，請使用拓撲建立器來關聯舊版 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="ced33-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="ced33-107">使用拓撲建立器關聯舊版 Edge 池</span><span class="sxs-lookup"><span data-stu-id="ced33-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="ced33-108">在拓撲建立器中開啟 [試驗區] 拓撲。</span><span class="sxs-lookup"><span data-stu-id="ced33-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="ced33-109">選取您的 Lync Server 2013 網站。</span><span class="sxs-lookup"><span data-stu-id="ced33-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="ced33-110">在 [**動作**] 功能表上，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ced33-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="ced33-111">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [Office 通訊伺服器 2007 r2 控制器]，或 [Office 通訊伺服器 2007 r2 Edge 伺服器] （如果沒有列出主管）。</span><span class="sxs-lookup"><span data-stu-id="ced33-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="ced33-112">![[編輯內容] 對話方塊，[同盟路由] 頁面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[編輯內容] 對話方塊，[同盟路由] 頁面")</span><span class="sxs-lookup"><span data-stu-id="ced33-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="ced33-113">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ced33-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="ced33-114">在 [拓撲建立器] 中，在 [Lync Server 2013] 節點底下，流覽至 [**標準版] 伺服器**或 [**企業版] 前端池**，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ced33-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="ced33-115">在 [**關聯**性] 底下，選取 [關聯邊緣池] 旁的核取方塊 **（適用于媒體元件）**。</span><span class="sxs-lookup"><span data-stu-id="ced33-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="ced33-116">從清單中選取 BackCompatSite 的邊緣伺服器介面。</span><span class="sxs-lookup"><span data-stu-id="ced33-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="ced33-117">![[編輯內容] 對話方塊，[一般] 頁面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[編輯內容] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="ced33-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="ced33-118">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ced33-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="ced33-119">在 [**拓撲**建立器] 中，選取最頂端的節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="ced33-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="ced33-120">在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ced33-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="ced33-121">**發佈嚮導**完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ced33-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

