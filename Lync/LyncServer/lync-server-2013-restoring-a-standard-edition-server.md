---
title: Lync Server 2013：還原標準版伺服器
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
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="87de8-102">在 Lync Server 2013 中還原標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="87de8-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87de8-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="87de8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="87de8-104">如果沒有託管中央管理儲存區的標準版伺服器失敗，請遵循本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="87de8-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="87de8-105">如果中央管理儲存區失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="87de8-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="87de8-106">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="87de8-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="87de8-107">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="87de8-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="87de8-108">您可能會想要在安裝作業系統與 SQL Server 之後進行影像複製，然後還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="87de8-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="87de8-109">若要還原標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="87de8-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="87de8-110">從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="87de8-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87de8-111">遵循貴組織的伺服器部署程式來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="87de8-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="87de8-112">從屬於 [RTCUniversalServerAdmins] 群組和 [本機管理員] 群組成員的使用者帳戶登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="87de8-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="87de8-113">將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放位置並共用資料夾，以還原檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="87de8-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="87de8-114">已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，以便使用檔案的元件可以存取它們。</span><span class="sxs-lookup"><span data-stu-id="87de8-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="87de8-115">執行拓撲建造器：</span><span class="sxs-lookup"><span data-stu-id="87de8-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="87de8-116">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="87de8-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="87de8-117">按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87de8-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="87de8-118">選取拓撲，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="87de8-118">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="87de8-119">按一下 **[是]** 以確認您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="87de8-119">Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="87de8-120">流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="87de8-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="87de8-121">使用 Lync Server 部署嚮導來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="87de8-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="87de8-122">執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。</span><span class="sxs-lookup"><span data-stu-id="87de8-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="87de8-123">執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="87de8-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="87de8-124">執行**步驟3：要求、安裝或指派憑證**來指派憑證。</span><span class="sxs-lookup"><span data-stu-id="87de8-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="87de8-125">執行**步驟4：啟動服務**以在伺服器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="87de8-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="87de8-126">如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。</span><span class="sxs-lookup"><span data-stu-id="87de8-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="87de8-127">若要還原使用者資料，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="87de8-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="87de8-128">從 $Backup\\將 ExportedUserData 複製到本機目錄。</span><span class="sxs-lookup"><span data-stu-id="87de8-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="87de8-129">您必須先停止 Lync services，才能還原使用者資料。</span><span class="sxs-lookup"><span data-stu-id="87de8-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="87de8-130">若要這麼做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="87de8-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="87de8-131">若要還原使用者資料，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="87de8-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="87de8-132">例如：</span><span class="sxs-lookup"><span data-stu-id="87de8-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="87de8-133">輸入以下內容以重新開機 Lync services：</span><span class="sxs-lookup"><span data-stu-id="87de8-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="87de8-134">如果您已在此標準版伺服器上部署回應群組，請還原回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="87de8-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="87de8-135">如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="87de8-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="87de8-136">如果您已在此標準版伺服器上部署持久的聊天，請還原持久聊天資料庫（mgc）。</span><span class="sxs-lookup"><span data-stu-id="87de8-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="87de8-137">如果您使用 SQL Server 備份來備份永久性聊天資料庫，請使用 SQL Server 還原程式來還原它。</span><span class="sxs-lookup"><span data-stu-id="87de8-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="87de8-138">如果您使用 Export CsPersistentChatData Cmdlet 來備份，請使用匯入-CsPersistentChatData 將其還原。</span><span class="sxs-lookup"><span data-stu-id="87de8-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

