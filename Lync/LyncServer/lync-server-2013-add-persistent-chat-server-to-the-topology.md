---
title: Lync Server 2013：將常設聊天室伺服器新增至拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="14d1f-102">在 Lync Server 2013 中將常設聊天室伺服器新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="14d1f-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d1f-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="14d1f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="14d1f-104">您必須先在拓撲中加入 Lync Server 2013、持久聊天伺服器支援，然後才能設定您的部署支援永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="14d1f-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="14d1f-105">本主題中的資訊說明如何使用拓撲建立器，將持續聊天伺服器支援新增至現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="14d1f-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="14d1f-106">在拓撲中新增持續聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="14d1f-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="14d1f-107">若要在沒有災害復原設定的情況下安裝單一持久聊天伺服器池，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="14d1f-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="14d1f-108">若要針對高可用性和災難復原來設定延伸持久聊天伺服器池，請參閱在部署檔中設定[持久聊天伺服器以取得 Lync Server 2013 的高可用性和災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="14d1f-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="14d1f-109">若要部署多個持續聊天伺服器池，請針對每個池重複執行相同的程式。</span><span class="sxs-lookup"><span data-stu-id="14d1f-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="14d1f-110">在執行 Lync Server 2013 或已安裝 Lync Server 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="14d1f-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14d1f-111">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須安裝 Lync Server 2013 server。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您要用於持續聊天伺服器檔案存放區的檔案存放區上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立器可以設定所需的 dacl。或具有同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="14d1f-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="14d1f-112">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="14d1f-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="14d1f-113">在主控台樹中，流覽至 [**永久聊天池**] 節點，然後展開以選取持續聊天伺服器池，或以滑鼠右鍵按一下該節點，然後選取 [**新增持久聊天] 池**。</span><span class="sxs-lookup"><span data-stu-id="14d1f-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="14d1f-114">您必須定義池子的完整功能變數名稱（FQDN），並指出該池是單一伺服器池或多重伺服器池部署。</span><span class="sxs-lookup"><span data-stu-id="14d1f-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="14d1f-115">您可以選擇**多個電腦池**或**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="14d1f-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="14d1f-116">如果您打算在持久聊天伺服器池中安裝多個持續聊天伺服器前端伺服器，請選擇前者。</span><span class="sxs-lookup"><span data-stu-id="14d1f-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="14d1f-117">現在就進行這項選擇，或在稍後進行，因為在您建立單一電腦池之後，您稍後就不能再新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="14d1f-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="14d1f-118">如果您選擇多個電腦池，請輸入組成該池的個別持久聊天伺服器前端伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="14d1f-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14d1f-119">如果要在 Lync Server 2013&nbsp;標準版伺服器上安裝永久聊天伺服器角色，fqdn 必須與標準版伺服器的 fqdn 相符。</span><span class="sxs-lookup"><span data-stu-id="14d1f-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="14d1f-120">定義持續聊天伺服器池的簡單**顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="14d1f-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="14d1f-121">顯示名稱可以由自訂用戶端使用，特別是在有多個持續聊天伺服器池時，以區別會議室。</span><span class="sxs-lookup"><span data-stu-id="14d1f-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="14d1f-122">定義持續聊天伺服器用來與 Lync Server 前端伺服器進行通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="14d1f-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="14d1f-123">預設埠是5041。</span><span class="sxs-lookup"><span data-stu-id="14d1f-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="14d1f-124">如果您的組織需要合規性支援，請選取 [**啟用合規性**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="14d1f-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="14d1f-125">如果已選取，持久的聊天伺服器合規性服務會安裝在與永久聊天伺服器前端伺服器相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="14d1f-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="14d1f-126">接著系統會提示您選取一個 SQL Server 後端伺服器，以進行持續聊天伺服器的相容性。</span><span class="sxs-lookup"><span data-stu-id="14d1f-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="14d1f-127">針對持續聊天伺服器池指派網站關聯性。</span><span class="sxs-lookup"><span data-stu-id="14d1f-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="14d1f-128">選取 [**使用此 pool 做為網站\<SiteName\>的預設值**] 核取方塊，或**將此 pool 作為 [所有網站**] 的預設值，將此永久性聊天伺服器池指定為目前網站或所有網站的預設池。</span><span class="sxs-lookup"><span data-stu-id="14d1f-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="14d1f-129">當 Lync 2013 用戶端用來建立及管理會議室時，聊天室的建立和管理體驗會使用與使用者網站相關聯的預設池，以便在該池中傳送聊天室的建立和管理作業。</span><span class="sxs-lookup"><span data-stu-id="14d1f-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="14d1f-130">這僅適用于已部署多個持久聊天伺服器池，且想要使用持續聊天伺服器的聊天室建立和管理功能。</span><span class="sxs-lookup"><span data-stu-id="14d1f-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14d1f-131">您可以使用持續聊天伺服器軟體發展工具組（SDK）來自訂聊天室的建立與管理功能。</span><span class="sxs-lookup"><span data-stu-id="14d1f-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="14d1f-132">如需如何設定 SQL Server 備份資料庫以進行災難復原的詳細資料，請參閱在部署檔中<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">針對 Lync server 2013 的高可用性和災難復原設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="14d1f-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="14d1f-133">您可以執行下列其中一項動作，**以定義持續式聊天伺服器後端（儲存聊天室內容的位置）的 SQL store** ：</span><span class="sxs-lookup"><span data-stu-id="14d1f-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="14d1f-134">若要使用現有的 SQL Server 資料庫，請在下拉式清單中，按一下您要使用的 SQL Server 資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="14d1f-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="14d1f-135">若要指定新的 SQL Server 資料庫，請按一下 [**新增**]，然後在 **[定義新的 sql Store**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="14d1f-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="14d1f-136">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="14d1f-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="14d1f-137">您可以選取 [**預設實例**] 來使用預設實例，或者，若要指定不同的實例，請選取 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="14d1f-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="14d1f-138">如果您已啟用合規性，請定義 SQL Server 合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="14d1f-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14d1f-139">如需有關如何針對持久聊天伺服器資料庫和持續性聊天伺服器規範資料庫設定 SQL Server 鏡像的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">持久聊天伺服器以取得 Lync Server 2013 的高可用性和災害復原</A>。</span><span class="sxs-lookup"><span data-stu-id="14d1f-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="14d1f-140">定義檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="14d1f-140">Define the file store.</span></span> <span data-ttu-id="14d1f-141">檔案存放區是儲存上傳至檔案存放庫之任何檔案複本的資料夾（例如，儲存張貼到聊天室的檔案附件）。</span><span class="sxs-lookup"><span data-stu-id="14d1f-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="14d1f-142">如果是多重伺服器持續聊天伺服器拓撲，這必須是通用命名慣例（UNC）路徑;而且，對於單一伺服器持續聊天伺服器拓撲，它可以是本機檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="14d1f-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="14d1f-143">若要使用現有的檔案存放區，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="14d1f-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="14d1f-144">在 [檔案**伺服器 FQDN**] 中，指定您要在其中建立新檔案存放區之檔案存放區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="14d1f-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="14d1f-145">在 [檔案**共用**] 中，指定您要使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="14d1f-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14d1f-146">您可以在建立檔案存放區前，在拓撲結構建立器中定義檔案存放區，但您必須先在您定義的定義位置中建立檔案存放區，然後才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="14d1f-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="14d1f-147">選取要做為此持續聊天伺服器池的下一個躍點的前端伺服器池。</span><span class="sxs-lookup"><span data-stu-id="14d1f-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="14d1f-148">這是可將持續聊天伺服器要求路由至此池中的前端伺服器池。</span><span class="sxs-lookup"><span data-stu-id="14d1f-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="14d1f-149">若要儲存配置，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="14d1f-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="14d1f-150">[持續聊天伺服器] 池會出現在拓撲建立器中，並隨附您的特定 [池] 設定。</span><span class="sxs-lookup"><span data-stu-id="14d1f-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="14d1f-151">若要立即發佈您已永久聊天伺服器的更新拓撲，請參閱在部署檔中[發佈 Lync Server 2013 的更新拓撲](lync-server-2013-publish-the-updated-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="14d1f-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14d1f-152">在已開啟 [拓撲結構建立器] 的情況下，您可以繼續在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中發佈更新拓撲中的</A>步驟3，開始發佈您更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="14d1f-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

