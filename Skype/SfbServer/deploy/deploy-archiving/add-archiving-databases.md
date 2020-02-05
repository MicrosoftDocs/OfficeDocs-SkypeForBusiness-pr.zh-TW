---
title: 在商務用 Skype Server 中新增封存資料庫至現有的部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要：請閱讀本主題，以瞭解如何將封存資料庫新增到您的商務用 Skype Server 部署。
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769046"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="2acbc-103">在商務用 Skype Server 中新增封存資料庫至現有的部署</span><span class="sxs-lookup"><span data-stu-id="2acbc-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="2acbc-104">**摘要：** 請閱讀本主題，以瞭解如何將封存資料庫新增到您的商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="2acbc-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="2acbc-105">您必須先將存檔納入拓撲中，才能設定您的部署支援封存。</span><span class="sxs-lookup"><span data-stu-id="2acbc-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="2acbc-106">本主題中的資訊說明如何使用拓撲產生器進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2acbc-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="2acbc-107">新增封存資料庫至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="2acbc-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="2acbc-108">發佈更新的拓撲，以將封存資料庫新增到您的商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="2acbc-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2acbc-109">如果您想要使用 Microsoft Exchange 整合來在 Exchange 伺服器上為您的部署中的所有使用者儲存存檔資料和檔案，請勿指定 **[封存 Sql server store** ] 或 **[使用 SQL Server store 鏡像**資訊]。</span><span class="sxs-lookup"><span data-stu-id="2acbc-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="2acbc-110">在拓撲中新增封存資料庫</span><span class="sxs-lookup"><span data-stu-id="2acbc-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="2acbc-111">在執行商務用 Skype Server 的電腦上，或安裝 [商務用 Skype Server] 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="2acbc-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="2acbc-112">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="2acbc-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="2acbc-113">在主控台樹中，流覽至您要在其中部署封存的 [前端] 池，然後按一下您要部署封存的 [前端] 池名稱。</span><span class="sxs-lookup"><span data-stu-id="2acbc-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="2acbc-114">在 [**動作**] 功能表中，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="2acbc-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="2acbc-115">在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="2acbc-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="2acbc-116">**向下滾動至 [** 封存]。</span><span class="sxs-lookup"><span data-stu-id="2acbc-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="2acbc-117">選取 [**存檔**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2acbc-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="2acbc-118">在 **[封存 SQL Server store** ] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2acbc-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="2acbc-119">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="2acbc-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="2acbc-120">如果您的所有使用者都是以 Microsoft Exchange Server 2013 或更高版本為宿主，您可以將 Exchange 中所有使用者的商務用 Skype 通訊封存。</span><span class="sxs-lookup"><span data-stu-id="2acbc-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="2acbc-121">在這種情況下，您不需要設定 SQL Server 封存存放區。</span><span class="sxs-lookup"><span data-stu-id="2acbc-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="2acbc-122">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2acbc-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="2acbc-123">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2acbc-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="2acbc-124">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="2acbc-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="2acbc-125">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="2acbc-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="2acbc-126">如果您想要使用 SQL Server store 鏡像，請選取 **[啟用 Sql Server store 鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2acbc-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="2acbc-127">若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。</span><span class="sxs-lookup"><span data-stu-id="2acbc-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="2acbc-128">若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2acbc-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="2acbc-129">是.</span><span class="sxs-lookup"><span data-stu-id="2acbc-129">a.</span></span> <span data-ttu-id="2acbc-130">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2acbc-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="2acbc-131">乙.</span><span class="sxs-lookup"><span data-stu-id="2acbc-131">b.</span></span> <span data-ttu-id="2acbc-132">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="2acbc-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="2acbc-133">c-clip.</span><span class="sxs-lookup"><span data-stu-id="2acbc-133">c.</span></span> <span data-ttu-id="2acbc-134">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="2acbc-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="2acbc-135">如果您啟用 SQL Server 鏡像，且想要包含 SQL Server 鏡像見證（第三個獨立的 SQL Server 實例，可偵測主要 SQL Server 和鏡像實例的健康情況），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2acbc-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="2acbc-136">是.</span><span class="sxs-lookup"><span data-stu-id="2acbc-136">a.</span></span> <span data-ttu-id="2acbc-137">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2acbc-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="2acbc-138">乙.</span><span class="sxs-lookup"><span data-stu-id="2acbc-138">b.</span></span> <span data-ttu-id="2acbc-139">按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。</span><span class="sxs-lookup"><span data-stu-id="2acbc-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="2acbc-140">c-clip.</span><span class="sxs-lookup"><span data-stu-id="2acbc-140">c.</span></span> <span data-ttu-id="2acbc-141">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="2acbc-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="2acbc-142">若要儲存配置，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2acbc-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="2acbc-143">發佈已更新的拓撲，以將封存資料庫新增到您的部署</span><span class="sxs-lookup"><span data-stu-id="2acbc-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="2acbc-144">在執行商務用 Skype Server 的電腦上，或已安裝商務用 Skype Server 系統管理工具的電腦上，請使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權利的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="2acbc-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2acbc-145">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將伺服器新增到拓撲中。您必須使用**網域系統管理員**群組和**RTCUniversalServerAdmins**群組成員的帳戶，且在您用於商務用 Skype server 檔存放區的檔案共用上擁有完全控制許可權（讀取、寫入及修改），才能讓拓撲建立員設定必要的隨機存取控制清單（dacl），或具有同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2acbc-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="2acbc-146">使用拓撲建立器開啟您在前一節所建立的拓撲。</span><span class="sxs-lookup"><span data-stu-id="2acbc-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="2acbc-147">在主控台樹中，以滑鼠右鍵按一下 [**商務用 Skype Server**]，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="2acbc-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="2acbc-148">在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2acbc-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="2acbc-149">在 [**建立資料庫**] 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2acbc-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2acbc-150">如果您沒有建立資料庫的適當許可權，您可以取消選取資料庫，且具有適當許可權的人員可以建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2acbc-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="2acbc-151">> 只有專用 SQL Server 上的資料庫才能使用拓撲建立器進行安裝。</span><span class="sxs-lookup"><span data-stu-id="2acbc-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="2acbc-152">與其他伺服器元件 collocated 之 SQL server 上的資料庫，必須透過在該電腦上執行本機安裝程式來安裝。</span><span class="sxs-lookup"><span data-stu-id="2acbc-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="2acbc-153">在 [**發佈嚮導完成]** 頁面上，確認拓撲已順利發佈，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="2acbc-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2acbc-154">發佈拓朴之後，您必須先設定用於封存的選項和原則，才能存檔任何內容。</span><span class="sxs-lookup"><span data-stu-id="2acbc-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="2acbc-155">如需詳細資訊，請參閱[設定商務用 Skype server](configure-archiving-options.md)的封存選項，以及[設定商務用 skype server 的存檔原則](configure-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2acbc-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

