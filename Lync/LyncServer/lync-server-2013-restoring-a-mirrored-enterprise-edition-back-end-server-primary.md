---
title: 還原鏡像的 Enterprise Edition 後端伺服器-主要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e28b3657e5e64b1372b924d04b9d42a58460658
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511570"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="40533-102">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要</span><span class="sxs-lookup"><span data-stu-id="40533-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40533-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="40533-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="40533-104">如果您在鏡像設定中有 Enterprise Edition 後端伺服器，且只有主資料庫失敗，請遵循本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="40533-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="40533-105">如果主資料庫和鏡像都失敗，請參閱 [在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="40533-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="40533-106">若只有鏡像失敗，請參閱 [在 Lync server 2013-鏡像中還原鏡像的 Enterprise Edition 後端伺服器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。</span><span class="sxs-lookup"><span data-stu-id="40533-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="40533-107">若主控中央管理存放區的資料庫失敗，請參閱 [在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="40533-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="40533-108">如果不是後端伺服器的 Enterprise Edition 成員伺服器失敗，請參閱 [在 Lync server 2013 中還原 Enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="40533-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="40533-109">建議您先取得系統的影像複本，再開始還原。</span><span class="sxs-lookup"><span data-stu-id="40533-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="40533-110">您可以使用這個影像做為復原點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="40533-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="40533-111">在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="40533-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="40533-112">在本主題中，範例主要資料庫會具有 BE1.contoso.com FQDN) 的完整功能變數名稱 (，而且鏡像資料庫的 FQDN 為 BE2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="40533-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="40533-113">若要還原 Enterprise Edition 後端伺服器主資料庫</span><span class="sxs-lookup"><span data-stu-id="40533-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="40533-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="40533-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="40533-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="40533-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="40533-116">強制所有已設定的資料庫容錯移轉至鏡像。</span><span class="sxs-lookup"><span data-stu-id="40533-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="40533-117">針對您在此伺服器上設定的每個資料庫類型，輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="40533-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="40533-118">例如：</span><span class="sxs-lookup"><span data-stu-id="40533-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="40533-119">若您已設定後端資料庫以使用具有見證的同步鏡像，將自動進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="40533-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="40533-120">完成容錯移轉之後，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="40533-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="40533-121">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="40533-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="40533-122">停用後臺鏡像在後端伺服器上：按一下 [ **Enterprise Edition 前端** 集區] 底下的 [集區]，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="40533-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="40533-123">在 [ **一般** ] 索引標籤的 [ **關聯**] 下，清除 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="40533-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="40533-124">請視需要執行這項作業以進行封存與監控。</span><span class="sxs-lookup"><span data-stu-id="40533-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="40533-125">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40533-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="40533-126">以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [ **拓撲**]，然後按一下 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="40533-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="40533-127">選取 [仍可正常運作的後端 (BE2.contoso.com) 成為新的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="40533-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="40533-128">若要執行此動作，請在 [ **Enterprise Edition 前端** 集區] 底下的集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="40533-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="40533-129">在 [ **一般** ] 索引標籤的 [ **關聯**] 下，于範例中的範例中，輸入 [ **SQL Server 儲存區** ] 欄位中的功能後端的 FQDN (，BE2.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="40533-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="40533-130">以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [ **拓撲**]，然後按一下 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="40533-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="40533-131">重新開機服務，讓每個伺服器都可以讀取新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="40533-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="40533-132">從 Lync Server 管理命令介面，在屬於此集區的每部前端伺服器上執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="40533-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="40533-133">卸載鏡像。</span><span class="sxs-lookup"><span data-stu-id="40533-133">Uninstall mirroring.</span></span> <span data-ttu-id="40533-134">在 Lync Server 管理命令介面中，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="40533-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="40533-135">例如：</span><span class="sxs-lookup"><span data-stu-id="40533-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="40533-136">請對此伺服器上的所有資料庫類型執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="40533-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="40533-137">在此範例中建立具有相同 FQDN (的全新或全新伺服器，DB1.contoso.com) 為失敗的電腦，安裝作業系統，然後還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="40533-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="40533-138">這台伺服器將會做為新的鏡像運作。</span><span class="sxs-lookup"><span data-stu-id="40533-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="40533-139">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入新伺服器。</span><span class="sxs-lookup"><span data-stu-id="40533-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="40533-140">安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。</span><span class="sxs-lookup"><span data-stu-id="40533-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="40533-141">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="40533-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="40533-142">使用拓撲產生器來安裝鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="40533-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="40533-143">執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="40533-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="40533-144">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="40533-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="40533-145">在後端伺服器上啟用鏡像。</span><span class="sxs-lookup"><span data-stu-id="40533-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="40533-146">若要執行此動作，請在 [ **Enterprise Edition 前端** 集區] 底下的集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="40533-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="40533-147">在 [ **一般** ] 索引標籤的 [ **關聯**] 下，選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="40533-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="40533-148">若有必要，也要進行封存與監控。</span><span class="sxs-lookup"><span data-stu-id="40533-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="40533-149">然後在 [ **鏡像 SQL Server 儲存區** ] 欄位中，輸入新伺服器的 FQDN (n 此範例，BE1.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="40533-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="40533-150">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40533-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="40533-151">以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [ **拓撲**]，然後按一下 [ **安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="40533-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="40533-152">遵循 [ **安裝資料庫** ] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="40533-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="40533-153">在 [ **建立資料庫** ] 頁面上，選取您要重新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="40533-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="40533-154">依照嚮導執行，直到您到達提示 [ **建立鏡像資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="40533-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="40533-155">選取您要安裝的資料庫，然後完成此程式。</span><span class="sxs-lookup"><span data-stu-id="40533-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

