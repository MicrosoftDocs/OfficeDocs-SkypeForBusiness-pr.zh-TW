---
title: 在商務用 Skype Server 中變更封存資料庫選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：瞭解如何變更商務用 Skype Server 的存檔資料庫選項。
ms.openlocfilehash: 3e7ae30e012464b6d1f72e323dd60ad397e7430d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992760"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="ccd12-103">在商務用 Skype Server 中變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="ccd12-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="ccd12-104">**摘要：** 瞭解如何變更商務用 Skype Server 的存檔資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="ccd12-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="ccd12-105">如果您使用 SQL Server storage 部署歸檔來儲存任何使用者的儲存空間，您可以變更下列資料庫儲存空間：</span><span class="sxs-lookup"><span data-stu-id="ccd12-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="ccd12-106">使用不同的 SQL Server 資料庫來存檔儲存空間。</span><span class="sxs-lookup"><span data-stu-id="ccd12-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="ccd12-107">這包括主要的歸檔資料庫，以及您用於 SQL Server 鏡像的任何資料庫。</span><span class="sxs-lookup"><span data-stu-id="ccd12-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="ccd12-108">切換至 Microsoft Exchange 整合，以儲存 Exchange 伺服器上的封存資料和檔案。</span><span class="sxs-lookup"><span data-stu-id="ccd12-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="ccd12-109">如果您的所有使用者都是駐留在 Exchange 伺服器上，而您想要在部署中的所有使用者都使用 Microsoft Exchange 儲存空間，您應該從拓撲中移除 SQL Server store 資料庫。</span><span class="sxs-lookup"><span data-stu-id="ccd12-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="ccd12-110">若要進行其中一個變更，您必須執行拓撲建立器，進行變更，然後再次發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="ccd12-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="ccd12-111">除非您有不在 Exchange 伺服器上的商務用 Skype 使用者，否則請勿指定 **[封存 Sql server store** ] 或 **[啟用 sql server store 鏡像**資訊]。</span><span class="sxs-lookup"><span data-stu-id="ccd12-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="ccd12-112">變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="ccd12-112">Change Archiving database options</span></span>

1. <span data-ttu-id="ccd12-113">在執行商務用 Skype Server 的電腦上，或安裝 [商務用 Skype Server] 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="ccd12-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ccd12-114">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將元件新增到拓撲中。您必須使用的帳戶是**Domain Admins**群組和**RTCUniversalServerAdmins**群組的成員，且在您用於商務用 Skype Server 檔存放區的檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立器可以設定必要的隨機存取控制清單（Dacl）或具有同等許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ccd12-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="ccd12-115">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="ccd12-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="ccd12-116">在主控台樹中，流覽至您已部署封存的 [前端] 池，然後按一下您要變更資料庫選項的前端池名稱。</span><span class="sxs-lookup"><span data-stu-id="ccd12-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="ccd12-117">在 [**動作**] 功能表中，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ccd12-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="ccd12-118">在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="ccd12-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="ccd12-119">**向下滾動至 [** 封存]。</span><span class="sxs-lookup"><span data-stu-id="ccd12-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="ccd12-120">在 [**存檔**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="ccd12-121">若要變更為不同的現有 SQL Server store，請在 [封存**Sql server store**] 下的下拉式清單方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="ccd12-122">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ccd12-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="ccd12-123">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="ccd12-124">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ccd12-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="ccd12-125">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="ccd12-126">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccd12-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="ccd12-127">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ccd12-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="ccd12-128">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ccd12-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="ccd12-129">若要新增 SQL Server store 以進行鏡像或變更為其他現有的 sql server store for SQL server store 鏡像，請選取 [**啟用 SQL Server store 鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="ccd12-130">若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。</span><span class="sxs-lookup"><span data-stu-id="ccd12-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="ccd12-131">若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="ccd12-132">是.</span><span class="sxs-lookup"><span data-stu-id="ccd12-132">a.</span></span> <span data-ttu-id="ccd12-133">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccd12-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="ccd12-134">乙.</span><span class="sxs-lookup"><span data-stu-id="ccd12-134">b.</span></span> <span data-ttu-id="ccd12-135">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ccd12-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="ccd12-136">c-clip.</span><span class="sxs-lookup"><span data-stu-id="ccd12-136">c.</span></span> <span data-ttu-id="ccd12-137">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ccd12-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="ccd12-138">如果您啟用 SQL Server 鏡像，並想要新增或變更 SQL Server 鏡像見證（第三個是可偵測主要 SQL Server 服務器與鏡像實例之健康情況的第三個 SQL Server 實例），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ccd12-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="ccd12-139">是.</span><span class="sxs-lookup"><span data-stu-id="ccd12-139">a.</span></span> <span data-ttu-id="ccd12-140">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccd12-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="ccd12-141">乙.</span><span class="sxs-lookup"><span data-stu-id="ccd12-141">b.</span></span> <span data-ttu-id="ccd12-142">按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。</span><span class="sxs-lookup"><span data-stu-id="ccd12-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="ccd12-143">c-clip.</span><span class="sxs-lookup"><span data-stu-id="ccd12-143">c.</span></span> <span data-ttu-id="ccd12-144">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ccd12-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="ccd12-145">若要切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 伺服器上（如果您部署中的所有使用者都駐留在您的 Exchange 伺服器上），請刪除所有儲存資料庫的資訊。</span><span class="sxs-lookup"><span data-stu-id="ccd12-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="ccd12-146">如果您有任何不是駐留在 Exchange 伺服器上的商務用 Skype 使用者，請勿刪除 SQL Server store 資訊。</span><span class="sxs-lookup"><span data-stu-id="ccd12-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="ccd12-147">若要儲存配置，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ccd12-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ccd12-148">您在拓撲建立器中所做的變更不會生效，除非您發佈新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ccd12-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="ccd12-149">如需詳細資訊，請參閱[在商務用 Skype Server 中新增封存資料庫至現有的部署](../../deploy/deploy-archiving/add-archiving-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd12-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="ccd12-150">使用 Windows PowerShell 變更封存資料庫的位置</span><span class="sxs-lookup"><span data-stu-id="ccd12-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="ccd12-151">在大多數情況下，您不需要變更封存資料庫的位置，這是在您安裝 [封存伺服器] 時指定的。</span><span class="sxs-lookup"><span data-stu-id="ccd12-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="ccd12-152">不過，如果發生硬體故障或其他問題，您可以使用**CsArchivingServer** Cmdlet，將存檔伺服器指向新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="ccd12-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="ccd12-153">下列範例會變更 ArchivingServer 的存檔資料庫的位置： atl-cs-001.contoso.com 封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccd12-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="ccd12-154">在這個範例中，新的資料庫位於 ArchivingDatabase： atl-sql-001.contoso.com：</span><span class="sxs-lookup"><span data-stu-id="ccd12-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


