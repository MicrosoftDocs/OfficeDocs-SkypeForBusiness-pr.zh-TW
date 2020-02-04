---
title: 還原鏡像企業版後端伺服器-主要
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
ms.openlocfilehash: 07546b59839631cbd558e91e3e617fefd1c6e362
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="1ef76-102">在 Lync Server 2013 中還原鏡像企業版後端伺服器-主要</span><span class="sxs-lookup"><span data-stu-id="1ef76-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef76-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="1ef76-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="1ef76-104">如果您在鏡像設定中有企業版後端伺服器，而且只有主資料庫發生故障，請依照本節中的程式執行。</span><span class="sxs-lookup"><span data-stu-id="1ef76-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="1ef76-105">如果主資料庫和鏡像都未通過，請參閱[在 Lync Server 2013 中還原企業版後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef76-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="1ef76-106">如果只有鏡像失敗，請參閱[在 Lync Server 2013-mirror 中還原鏡像企業版後端伺服器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef76-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="1ef76-107">如果裝載中央管理儲存區的資料庫失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef76-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="1ef76-108">如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef76-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="1ef76-109">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="1ef76-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="1ef76-110">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="1ef76-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="1ef76-111">您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="1ef76-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="1ef76-112">在本主題中，範例主資料庫將會有 BE1.contoso.com 的完整功能變數名稱（FQDN），而鏡像資料庫將擁有 FQDN （BE2.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="1ef76-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="1ef76-113">若要還原企業版後端伺服器的主資料庫</span><span class="sxs-lookup"><span data-stu-id="1ef76-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="1ef76-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ef76-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="1ef76-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1ef76-116">強制所有已設定的資料庫都能容錯移轉到鏡像。</span><span class="sxs-lookup"><span data-stu-id="1ef76-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="1ef76-117">針對您在此伺服器上設定的每個資料庫類型，輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1ef76-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="1ef76-118">例如：</span><span class="sxs-lookup"><span data-stu-id="1ef76-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="1ef76-119">如果您已將後端資料庫設定為使用與見證的同步處理鏡像，則會自動進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1ef76-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="1ef76-120">完成容錯移轉之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1ef76-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="1ef76-121">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="1ef76-122">停用後端伺服器上的鏡像：以滑鼠右鍵按一下 [**企業版頂層端池**] 下的 [池]，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="1ef76-123">在 [**一般**] 索引標籤的 [**關聯**] 底下，清除 [**啟用 SQL Server store 鏡像**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ef76-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="1ef76-124">如有需要，請執行此動作以進行封存和監視。</span><span class="sxs-lookup"><span data-stu-id="1ef76-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="1ef76-125">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ef76-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="1ef76-126">以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="1ef76-127">選取 [仍正常運作的後端（BE2.contoso.com）] 做為新的 SQL store。</span><span class="sxs-lookup"><span data-stu-id="1ef76-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="1ef76-128">若要這樣做，請以滑鼠右鍵按一下 [**企業版頂層端池**] 底下的 [池]，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="1ef76-129">在 [**一般**] 索引標籤的 [**關聯**性] 底下，于 [ **SQL Server store** ] 欄位中輸入 [作用中後端] 的 FQDN （在我們的範例中為 BE2.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="1ef76-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="1ef76-130">以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="1ef76-131">重新開機服務，讓每個伺服器都能讀取新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="1ef76-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="1ef76-132">從 Lync Server 管理命令介面，在屬於此 pool 的每個前端伺服器上執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1ef76-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="1ef76-133">卸載鏡像。</span><span class="sxs-lookup"><span data-stu-id="1ef76-133">Uninstall mirroring.</span></span> <span data-ttu-id="1ef76-134">從 Lync Server 管理命令介面，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1ef76-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="1ef76-135">例如：</span><span class="sxs-lookup"><span data-stu-id="1ef76-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="1ef76-136">針對此伺服器上的所有資料庫類型執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1ef76-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="1ef76-137">在失敗的電腦上建立具有相同 FQDN （在這個範例中為 DB1.contoso.com）的乾淨或新伺服器、安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="1ef76-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="1ef76-138">這個伺服器將做為新的鏡像。</span><span class="sxs-lookup"><span data-stu-id="1ef76-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="1ef76-139">從屬於 [RTCUniversalServerAdmins] 群組成員的使用者帳戶登入新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ef76-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="1ef76-140">安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。</span><span class="sxs-lookup"><span data-stu-id="1ef76-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="1ef76-141">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ef76-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="1ef76-142">使用拓撲產生器來安裝鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="1ef76-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="1ef76-143">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1ef76-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="1ef76-144">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="1ef76-145">在後端伺服器上啟用鏡像。</span><span class="sxs-lookup"><span data-stu-id="1ef76-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="1ef76-146">若要這樣做，請以滑鼠右鍵按一下 [**企業版頂層端池**] 底下的 [池]，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="1ef76-147">在 [**一般**] 索引標籤的 [**關聯**] 底下，選取 [**啟用 SQL Server store 鏡像**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ef76-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="1ef76-148">如有需要，也可以進行封存和監視。</span><span class="sxs-lookup"><span data-stu-id="1ef76-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="1ef76-149">接著，在 [**鏡像 SQL Server store** ] 欄位中，輸入新伺服器的 FQDN （n 這個範例，BE1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="1ef76-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="1ef76-150">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ef76-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="1ef76-151">以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲圖**]，然後按一下 [**安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="1ef76-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="1ef76-152">遵循 [**安裝資料庫**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="1ef76-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="1ef76-153">在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="1ef76-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="1ef76-154">依照嚮導進行，直到出現提示，然後**建立鏡像資料庫**。</span><span class="sxs-lookup"><span data-stu-id="1ef76-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="1ef76-155">選取您要安裝的資料庫，然後完成這個程式。</span><span class="sxs-lookup"><span data-stu-id="1ef76-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

