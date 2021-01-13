---
title: 在商務用 Skype Server 中將監控報告與鏡像資料庫相關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要：瞭解如何將監控報告與商務用 Skype Server 所使用的鏡像資料庫產生關聯。
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802163"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="d9c42-103">在商務用 Skype Server 中將監控報告與鏡像資料庫相關聯</span><span class="sxs-lookup"><span data-stu-id="d9c42-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="d9c42-104">**摘要：** 瞭解如何將監控報告與商務用 Skype Server 所使用的鏡像資料庫產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d9c42-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="d9c42-105">監視含鏡像資料庫的報表</span><span class="sxs-lookup"><span data-stu-id="d9c42-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="d9c42-106">[！注意] 如果您為監控資料庫設定鏡像，則在發生容錯移轉時，鏡像資料庫將會以主資料庫的方式接管。</span><span class="sxs-lookup"><span data-stu-id="d9c42-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="d9c42-107">不過，如果您使用商務用 Skype Server 監控報告，而且發生容錯移轉，您可能會發現監控報告未連接至鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="d9c42-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="d9c42-108">這是因為，當您安裝監控報告時，只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="d9c42-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="d9c42-109">若要取得監控報告自動容錯移轉至鏡像資料庫，您必須將鏡像資料庫新增為「容錯移轉協力廠商」，以供監視報告 (一個資料庫用於通話詳細資料記錄資料，另一個用於 (經驗品質 QoE) 資料) 。</span><span class="sxs-lookup"><span data-stu-id="d9c42-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="d9c42-110"> (請注意，安裝監控報告之後，應該執行此步驟。 ) 您可以手動編輯這兩個資料庫所使用的連線字串值，以新增容錯移轉夥伴資訊。</span><span class="sxs-lookup"><span data-stu-id="d9c42-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="d9c42-111">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="d9c42-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="d9c42-112">使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。</span><span class="sxs-lookup"><span data-stu-id="d9c42-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="d9c42-113">Reporting Services 首頁 URL 包含：</span><span class="sxs-lookup"><span data-stu-id="d9c42-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="d9c42-114">**Http：** 前置詞。</span><span class="sxs-lookup"><span data-stu-id="d9c42-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="d9c42-115">安裝 Reporting Services 之電腦的完整功能變數名稱 (FQDN)  (例如， **atl-sql-001.litwareinc.com**) 。</span><span class="sxs-lookup"><span data-stu-id="d9c42-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="d9c42-116">字元字串 **/Reports_**。</span><span class="sxs-lookup"><span data-stu-id="d9c42-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="d9c42-117">安裝監視報告的資料庫實例名稱 (例如， **而 archinst**) 。</span><span class="sxs-lookup"><span data-stu-id="d9c42-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="d9c42-118">例如，如果已在電腦 atl-sql-001.litwareinc.com 上安裝 SQL Server Reporting Services，且監控報告使用資料庫實例而 archinst，則首頁 URL 會如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9c42-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="d9c42-119">存取 Reporting Services 首頁之後，請按一下 [ **ServerReports**]，然後按一下 [ **Reports_Content**]。</span><span class="sxs-lookup"><span data-stu-id="d9c42-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="d9c42-120">這將帶您前往商務用 Skype Server Monitoring Reports 的 **Reports_Content** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d9c42-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="d9c42-121">在 [ **Reports_Content** ] 頁面上，按一下 [ **CDRDB** ] 資料來源。</span><span class="sxs-lookup"><span data-stu-id="d9c42-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="d9c42-122">在 [ **CDRDB** ] 頁面的 [ **屬性** ] 索引標籤上，尋找標示為 [連線 **字串**] 的文字方塊。</span><span class="sxs-lookup"><span data-stu-id="d9c42-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="d9c42-123">目前的連接字串將如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9c42-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="d9c42-124">資料來源 = (local) \archinst; 初始目錄 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d9c42-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="d9c42-125">編輯連接字串，以包含鏡像資料庫的伺服器名稱和資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="d9c42-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="d9c42-126">例如，如果伺服器命名為 atl-001，且鏡像資料庫位於而 archinst 實例中，您將需要使用下列語法來新增以指定鏡像資料庫：</span><span class="sxs-lookup"><span data-stu-id="d9c42-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="d9c42-127">容錯移轉 Partner = atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="d9c42-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="d9c42-128">您已編輯的連接字串看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9c42-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="d9c42-129">資料來源 = (local) \archinst;容錯移轉夥伴 = atl-mirror-001\archinst; 初始目錄 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d9c42-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="d9c42-130">更新連接字串後 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="d9c42-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="d9c42-131">在 [ **CDRDB** ] 頁面上，按一下 [ **Reports_Content** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="d9c42-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="d9c42-132">按一下 [ **QMSDB** ] 資料來源，然後編輯 QoE 資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="d9c42-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="d9c42-133">例如：</span><span class="sxs-lookup"><span data-stu-id="d9c42-133">For example:</span></span>
    
    <span data-ttu-id="d9c42-134">資料來源 = (local) \archinst;容錯移轉夥伴 = atl-mirror-001\archinst; 初始目錄 = QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="d9c42-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="d9c42-135">按一下 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="d9c42-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9c42-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9c42-136">See also</span></span>

[<span data-ttu-id="d9c42-137">在商務用 Skype Server 中安裝監視報告</span><span class="sxs-lookup"><span data-stu-id="d9c42-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="d9c42-138">在商務用 Skype Server 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="d9c42-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
