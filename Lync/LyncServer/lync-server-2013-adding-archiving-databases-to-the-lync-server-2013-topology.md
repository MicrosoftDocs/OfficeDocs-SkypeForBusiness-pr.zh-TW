---
title: Lync Server 2013： 將封存資料庫新增至 Lync Server 2013 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d6f4ff4b3881f9dfbd4707d2956aa738b9a375
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="b84c7-102">將封存資料庫新增至 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="b84c7-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b84c7-103">_**主題上次修改日期：** 2012年-10-10_</span><span class="sxs-lookup"><span data-stu-id="b84c7-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b84c7-104">您必須先將封存納入拓撲中，才能設定部署來支援封存。</span><span class="sxs-lookup"><span data-stu-id="b84c7-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="b84c7-105">本主題中的資訊說明如何使用拓撲產生器來新增封存至您現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b84c7-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b84c7-106">如果您想要用於封存資料和 Exchange 2013 伺服器上的所有使用者的檔案儲存在您部署 Microsoft Exchange 整合，未指定<STRONG>封存 SQL Server 儲存區</STRONG>，或<STRONG>使用 SQL Server 儲存區鏡像</STRONG>的資訊。</span><span class="sxs-lookup"><span data-stu-id="b84c7-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="b84c7-107">新增封存資料庫支援至拓撲</span><span class="sxs-lookup"><span data-stu-id="b84c7-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="b84c7-108">在電腦上，執行 Lync Server 2013 中，或 Lync Server 系統管理工具安裝，登入使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="b84c7-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b84c7-109">您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要的伺服器新增至拓撲，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且您使用 Lync Server 2013 檔案存放區 （亦即，以便拓撲產生器可以設定必要的判別存取控制清單 (Dacl) 的檔案共用具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶或具有相等的權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b84c7-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="b84c7-110">啟動拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="b84c7-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="b84c7-111">在主控台樹狀目錄中，瀏覽至要部署封存的前端集區，然後按一下要部署封存的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="b84c7-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="b84c7-112">在 [動作]\*\*\*\* 功能表中，按一下 [編輯內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b84c7-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="b84c7-113">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="b84c7-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="b84c7-114">向下捲動至 [封存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b84c7-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="b84c7-115">選取 [封存]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b84c7-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="b84c7-116">在 [**封存 SQL Server 儲存區，** 執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b84c7-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="b84c7-117">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="b84c7-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="b84c7-118">如果您的所有使用者位於 Microsoft Exchange Server 2013 或上方，您可以為所有使用者在 Exchange 中封存 Lync 通訊。</span><span class="sxs-lookup"><span data-stu-id="b84c7-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="b84c7-119">在此情況下，您不需要設定 SQL Server 封存存放區。</span><span class="sxs-lookup"><span data-stu-id="b84c7-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="b84c7-120">若要指定新的 SQL Server 儲存區，按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b84c7-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="b84c7-121">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b84c7-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="b84c7-122">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b84c7-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="b84c7-123">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="b84c7-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="b84c7-124">如果您想要使用 SQL Server 儲存區鏡像，選取 [**啟用 SQL Server 儲存區鏡像**，，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b84c7-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="b84c7-125">若要使用現有的 SQL Server 儲存區作為鏡像，在 [**封存 SQL Server 儲存區鏡像**] 下拉式清單方塊中，按一下您想要用於鏡像的 SQL Server 存放區的名稱。</span><span class="sxs-lookup"><span data-stu-id="b84c7-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="b84c7-126">若要指定新的 SQL Server 儲存區作為鏡像，請按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b84c7-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="b84c7-127">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的 SQL server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b84c7-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="b84c7-128">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b84c7-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="b84c7-129">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="b84c7-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="b84c7-130">如果您啟用 SQL Server 鏡像，並想要包含 SQL Server 鏡像見證 （第三個，個別的 SQL Server 執行個體，可偵測主要 SQL Server 伺服器的健康狀況和鏡像執行個體），選取 [**使用 SQL Server 鏡像見證啟用自動容錯移轉**] 核取方塊，，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b84c7-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="b84c7-131">在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 鏡像見證伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b84c7-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="b84c7-132">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b84c7-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="b84c7-133">如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="b84c7-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="b84c7-134">若要儲存設定，請按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b84c7-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

