---
title: 連線 Survivable Branch Appliance
description: 連接 Survivable 分支裝置。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5bbf9e1a4189d3c80d6dec449adf68b82cd3691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550279"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="e93e9-103">連線 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="e93e9-103">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93e9-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e93e9-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e93e9-105">每個 Survivable Branch 裝置 (SBA) 都會與前端集區相關聯，以充當 SBA 的備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="e93e9-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="e93e9-106">當前端集區遷移至 Lync Server 2013 時，當集區遷移至 Lync Server 2013 時，SBA 必須解除與 Lync Server 2010 前端集區的關聯，且在將集區遷移至 Lync Server 後，便可與升級的前端集區重新建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e93e9-106">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="e93e9-107">這包括在拓撲產生器中從舊版 Lync Server 2010 拓撲刪除 SBA，然後將 SBA 新增至 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="e93e9-107">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="e93e9-108">位於舊版 Lync Server 2010 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="e93e9-108">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="e93e9-109">將 SBA 新增至 Lync Server 2013 拓撲之後，就可以將這些使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="e93e9-109">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="e93e9-110">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="e93e9-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="e93e9-111">將駐留在舊版 SBA Lync Server 2010 的分支使用者移至另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="e93e9-111">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="e93e9-112">從舊版 Lync Server 2010 拓撲移除 SBA，以中斷現有前端集區的備份註冊機的連線。</span><span class="sxs-lookup"><span data-stu-id="e93e9-112">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="e93e9-113">將 SBA 新增至 Lync Server 2013 拓撲，並將這個新的前端集區設定為備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="e93e9-113">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="e93e9-114">將分支使用者移至新的 Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="e93e9-114">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="e93e9-115">**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**</span><span class="sxs-lookup"><span data-stu-id="e93e9-115">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="e93e9-116">開啟 **拓撲**產生器。</span><span class="sxs-lookup"><span data-stu-id="e93e9-116">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="e93e9-117">在左窗格中，以滑鼠右鍵按一下 [ **分支網站**]，然後按一下 [ **新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="e93e9-117">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="e93e9-118">在 [ **定義新的分支網站** ] 對話方塊中，按一下 [ **名稱**]，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="e93e9-118">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="e93e9-119"> (選用) 按一下 [ **描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="e93e9-119">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="e93e9-120">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e93e9-120">Click **Next**.</span></span>

6.  <span data-ttu-id="e93e9-121"> (選用) 在下一個 [ **定義新的分支網站** ] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e93e9-121">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="e93e9-122">按一下 [ **城市**]，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="e93e9-122">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="e93e9-123">按一下 [ **省/地區**]，然後輸入分支網站所在位置的省或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="e93e9-123">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="e93e9-124">按一下 [ **國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。</span><span class="sxs-lookup"><span data-stu-id="e93e9-124">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="e93e9-125">按 **[下一步]**，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="e93e9-125">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="e93e9-126">如果您在此網站使用 Lync 2010 Survivable 分支裝置或伺服器，請務必取消選取 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 選項。</span><span class="sxs-lookup"><span data-stu-id="e93e9-126">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="e93e9-127">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e93e9-127">Click **Finish**.</span></span>

8.  <span data-ttu-id="e93e9-128">若要將舊版 Lync Server 2010 SBA 關聯至 Lync Server 2013 前端集區：</span><span class="sxs-lookup"><span data-stu-id="e93e9-128">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="e93e9-129">展開已經建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="e93e9-129">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="e93e9-130">以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="e93e9-130">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="e93e9-131">按一下 [ **Survivable 分支裝置 ...]。**</span><span class="sxs-lookup"><span data-stu-id="e93e9-131">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="e93e9-132">依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e93e9-132">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="e93e9-133">如需有關 [嚮導專案] 的詳細資訊，請參閱 [在 Lync Server 2013 中定義 Survivable Branch 裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e93e9-133">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e93e9-134">Lync Server 2010 Survivable Branch 裝置只能與 Lync Server 2010 Monitoring Store 相關聯。</span><span class="sxs-lookup"><span data-stu-id="e93e9-134">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="e93e9-135">如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在 **此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e93e9-135">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="e93e9-136">針對您要新增至拓撲的每一個分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="e93e9-136">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

