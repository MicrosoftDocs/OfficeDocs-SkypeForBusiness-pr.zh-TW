---
title: 變更商務用 Skype Server 中的封存資料庫選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：瞭解如何變更商務用 Skype 伺服器的封存資料庫選項。
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817693"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="3f122-103">變更商務用 Skype Server 中的封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="3f122-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="3f122-104">**摘要：** 瞭解如何變更商務用 Skype 伺服器的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="3f122-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="3f122-105">如果您使用 SQL Server storage 部署封存，以封存任何使用者的儲存體，您可以進行下列資料庫儲存變更：</span><span class="sxs-lookup"><span data-stu-id="3f122-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="3f122-106">使用不同的 SQL Server 資料庫來封存儲存體。</span><span class="sxs-lookup"><span data-stu-id="3f122-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="3f122-107">這包括主要封存資料庫和您用來進行 SQL Server 鏡像的任何資料庫。</span><span class="sxs-lookup"><span data-stu-id="3f122-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="3f122-108">切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="3f122-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="3f122-109">如果您的所有使用者都位於 Exchange 伺服器上，而您想要將 Microsoft Exchange storage 用於部署中的所有使用者，則應該從拓撲中移除 SQL Server 儲存區資料庫。</span><span class="sxs-lookup"><span data-stu-id="3f122-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="3f122-110">若要進行這項變更，您必須執行拓撲產生器、進行變更，然後重新發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="3f122-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="3f122-111">除非您的商務用 Skype 使用者不是位於 Exchange 伺服器上，否則請勿指定封存 **Sql server 儲存區** 或 **啟用 SQL server 儲存區鏡像** 資訊。</span><span class="sxs-lookup"><span data-stu-id="3f122-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="3f122-112">變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="3f122-112">Change Archiving database options</span></span>

1. <span data-ttu-id="3f122-113">在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或是具有同等使用者權限的帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="3f122-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3f122-114">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將元件新增至拓撲），則必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶。而且具有在您用於商務用 Skype Server 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由存取控制清單 (dacl) ，或具有 (對等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f122-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="3f122-115">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="3f122-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="3f122-116">在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="3f122-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="3f122-117">在 [動作] 功能表上，按一下 [編輯屬性]。</span><span class="sxs-lookup"><span data-stu-id="3f122-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="3f122-118">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="3f122-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="3f122-119">向下捲動至 **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="3f122-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="3f122-120">在 **[封存]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f122-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="3f122-121">如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區] 的下拉式清單方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f122-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="3f122-122">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="3f122-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="3f122-123">如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f122-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="3f122-124">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="3f122-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="3f122-125">若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f122-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="3f122-126">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3f122-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="3f122-127">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="3f122-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="3f122-128">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3f122-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3f122-129">如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f122-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="3f122-130">若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="3f122-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="3f122-131">若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3f122-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="3f122-132">a.</span><span class="sxs-lookup"><span data-stu-id="3f122-132">a.</span></span> <span data-ttu-id="3f122-133">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3f122-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="3f122-134">b.</span><span class="sxs-lookup"><span data-stu-id="3f122-134">b.</span></span> <span data-ttu-id="3f122-135">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="3f122-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="3f122-136">c.</span><span class="sxs-lookup"><span data-stu-id="3f122-136">c.</span></span> <span data-ttu-id="3f122-137">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3f122-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3f122-138">如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3f122-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="3f122-139">a.</span><span class="sxs-lookup"><span data-stu-id="3f122-139">a.</span></span> <span data-ttu-id="3f122-140">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3f122-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="3f122-141">b.</span><span class="sxs-lookup"><span data-stu-id="3f122-141">b.</span></span> <span data-ttu-id="3f122-142">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="3f122-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="3f122-143">c.</span><span class="sxs-lookup"><span data-stu-id="3f122-143">c.</span></span> <span data-ttu-id="3f122-144">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3f122-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3f122-145">若要切換至 Microsoft Exchange 整合，將封存資料和檔案儲存在 Exchange 伺服器上 (如果您部署中的所有使用者都位於 Exchange 伺服器) 上，請刪除封存資料庫的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="3f122-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="3f122-146">如果您有任何商務用 Skype 使用者非位於 Exchange 伺服器上，請勿刪除 SQL Server 儲存區資訊。</span><span class="sxs-lookup"><span data-stu-id="3f122-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="3f122-147">如要儲存設定，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3f122-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3f122-148">在您發佈新的拓撲之前，您在拓撲產生器中所做的變更不會生效。</span><span class="sxs-lookup"><span data-stu-id="3f122-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="3f122-149">如需詳細資訊，請參閱 [在商務用 Skype Server 中新增封存資料庫至現有的部署](../../deploy/deploy-archiving/add-archiving-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="3f122-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="3f122-150">使用 Windows PowerShell 變更封存資料庫的位置</span><span class="sxs-lookup"><span data-stu-id="3f122-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="3f122-151">在大多數情況下，您不需要變更封存資料庫的位置，此資料庫會在您安裝封存伺服器時指定。</span><span class="sxs-lookup"><span data-stu-id="3f122-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="3f122-152">不過，如果發生硬體故障或其他問題，您可以使用 **CsArchivingServer** 指令程式將封存伺服器指向新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="3f122-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="3f122-153">下列範例會變更 ArchivingServer： atl-cs-001.contoso.com 封存伺服器之封存資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="3f122-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="3f122-154">在此範例中，新的資料庫位於 ArchivingDatabase： atl-sql-001.contoso.com：</span><span class="sxs-lookup"><span data-stu-id="3f122-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


