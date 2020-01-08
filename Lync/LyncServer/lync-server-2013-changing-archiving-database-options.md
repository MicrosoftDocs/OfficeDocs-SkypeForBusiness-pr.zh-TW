---
title: Lync Server 2013：變更封存資料庫選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="ed49e-102">在 Lync Server 2013 中變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="ed49e-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed49e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ed49e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ed49e-104">如果您使用 SQL Server storage 部署歸檔來儲存任何使用者的儲存空間，您可以變更下列資料庫儲存空間：</span><span class="sxs-lookup"><span data-stu-id="ed49e-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="ed49e-105">使用不同的 SQL Server 資料庫來存檔儲存空間。</span><span class="sxs-lookup"><span data-stu-id="ed49e-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="ed49e-106">這包括主要的歸檔資料庫，以及您用於 SQL Server 鏡像的任何資料庫。</span><span class="sxs-lookup"><span data-stu-id="ed49e-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="ed49e-107">切換至 Microsoft Exchange 整合，以儲存 Exchange 2013 伺服器上的封存資料和檔案。</span><span class="sxs-lookup"><span data-stu-id="ed49e-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="ed49e-108">如果您的所有使用者都是在您的 Exchange 2013 伺服器上，而您想要在部署中的所有使用者都使用 Microsoft Exchange 儲存空間，您應該從拓撲中移除 SQL Server store 資料庫。</span><span class="sxs-lookup"><span data-stu-id="ed49e-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="ed49e-109">若要進行其中一個變更，您必須執行拓撲建立器，進行變更，然後再次發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="ed49e-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="ed49e-110">您可以使用拓撲產生器來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ed49e-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="ed49e-111">請勿指定 **[封存 Sql server store** ] 或 **[啟用 sql server store 鏡像**資訊]，除非您有未駐留在 Exchange 2013 伺服器上的 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="ed49e-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="ed49e-112">變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="ed49e-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="ed49e-113">在執行 Lync Server 2013 或安裝 Lync Server 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或具有同等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="ed49e-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed49e-114">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將元件新增到拓撲中。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您用於 Lync Server 2013 檔案存放區之檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立員可以設定必要的隨機存取控制清單（Dacl），或是具有同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ed49e-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="ed49e-115">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="ed49e-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="ed49e-116">在主控台樹中，流覽至您已部署封存的 [前端] 池，然後按一下您要變更資料庫選項的前端池名稱。</span><span class="sxs-lookup"><span data-stu-id="ed49e-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="ed49e-117">在 [**動作**] 功能表中，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ed49e-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="ed49e-118">在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="ed49e-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="ed49e-119">**向下滾動至 [** 封存]。</span><span class="sxs-lookup"><span data-stu-id="ed49e-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="ed49e-120">在 [**存檔**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="ed49e-121">若要變更為不同的現有 SQL Server store，請在 [封存**Sql server store**] 下的下拉式清單方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="ed49e-122">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ed49e-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="ed49e-123">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="ed49e-124">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ed49e-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="ed49e-125">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="ed49e-126">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ed49e-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="ed49e-127">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ed49e-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="ed49e-128">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ed49e-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ed49e-129">若要新增 SQL Server store 以進行鏡像或變更為其他現有的 sql server store for SQL server store 鏡像，請選取 [**啟用 SQL Server store 鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="ed49e-130">若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。</span><span class="sxs-lookup"><span data-stu-id="ed49e-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="ed49e-131">若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="ed49e-132">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ed49e-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="ed49e-133">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ed49e-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="ed49e-134">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ed49e-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="ed49e-135">如果您啟用 SQL Server 鏡像，並想要新增或變更 SQL Server 鏡像見證（第三個是可偵測主要 SQL Server 服務器與鏡像實例之健康情況的第三個 SQL Server 實例），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ed49e-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="ed49e-136">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ed49e-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="ed49e-137">按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。</span><span class="sxs-lookup"><span data-stu-id="ed49e-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="ed49e-138">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ed49e-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ed49e-139">若要切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 2013 伺服器上（如果您部署中的所有使用者都是在您的 Exchange 2013 伺服器上託管），請刪除所有存檔資料庫的資訊。</span><span class="sxs-lookup"><span data-stu-id="ed49e-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ed49e-140">如果您有任何不是託管于 Exchange 2013 伺服器的 Lync 使用者，請勿刪除 SQL Server store 資訊。</span><span class="sxs-lookup"><span data-stu-id="ed49e-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="ed49e-141">若要儲存配置，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ed49e-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ed49e-142">您在拓撲建立器中所做的變更不會生效，除非您發佈新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ed49e-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="ed49e-143">如需詳細資訊，請參閱發佈更新後的拓撲，以在部署檔的<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Lync Server 2013 中新增封存資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="ed49e-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

