---
title: 在商務用 Skype Server 2015 中規劃持續聊天伺服器的高可用性與災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中規劃持久聊天伺服器的高可用性和災難復原。'
ms.openlocfilehash: 0cdd1d17680f0546a0081bb769e2c6f45a370d0c
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194019"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8b85c-103">在商務用 Skype Server 2015 中規劃持續聊天伺服器的高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="8b85c-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8b85c-104">**摘要:** 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 中規劃持續聊天伺服器的高可用性和災難復原。</span><span class="sxs-lookup"><span data-stu-id="8b85c-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8b85c-105">持續性聊天伺服器的高可用性和災難復原需要額外的資源, 超出完整操作所需的資源。</span><span class="sxs-lookup"><span data-stu-id="8b85c-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8b85c-106">持續聊天伺服器資料庫不支援使用 SQL AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="8b85c-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8b85c-107">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="8b85c-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8b85c-108">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8b85c-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="8b85c-109">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="8b85c-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="8b85c-110">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="8b85c-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="8b85c-111">資源需求</span><span class="sxs-lookup"><span data-stu-id="8b85c-111">Resource requirements</span></span>

<span data-ttu-id="8b85c-112">在針對高可用性和災害復原設定持續聊天伺服器前, 請確定您有下列額外的資源。</span><span class="sxs-lookup"><span data-stu-id="8b85c-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="8b85c-113">一個專用的資料庫實例位於與持久性聊天伺服器服務的主前端相同的物理資料中心。</span><span class="sxs-lookup"><span data-stu-id="8b85c-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="8b85c-114">此資料庫將充當主要持久聊天資料庫的 SQL Server mirror。</span><span class="sxs-lookup"><span data-stu-id="8b85c-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="8b85c-115">或者, 如果您想要將自動容錯移轉到鏡像資料庫, 請指定額外的 SQL Server 作為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="8b85c-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="8b85c-116">一個位於另一個物理資料中心的專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="8b85c-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="8b85c-117">此資料庫將充當主要資料中心中資料庫的 SQL Server 記錄傳送次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b85c-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="8b85c-118">要作為次要資料庫之 SQL Server mirror 的一個專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="8b85c-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="8b85c-119">或者, 您也可以將其他 SQL Server 指派給伺服器做為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="8b85c-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="8b85c-120">這兩者必須位於與次要資料庫相同的物理資料中心。</span><span class="sxs-lookup"><span data-stu-id="8b85c-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="8b85c-121">如果已啟用持續聊天伺服器合規性, 則需要額外的三個專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="8b85c-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="8b85c-122">其分配與先前在持續聊天資料庫中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="8b85c-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="8b85c-123">雖然合規性資料庫可以與持久聊天資料庫共用相同的 SQL Server 實例, 但建議使用獨立實例提供高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="8b85c-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="8b85c-124">必須針對 SQL Server 記錄傳送事務記錄記錄建立並指派檔案共用。</span><span class="sxs-lookup"><span data-stu-id="8b85c-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="8b85c-125">在兩個資料中心中的所有 SQL 伺服器都執行持續聊天資料庫, 必須擁有此檔案共用的讀/寫存取權。</span><span class="sxs-lookup"><span data-stu-id="8b85c-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="8b85c-126">此共用沒有定義為 [您的顯示格式] 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b85c-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="8b85c-127">次要資料庫伺服器上的檔案共用, 可作為從主要伺服器檔案共用複製的 SQL Server 事務日誌的目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="8b85c-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="8b85c-128">災害復原與高可用性解決方案</span><span class="sxs-lookup"><span data-stu-id="8b85c-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="8b85c-129">商務用 Skype 伺服器支援後端伺服器的多種高可用性模式, 包括資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="8b85c-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="8b85c-130">如需詳細資訊, 請參閱[在商務用 Skype Server 2015 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8b85c-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="8b85c-131">本主題中所述持續聊天伺服器的災害復原解決方案是以延伸持續性聊天伺服器池為基礎。</span><span class="sxs-lookup"><span data-stu-id="8b85c-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="8b85c-132">已延伸的虛擬區域網路絡 (VLAN) 不需要。</span><span class="sxs-lookup"><span data-stu-id="8b85c-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="8b85c-133">透過拉伸持續性聊天伺服器池, 您可以將拓撲中的一個池設定成邏輯, 但實際會將伺服器放在兩個不同資料中心的池中。</span><span class="sxs-lookup"><span data-stu-id="8b85c-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="8b85c-134">您可以用相同的方式設定資料庫的 SQL Server 鏡像, 並在相同的資料中心部署資料庫和鏡像。</span><span class="sxs-lookup"><span data-stu-id="8b85c-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="8b85c-135">您需要在次要資料中心中設定備份資料庫 (在災害復原期間有選擇性的鏡像來提供高可用性)。</span><span class="sxs-lookup"><span data-stu-id="8b85c-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="8b85c-136">這是在災害復原期間用來進行容錯移轉的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b85c-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="8b85c-137">如需有關如何設定持久聊天伺服器的高可用性和災難復原的詳細資料, 請參閱[在商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災難](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)復原。</span><span class="sxs-lookup"><span data-stu-id="8b85c-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="8b85c-138">下圖顯示如何在兩個不同的延伸池拓撲中設定持續性聊天伺服器池:</span><span class="sxs-lookup"><span data-stu-id="8b85c-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="8b85c-139">當資料中心位於具有高頻寬/低延遲的地理位置時, 延伸持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="8b85c-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="8b85c-140">當資料中心位於具有低頻寬/高延遲的地理位置時, 延伸持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="8b85c-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="8b85c-141">圖1顯示延伸的持久聊天伺服器池拓撲, 其中資料中心是具有高頻寬/低延遲的地理位置。</span><span class="sxs-lookup"><span data-stu-id="8b85c-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="8b85c-142">假設下列是邏輯與物理拓朴:</span><span class="sxs-lookup"><span data-stu-id="8b85c-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="8b85c-143">邏輯拓撲包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="8b85c-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="8b85c-144">在包含伺服器1到8的網站1和2之間的持續聊天池。</span><span class="sxs-lookup"><span data-stu-id="8b85c-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="8b85c-145">前端伺服器池、持久聊天資料庫、鏡像資料庫, 以及 (您也可以選擇) 見證資料庫 (不會顯示在圖表中) 實際位於網站1。</span><span class="sxs-lookup"><span data-stu-id="8b85c-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="8b85c-146">第二個前端伺服器池, 以及實際位於網站2上的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b85c-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="8b85c-147">物理拓朴是由網站1和2組成, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8b85c-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="8b85c-148">持續式聊天池, 包含伺服器1到4、兩個作用中、兩個閒置的網站1。</span><span class="sxs-lookup"><span data-stu-id="8b85c-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="8b85c-149">持續式聊天池, 包含伺服器5到8、兩個作用中、兩個閒置的網站2。</span><span class="sxs-lookup"><span data-stu-id="8b85c-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="8b85c-150">[前端伺服器] 池、持久聊天資料庫、鏡像資料庫, 以及 (您也可以選擇) [網站 1] 上的 [見證資料庫] (未顯示在圖表中)。</span><span class="sxs-lookup"><span data-stu-id="8b85c-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="8b85c-151">前端伺服器池和備份資料庫, 也就是網站2上的 SQL 記錄傳送目標。</span><span class="sxs-lookup"><span data-stu-id="8b85c-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="8b85c-152">**當資料中心位於具有高頻寬/低延遲的地理位置時, 延伸持久聊天伺服器池**</span><span class="sxs-lookup"><span data-stu-id="8b85c-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![具有高頻寬/低延遲的持續聊天延伸池](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="8b85c-154">圖2顯示延伸的持久聊天伺服器池拓撲, 其中資料中心是具有低頻寬/高延遲的地理位置。</span><span class="sxs-lookup"><span data-stu-id="8b85c-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="8b85c-155">邏輯拓撲包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="8b85c-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="8b85c-156">在包含伺服器1到8的網站1和2之間的持續聊天池。</span><span class="sxs-lookup"><span data-stu-id="8b85c-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="8b85c-157">前端伺服器池、持久聊天資料庫、鏡像資料庫, 以及 (您也可以選擇) 見證資料庫 (不會顯示在圖表中) 實際位於網站1。</span><span class="sxs-lookup"><span data-stu-id="8b85c-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="8b85c-158">第二個前端伺服器池, 以及實際位於網站2上的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b85c-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="8b85c-159">物理拓朴是由網站1和2組成, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8b85c-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="8b85c-160">在網站1上, 包含伺服器1到 4 (所有作用中) 的持久聊天池。</span><span class="sxs-lookup"><span data-stu-id="8b85c-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="8b85c-161">在網站2上, 包含伺服器5到8的永久聊天池, 所有空閒中。</span><span class="sxs-lookup"><span data-stu-id="8b85c-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="8b85c-162">[前端伺服器] 池、持久聊天資料庫、鏡像資料庫, 以及 (您也可以選擇) [網站 1] 上的 [見證資料庫] (未顯示在圖表中)。</span><span class="sxs-lookup"><span data-stu-id="8b85c-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="8b85c-163">前端伺服器池和備份資料庫, 也就是網站2上的 SQL 記錄傳送目標。</span><span class="sxs-lookup"><span data-stu-id="8b85c-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="8b85c-164">**當資料中心位於具有低頻寬/高延遲的地理位置時, 延伸持續性聊天伺服器池**</span><span class="sxs-lookup"><span data-stu-id="8b85c-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![使用低頻寬/高延遲的持續聊天延伸池](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

