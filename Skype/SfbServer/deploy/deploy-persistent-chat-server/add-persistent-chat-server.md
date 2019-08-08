---
title: 在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器。'
ms.openlocfilehash: 7d5a61dd001c759eab4b168cb3543032de7b4fc4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239864"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="a40ad-103">在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="a40ad-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="a40ad-104">**摘要:** 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="a40ad-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="a40ad-105">在您規劃要部署持久聊天伺服器的每個伺服器上安裝必備軟體之後, 您可以使用拓撲建立器進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="a40ad-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="a40ad-106">更新您的拓撲以包含持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="a40ad-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="a40ad-107">發行更新後的拓撲</span><span class="sxs-lookup"><span data-stu-id="a40ad-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="a40ad-108">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="a40ad-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a40ad-109">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="a40ad-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="a40ad-110">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="a40ad-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a40ad-111">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="a40ad-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="a40ad-112">更新您的拓撲以包含持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="a40ad-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="a40ad-113">若要在沒有災害復原設定的情況下安裝單一持久聊天伺服器池, 請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a40ad-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="a40ad-114">若要針對高可用性和災難復原來設定延伸持久聊天伺服器池, 請參閱[在商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災害復原](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="a40ad-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="a40ad-115">若要部署多個持續聊天伺服器池, 請針對每個池重複執行相同的程式。</span><span class="sxs-lookup"><span data-stu-id="a40ad-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="a40ad-116">在執行商務用 Skype Server 或已安裝商務用 skype Server 系統管理工具的電腦上, 使用屬於 [本機使用者] 群組成員的帳戶登入 (或是擁有同等使用者權限的帳戶)。</span><span class="sxs-lookup"><span data-stu-id="a40ad-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a40ad-117">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴, 但若要發佈拓撲 (需要安裝商務用 Skype Server), 您必須使用屬於**Domain Admins**群組成員的帳戶, 以及**RTCUniversalServerAdmins**群組, 且在您要用於持續聊天伺服器檔案存放區的檔案存放區上擁有完全控制許可權 (讀取、寫入及修改), 讓拓撲產生器可以設定所需的 dacl, 或使用對等權利。</span><span class="sxs-lookup"><span data-stu-id="a40ad-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="a40ad-118">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="a40ad-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="a40ad-119">在主控台樹狀結構中, 流覽至 [**永久聊天池**] 節點, 然後展開以選取商務用 Skype 伺服器池, 或以滑鼠右鍵按一下該節點, 然後選取 [**新增持久聊天] 池**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="a40ad-120">您必須定義池子的完整功能變數名稱 (FQDN), 並指出該池是單一伺服器池或多重伺服器池部署。</span><span class="sxs-lookup"><span data-stu-id="a40ad-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="a40ad-121">您可以選擇**多個電腦池**或**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="a40ad-122">如果您打算在持久聊天伺服器池中進行多個前端伺服器的規劃, 請選擇前者。</span><span class="sxs-lookup"><span data-stu-id="a40ad-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="a40ad-123">現在就進行這項選擇, 或在稍後進行, 因為在您建立單一電腦池之後, 您稍後就不能再新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="a40ad-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="a40ad-124">如果您選擇多個電腦池, 請輸入組成該池之個別前端伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="a40ad-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a40ad-125">如果要在標準版伺服器上安裝永久聊天伺服器角色, FQDN 必須與標準版伺服器的 FQDN 相符。</span><span class="sxs-lookup"><span data-stu-id="a40ad-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="a40ad-126">定義持續聊天伺服器池的簡單**顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="a40ad-127">顯示名稱可以由自訂用戶端使用, 特別是在有多個持續聊天伺服器池來區分房間時。</span><span class="sxs-lookup"><span data-stu-id="a40ad-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="a40ad-128">定義持續聊天伺服器用來與商務用 Skype Server 前端伺服器通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="a40ad-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="a40ad-129">預設埠是5041。</span><span class="sxs-lookup"><span data-stu-id="a40ad-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="a40ad-130">如果您的組織需要合規性支援, 請選取 [**啟用合規性**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a40ad-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="a40ad-131">如果已選取, 持久的聊天伺服器合規性服務會安裝在與永久聊天伺服器前端伺服器相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a40ad-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="a40ad-132">接著系統會提示您選取一個 SQL Server 後端伺服器, 以進行持續聊天伺服器的相容性。</span><span class="sxs-lookup"><span data-stu-id="a40ad-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="a40ad-133">針對持續聊天伺服器池指派網站關聯性。</span><span class="sxs-lookup"><span data-stu-id="a40ad-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="a40ad-134">選取 [**使用此 pool 做為網站\<SiteName\>的預設值**] 核取方塊, 或**將此 pool 作為 [所有網站**] 的預設值, 將此永久性聊天伺服器池指定為目前網站或所有網站的預設池。</span><span class="sxs-lookup"><span data-stu-id="a40ad-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="a40ad-135">當商務用 Skype 用戶端用來建立及管理會議室時, 聊天室的建立和管理體驗會使用與使用者網站相關聯的預設池, 以便在該池中傳送聊天室的建立和管理作業。</span><span class="sxs-lookup"><span data-stu-id="a40ad-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="a40ad-136">這僅適用于已部署多個持久聊天伺服器池, 且想要使用持續聊天伺服器的聊天室建立和管理功能。</span><span class="sxs-lookup"><span data-stu-id="a40ad-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a40ad-137">您可以使用持續聊天伺服器軟體發展工具組 (SDK) 來自訂聊天室的建立與管理功能。</span><span class="sxs-lookup"><span data-stu-id="a40ad-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="a40ad-138">您可以執行下列其中一項動作,**以定義持續式聊天伺服器後端 (儲存聊天室內容的位置) 的 SQL store** :</span><span class="sxs-lookup"><span data-stu-id="a40ad-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="a40ad-139">若要使用現有的 SQL Server store, 請在下拉式清單中, 按一下您要使用的 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="a40ad-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="a40ad-140">若要指定新的 SQL Server 資料庫, 請按一下 [**新增**], 然後在 **[定義新的 sql Store**] 中, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="a40ad-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="a40ad-141">在 **[SQL SERVER FQDN**] 中, 指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a40ad-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="a40ad-142">您可以選取 [**預設實例**] 來使用預設實例, 或者, 若要指定不同的實例, 請選取 [**命名實例**], 然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="a40ad-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a40ad-143">如需如何設定 SQL Server 備份資料庫以進行災難復原的詳細資料, 請參閱[在商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災害復原](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="a40ad-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="a40ad-144">如果您已啟用合規性, 請定義 SQL Server 合規性存放區。</span><span class="sxs-lookup"><span data-stu-id="a40ad-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a40ad-145">如需有關如何設定 SQL Server 鏡像以取得持久聊天伺服器資料庫和持續聊天伺服器合規性資料庫之高可用性的詳細資訊, 請參閱[在 Skype 中設定持久聊天伺服器的高可用性與災害復原商務用伺服器 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="a40ad-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="a40ad-146">定義檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="a40ad-146">Define the file store.</span></span> <span data-ttu-id="a40ad-147">檔案存放區是儲存上傳至檔案存放庫之任何檔案複本的資料夾 (例如, 儲存張貼到聊天室的檔案附件)。</span><span class="sxs-lookup"><span data-stu-id="a40ad-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="a40ad-148">如果是多重伺服器持續聊天伺服器拓撲, 這必須是通用命名慣例 (UNC) 路徑;而且, 對於單一伺服器持續聊天伺服器拓撲, 它可以是本機檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="a40ad-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="a40ad-149">若要使用現有的檔案存放區, 請執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="a40ad-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="a40ad-150">在 [檔案**伺服器 FQDN**] 中, 指定您要在其中建立新檔案存放區之電腦的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a40ad-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="a40ad-151">在 [檔案**共用**] 中, 指定您要使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="a40ad-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="a40ad-152">您可以在建立檔案存放區前, 在拓撲結構建立器中定義檔案存放區, 但您必須先在您定義的定義位置中建立檔案存放區, 然後才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="a40ad-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="a40ad-153">如果檔案存放區尚不存在, 則無法發佈拓朴的嘗試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a40ad-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="a40ad-154">選取要做為此持續聊天伺服器池的下一個躍點的前端伺服器池。</span><span class="sxs-lookup"><span data-stu-id="a40ad-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="a40ad-155">這是可將持續聊天伺服器要求路由至此池中的前端伺服器池。</span><span class="sxs-lookup"><span data-stu-id="a40ad-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="a40ad-156">若要儲存配置, 請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="a40ad-157">[持續聊天伺服器] 池會出現在拓撲建立器中, 並隨附您的特定 [池] 設定。</span><span class="sxs-lookup"><span data-stu-id="a40ad-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="a40ad-158">若要發佈您已新增持久聊天伺服器的更新拓撲, 請參閱發佈更新後的拓撲。</span><span class="sxs-lookup"><span data-stu-id="a40ad-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a40ad-159">在已開啟拓撲結構建立器的情況下, 您可以繼續進行 [發佈更新拓撲] 中的步驟 3, 以開始發佈您更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="a40ad-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="a40ad-160">發行更新後的拓撲</span><span class="sxs-lookup"><span data-stu-id="a40ad-160">Publish the updated topology</span></span>
<span data-ttu-id="a40ad-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="a40ad-161"></span></span>

<span data-ttu-id="a40ad-162">在拓撲建立器中更新拓撲之後, 您必須先將拓撲發佈到中央管理儲存區, 才能設定及使用商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="a40ad-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="a40ad-163">唯讀複本會將資料複製到拓撲中的所有伺服器, 以讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="a40ad-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="a40ad-164">在發佈拓撲前, 請先安裝持久聊天伺服器的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a40ad-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="a40ad-165">使用拓撲建立器, 選取 [**動作**] 並**安裝資料庫**以安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="a40ad-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="a40ad-166">在執行商務用 Skype Server 或已安裝商務用 skype Server 系統管理工具的電腦上, 請使用同時是**Domain Admins**群組和**RTCUniversalServerAdmins**群組成員的帳戶登入。而且, 在檔案存放區上具有 [完全控制] 許可權 (讀取、寫入及修改), 用於持續聊天伺服器檔案存放區 (讓拓撲建立器可以設定所需的隨機存取控制清單 (Dacl)), 或是具有同等使用者的帳戶。版權.</span><span class="sxs-lookup"><span data-stu-id="a40ad-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="a40ad-167">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="a40ad-167">Start Topology Builder.</span></span> <span data-ttu-id="a40ad-168">如果您儲存在本機檔案中, 請選取 [**從本機檔案開啟拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="a40ad-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="a40ad-169">在主控台樹中, 以滑鼠右鍵按一下 [**商務用 Skype Server 2015**], 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="a40ad-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="a40ad-170">在 [**發佈拓撲**] 頁面上, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a40ad-171">在 [**發佈嚮導完成]** 頁面上, 確認拓撲已順利發佈, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a40ad-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

