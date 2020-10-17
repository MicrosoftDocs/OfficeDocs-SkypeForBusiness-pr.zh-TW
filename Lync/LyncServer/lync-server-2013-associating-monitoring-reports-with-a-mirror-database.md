---
title: Lync Server 2013：將監控報告與鏡像資料庫相關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655c6ec788b934a533295fee577e72febb7818de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527100"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="576a4-102">在 Lync Server 2013 中將監控報告與鏡像資料庫相關聯</span><span class="sxs-lookup"><span data-stu-id="576a4-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576a4-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="576a4-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="576a4-104">[！注意] 如果您為監控資料庫設定鏡像，則在發生容錯移轉時，鏡像資料庫將會以主資料庫的方式接管。</span><span class="sxs-lookup"><span data-stu-id="576a4-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="576a4-105">不過，如果您使用 Lync Server 監控報告，而且發生容錯移轉，您可能會發現監控報告未連接至鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="576a4-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="576a4-106">這是因為，當您安裝監控報告時，只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="576a4-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="576a4-107">若要取得監控報告自動容錯移轉至鏡像資料庫，您必須將鏡像資料庫新增為「容錯移轉協力廠商」，以供監視報告 (一個資料庫用於通話詳細資料記錄資料，另一個用於 (經驗品質 QoE) 資料) 。</span><span class="sxs-lookup"><span data-stu-id="576a4-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="576a4-108"> (請注意，安裝監控報告之後，應該執行此步驟。 ) 您可以手動編輯這兩個資料庫所使用的連線字串值，以新增容錯移轉夥伴資訊。</span><span class="sxs-lookup"><span data-stu-id="576a4-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="576a4-109">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="576a4-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="576a4-110">使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。</span><span class="sxs-lookup"><span data-stu-id="576a4-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="576a4-111">Reporting Services 首頁 URL 包含：</span><span class="sxs-lookup"><span data-stu-id="576a4-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="576a4-112">**Http：** 前置詞。</span><span class="sxs-lookup"><span data-stu-id="576a4-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="576a4-113">安裝 Reporting Services 之電腦的完整功能變數名稱 (FQDN)  (例如， **atl-sql-001.litwareinc.com**) 。</span><span class="sxs-lookup"><span data-stu-id="576a4-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="576a4-114">字元字串 \*\*/Reports \_ \*\*。</span><span class="sxs-lookup"><span data-stu-id="576a4-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="576a4-115">安裝監視報告的資料庫實例名稱 (例如， **而 archinst**) 。</span><span class="sxs-lookup"><span data-stu-id="576a4-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="576a4-116">例如，如果已在電腦 atl-sql-001.litwareinc.com 上安裝 SQL Server Reporting Services，且監控報告使用資料庫實例而 archinst，則首頁 URL 會如下所示：</span><span class="sxs-lookup"><span data-stu-id="576a4-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="576a4-117">存取 Reporting Services 首頁之後，請按一下 [ **LyncServerReports**]，然後按一下 [ **報表 \_ 內容**]。</span><span class="sxs-lookup"><span data-stu-id="576a4-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="576a4-118">這將帶您前往 Lync Server Monitoring Reports 的「 **報告 \_ 內容** 」頁面。</span><span class="sxs-lookup"><span data-stu-id="576a4-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="576a4-119">在 [ **報告 \_ 內容** ] 頁面上，按一下 [ **CDRDB** ] 資料來源。</span><span class="sxs-lookup"><span data-stu-id="576a4-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="576a4-120">在 [ **CDRDB** ] 頁面的 [ **屬性** ] 索引標籤上，尋找標示為 [連線 **字串**] 的文字方塊。</span><span class="sxs-lookup"><span data-stu-id="576a4-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="576a4-121">目前的連接字串將如下所示：</span><span class="sxs-lookup"><span data-stu-id="576a4-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="576a4-122">**資料來源 = (local) \\ 而 archinst; 初始目錄 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="576a4-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="576a4-123">編輯連接字串，以包含鏡像資料庫的伺服器名稱和資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="576a4-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="576a4-124">例如，如果伺服器命名為 atl-001，且鏡像資料庫位於而 archinst 實例中，您將需要使用下列語法來新增以指定鏡像資料庫：</span><span class="sxs-lookup"><span data-stu-id="576a4-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="576a4-125">**容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst**</span><span class="sxs-lookup"><span data-stu-id="576a4-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="576a4-126">您已編輯的連接字串看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="576a4-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="576a4-127">**資料來源 = (local) \\ 而 archinst;容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst; 初始目錄 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="576a4-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="576a4-128">更新連接字串後 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="576a4-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="576a4-129">在 [ **CDRDB** ] 頁面上，按一下 [ **報表 \_ 內容** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="576a4-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="576a4-130">按一下 [ **QMSDB** ] 資料來源，然後編輯 QoE 資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="576a4-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="576a4-131">例如：</span><span class="sxs-lookup"><span data-stu-id="576a4-131">For example:</span></span>
    
    <span data-ttu-id="576a4-132">**資料來源 = (local) \\ 而 archinst;容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst; 初始目錄 = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="576a4-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="576a4-133">按一下 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="576a4-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="576a4-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="576a4-134">See Also</span></span>


[<span data-ttu-id="576a4-135">安裝 Lync Server 2013 監控報告</span><span class="sxs-lookup"><span data-stu-id="576a4-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="576a4-136">在 Lync Server 2013 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="576a4-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

