---
title: 連線 Survivable Branch Appliance
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
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="61e4d-102">連線 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="61e4d-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61e4d-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="61e4d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="61e4d-104">每個 Survivable 分支裝置（SBA）都與一個前端池相關聯，可充當 SBA 的備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="61e4d-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="61e4d-105">當您將前端池遷移至 Lync Server 2013 時，在升級池時，必須從 Lync Server 2010 前端池解除 SBA，而將池遷移至 Lync Server 2013 之後，SBA 就可以與升級的前端池重新關聯。</span><span class="sxs-lookup"><span data-stu-id="61e4d-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="61e4d-106">這涉及從拓撲產生器中的舊版 Lync Server 2010 拓朴刪除 SBA，然後將 SBA 新增至 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="61e4d-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="61e4d-107">必須先將駐留在舊版 Lync Server 2010 SBA 的使用者移到另一個前端池，才能從拓撲結構中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="61e4d-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="61e4d-108">將 SBA 新增至 Lync Server 2013 拓撲之後，這些使用者就可以移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="61e4d-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="61e4d-109">下列步驟摘要如下所示：</span><span class="sxs-lookup"><span data-stu-id="61e4d-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="61e4d-110">將駐留在舊版 SBA Lync Server 2010 的分支使用者移至另一個前端池。</span><span class="sxs-lookup"><span data-stu-id="61e4d-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="61e4d-111">從舊版 Lync Server 2010 拓撲中移除 SBA，以將現有的前端池與備份註冊機構斷開連線。</span><span class="sxs-lookup"><span data-stu-id="61e4d-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="61e4d-112">在 Lync Server 2013 拓撲中新增 SBA，並將這個新的 [前端] 池設定為備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="61e4d-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="61e4d-113">將分支使用者移至新的 Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="61e4d-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="61e4d-114">**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**</span><span class="sxs-lookup"><span data-stu-id="61e4d-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="61e4d-115">開啟**拓撲**建立器。</span><span class="sxs-lookup"><span data-stu-id="61e4d-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="61e4d-116">在左窗格中，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="61e4d-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="61e4d-117">在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="61e4d-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="61e4d-118">可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="61e4d-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="61e4d-119">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="61e4d-119">Click **Next**.</span></span>

6.  <span data-ttu-id="61e4d-120">可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="61e4d-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="61e4d-121">按一下 [**城市**]，然後輸入分支網站所在城市的名稱。</span><span class="sxs-lookup"><span data-stu-id="61e4d-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="61e4d-122">按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="61e4d-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="61e4d-123">按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。</span><span class="sxs-lookup"><span data-stu-id="61e4d-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="61e4d-124">按一下 **[下一步]**，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="61e4d-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="61e4d-125">如果您是在此網站使用 Lync 2010 Survivable 分支裝置或伺服器，請務必取消選取 [**當此嚮導關閉時，開啟新的 Survivable 嚮導]** 選項。</span><span class="sxs-lookup"><span data-stu-id="61e4d-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="61e4d-126">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="61e4d-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="61e4d-127">若要將舊版 Lync Server 2010 SBA 與 Lync Server 2013 前端池建立關聯：</span><span class="sxs-lookup"><span data-stu-id="61e4d-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="61e4d-128">展開已建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="61e4d-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="61e4d-129">以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="61e4d-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="61e4d-130">按一下 [ **Survivable 分支裝置]。**</span><span class="sxs-lookup"><span data-stu-id="61e4d-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="61e4d-131">依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="61e4d-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="61e4d-132">如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="61e4d-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61e4d-133">Lync Server 2010 Survivable 分支裝置只能與 Lync Server 2010 監視存放區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="61e4d-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="61e4d-134">如果您不是在此網站使用 Survivable 分支裝置或伺服器，請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="61e4d-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="61e4d-135">針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="61e4d-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

