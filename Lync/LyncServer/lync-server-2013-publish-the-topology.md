---
title: Lync Server 2013：發行拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="9914a-102">在 Lync Server 2013 中發行拓撲</span><span class="sxs-lookup"><span data-stu-id="9914a-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9914a-103">_**主題上次修改日期：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="9914a-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="9914a-104">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="9914a-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="9914a-105">您也可以委派適當的管理員權力和許可權。</span><span class="sxs-lookup"><span data-stu-id="9914a-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="9914a-106">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9914a-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="9914a-107">針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="9914a-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="9914a-108">在拓撲建立器中定義拓朴之後，您必須將拓撲發佈到中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="9914a-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="9914a-109">[中央管理] 儲存區提供可靠、schematized 的資料儲存，以定義、設定、維護、管理、描述及操作 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="9914a-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="9914a-110">它也會驗證資料，以協助確保配置一致性。</span><span class="sxs-lookup"><span data-stu-id="9914a-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="9914a-111">此設定資料的所有變更都會出現在中央管理商店，消除「不同步」問題。</span><span class="sxs-lookup"><span data-stu-id="9914a-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="9914a-112">唯讀複本會將資料複製到拓撲中的所有伺服器，包括邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9914a-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9914a-113">SQL Server 需要至少 20 GB 的可用磁碟空間，才能成功發佈初始拓撲，並建立中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="9914a-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9914a-114">僅限 Enterprise Edition：若要發佈拓朴，SQL Server 的後端伺服器必須在線上，且在適當的地方出現防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="9914a-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="9914a-115">如需指定防火牆例外狀況的詳細資料，請參閱<A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">瞭解使用 Lync Server 2013 的 SQL Server 防火牆需求</A>。</span><span class="sxs-lookup"><span data-stu-id="9914a-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="9914a-116">如需有關設定 SQL Server 的詳細資訊，請參閱<A href="lync-server-2013-configure-sql-server-for-lync-server.md">設定 Lync server 2013 的 SQL Server</A>。</span><span class="sxs-lookup"><span data-stu-id="9914a-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="9914a-117">發佈拓撲</span><span class="sxs-lookup"><span data-stu-id="9914a-117">To publish a topology</span></span>

1.  <span data-ttu-id="9914a-118">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="9914a-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9914a-119">選取以從本機檔案開啟拓撲。</span><span class="sxs-lookup"><span data-stu-id="9914a-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="9914a-120">如果您在已定義拓撲的電腦上，這會位於您在先前步驟中儲存它的位置。</span><span class="sxs-lookup"><span data-stu-id="9914a-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="9914a-121">通常，這會是設定拓朴之使用者的 [檔] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="9914a-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="9914a-122">以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="9914a-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="9914a-123">在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9914a-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="9914a-124">在 [**建立資料庫**] 頁面上，選取您要發佈的資料庫。</span><span class="sxs-lookup"><span data-stu-id="9914a-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9914a-125">如果您沒有建立資料庫的適當許可權，您可以清除這些資料庫旁邊的核取方塊，而具有適當許可權的人員就可以在稍後建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="9914a-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="9914a-126">如需詳細資訊，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。</span><span class="sxs-lookup"><span data-stu-id="9914a-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="9914a-127">您也可以按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="9914a-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="9914a-128">[高級 SQL Server 資料檔位置] 選項可讓您選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="9914a-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="9914a-129">**自動判斷資料庫檔案位置**：此選項會將記錄和資料檔案散佈到最佳位置，以根據您的 SQL server 伺服器上的磁片設定來判斷最佳的操作效能。</span><span class="sxs-lookup"><span data-stu-id="9914a-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="9914a-130">**使用 SQL Server 實例預設值**–此選項使用實例設定，將記錄和資料檔案放到 SQL server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9914a-130">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="9914a-131">這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="9914a-131">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="9914a-132">SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。</span><span class="sxs-lookup"><span data-stu-id="9914a-132">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="9914a-133">按一下 **[確定]**，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="9914a-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="9914a-134">在 [**選取中央管理伺服器**] 頁面上，選取 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="9914a-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="9914a-135">您也可以按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="9914a-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="9914a-136">[高級 SQL Server 資料檔位置] 選項可讓您選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="9914a-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="9914a-137">**自動判斷資料庫檔案位置**：此選項會將記錄和資料檔案散佈到最佳位置，以根據您的 SQL server 伺服器上的磁片設定來判斷最佳的操作效能。</span><span class="sxs-lookup"><span data-stu-id="9914a-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="9914a-138">**使用 SQL Server 實例預設值**–此選項使用實例設定，將記錄和資料檔案放到 SQL server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9914a-138">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="9914a-139">這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="9914a-139">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="9914a-140">SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。</span><span class="sxs-lookup"><span data-stu-id="9914a-140">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="9914a-141">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9914a-141">Click **OK**.</span></span>

9.  <span data-ttu-id="9914a-142">按一下 **[下一步]** 以完成發佈程式。</span><span class="sxs-lookup"><span data-stu-id="9914a-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="9914a-143">發佈程式完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9914a-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="9914a-144">成功發佈拓撲之後，您就可以開始在拓撲中執行 Lync Server 2013 的每個伺服器上安裝中央管理儲存的本機複本。</span><span class="sxs-lookup"><span data-stu-id="9914a-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="9914a-145">我們建議您從第一個前端池開始。</span><span class="sxs-lookup"><span data-stu-id="9914a-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9914a-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="9914a-146">See Also</span></span>


[<span data-ttu-id="9914a-147">針對 Lync Server 2013 設定前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="9914a-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

