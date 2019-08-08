---
title: 在商務用 Skype Server 中將監控報告與鏡像資料庫建立關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '摘要: 瞭解如何將監視報告與商務用 Skype 伺服器所使用的鏡像資料庫建立關聯。'
ms.openlocfilehash: 522ed5f9bd6e437a83e9cb3575ca92c0bd049e44
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239884"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="16399-103">在商務用 Skype Server 中將監控報告與鏡像資料庫建立關聯</span><span class="sxs-lookup"><span data-stu-id="16399-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="16399-104">**摘要:** 瞭解如何將監視報告與商務用 Skype 伺服器所使用的鏡像資料庫建立關聯。</span><span class="sxs-lookup"><span data-stu-id="16399-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="16399-105">使用鏡像資料庫監控報表</span><span class="sxs-lookup"><span data-stu-id="16399-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="16399-106">如果您為監視資料庫設定鏡像, 則在發生容錯移轉時, 鏡像資料庫將會作為主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="16399-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="16399-107">不過, 如果您使用商務用 Skype Server Monitoring 報告, 且發生容錯移轉, 您可能會發現監視報告無法連線到鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="16399-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="16399-108">這是因為, 當您安裝監視報告時, 只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="16399-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="16399-109">若要取得監視報告以自動容錯移轉到鏡像資料庫, 您必須將鏡像資料庫新增為「容錯移轉夥伴」, 以供監視報告所使用的兩個資料庫 (一個資料庫用於呼叫詳細資料記錄資料, 另一個資料庫的品質為體驗 (QoE) 資料)。</span><span class="sxs-lookup"><span data-stu-id="16399-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="16399-110">(請注意, 在您安裝監控報告之後, 應該執行此步驟)。您可以手動編輯這兩個資料庫所使用的連線字串值, 以新增容錯移轉合作夥伴資訊。</span><span class="sxs-lookup"><span data-stu-id="16399-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="16399-111">若要這樣做, 請完成下列程式:</span><span class="sxs-lookup"><span data-stu-id="16399-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="16399-112">使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。</span><span class="sxs-lookup"><span data-stu-id="16399-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="16399-113">[報表服務] 首頁 URL 包括:</span><span class="sxs-lookup"><span data-stu-id="16399-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="16399-114">[ **Http:** prefix]。</span><span class="sxs-lookup"><span data-stu-id="16399-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="16399-115">安裝 Reporting Services 的電腦的完整功能變數名稱 (FQDN) (例如, **atl-sql-001.litwareinc.com**)。</span><span class="sxs-lookup"><span data-stu-id="16399-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="16399-116">字元字串 **/Reports_**。</span><span class="sxs-lookup"><span data-stu-id="16399-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="16399-117">安裝監視報告的資料庫實例名稱 (例如, **archinst**)。</span><span class="sxs-lookup"><span data-stu-id="16399-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="16399-118">例如, 如果 SQL Server Reporting Services 已安裝在電腦 atl-sql-001.litwareinc.com 上, 而監視報告使用資料庫實例 archinst, 則首頁 URL 看起來會像這樣:</span><span class="sxs-lookup"><span data-stu-id="16399-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="16399-119">在您存取完 [報表服務] 首頁之後, 按一下 [ **ServerReports**], 然後按一下 [ **Reports_Content**]。</span><span class="sxs-lookup"><span data-stu-id="16399-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="16399-120">這會將您帶到商務用 Skype Server 監視報告的**Reports_Content**頁面。</span><span class="sxs-lookup"><span data-stu-id="16399-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="16399-121">在 [ **Reports_Content** ] 頁面上, 按一下 [ **CDRDB**資料來源]。</span><span class="sxs-lookup"><span data-stu-id="16399-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="16399-122">在 [ **CDRDB** ] 頁面的 [**屬性**] 索引標籤上, 尋找標示為 [**連接字串**] 的文字方塊。</span><span class="sxs-lookup"><span data-stu-id="16399-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="16399-123">目前的連接字串看起來會像這樣:</span><span class="sxs-lookup"><span data-stu-id="16399-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="16399-124">資料來源 = (local) \archinst; 初始目錄 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="16399-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="16399-125">編輯連接字串, 以包含鏡像資料庫的伺服器名稱和資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="16399-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="16399-126">例如, 如果伺服器已命名為 atl-001 且鏡像資料庫位於 archinst 實例中, 您將需要新增才能使用下列語法來指定鏡像資料庫:</span><span class="sxs-lookup"><span data-stu-id="16399-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="16399-127">容錯移轉合作夥伴 = atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="16399-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="16399-128">您編輯的連線字串看起來會像這樣:</span><span class="sxs-lookup"><span data-stu-id="16399-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="16399-129">資料來源 = (local) \archinst;容錯移轉合作夥伴 = atl-mirror-001\archinst; 初始目錄 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="16399-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="16399-130">更新連接字串之後, 按一下 [ \*\*\*\* 套用]。</span><span class="sxs-lookup"><span data-stu-id="16399-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="16399-131">在 [ **CDRDB** ] 頁面上, 按一下 [ **Reports_Content** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="16399-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="16399-132">按一下 [ **QMSDB**資料來源], 然後編輯 QoE 資料庫的連線字串。</span><span class="sxs-lookup"><span data-stu-id="16399-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="16399-133">例如：</span><span class="sxs-lookup"><span data-stu-id="16399-133">For example:</span></span>
    
    <span data-ttu-id="16399-134">資料來源 = (local) \archinst;容錯移轉合作夥伴 = atl-mirror-001\archinst; 初始目錄 = QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="16399-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="16399-135">按一下\*\*\*\*[套用]。</span><span class="sxs-lookup"><span data-stu-id="16399-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="16399-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="16399-136">See also</span></span>

[<span data-ttu-id="16399-137">在商務用 Skype Server 中安裝監視報告</span><span class="sxs-lookup"><span data-stu-id="16399-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="16399-138">在商務用 Skype Server 中使用監視報告</span><span class="sxs-lookup"><span data-stu-id="16399-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
