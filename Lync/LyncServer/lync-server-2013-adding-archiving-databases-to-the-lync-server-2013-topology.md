---
title: Lync Server 2013：將封存資料庫新增至 Lync Server 2013 拓撲
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
ms.openlocfilehash: ebc2f06e6e3fa2646989e4697354c71f7f0249da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521390"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="57639-102">將封存資料庫新增至 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="57639-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57639-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="57639-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="57639-104">您必須先將封存納入拓撲中，才能設定部署來支援封存。</span><span class="sxs-lookup"><span data-stu-id="57639-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="57639-105">本主題中的資訊說明如何使用拓撲產生器，將封存新增至現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="57639-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57639-106">若要使用 Microsoft Exchange 整合將封存資料和檔案儲存在部署中的所有使用者的 Exchange 2013 伺服器上，請勿指定「封存 <STRONG>Sql server 儲存區</STRONG> 」或「 <STRONG>使用 SQL server 儲存區鏡像</STRONG> 資訊」。</span><span class="sxs-lookup"><span data-stu-id="57639-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="57639-107">新增封存資料庫支援至拓撲</span><span class="sxs-lookup"><span data-stu-id="57639-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="57639-108">在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="57639-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57639-109">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將伺服器新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的自由存取控制清單 (dacl) ，或具有同等 (權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="57639-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="57639-110">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="57639-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="57639-111">在主控台樹狀目錄中，瀏覽至要部署封存的前端集區，然後按一下要部署封存的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="57639-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="57639-112">在 [動作]\*\*\*\* 功能表中，按一下 [編輯內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57639-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="57639-113">在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。</span><span class="sxs-lookup"><span data-stu-id="57639-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="57639-114">向下捲動至 [封存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57639-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="57639-115">選取 [封存]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57639-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="57639-116">在 **[封存 SQL Server 儲存區** ] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="57639-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="57639-117">如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="57639-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="57639-118">如果您的所有使用者都位於 Microsoft Exchange Server 2013 或更新版本，您可以在 Exchange 中封存所有使用者的 Lync 通訊。</span><span class="sxs-lookup"><span data-stu-id="57639-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="57639-119">在此情況下，您不需要設定 SQL Server 封存儲存區。</span><span class="sxs-lookup"><span data-stu-id="57639-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="57639-120">若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57639-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="57639-121">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="57639-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="57639-122">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="57639-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="57639-123">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="57639-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="57639-124">若要使用 SQL Server 儲存區鏡像，請選取 **[啟用 Sql Server 儲存區鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57639-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="57639-125">若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。</span><span class="sxs-lookup"><span data-stu-id="57639-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="57639-126">若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="57639-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="57639-127">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="57639-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="57639-128">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。</span><span class="sxs-lookup"><span data-stu-id="57639-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="57639-129">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="57639-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="57639-130">如果您啟用 SQL Server 鏡像，而且想要包含 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="57639-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="57639-131">在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="57639-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="57639-132">按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。</span><span class="sxs-lookup"><span data-stu-id="57639-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="57639-133">如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="57639-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="57639-134">若要儲存設定，請按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57639-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

