---
title: 連接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="71d01-102">連接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="71d01-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71d01-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="71d01-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="71d01-104">每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="71d01-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="71d01-105">當升級之集區時，一旦集區已移轉至 Lync Server 2013 時，必須分離前端集區移轉至 Lync Server 2013，SBA 從 Lync Server 2010 前端集區時，SBA 可以重新相關聯的已升級的前端集區。</span><span class="sxs-lookup"><span data-stu-id="71d01-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="71d01-106">這包括刪除 SBA 從拓撲產生器的舊版 Lync Server 2010 拓撲並再將 SBA 新增至 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="71d01-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="71d01-107">隸屬於舊版 Lync Server 2010 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。</span><span class="sxs-lookup"><span data-stu-id="71d01-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="71d01-108">一旦 SBA 新增至 Lync Server 2013 拓撲後，這些使用者可以再移回 sba。</span><span class="sxs-lookup"><span data-stu-id="71d01-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="71d01-109">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="71d01-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="71d01-110">將分支使用者隸屬於舊版 SBA Lync Server 2010 至另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="71d01-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="71d01-111">若要中斷作為備份登錄器的現有前端集區的舊版 Lync Server 2010 拓撲移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="71d01-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="71d01-112">將 SBA 新增至 Lync Server 2013 拓撲，並將此新前端集區設定為備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="71d01-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="71d01-113">將分支使用者移至新的 Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="71d01-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="71d01-114">**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**</span><span class="sxs-lookup"><span data-stu-id="71d01-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="71d01-115">開啟**拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="71d01-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="71d01-116">在左窗格中以滑鼠右鍵按一下 [**分支站台**，，，然後按一下 [**新的分支網站**。</span><span class="sxs-lookup"><span data-stu-id="71d01-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="71d01-117">在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="71d01-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="71d01-118">（選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。</span><span class="sxs-lookup"><span data-stu-id="71d01-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="71d01-119">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71d01-119">Click **Next**.</span></span>

6.  <span data-ttu-id="71d01-120">（選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="71d01-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="71d01-121">按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="71d01-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="71d01-122">按一下 [省/地區\*\*\*\*，然後輸入位置的省或地區的分支網站所在的名稱。</span><span class="sxs-lookup"><span data-stu-id="71d01-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="71d01-123">按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。</span><span class="sxs-lookup"><span data-stu-id="71d01-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="71d01-124">按一下 [**下一步**，，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="71d01-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="71d01-125">如果您在此網站使用的 Lync 2010 Survivable Branch Appliance 或 Server，請務必取消選取 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**的選項。</span><span class="sxs-lookup"><span data-stu-id="71d01-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="71d01-126">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71d01-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="71d01-127">若要建立舊版 Lync Server 2010 SBA 與 Lync Server 2013 前端集區的關聯：</span><span class="sxs-lookup"><span data-stu-id="71d01-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="71d01-128">展開已建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="71d01-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="71d01-129">以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="71d01-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="71d01-130">按一下 [ **Survivable Branch Appliance...**</span><span class="sxs-lookup"><span data-stu-id="71d01-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="71d01-131">依照精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="71d01-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="71d01-132">精靈項目的相關資訊，請參閱[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="71d01-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71d01-133">Lync Server 2010 Survivable Branch Appliance 僅可與 Lync Server 2010 監控儲存區相關聯。</span><span class="sxs-lookup"><span data-stu-id="71d01-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="71d01-134">如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="71d01-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="71d01-135">針對您想要新增至拓撲每一個分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="71d01-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

