---
title: Lync Server 2013：將 Persistent Chat Server 新增至拓撲
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
ms.openlocfilehash: 4656c21d9d28d84259bfaa108c399f36bd2c3d72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521440"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="3ca44-102">在 Lync Server 2013 中將 Persistent Chat Server 新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="3ca44-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca44-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3ca44-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3ca44-104">您必須在拓撲中納入 Lync Server 2013 和 Persistent Chat Server 支援，才能設定您的部署以支援 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="3ca44-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="3ca44-105">本主題中的資訊說明如何使用拓撲產生器，將 Persistent Chat Server 支援新增至現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="3ca44-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="3ca44-106">將 Persistent Chat Server 新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="3ca44-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="3ca44-107">請執行下列步驟來安裝單一持久聊天伺服器集區，而不需要災難修復設定。</span><span class="sxs-lookup"><span data-stu-id="3ca44-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="3ca44-108">若要設定高可用性和嚴重損壞修復的延伸持久聊天伺服器集區，請參閱部署檔中的在 [Lync server 2013 中設定 Persistent Chat server，以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="3ca44-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3ca44-109">若要部署多個 Persistent Chat Server 集區，請對每個集區重複相同的程式。</span><span class="sxs-lookup"><span data-stu-id="3ca44-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="3ca44-110">在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3ca44-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ca44-111">您可以使用本機使用者群組的成員帳戶來定義拓撲，但發行拓撲（安裝 Lync Server 2013 Server 所需）。您必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶，且具有在您要用於 Persistent Chat Server 檔案存放區之檔案存放區上的「完全控制」許可權 (（即讀取、寫入及修改) ），如此一來 (，拓撲產生器才能設定所需的 dacl) ，或具有對等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3ca44-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="3ca44-112">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="3ca44-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="3ca44-113">在主控台樹中，流覽至 [ **Persistent chat** 集區] 節點，並展開以選取 [Persistent chat Server 集區]，或以滑鼠右鍵按一下該節點，然後選取 [ **新增持久聊天集**區]。</span><span class="sxs-lookup"><span data-stu-id="3ca44-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="3ca44-114">您必須定義集區的完整網域名稱 (FQDN)，並指出集區將是單一伺服器集區或多重伺服器集區部署。</span><span class="sxs-lookup"><span data-stu-id="3ca44-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="3ca44-115">您可以選擇 [多重電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ca44-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="3ca44-116">如果您計畫在 Persistent Chat Server 集區中有一個以上的 Persistent Chat Server 前端伺服器，請選擇前者。</span><span class="sxs-lookup"><span data-stu-id="3ca44-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="3ca44-117">立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="3ca44-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="3ca44-118">如果您選擇 [多部電腦集區]，請輸入組成集區之個別 Persistent Chat Server 前端伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ca44-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ca44-119">若要在 Lync Server 2013 Standard Edition server 上安裝 Persistent Chat Server role &nbsp; ，FQDN 必須符合 Standard edition server 的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="3ca44-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="3ca44-120">定義 Persistent Chat Server 集區的簡易 **顯示名稱** 。</span><span class="sxs-lookup"><span data-stu-id="3ca44-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="3ca44-121">顯示名稱可供自訂用戶端使用，特別是在有多個 Persistent Chat Server 集區時，可以區別會議室。</span><span class="sxs-lookup"><span data-stu-id="3ca44-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="3ca44-122">定義 Persistent Chat Server 使用的埠，以與 Lync Server 前端伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3ca44-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="3ca44-123">預設的連接埠為 5041。</span><span class="sxs-lookup"><span data-stu-id="3ca44-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="3ca44-124">如果您的組織需要規範支援，請選取 [用規範記錄]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3ca44-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="3ca44-125">如有選取，Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="3ca44-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="3ca44-126">稍後會提示您選取 SQL Server 後端伺服器以進行 Persistent Chat Server 相容性。</span><span class="sxs-lookup"><span data-stu-id="3ca44-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="3ca44-127">為 Persistent Chat Server 集區指派網站相關性。</span><span class="sxs-lookup"><span data-stu-id="3ca44-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="3ca44-128">選取 [**使用此集區作為網站 \<SiteName\> 預設值**] 核取方塊，或**使用此集區作為所有網站的預設**值，將此 Persistent Chat Server 集區指定為目前網站或所有網站的預設集區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="3ca44-129">當 Lync 2013 用戶端用來建立及管理聊天室時，會使用與使用者網站相關聯的預設集區建立和管理體驗，讓其可以將會議室建立及管理作業路由傳送至該集區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="3ca44-130">這只有當您部署多個 Persistent Chat Server 集區，且想要使用 Persistent Chat Server 的聊天室建立及管理功能時，才適用。</span><span class="sxs-lookup"><span data-stu-id="3ca44-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ca44-131">您可以使用 Persistent Chat Server 軟體發展工具組 (SDK) ，自訂聊天室建立和管理功能。</span><span class="sxs-lookup"><span data-stu-id="3ca44-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="3ca44-132">如需如何設定 SQL Server 備份資料庫以進行嚴重損壞修復的詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中設定 Persistent Chat Server 以取得高可用性和嚴重損壞修復</A> 。</span><span class="sxs-lookup"><span data-stu-id="3ca44-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="3ca44-133">透過執行下列其中一項操作，定義 \*\*Persistent Chat Server 後端 (的 SQL 存放區。) 儲存聊天室內容 \*\* 的方式：</span><span class="sxs-lookup"><span data-stu-id="3ca44-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="3ca44-134">若要使用現有的 SQL Server 資料庫，請在下拉式清單中，按一下您要使用之 SQL Server 資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ca44-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="3ca44-135">若要指定新的 SQL Server 資料庫，請按一下 [ **新增**]，然後在 **[定義新的 SQL 存放區**] 中執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3ca44-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="3ca44-136">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3ca44-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="3ca44-137">選取 [預設執行個體]\*\*\*\* 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]\*\*\*\*，並指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="3ca44-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="3ca44-138">如果您已啟用規範，請定義 SQL Server 規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="3ca44-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ca44-139">如需如何針對 Persistent Chat Server 資料庫和 Persistent Chat Server 合規性資料庫設定高可用性之 SQL Server 鏡像的詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中設定 Persistent Chat Server，以取得高可用性和嚴重損壞修復</A> 。</span><span class="sxs-lookup"><span data-stu-id="3ca44-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="3ca44-140">定義檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-140">Define the file store.</span></span> <span data-ttu-id="3ca44-141">檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。</span><span class="sxs-lookup"><span data-stu-id="3ca44-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="3ca44-142">在多重伺服器持久聊天伺服器拓撲的情況下，這必須是通用命名慣例 (UNC) 路徑;而且，針對單一伺服器的持久聊天伺服器拓撲，它可以是本機檔路徑。</span><span class="sxs-lookup"><span data-stu-id="3ca44-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="3ca44-143">若要使用現有的檔案存放區，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3ca44-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="3ca44-144">在 [檔案伺服器 FQDN]\*\*\*\* 中，指定您要建立新檔案存放區的檔案存放區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3ca44-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="3ca44-145">在 [檔案共用]\*\*\*\* 中，指定要使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ca44-146">您可以在建立檔案存放區之前，先在拓撲產生器中定義檔案存放區，但是您必須先在您定義的位置中建立檔案存放區，然後才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="3ca44-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="3ca44-147">選取此 Persistent Chat Server 集區的下一個躍點要使用的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="3ca44-148">這是可以將 Persistent Chat Server 要求路由傳送至此集區的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3ca44-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="3ca44-149">若要儲存組態，請按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ca44-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="3ca44-150">Persistent Chat Server 集區會出現在拓撲產生器中，且附帶您的特定集區設定。</span><span class="sxs-lookup"><span data-stu-id="3ca44-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="3ca44-151">若要立即發佈您已有持久聊天伺服器的更新拓撲，請參閱部署檔中的在 [Lync Server 2013 中發佈更新的拓撲](lync-server-2013-publish-the-updated-topology.md) 。</span><span class="sxs-lookup"><span data-stu-id="3ca44-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ca44-152">在已開啟拓撲產生器的情況下，您可以繼續在 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中發佈更新的拓撲中的</A> 步驟3，以開始發行更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="3ca44-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

