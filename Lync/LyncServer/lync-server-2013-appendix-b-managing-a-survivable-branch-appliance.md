---
title: Lync Server 2013：附錄 B：管理 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="3f1d9-102">Lync Server 2013 中的附錄 B：管理 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="3f1d9-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f1d9-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3f1d9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3f1d9-104">本主題說明管理 Survivable 分支裝置的程式。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-105">具體來說，如何取代及重新命名 Survivable 分支裝置，以及如何變更與 Survivable 分支裝置相關聯的 Lync Server 2013 前端池。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="3f1d9-106">若要取代 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="3f1d9-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="3f1d9-107">在 Survivable 分支裝置上停止所有 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-108">（請參閱 Survivable 分支裝置供應商檔。）</span><span class="sxs-lookup"><span data-stu-id="3f1d9-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="3f1d9-109">採用從網域中移除 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="3f1d9-110">若要刪除 Active Directory 網域服務中的 Survivable 分支裝置電腦物件，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="3f1d9-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="3f1d9-111">以企業系統管理員群組的成員身分登入成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="3f1d9-112">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="3f1d9-113">以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="3f1d9-114">再次新增 Survivable 分支裝置電腦物件。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="3f1d9-115">（請參閱[在 Lync Server 2013 的 Active Directory 中新增 Survivable 分支裝置](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。）</span><span class="sxs-lookup"><span data-stu-id="3f1d9-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="3f1d9-116">等待 Active Directory 複製發生。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="3f1d9-117">開啟 Lync Server 管理命令介面，然後輸入**Enable-CSTopology**。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="3f1d9-118">將新的 Survivable 分支裝置連線到網路，然後依照[使用 Lync server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)的步驟進行，以使用 lync server [2013-分支網站工作來部署 Survivable 分支裝置或伺服器](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="3f1d9-119">若要重新命名 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="3f1d9-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="3f1d9-120">將使用者移至中心網站。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-120">Move users to the central site.</span></span> <span data-ttu-id="3f1d9-121">如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="3f1d9-122">在 Survivable 分支裝置上停止所有 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-123">（請參閱 Survivable 分支裝置供應商檔。）</span><span class="sxs-lookup"><span data-stu-id="3f1d9-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="3f1d9-124">若要從拓撲中移除 Survivable 分支裝置，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="3f1d9-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="3f1d9-125">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="3f1d9-126">在主控台樹中，展開 [**分支網站**]，按一下 [Survivable 分支裝置]，然後按一下 [動作] 窗格上的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="3f1d9-127">從網域中移除 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="3f1d9-128">若要刪除 Active Directory 中的 Survivable 分支裝置電腦物件，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3f1d9-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="3f1d9-129">以企業系統管理員群組的成員身分登入網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="3f1d9-130">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="3f1d9-131">以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="3f1d9-132">將 Survivable 分支裝置還原為出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="3f1d9-133">（請參閱 Survivable 分支裝置供應商檔。）</span><span class="sxs-lookup"><span data-stu-id="3f1d9-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="3f1d9-134">遵循[使用 Lync server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的步驟進行-中心網站工作，並[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器（分支網站工作）](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="3f1d9-135">將使用者移至重新命名的 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-136">如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="3f1d9-137">若要變更 Survivable 分支裝置所關聯的 Lync Server 前端池</span><span class="sxs-lookup"><span data-stu-id="3f1d9-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="3f1d9-138">從 Survivable 分支裝置將使用者移至中央網站上的 Lync Server 前端池。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="3f1d9-139">如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="3f1d9-140">停止 Survivable 分支裝置上的所有 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-141">（請參閱 Survivable 分支裝置供應商檔）。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="3f1d9-142">若要更新 Survivable 分支裝置所關聯的 Lync Server 前端池，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3f1d9-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="3f1d9-143">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="3f1d9-144">展開 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="3f1d9-145">以滑鼠右鍵按一下要修改的 Survivable 分支裝置物件，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="3f1d9-146">在 [復原] 底下，選取要與 Survivable 分支裝置相關聯的新 [前端] 池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="3f1d9-147">在主控台樹中，以滑鼠右鍵按一下新的 Survivable 分支裝置，按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="3f1d9-148">在 Survivable 分支裝置上重新開機所有 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="3f1d9-149">測試 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f1d9-150">如需詳細資訊，請參閱[Lync Server 2013 中的 Survivable 分支裝置或伺服器上的家用使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="3f1d9-151">將使用者從中央網站的 Lync Server 前端池移至 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

