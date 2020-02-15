---
title: Lync Server 2013： 將 Persistent Chat Server 新增至拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e34643c2a9f838d9a8c66cdfc04698d813db01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="b9cc6-102">將常設聊天室伺服器新增至 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="b9cc6-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9cc6-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="b9cc6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b9cc6-104">您必須納入 Lync Server 2013，Persistent Chat Server 支援，您才能設定部署以支援 Persistent Chat Server 的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="b9cc6-105">本主題中的資訊說明如何使用拓撲產生器將 Persistent Chat Server 支援新增至您現有的拓樸。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="b9cc6-106">若要將 Persistent Chat Server 新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="b9cc6-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="b9cc6-107">執行下列步驟安裝而不需要災害復原設定單一 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="b9cc6-108">設定高可用性和災害復原的延伸 Persistent Chat Server 集區，請參閱部署文件中的[Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b9cc6-109">若要部署多個 Persistent Chat Server 集區，請針對每個集區重複相同的程序。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="b9cc6-110">在電腦上，執行 Lync Server 2013，或在 Lync Server 系統管理工具安裝上使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶） 登入。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9cc6-111">您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要安裝 Lync Server 2013 伺服器，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且在您要使用 Persistent Chat Server 檔案存放區 （亦即，讓拓撲產生器可以設定必要的 Dacl） 的檔案存放區上具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶或具有相等的權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="b9cc6-112">啟動拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="b9cc6-113">在主控台樹狀目錄中，瀏覽至 [**常設聊天室集區**] 節點，並展開它選取 Persistent Chat Server 集區]，或在節點上按一下滑鼠右鍵，並選取 [**新增常設聊天室集區**。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="b9cc6-114">您必須定義集區的完整網域名稱 (FQDN)，並指出集區將是單一伺服器集區或多重伺服器集區部署。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="b9cc6-115">您可以選擇 [多重電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="b9cc6-116">如果您計劃要 Persistent Chat Server 集區中有多個 Persistent Chat Server 前端伺服器，請選擇 [前者]。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="b9cc6-117">立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="b9cc6-118">如果您選擇多部電腦集區]，輸入個別 Persistent Chat Server 前端伺服器組成之集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9cc6-119">如果 Persistent Chat Server role 安裝在 Lync Server 2013&nbsp;Standard Edition server FQDN 必須符合的 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="b9cc6-120">定義常設聊天室伺服器集區的簡易**顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="b9cc6-121">自訂用戶端，可以使用的顯示名稱，特別是當有多個 Persistent Chat Server 集區，來區分聊天室。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="b9cc6-122">定義常設聊天室伺服器用來與 Lync Server 前端伺服器進行通訊的連接埠。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="b9cc6-123">預設的連接埠為 5041。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="b9cc6-124">如果您的組織需要規範支援，請選取 [用規範記錄]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="b9cc6-125">如果選擇，Persistent Chat Server 前端伺服器相同的電腦上安裝的常設聊天室伺服器規範服務。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="b9cc6-126">系統會提示您稍後選取 SQL Server 後端伺服器的常設聊天室伺服器規範。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="b9cc6-127">指派 Persistent Chat Server 集區的站台相似性。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="b9cc6-128">選取 [**使用此集區作為預設網站\<SiteName\> \*\* ] 核取方塊，或若要指定此 Persistent Chat Server 集區作為預設的集區的目前網站或所有網站的 [**使用此集區作為所有網站的預設值\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="b9cc6-129">Lync 2013 用戶端是用來建立及管理聊天室，與使用者網站相關聯的預設集區會使用會議室架設與管理經驗，讓它可將聊天室建立和管理作業路由傳送至該集區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="b9cc6-130">這僅適用於當您有多個 Persistent Chat Server 集區部署，而且想要使用 Persistent Chat Server 的會議室架設與管理功能。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9cc6-131">您可以自訂使用常設聊天室伺服器軟體開發套件 (SDK) 的聊天室建立和管理功能。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="b9cc6-132">如需如何設定 SQL Server 備份資料庫進行災害復原的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原</A>。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="b9cc6-133">定義**SQL 存放區的常設聊天室伺服器 Back End （其中儲存聊天室內容）** 執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b9cc6-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="b9cc6-134">若要使用現有的 SQL Server 資料庫，在下拉式清單中，按一下您想要使用 SQL Server 資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="b9cc6-135">若要指定新的 SQL Server 資料庫，按一下 [**新增**]，並在 [**定義新 SQL 存放區**，執行下列：</span><span class="sxs-lookup"><span data-stu-id="b9cc6-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="b9cc6-136">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 資料庫的 SQL server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="b9cc6-137">選取 [預設執行個體]\*\*\*\* 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]\*\*\*\*，並指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="b9cc6-138">如果已啟用規範，請定義的 SQL Server 規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9cc6-139">如需如何設定高可用性的 Persistent Chat Server 資料庫以及常設聊天室伺服器規範資料庫的 SQL Server 鏡像的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原</A>。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="b9cc6-140">定義檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-140">Define the file store.</span></span> <span data-ttu-id="b9cc6-141">檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="b9cc6-142">在多部伺服器 Persistent Chat Server 拓撲，這必須是通用命名慣例 (UNC) 路徑;與單一伺服器 Persistent Chat Server 拓撲，它可以是本機檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="b9cc6-143">若要使用現有的檔案存放區，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b9cc6-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="b9cc6-144">在 [檔案伺服器 FQDN]\*\*\*\* 中，指定您要建立新檔案存放區的檔案存放區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="b9cc6-145">在 [檔案共用]\*\*\*\* 中，指定要使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9cc6-146">您建立的檔案存放區，但是您必須建立檔案存放區中定義的位置才能發行拓撲之前，您可以在拓撲產生器中定義的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="b9cc6-147">選取要用來作為下一個躍點此 Persistent Chat Server 集區的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="b9cc6-148">這是將能夠將 Persistent Chat Server 要求路由傳送到此集區的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="b9cc6-149">若要儲存組態，請按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="b9cc6-150">Persistent Chat Server 集區會出現在拓撲產生器伴隨著您特定集區的設定。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="b9cc6-151">若要立即發佈更新過的拓撲後要 Persistent Chat Server，請參閱部署文件中的[發佈 Lync Server 2013 中更新的拓樸](lync-server-2013-publish-the-updated-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9cc6-152">使用拓撲產生器已經開啟，您可以繼續步驟 3 中<A href="lync-server-2013-publish-the-updated-topology.md">發佈 Lync Server 2013 中更新的拓樸</A>開始發佈更新過的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b9cc6-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

