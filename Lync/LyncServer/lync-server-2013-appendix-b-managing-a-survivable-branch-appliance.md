---
title: Lync Server 2013：附錄 B：管理 Survivable 分支裝置
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
ms.openlocfilehash: 27975119b9e54b96ba7472ce1e60d64a51671c5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="fdff6-102">附錄 B：在 Lync Server 2013 中管理 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="fdff6-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdff6-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fdff6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fdff6-104">本主題說明管理 Survivable 分支裝置的程式。</span><span class="sxs-lookup"><span data-stu-id="fdff6-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-105">具體而言，如何取代和重新命名 Survivable 分支裝置，以及如何變更與 Survivable Branch 裝置相關聯的 Lync Server 2013 前端集區。</span><span class="sxs-lookup"><span data-stu-id="fdff6-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="fdff6-106">取代 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="fdff6-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="fdff6-107">停止 Survivable 分支裝置上所有的 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="fdff6-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-108"> (請參閱 Survivable Branch 裝置廠商檔。 ) </span><span class="sxs-lookup"><span data-stu-id="fdff6-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="fdff6-109"> (建議) 從網域移除 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="fdff6-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="fdff6-110">請遵循下列步驟，刪除 Active Directory 網域服務中的 Survivable Branch 裝置電腦物件：</span><span class="sxs-lookup"><span data-stu-id="fdff6-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="fdff6-111">以 Enterprise Admins 群組成員的身分，登入成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="fdff6-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="fdff6-112">依序按一下 **[開始]**、**[系統管理工具]** 和 **[Active Directory 使用者和電腦]**。</span><span class="sxs-lookup"><span data-stu-id="fdff6-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="fdff6-113">以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="fdff6-114">再次新增 Survivable Branch 裝置電腦物件。</span><span class="sxs-lookup"><span data-stu-id="fdff6-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="fdff6-115"> (請參閱[將 Survivable 分支裝置新增至 Active Directory 中的 Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="fdff6-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="fdff6-116">等候 Active Directory 複寫進行。</span><span class="sxs-lookup"><span data-stu-id="fdff6-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="fdff6-117">開啟 Lync Server 管理命令介面，然後輸入**Enable-CSTopology**。</span><span class="sxs-lookup"><span data-stu-id="fdff6-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="fdff6-118">將新的 Survivable 分支裝置連接至網路，然後依照以[Lync server 2013-中央網站工作部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)的步驟進行，並[部署 Survivable branch 裝置或具有 lync Server 2013 的伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作。</span><span class="sxs-lookup"><span data-stu-id="fdff6-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="fdff6-119">若要重新命名 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="fdff6-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="fdff6-120">將使用者移至中央網站。</span><span class="sxs-lookup"><span data-stu-id="fdff6-120">Move users to the central site.</span></span> <span data-ttu-id="fdff6-121">如需詳細資訊，請參閱[將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="fdff6-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="fdff6-122">停止 Survivable 分支裝置上所有的 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="fdff6-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-123"> (請參閱 Survivable Branch 裝置廠商檔。 ) </span><span class="sxs-lookup"><span data-stu-id="fdff6-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="fdff6-124">遵循下列步驟，將 Survivable 分支裝置從拓撲中移除：</span><span class="sxs-lookup"><span data-stu-id="fdff6-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="fdff6-125">依序按一下 [**開始**]、[**所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="fdff6-126">在主控台樹中，展開 [**分支網站**]，然後按一下 [Survivable 分支裝置]，然後按一下動作窗格上的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="fdff6-127">從網域中移除 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="fdff6-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="fdff6-128">請遵循下列步驟，刪除 Active Directory 中的 Survivable Branch 裝置電腦物件：</span><span class="sxs-lookup"><span data-stu-id="fdff6-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="fdff6-129">以 Enterprise Admins 群組成員的身分登入網域控制站。</span><span class="sxs-lookup"><span data-stu-id="fdff6-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="fdff6-130">依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 及 [Active Directory 使用者及電腦]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdff6-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="fdff6-131">以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="fdff6-132">將 Survivable 分支裝置還原為出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="fdff6-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="fdff6-133"> (請參閱 Survivable Branch 裝置廠商檔。 ) </span><span class="sxs-lookup"><span data-stu-id="fdff6-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="fdff6-134">請遵循[使用 Lync server 2013-中央網站工作部署 Survivable Branch 裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)的步驟，並[部署具有 lync Server 2013 的 Survivable 分支裝置或伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作。</span><span class="sxs-lookup"><span data-stu-id="fdff6-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="fdff6-135">將使用者移至重新命名的 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="fdff6-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-136">如需詳細資訊，請參閱[將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="fdff6-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="fdff6-137">變更 Survivable 分支裝置相關聯的 Lync Server 前端集區</span><span class="sxs-lookup"><span data-stu-id="fdff6-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="fdff6-138">將使用者從 Survivable Branch 裝置移至中央網站的 Lync Server 前端集區。</span><span class="sxs-lookup"><span data-stu-id="fdff6-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="fdff6-139">如需詳細資訊，請參閱[將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="fdff6-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="fdff6-140">停止 Survivable 分支裝置上所有的 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="fdff6-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-141"> (請參閱 Survivable Branch 裝置廠商檔) 。</span><span class="sxs-lookup"><span data-stu-id="fdff6-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="fdff6-142">遵循下列步驟，更新與 Survivable 分支裝置相關聯的 Lync Server 前端集區：</span><span class="sxs-lookup"><span data-stu-id="fdff6-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="fdff6-143">依序按一下 [**開始**]、[**所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="fdff6-144">展開 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="fdff6-145">以滑鼠右鍵按一下要修改的 Survivable 分支裝置物件，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="fdff6-146">在 [復原能力] 底下，選取要與 Survivable 分支裝置相關聯的新前端集區，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fdff6-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="fdff6-147">在主控台樹中，以滑鼠右鍵按一下新的 Survivable 分支裝置，按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="fdff6-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="fdff6-148">重新開機 Survivable 分支裝置上的所有 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="fdff6-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="fdff6-149">測試 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="fdff6-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="fdff6-150">如需詳細資訊，請參閱在[Lync Server 2013 中的 Survivable 分支裝置或伺服器上的家庭使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fdff6-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="fdff6-151">將使用者從中央網站的 Lync Server 前端集區移至 Survivable Branch 裝置。</span><span class="sxs-lookup"><span data-stu-id="fdff6-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

