---
title: Lync Server 2013： 變更封存資料庫選項
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
ms.openlocfilehash: 9797aa794574180727549b7191a48a085aeb6d59
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="70a5a-102">Lync Server 2013 中的變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="70a5a-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70a5a-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="70a5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="70a5a-104">如果您部署的任何使用者的封存儲存區中使用 SQL Server 儲存區的封存，您可以在儲存變更時進行下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="70a5a-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="70a5a-105">封存存放區使用不同的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="70a5a-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="70a5a-106">這包括主要封存資料庫與您使用 SQL Server 鏡像的任何資料庫。</span><span class="sxs-lookup"><span data-stu-id="70a5a-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="70a5a-107">切換到 [Microsoft Exchange 整合來儲存封存資料和 Exchange 2013 伺服器上的檔案。</span><span class="sxs-lookup"><span data-stu-id="70a5a-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="70a5a-108">如果您的所有使用者都位於您的 Exchange 2013 伺服器，而且您想要使用 Microsoft Exchange 儲存區中部署的所有使用者，您應該從拓撲移除 SQL Server 儲存區資料庫。</span><span class="sxs-lookup"><span data-stu-id="70a5a-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="70a5a-109">若要讓這些變更其中一項，您必須執行拓撲產生器、 進行的變更，並再一次發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="70a5a-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="70a5a-110">若要這麼做，您可以使用拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="70a5a-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="70a5a-111">除非您有不位於 Exchange 2013 伺服器的 Lync 使用者未指定**封存 SQL Server 儲存區**，或**啟用 SQL Server 儲存區鏡像**資訊。</span><span class="sxs-lookup"><span data-stu-id="70a5a-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="70a5a-112">變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="70a5a-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="70a5a-113">在電腦上，執行 Lync Server 2013 中，或 Lync Server 系統管理工具安裝，登入使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="70a5a-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70a5a-114">您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要元件新增至拓撲，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且您使用 Lync Server 2013 檔案存放區 （亦即，以便拓撲產生器可以設定必要的判別存取控制清單 （在檔案共用上具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶Dacl)，或具有相等的權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="70a5a-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="70a5a-115">啟動拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="70a5a-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="70a5a-116">在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="70a5a-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="70a5a-117">在 [動作]\*\*\*\* 功能表上，按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a5a-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="70a5a-118">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="70a5a-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="70a5a-119">向下捲動至 **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="70a5a-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="70a5a-120">在 **[封存]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="70a5a-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="70a5a-121">如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區]\*\*\*\* 的下拉式清單方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="70a5a-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="70a5a-122">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="70a5a-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="70a5a-123">如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="70a5a-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="70a5a-124">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="70a5a-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="70a5a-125">若要指定新的 SQL Server 儲存區，按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="70a5a-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="70a5a-126">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="70a5a-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="70a5a-127">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="70a5a-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="70a5a-128">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="70a5a-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="70a5a-129">如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="70a5a-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="70a5a-130">若要使用現有的 SQL Server 儲存區作為鏡像，在 [**封存 SQL Server 儲存區鏡像**] 下拉式清單方塊中，按一下您想要用於鏡像的 SQL Server 存放區的名稱。</span><span class="sxs-lookup"><span data-stu-id="70a5a-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="70a5a-131">若要指定新的 SQL Server 儲存區作為鏡像，請按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="70a5a-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="70a5a-132">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的 SQL server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="70a5a-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="70a5a-133">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="70a5a-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="70a5a-134">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="70a5a-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="70a5a-135">如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 （第三個，個別的 SQL Server 執行個體，可偵測主要 SQL Server 伺服器的健康狀況和鏡像執行個體），選取 [**使用 SQL Server 鏡像見證啟用自動容錯移轉**] 核取方塊，，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="70a5a-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="70a5a-136">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 鏡像見證伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="70a5a-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="70a5a-137">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="70a5a-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="70a5a-138">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="70a5a-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="70a5a-139">若要切換至 Microsoft Exchange 整合來儲存封存資料和 Exchange 2013 伺服器 （如果您在部署中的所有使用者都位於您的 Exchange 2013 伺服器） 上的檔案，請刪除封存資料庫的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="70a5a-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="70a5a-140">如果您有任何不位於 Exchange 2013 伺服器的 Lync 使用者時，請勿刪除 SQL Server 存放區資訊。</span><span class="sxs-lookup"><span data-stu-id="70a5a-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="70a5a-141">如要儲存設定，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="70a5a-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="70a5a-142">在拓撲產生器所進行的變更才會生效直到您發佈新拓撲。</span><span class="sxs-lookup"><span data-stu-id="70a5a-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="70a5a-143">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">發佈更新過的拓撲，以新增 Lync Server 2013 中的封存資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="70a5a-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

