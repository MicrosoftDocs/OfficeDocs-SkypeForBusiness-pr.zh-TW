---
title: Lync Server 2013：還原企業版後端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="5a359-102">在 Lync Server 2013 中還原企業版後端伺服器</span><span class="sxs-lookup"><span data-stu-id="5a359-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a359-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="5a359-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="5a359-104">在下列兩種情況下，請使用本主題中所述的程式：</span><span class="sxs-lookup"><span data-stu-id="5a359-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="5a359-105">鏡像企業版 Server 後端伺服器的主要和鏡像資料庫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="5a359-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="5a359-106">無法鏡像的企業版後端伺服器失敗。</span><span class="sxs-lookup"><span data-stu-id="5a359-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="5a359-107">如果您擁有鏡像的企業版版本後端，且只有鏡像或主資料庫發生故障，請參閱[在 Lync server 2013 中還原鏡像的企業版後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)是還原主要資料庫，以及[在 Lync Server 2013 中還原鏡像企業版後端伺服器-鏡像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)以還原鏡像。</span><span class="sxs-lookup"><span data-stu-id="5a359-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="5a359-108">如果中央管理儲存區失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="5a359-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="5a359-109">如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5a359-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5a359-110">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="5a359-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="5a359-111">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="5a359-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="5a359-112">您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="5a359-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="5a359-113">若要還原企業版後端伺服器</span><span class="sxs-lookup"><span data-stu-id="5a359-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="5a359-114">從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="5a359-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a359-115">遵循貴組織的伺服器部署程式來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="5a359-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="5a359-116">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a359-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="5a359-117">安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。</span><span class="sxs-lookup"><span data-stu-id="5a359-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a359-118">根據您的部署，後端伺服器可能會包含多個 collocated 或個別的資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a359-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="5a359-119">遵循相同的程式，安裝您最初用來部署伺服器的 SQL Server，包括 SQL Server 許可權和登錄名。</span><span class="sxs-lookup"><span data-stu-id="5a359-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="5a359-120">安裝 SQL Server 之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5a359-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="5a359-121">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="5a359-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="5a359-122">按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5a359-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="5a359-123">選取拓撲，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="5a359-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="5a359-124">按一下 **[是]** 以確認您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="5a359-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="5a359-125">以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="5a359-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="5a359-126">遵循 [**發佈拓撲**嚮導]。</span><span class="sxs-lookup"><span data-stu-id="5a359-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="5a359-127">在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a359-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5a359-128">[<STRONG>建立資料庫</STRONG>] 頁面上只會顯示獨立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a359-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="5a359-129">如果您要還原已鏡像的後端，請繼續追蹤其餘的嚮導，直到出現提示**建立鏡像資料庫**為止。</span><span class="sxs-lookup"><span data-stu-id="5a359-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="5a359-130">選取您要安裝的資料庫，並完成程式。</span><span class="sxs-lookup"><span data-stu-id="5a359-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="5a359-131">依照嚮導的其餘部分進行，然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="5a359-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5a359-132">您可以使用<STRONG>CsDatabase</STRONG> Cmdlet 來建立每個資料庫，以及<STRONG>安裝 CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不需要執行拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="5a359-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="5a359-133">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="5a359-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="5a359-134">若要還原使用者資料，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5a359-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="5a359-135">從 $Backup\\將 ExportedUserData 複製到本機目錄。</span><span class="sxs-lookup"><span data-stu-id="5a359-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="5a359-136">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5a359-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="5a359-137">您必須先停止 Lync services，才能還原使用者資料。</span><span class="sxs-lookup"><span data-stu-id="5a359-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="5a359-138">若要這麼做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="5a359-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="5a359-139">若要還原使用者資料，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="5a359-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="5a359-140">例如：</span><span class="sxs-lookup"><span data-stu-id="5a359-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="5a359-141">輸入以下內容以重新開機 Lync Services：</span><span class="sxs-lookup"><span data-stu-id="5a359-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="5a359-142">如果您已在此池中部署回應群組，請還原回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="5a359-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="5a359-143">如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5a359-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="5a359-144">如果您要還原包含封存或監視資料庫的後端伺服器，請使用 SQL Server 工具（例如 SQL Server Management Studio）還原存檔或監視資料。</span><span class="sxs-lookup"><span data-stu-id="5a359-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="5a359-145">如需詳細資訊，請參閱[在 Lync Server 2013 中還原監視或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。</span><span class="sxs-lookup"><span data-stu-id="5a359-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

