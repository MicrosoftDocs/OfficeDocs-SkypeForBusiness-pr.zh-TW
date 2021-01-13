---
title: 將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要：閱讀此主題以瞭解如何將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲。
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825103"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="655d4-103">將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲</span><span class="sxs-lookup"><span data-stu-id="655d4-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="655d4-104">**摘要：** 閱讀此主題以瞭解如何將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="655d4-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="655d4-105">在您計畫部署 Persistent Chat Server 的每部伺服器上安裝必要軟體之後，您可以使用拓撲產生器來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="655d4-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="655d4-106">更新您的拓撲以包含 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="655d4-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="655d4-107">發行更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="655d4-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="655d4-108">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="655d4-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="655d4-109">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="655d4-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="655d4-110">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="655d4-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="655d4-111">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="655d4-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="655d4-112">更新您的拓撲以包含 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="655d4-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="655d4-113">請執行下列步驟來安裝單一持久聊天伺服器集區，而不需要災難修復設定。</span><span class="sxs-lookup"><span data-stu-id="655d4-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="655d4-114">若要設定高可用性和嚴重損壞修復的延伸持久聊天伺服器集區，請參閱 [在商務用 Skype server 2015 中設定 Persistent Chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="655d4-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="655d4-115">若要部署多個 Persistent Chat Server 集區，請對每個集區重複相同的程式。</span><span class="sxs-lookup"><span data-stu-id="655d4-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="655d4-116">在執行商務用 Skype 伺服器的電腦上，或已安裝商務用 Skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="655d4-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="655d4-117">您可以使用本機使用者群組的成員帳戶來定義拓撲，但發行拓撲（安裝商務用 Skype Server 所需）。您必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶，且具有您要用於 Persistent Chat Server 檔案存放區之檔案存放區的「讀取」、「寫入」和「修改」) 的「完全控制」許可權，讓 (拓撲產生器可以設定所需的 dacl) ，或具有相同權利的帳戶。 (</span><span class="sxs-lookup"><span data-stu-id="655d4-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="655d4-118">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="655d4-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="655d4-119">在主控台樹中，流覽至 [ **Persistent Chat** 集區] 節點，並展開以選取商務用 Skype 伺服器集區，或以滑鼠右鍵按一下該節點，然後選取 [ **新增持久聊天集** 區]。</span><span class="sxs-lookup"><span data-stu-id="655d4-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="655d4-120">您必須定義集區的完整功能變數名稱 (FQDN) ，並指出集區將會是單一伺服器集區還是多伺服器集區部署。</span><span class="sxs-lookup"><span data-stu-id="655d4-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="655d4-121">您可以選擇 [多重電腦集區] 或 [單一電腦集區]。</span><span class="sxs-lookup"><span data-stu-id="655d4-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="655d4-122">如果您打算在持久聊天伺服器集區中有多部前端伺服器，請選擇前者。</span><span class="sxs-lookup"><span data-stu-id="655d4-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="655d4-123">立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="655d4-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="655d4-124">如果您選擇 [多部電腦集區]，請輸入組成集區之個別前端伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="655d4-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="655d4-125">若要在 Standard Edition server 上安裝 Persistent Chat Server role，FQDN 必須符合 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="655d4-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="655d4-126">定義 Persistent Chat Server 集區的簡易 **顯示名稱** 。</span><span class="sxs-lookup"><span data-stu-id="655d4-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="655d4-127">顯示名稱可供自訂用戶端使用，特別是在有多個 Persistent Chat Server 集區來區分會議室時。</span><span class="sxs-lookup"><span data-stu-id="655d4-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="655d4-128">定義 Persistent Chat Server 使用的埠，以與商務用 Skype Server 前端伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="655d4-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="655d4-129">預設的連接埠為 5041。</span><span class="sxs-lookup"><span data-stu-id="655d4-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="655d4-130">如果您的組織需要規範支援，請選取 [用規範記錄] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="655d4-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="655d4-131">如有選取，Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="655d4-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="655d4-132">稍後會提示您選取 SQL Server 後端伺服器以進行 Persistent Chat Server 相容性。</span><span class="sxs-lookup"><span data-stu-id="655d4-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="655d4-133">為 Persistent Chat Server 集區指派網站相關性。</span><span class="sxs-lookup"><span data-stu-id="655d4-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="655d4-134">選取 [**使用此集區作為網站 \<SiteName\> 預設值**] 核取方塊，或 **使用此集區作為所有網站的預設** 值，將此 Persistent Chat Server 集區指定為目前網站或所有網站的預設集區。</span><span class="sxs-lookup"><span data-stu-id="655d4-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="655d4-135">當商務用 Skype 用戶端用來建立及管理聊天室時，會使用與使用者網站相關聯的預設集區建立和管理經驗，讓其可以將會議室建立和管理作業路由傳送至該集區。</span><span class="sxs-lookup"><span data-stu-id="655d4-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="655d4-136">這只有當您部署多個 Persistent Chat Server 集區，且想要使用 Persistent Chat Server 的聊天室建立及管理功能時，才適用。</span><span class="sxs-lookup"><span data-stu-id="655d4-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="655d4-137">您可以使用 Persistent Chat Server 軟體發展工具組 (SDK) ，自訂聊天室建立和管理功能。</span><span class="sxs-lookup"><span data-stu-id="655d4-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="655d4-138">透過執行下列其中一項操作，定義 **Persistent Chat Server 後端 (的 SQL 存放區。) 儲存聊天室內容** 的方式：</span><span class="sxs-lookup"><span data-stu-id="655d4-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="655d4-139">若要使用現有的 SQL Server 儲存區，請在下拉式清單中，按一下您要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="655d4-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="655d4-140">若要指定新的 SQL Server 資料庫，請按一下 [ **新增**]，然後在 **[定義新的 SQL 存放區**] 中執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="655d4-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="655d4-141">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="655d4-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="655d4-142">選取 [預設執行個體] 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]，並指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="655d4-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="655d4-143">如需如何設定 SQL Server 備份資料庫以進行嚴重損壞修復的詳細資訊，請參閱 [在商務用 Skype server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="655d4-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="655d4-144">如果您已啟用規範，請定義 SQL Server 規範存放區。</span><span class="sxs-lookup"><span data-stu-id="655d4-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="655d4-145">如需如何針對 Persistent Chat Server 資料庫和 Persistent Chat server 合規性資料庫設定高可用性之 SQL Server 鏡像的詳細資訊，請參閱 [在商務用 Skype server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="655d4-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="655d4-146">定義檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="655d4-146">Define the file store.</span></span> <span data-ttu-id="655d4-147">檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。</span><span class="sxs-lookup"><span data-stu-id="655d4-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="655d4-148">在多重伺服器持久聊天伺服器拓撲的情況下，這必須是通用命名慣例 (UNC) 路徑;而且，針對單一伺服器的持久聊天伺服器拓撲，它可以是本機檔路徑。</span><span class="sxs-lookup"><span data-stu-id="655d4-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="655d4-149">若要使用現有的檔案存放區，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="655d4-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="655d4-150">在 [ **檔案伺服器 FQDN**] 中，指定您要建立新檔案存放區之機器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="655d4-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="655d4-151">在 [檔案共用] 中，指定要使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="655d4-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="655d4-152">您可以在建立檔案存放區之前，先在拓撲產生器中定義檔案存放區，但是您必須先在您定義的位置中建立檔案存放區，然後才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="655d4-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="655d4-153">如果檔案存放區尚不存在，則嘗試發行拓撲會失敗。</span><span class="sxs-lookup"><span data-stu-id="655d4-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="655d4-154">選取此 Persistent Chat Server 集區的下一個躍點要使用的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="655d4-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="655d4-155">這是可以將 Persistent Chat Server 要求路由傳送至此集區的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="655d4-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="655d4-156">若要儲存組態，請按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="655d4-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="655d4-157">Persistent Chat Server 集區會出現在拓撲產生器中，且附帶您的特定集區設定。</span><span class="sxs-lookup"><span data-stu-id="655d4-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="655d4-158">若要發行您已新增持久聊天伺服器的更新拓撲，請參閱發行更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="655d4-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="655d4-159">在已開啟拓撲產生器的情況下，您可以繼續進行步驟3發行更新的拓撲，以開始發行更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="655d4-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="655d4-160">發行更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="655d4-160">Publish the updated topology</span></span>
<span data-ttu-id="655d4-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="655d4-161"><a name="BKMK_PublishTopology"> </a></span></span>

<span data-ttu-id="655d4-162">在拓撲產生器中更新拓撲之後，您必須將拓撲發行至中央管理存放區，才能設定及使用商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="655d4-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="655d4-163">資料的唯讀複本會複製到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="655d4-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="655d4-164">在發佈拓撲之前，請安裝 Persistent Chat Server 的資料庫。</span><span class="sxs-lookup"><span data-stu-id="655d4-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="655d4-165">使用拓撲產生器，選取 [ **動作** ] 並 **安裝資料庫** 以安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="655d4-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="655d4-166">在執行商務用 Skype 伺服器的電腦上，或在其上安裝商務用 Skype Server 系統管理工具的電腦上，使用同時是 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶來登入，且具有要用於 Persistent Chat Server 檔案存放區之檔案存放區上的「讀取」、「寫入」和「修改」) 的「完全控制」許可權 ( (讀取、寫入及修改），讓拓撲產生器可以設定所需的自由存取控制清單 (dacl) #</span><span class="sxs-lookup"><span data-stu-id="655d4-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="655d4-167">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="655d4-167">Start Topology Builder.</span></span> <span data-ttu-id="655d4-168">如果您已在本機儲存，請從本機檔案選取 [ **開啟拓撲** ]。</span><span class="sxs-lookup"><span data-stu-id="655d4-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="655d4-169">在主控台樹中，以滑鼠右鍵按一下 [ **商務用 Skype Server 2015**]，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="655d4-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="655d4-170">在 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="655d4-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="655d4-171">在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="655d4-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

