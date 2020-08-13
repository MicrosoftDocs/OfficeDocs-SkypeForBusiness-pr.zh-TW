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
ms.openlocfilehash: 46212fc9910885ed1d6d833ef0f4b30c3a49b7c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="523a3-102">在 Lync Server 2013 中發佈拓撲</span><span class="sxs-lookup"><span data-stu-id="523a3-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="523a3-103">_**主題上次修改日期：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="523a3-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="523a3-104">若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="523a3-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="523a3-105">您也可以委派適當的系統管理員權利和使用權限。</span><span class="sxs-lookup"><span data-stu-id="523a3-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="523a3-106">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="523a3-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="523a3-107">若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="523a3-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="523a3-108">在拓撲產生器中定義拓撲之後，您必須將拓撲發行至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="523a3-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="523a3-109">中央管理存放區為定義、設定、維護、管理、描述及操作 Lync Server 2013 部署所需的資料提供了可靠且 schematized 的儲存。</span><span class="sxs-lookup"><span data-stu-id="523a3-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="523a3-110">它也會驗證資料，以協助確保設定的一致性。</span><span class="sxs-lookup"><span data-stu-id="523a3-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="523a3-111">對此設定資料所做的所有變更都會發生在中央管理存放區，消除「不同步」的問題。</span><span class="sxs-lookup"><span data-stu-id="523a3-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="523a3-112">資料的唯讀複本會複製到拓撲中的所有伺服器，包括 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="523a3-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="523a3-113">SQL Server 至少需要 20 GB 的可用磁碟空間，才可成功發行初始拓撲，並建立中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="523a3-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="523a3-114">僅限 Enterprise Edition：若要發行拓撲，SQL Server 後端伺服器必須上線，並納入防火牆例外中以供人存取。</span><span class="sxs-lookup"><span data-stu-id="523a3-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="523a3-115">如需指定防火牆例外狀況的詳細資訊，請參閱 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">瞭解 SQL Server 的防火牆需求（含 Lync Server 2013</A>）。</span><span class="sxs-lookup"><span data-stu-id="523a3-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="523a3-116">如需設定 SQL Server 的詳細資訊，請參閱 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE SQL Server For Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="523a3-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="523a3-117">若要發行拓撲</span><span class="sxs-lookup"><span data-stu-id="523a3-117">To publish a topology</span></span>

1.  <span data-ttu-id="523a3-118">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="523a3-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="523a3-p104">選取本機檔案以開啟其中的拓撲。如果您在操作當初用於定義拓撲的電腦，檔案就位於您在稍早步驟儲存該檔案的位置。此位置通常是當初設定拓撲的使用者的 Documents 資料夾。</span><span class="sxs-lookup"><span data-stu-id="523a3-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="523a3-122">在 [ **Lync Server 2013** ] 節點上按一下滑鼠右鍵，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="523a3-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="523a3-123">在 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="523a3-124">在 **[建立資料庫]** 頁面上，選取您要發行的資料庫。</span><span class="sxs-lookup"><span data-stu-id="523a3-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="523a3-125">如果您不具有建立某些資料庫的適當權限，可以清除那些資料庫旁邊的核取方塊，讓具有適當權限的其他人稍後再來建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="523a3-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="523a3-126">如需詳細資訊，請參閱 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。</span><span class="sxs-lookup"><span data-stu-id="523a3-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="523a3-127">(選用) 按一下 **[進階]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="523a3-128">[Advanced SQL Server 資料檔案] 位置選項可讓您選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="523a3-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="523a3-129">**自動判斷資料庫檔案位置** – 此選項會根據 SQL Server 型伺服器上的磁碟組態，判斷最佳的運作效能，將記錄和資料檔案分散至最佳位置。</span><span class="sxs-lookup"><span data-stu-id="523a3-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="523a3-p107">**使用 SQL Server 執行個體預設值** – 此選項會使用執行個體設定值，將記錄和資料檔案存放在 SQL Server 型伺服器上。此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。</span><span class="sxs-lookup"><span data-stu-id="523a3-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="523a3-133">依序按一下 **[確定]** 和 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="523a3-134">在 [ **選取中央管理伺服器** ] 頁面上，選取前端集區。</span><span class="sxs-lookup"><span data-stu-id="523a3-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="523a3-135">(選用) 按一下 **[進階]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="523a3-136">[高級 SQL Server 資料檔案] 位置選項可讓您選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="523a3-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="523a3-137">**自動判斷資料庫檔案位置** – 此選項會根據 SQL Server 型伺服器上的磁碟組態，判斷最佳的運作效能，將記錄和資料檔案分散至最佳位置。</span><span class="sxs-lookup"><span data-stu-id="523a3-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="523a3-p109">**使用 SQL Server 執行個體預設值** – 此選項會使用執行個體設定值，將記錄和資料檔案存放在 SQL Server 型伺服器上。此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。</span><span class="sxs-lookup"><span data-stu-id="523a3-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="523a3-141">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-141">Click **OK**.</span></span>

9.  <span data-ttu-id="523a3-142">按 **[下一步]** 完成發行程序。</span><span class="sxs-lookup"><span data-stu-id="523a3-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="523a3-143">當發行程序完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="523a3-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="523a3-144">成功發佈拓撲之後，您可以開始在拓撲中執行 Lync Server 2013 的各部伺服器上安裝中央管理存放區的本機複本。</span><span class="sxs-lookup"><span data-stu-id="523a3-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="523a3-145">建議您從第一部前端集區開始。</span><span class="sxs-lookup"><span data-stu-id="523a3-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="523a3-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="523a3-146">See Also</span></span>


[<span data-ttu-id="523a3-147">為 Lync Server 2013 設定前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="523a3-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

