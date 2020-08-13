---
title: Lync Server 2013：還原 Standard Edition Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77c49b7d1b02fc2d1cb41efd3fd68213fa8a0dfb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="4d66c-102">在 Lync Server 2013 中還原 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="4d66c-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d66c-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d66c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d66c-104">若未裝載中央管理存放區的 Standard Edition 伺服器失敗，請遵循本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="4d66c-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="4d66c-105">若中央管理存放區失敗，請參閱[在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="4d66c-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4d66c-106">建議您先取得系統的影像複本，再開始還原。</span><span class="sxs-lookup"><span data-stu-id="4d66c-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="4d66c-107">您可以使用這個影像做為復原點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="4d66c-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="4d66c-108">您可以在安裝作業系統及 SQL Server 之後擷取影像複本，然後再還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="4d66c-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="4d66c-109">還原 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="4d66c-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="4d66c-110">從具有相同完整功能變數名稱 (FQDN) 與失敗電腦相同的全新伺服器開始，安裝作業系統，然後還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="4d66c-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d66c-111">遵循貴組織的伺服器部署程序執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="4d66c-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="4d66c-112">從屬於 RTCUniversalServerAdmins 群組和本機 Administrators 群組成員的使用者帳戶，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d66c-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="4d66c-113">將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放區位置，然後共用資料夾，以還原檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="4d66c-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d66c-114">還原的檔案存放區的路徑和檔案名應該與備份的檔案存放區完全相同，以便使用該檔案的元件可以存取這些檔案。</span><span class="sxs-lookup"><span data-stu-id="4d66c-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="4d66c-115">執行拓撲產生器：</span><span class="sxs-lookup"><span data-stu-id="4d66c-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="4d66c-116">啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="4d66c-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="4d66c-117">按一下 [從現有部署下載拓撲]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d66c-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="4d66c-p103">選取拓撲，然後按一下 [儲存]\*\*\*\*。按一下 [是]\*\*\*\* 確定您的選擇。</span><span class="sxs-lookup"><span data-stu-id="4d66c-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="4d66c-120">流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署 \\ 嚮導 \\ 。</span><span class="sxs-lookup"><span data-stu-id="4d66c-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="4d66c-121">使用 Lync Server 部署嚮導執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="4d66c-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="4d66c-122">執行 [步驟 1: 安裝本機組態存放區]\*\*\*\*，以安裝本機設定檔。</span><span class="sxs-lookup"><span data-stu-id="4d66c-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="4d66c-123">執行**步驟2：安裝或移除 Lync Server 元件**，以安裝 lync server 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="4d66c-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="4d66c-124">執行 [步驟 3: 要求、安裝或指派憑證]\*\*\*\*，以指派憑證。</span><span class="sxs-lookup"><span data-stu-id="4d66c-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="4d66c-125">執行 [步驟 4: 啟動服務]\*\*\*\*，以啟動伺服器上的服務。</span><span class="sxs-lookup"><span data-stu-id="4d66c-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="4d66c-126">如需執行 [部署精靈] 的詳細資料，請參閱您要還原之伺服器角色的＜部署＞文件。</span><span class="sxs-lookup"><span data-stu-id="4d66c-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="4d66c-127">執行下列動作還原使用者資料：</span><span class="sxs-lookup"><span data-stu-id="4d66c-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="4d66c-128">將 ExportedUserData.zip 從 $Backup 複製 \\ 到本機目錄。</span><span class="sxs-lookup"><span data-stu-id="4d66c-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="4d66c-129">在您還原使用者資料之前，您必須停止 Lync 服務。</span><span class="sxs-lookup"><span data-stu-id="4d66c-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="4d66c-130">若要這麼做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="4d66c-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="4d66c-131">若要還原使用者資料，請在命令列上輸入：</span><span class="sxs-lookup"><span data-stu-id="4d66c-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="4d66c-132">例如：</span><span class="sxs-lookup"><span data-stu-id="4d66c-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="4d66c-133">輸入下列命令以重新開機 Lync 服務：</span><span class="sxs-lookup"><span data-stu-id="4d66c-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="4d66c-134">如果您已在此 Standard Edition server 上部署回應群組，請還原回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="4d66c-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="4d66c-135">如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="4d66c-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="4d66c-136">如果您已在此 Standard Edition server 上部署持續性聊天，請還原 Persistent Chat database (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="4d66c-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="4d66c-137">如果您使用 SQL Server 備份來備份 Persistent 聊天資料庫，請使用 SQL Server 還原程式還原。</span><span class="sxs-lookup"><span data-stu-id="4d66c-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="4d66c-138">如果您使用 Export-CsPersistentChatData Cmdlet 來備份它，請使用 Import-CsPersistentChatData 還原該指令。</span><span class="sxs-lookup"><span data-stu-id="4d66c-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

