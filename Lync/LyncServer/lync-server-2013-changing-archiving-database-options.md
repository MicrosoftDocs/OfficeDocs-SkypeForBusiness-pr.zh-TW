---
title: Lync Server 2013：變更封存資料庫選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f06b1327b1f0718015de0a877963ad7eb04cc03c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502710"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="e950b-102">在 Lync Server 2013 中變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="e950b-102">Changing Archiving database options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e950b-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e950b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e950b-104">如果您使用 SQL Server storage 部署封存，以封存任何使用者的儲存體，您可以進行下列資料庫儲存變更：</span><span class="sxs-lookup"><span data-stu-id="e950b-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="e950b-105">使用不同的 SQL Server 資料庫來封存儲存體。</span><span class="sxs-lookup"><span data-stu-id="e950b-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="e950b-106">這包括主要封存資料庫和您用來進行 SQL Server 鏡像的任何資料庫。</span><span class="sxs-lookup"><span data-stu-id="e950b-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="e950b-107">切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 2013 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e950b-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="e950b-108">如果您的所有使用者都位於 Exchange 2013 伺服器上，而您想要將 Microsoft Exchange storage 用於部署中的所有使用者，則應該從拓撲中移除 SQL Server 儲存區資料庫。</span><span class="sxs-lookup"><span data-stu-id="e950b-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="e950b-109">若要進行這項變更，您必須執行拓撲產生器、進行變更，然後重新發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="e950b-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="e950b-110">您可以使用拓撲產生器來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="e950b-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="e950b-111">除非您的 Lync 使用者不是位於 Exchange 2013 伺服器上，否則請勿指定封存 **Sql server 儲存區** 或 **啟用 SQL server 儲存區鏡像** 資訊。</span><span class="sxs-lookup"><span data-stu-id="e950b-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="e950b-112">變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="e950b-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="e950b-113">在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e950b-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e950b-114">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將元件新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync Server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由存取控制清單 (dacl) ，或具有 (同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e950b-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="e950b-115">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="e950b-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="e950b-116">在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="e950b-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="e950b-117">在 [動作]\*\*\*\* 功能表上，按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e950b-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="e950b-118">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="e950b-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="e950b-119">向下捲動至 **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="e950b-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="e950b-120">在 **[封存]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e950b-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="e950b-121">如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區]\*\*\*\* 的下拉式清單方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e950b-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="e950b-122">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="e950b-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="e950b-123">如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e950b-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="e950b-124">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="e950b-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="e950b-125">若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e950b-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="e950b-126">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e950b-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="e950b-127">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="e950b-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="e950b-128">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="e950b-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="e950b-129">如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e950b-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="e950b-130">若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="e950b-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="e950b-131">若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e950b-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="e950b-132">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e950b-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="e950b-133">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="e950b-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="e950b-134">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="e950b-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="e950b-135">如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e950b-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="e950b-136">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e950b-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="e950b-137">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="e950b-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="e950b-138">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="e950b-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="e950b-139">若要切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 2013 伺服器上 (如果您部署中的所有使用者都位於 Exchange 2013 伺服器) 上，請刪除封存資料庫的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="e950b-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e950b-140">如果您有任何 Lync 使用者不是位於 Exchange 2013 伺服器上，請勿刪除 SQL Server 儲存區資訊。</span><span class="sxs-lookup"><span data-stu-id="e950b-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="e950b-141">如要儲存設定，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e950b-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e950b-142">在您發佈新的拓撲之前，您在拓撲產生器中所做的變更不會生效。</span><span class="sxs-lookup"><span data-stu-id="e950b-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="e950b-143">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">發行更新的拓撲以在 Lync Server 2013 中新增封存資料庫</A> 。</span><span class="sxs-lookup"><span data-stu-id="e950b-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

