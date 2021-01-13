---
title: 在商務用 Skype Server 中將封存資料庫新增至現有的部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要：閱讀此主題以瞭解如何將封存資料庫新增至您的商務用 Skype Server 部署。
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820673"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="99112-103">在商務用 Skype Server 中將封存資料庫新增至現有的部署</span><span class="sxs-lookup"><span data-stu-id="99112-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="99112-104">**摘要：** 閱讀此主題以瞭解如何將封存資料庫新增至您的商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="99112-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="99112-105">您必須先將封存納入拓撲中，才能設定部署來支援封存。</span><span class="sxs-lookup"><span data-stu-id="99112-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="99112-106">本主題中的資訊說明如何使用拓撲產生器來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="99112-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="99112-107">將封存資料庫新增至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="99112-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="99112-108">發行更新的拓撲，將封存資料庫新增至您的商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="99112-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99112-109">如果您想要使用 Microsoft Exchange 整合將封存資料和檔案儲存在部署中的所有使用者的 Exchange 伺服器上，請勿指定封存 **SQL server 儲存區** ，或 **使用 SQL Server 儲存區鏡像** 資訊。</span><span class="sxs-lookup"><span data-stu-id="99112-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="99112-110">將封存資料庫新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="99112-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="99112-111">在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或是具有同等使用者權限的帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="99112-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="99112-112">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="99112-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="99112-113">在主控台樹中，流覽至您要部署封存的前端集區，然後按一下您要部署封存的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="99112-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="99112-114">在 [動作] 功能表上，按一下 [編輯屬性]。</span><span class="sxs-lookup"><span data-stu-id="99112-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="99112-115">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="99112-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="99112-116">向下捲動至 [封存]。</span><span class="sxs-lookup"><span data-stu-id="99112-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="99112-117">選取 [封存] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="99112-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="99112-118">在 **[封存 SQL Server 儲存區** ] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="99112-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="99112-119">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="99112-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="99112-120">如果您的所有使用者都位於 Microsoft Exchange Server 2013 或以上，您可以封存 Exchange 中所有使用者的商務用 Skype 通訊。</span><span class="sxs-lookup"><span data-stu-id="99112-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="99112-121">在此情況下，您不需要設定 SQL Server 封存儲存區。</span><span class="sxs-lookup"><span data-stu-id="99112-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="99112-122">若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="99112-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="99112-123">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="99112-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="99112-124">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="99112-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="99112-125">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="99112-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="99112-126">若要使用 SQL Server 儲存區鏡像，請選取 **[啟用 Sql Server 儲存區鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="99112-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="99112-127">若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="99112-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="99112-128">若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="99112-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="99112-129">a.</span><span class="sxs-lookup"><span data-stu-id="99112-129">a.</span></span> <span data-ttu-id="99112-130">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="99112-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="99112-131">b.</span><span class="sxs-lookup"><span data-stu-id="99112-131">b.</span></span> <span data-ttu-id="99112-132">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="99112-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="99112-133">c.</span><span class="sxs-lookup"><span data-stu-id="99112-133">c.</span></span> <span data-ttu-id="99112-134">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="99112-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="99112-135">如果您啟用 SQL Server 鏡像，而且想要包含 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 和鏡像實例的健康情況) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="99112-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="99112-136">a.</span><span class="sxs-lookup"><span data-stu-id="99112-136">a.</span></span> <span data-ttu-id="99112-137">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="99112-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="99112-138">b.</span><span class="sxs-lookup"><span data-stu-id="99112-138">b.</span></span> <span data-ttu-id="99112-139">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="99112-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="99112-140">c.</span><span class="sxs-lookup"><span data-stu-id="99112-140">c.</span></span> <span data-ttu-id="99112-141">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="99112-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="99112-142">如要儲存設定，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99112-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="99112-143">發行更新的拓撲，將封存資料庫新增至您的部署</span><span class="sxs-lookup"><span data-stu-id="99112-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="99112-144">在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="99112-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="99112-145">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但發行拓撲（必須用來將伺服器新增至拓撲）。您必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶，且具有在您用於商務用 Skype server 檔案存放區之檔案共用上的「讀取」、「寫入」和「修改」) 的「完全控制」許可權，讓拓撲 (產生器可以設定所需的自由存取控制清單 (dacl) ，或具有對等權利的帳戶。 (</span><span class="sxs-lookup"><span data-stu-id="99112-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="99112-146">使用拓撲產生器開啟您在上一節中建立的拓撲。</span><span class="sxs-lookup"><span data-stu-id="99112-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="99112-147">在主控台樹中，以滑鼠右鍵按一下 [ **商務用 Skype 伺服器**]，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="99112-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="99112-148">在 **[發行拓樸]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99112-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="99112-149">在 **[建立資料庫]** 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99112-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="99112-150">如果您未具備建立資料庫的適當權限，可以取消選取資料庫，讓具備適當權限的人能夠建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="99112-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="99112-151">> 只有專用 SQL Server 上的資料庫可以使用拓撲產生器安裝。</span><span class="sxs-lookup"><span data-stu-id="99112-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="99112-152">與其他伺服器元件組合之 SQL server 上的資料庫必須透過在該電腦上執行本機安裝程式來安裝。</span><span class="sxs-lookup"><span data-stu-id="99112-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="99112-153">在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="99112-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="99112-154">發行拓樸之後，您必須先為封存設定選項和原則，才能封存內容。</span><span class="sxs-lookup"><span data-stu-id="99112-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="99112-155">如需詳細資訊，請參閱設定商務用 [Skype 伺服器的封存選項](configure-archiving-options.md) 及 [設定商務用 skype 伺服器](configure-archiving-policies.md)的封存原則。</span><span class="sxs-lookup"><span data-stu-id="99112-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

