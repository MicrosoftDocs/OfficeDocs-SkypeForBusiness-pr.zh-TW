---
title: Lync Server 2013： 建立與鏡像資料庫的關聯監控報告
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
ms.openlocfilehash: 82d1ec6b1256326cca9e74d47d27820529050721
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="ac93c-102">與 Lync Server 2013 的鏡像資料庫建立關聯監控報告</span><span class="sxs-lookup"><span data-stu-id="ac93c-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac93c-103">_**上次修改主題：** 2014年-02-07_</span><span class="sxs-lookup"><span data-stu-id="ac93c-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ac93c-104">如果您設定監控資料庫鏡像，該鏡像資料庫會接管主要資料庫如果發生容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="ac93c-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="ac93c-105">不過，如果您使用 Lync Server 監控報告，並發生容錯移轉，您可能會發現監視報告不會連線至鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="ac93c-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="ac93c-106">這是因為當您安裝監控報告，您會指定位置的主要資料庫;您不指定之鏡像資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="ac93c-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="ac93c-107">若要取得自動容錯移轉至鏡像資料庫的監控報告，您必須新增鏡像資料庫為 「 容錯移轉夥伴 」 至兩個資料庫所使用的監控報告 （一個資料庫的通話詳細記錄資料，以及另一個用於品質經驗 (QoE) 資料）。</span><span class="sxs-lookup"><span data-stu-id="ac93c-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="ac93c-108">（請注意安裝監控報告之後，應該執行此步驟）。您可以新增的容錯移轉夥伴資訊以手動方式編輯這兩個資料庫所使用的連接字串值。</span><span class="sxs-lookup"><span data-stu-id="ac93c-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="ac93c-109">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="ac93c-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="ac93c-110">若要開啟 [ **SQL Server Reporting Services**首頁] 頁面上使用 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="ac93c-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="ac93c-111">Reporting Services 首頁的 URL 包括：</span><span class="sxs-lookup"><span data-stu-id="ac93c-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="ac93c-112">**Http:** 前置詞。</span><span class="sxs-lookup"><span data-stu-id="ac93c-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="ac93c-113">Reporting Services （例如， **atl-cs-sql-001.litwareinc.com**） 的安裝所在之電腦的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ac93c-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="ac93c-114">字元字串 **/報告\_**。</span><span class="sxs-lookup"><span data-stu-id="ac93c-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="ac93c-115">監控報告 （例如， **archinst**） 的安裝所在的資料庫執行個體名稱。</span><span class="sxs-lookup"><span data-stu-id="ac93c-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="ac93c-116">例如，如果電腦 atl-cs-001.litwareinc.com sql-001.litwareinc.com 上都安裝 SQL Server Reporting Services 和監控報告使用資料庫執行個體 archinst，首頁的 URL 看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="ac93c-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="ac93c-117">存取 [Reporting Services 首頁] 頁面之後，按一下 [ **LyncServerReports**，和 [**報告\_內容**。</span><span class="sxs-lookup"><span data-stu-id="ac93c-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="ac93c-118">會將帶您至**報告\_內容**的 Lync Server 監控報告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ac93c-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="ac93c-119">在**報告\_內容**] 頁面上，按一下 [ **CDRDB**資料來源。</span><span class="sxs-lookup"><span data-stu-id="ac93c-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="ac93c-120">在 [ **CDRDB** ] 頁面上的 [**屬性**] 索引標籤上尋找 [標示為**連接字串**] 文字方塊。</span><span class="sxs-lookup"><span data-stu-id="ac93c-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="ac93c-121">目前的連接字串看起來類似這樣：</span><span class="sxs-lookup"><span data-stu-id="ac93c-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="ac93c-122">**資料 source=(local)\\archinst; 初始目錄 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="ac93c-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="ac93c-123">編輯若要包含之鏡像資料庫的伺服器名稱及資料庫執行個體的連接字串。</span><span class="sxs-lookup"><span data-stu-id="ac93c-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="ac93c-124">例如，如果伺服器名為 atl-cs-001.litwareinc.com-鏡像-001 和鏡像資料庫處於 archinst 執行個體，您必須將新增至指定的鏡像資料庫，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ac93c-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="ac93c-125">**容錯移轉夥伴 = atl-鏡像-001\\archinst**</span><span class="sxs-lookup"><span data-stu-id="ac93c-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="ac93c-126">您已編輯的連接字串看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="ac93c-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="ac93c-127">**資料 source=(local)\\archinst;容錯移轉夥伴 = atl-鏡像-001\\archinst; 初始目錄 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="ac93c-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="ac93c-128">更新後的連接字串，按一下 [**套用**]。</span><span class="sxs-lookup"><span data-stu-id="ac93c-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="ac93c-129">在 [ **CDRDB** ] 頁面上，按一下 [**報告\_內容**連結。</span><span class="sxs-lookup"><span data-stu-id="ac93c-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="ac93c-130">按一下**QMSDB**資料來源]，然後編輯 QoE 資料庫連線字串。</span><span class="sxs-lookup"><span data-stu-id="ac93c-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="ac93c-131">例如：</span><span class="sxs-lookup"><span data-stu-id="ac93c-131">For example:</span></span>
    
    <span data-ttu-id="ac93c-132">**資料 source=(local)\\archinst;容錯移轉夥伴 = atl-鏡像-001\\archinst; 初始目錄 = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="ac93c-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="ac93c-133">按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac93c-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ac93c-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac93c-134">See Also</span></span>


[<span data-ttu-id="ac93c-135">安裝 Lync Server 2013 監控報告</span><span class="sxs-lookup"><span data-stu-id="ac93c-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="ac93c-136">Lync Server 2013 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="ac93c-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

