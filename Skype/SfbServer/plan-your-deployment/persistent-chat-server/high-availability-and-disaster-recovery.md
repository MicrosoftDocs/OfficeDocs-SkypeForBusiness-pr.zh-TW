---
title: 在商務用 Skype Server 2015 中規劃持久聊天伺服器的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃持久聊天伺服器的高可用性和嚴重損壞修復。
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832353"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="0b889-103">在商務用 Skype Server 2015 中規劃持久聊天伺服器的高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="0b889-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0b889-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃持久聊天伺服器的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="0b889-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0b889-105">Persistent Chat Server 的高可用性和嚴重損壞復原需要額外的資源，以超出完整作業的一般需求。</span><span class="sxs-lookup"><span data-stu-id="0b889-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0b889-106">Persistent Chat Server 資料庫不支援使用 SQL AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="0b889-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0b889-107">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="0b889-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0b889-108">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="0b889-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="0b889-109">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="0b889-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="0b889-110">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="0b889-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="0b889-111">資源需求</span><span class="sxs-lookup"><span data-stu-id="0b889-111">Resource requirements</span></span>

<span data-ttu-id="0b889-112">設定持久聊天伺服器以取得高可用性和嚴重損壞修復之前，請先確定您有下列額外資源。</span><span class="sxs-lookup"><span data-stu-id="0b889-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="0b889-113">一個專用的資料庫實例位於 Persistent Chat Server 服務的主前端所在的相同實體資料中心。</span><span class="sxs-lookup"><span data-stu-id="0b889-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="0b889-114">此資料庫會做為主要持久聊天資料庫的 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="0b889-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="0b889-115">（選用）如果您想要自動容錯移轉至鏡像資料庫，請指定其他 SQL Server 作為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="0b889-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="0b889-116">一個位於其他實體資料中心的專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="0b889-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="0b889-117">此資料庫會做為主要資料中心資料庫的 SQL Server 記錄傳送次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="0b889-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="0b889-118">一個專用的資料庫實例充當次要資料庫的 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="0b889-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="0b889-119">（選用）將另一部 SQL Server 指定給伺服器做為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="0b889-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="0b889-120">這兩者都必須與次要資料庫位於相同的實體資料中心。</span><span class="sxs-lookup"><span data-stu-id="0b889-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="0b889-121">如果啟用 Persistent Chat Server 相容性，則需要額外三個專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="0b889-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="0b889-122">其分配與先前對 Persistent 聊天資料庫所述的方式相同。</span><span class="sxs-lookup"><span data-stu-id="0b889-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="0b889-123">規範資料庫可以與 Persistent Chat 資料庫共用相同的 SQL Server 實例，但建議使用獨立的高可用性和嚴重損壞修復實例。</span><span class="sxs-lookup"><span data-stu-id="0b889-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="0b889-124">必須為 SQL Server 記錄傳送交易記錄檔建立及指定檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0b889-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="0b889-125">執行持續性聊天資料庫之資料中心內的所有 SQL Server，都必須具有此檔案共用的讀取/寫入權限。</span><span class="sxs-lookup"><span data-stu-id="0b889-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="0b889-126">此共用並未定義為 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b889-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="0b889-127">輔助資料庫伺服器上的檔案共用，用作從主要伺服器檔案共用複製之 SQL Server 交易記錄檔的目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="0b889-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="0b889-128">嚴重損壞修復和高可用性解決方案</span><span class="sxs-lookup"><span data-stu-id="0b889-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="0b889-129">商務用 Skype 伺服器支援多種模式的後端伺服器（包括資料庫鏡像）高可用性。</span><span class="sxs-lookup"><span data-stu-id="0b889-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="0b889-130">如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0b889-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="0b889-131">本主題中所述 Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。</span><span class="sxs-lookup"><span data-stu-id="0b889-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="0b889-132">不需要延伸虛擬區域網路絡 (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="0b889-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="0b889-133">透過拉伸一種 Persistent Chat Server 集區，您可以在不同的拓撲中設定一個集區，但您實際將伺服器集區中的伺服器放在兩個不同的資料中心。</span><span class="sxs-lookup"><span data-stu-id="0b889-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="0b889-134">您可以以相同的方式設定資料庫的 SQL Server 鏡像，並在相同的資料中心內部署資料庫和鏡像。</span><span class="sxs-lookup"><span data-stu-id="0b889-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="0b889-135">您必須在次要資料中心設定備份資料庫 (包含於災害復原期間提供高可用性的選用鏡像)。</span><span class="sxs-lookup"><span data-stu-id="0b889-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="0b889-136">此為在災害復原期間用於容錯移轉的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="0b889-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="0b889-137">如需如何為 Persistent Chat Server 設定高可用性和嚴重損壞修復的詳細資訊，請參閱 [在商務用 Skype server 2015 中設定 Persistent Chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="0b889-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="0b889-138">下圖顯示可在兩個不同的延伸集區拓撲中設定 Persistent Chat Server 集區的方式：</span><span class="sxs-lookup"><span data-stu-id="0b889-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="0b889-139">當資料中心具有高頻寬/低延遲時，延伸的持久聊天伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="0b889-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="0b889-140">資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="0b889-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="0b889-141">圖1顯示連續的持久聊天伺服器集區拓撲，其中資料中心的地理位置具有高頻寬/低延遲。</span><span class="sxs-lookup"><span data-stu-id="0b889-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="0b889-142">針對邏輯和實體拓撲採用下列各項：</span><span class="sxs-lookup"><span data-stu-id="0b889-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="0b889-143">邏輯拓撲包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="0b889-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="0b889-144">跨網站1和2的持久聊天集區，包含伺服器1到8。</span><span class="sxs-lookup"><span data-stu-id="0b889-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="0b889-145">前端伺服器集區、持久聊天資料庫、鏡像資料庫，以及（選擇性） (不會顯示在實際位於網站1上的圖表) 中。</span><span class="sxs-lookup"><span data-stu-id="0b889-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="0b889-146">第二部前端伺服器集區和備份資料庫位於網站2的實際位置。</span><span class="sxs-lookup"><span data-stu-id="0b889-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="0b889-147">實體拓撲包含網站1和2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0b889-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="0b889-148">Persistent Chat 集區，包含伺服器1到4、兩個主動、兩個空閒的網站1。</span><span class="sxs-lookup"><span data-stu-id="0b889-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="0b889-149">Persistent Chat 集區，包含伺服器5到8、兩個主動、兩個空閒的網站2。</span><span class="sxs-lookup"><span data-stu-id="0b889-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="0b889-150">在網站1上，前端伺服器集區、持久聊天資料庫、鏡像資料庫及（選擇性）的見證資料庫 (不會顯示在圖表) 中。</span><span class="sxs-lookup"><span data-stu-id="0b889-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="0b889-151">前端伺服器集區，以及備份資料庫，也就是網站2上的 SQL 記錄傳送目標。</span><span class="sxs-lookup"><span data-stu-id="0b889-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="0b889-152">**資料中心具有高頻寬/低延遲時的延伸 Persistent Chat Server 集區**</span><span class="sxs-lookup"><span data-stu-id="0b889-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![具有高頻寬/低延遲的持續性聊天延伸集區](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="0b889-154">圖2顯示資料中心地理位置具有低頻寬/高延遲的延伸持久聊天伺服器集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b889-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="0b889-155">邏輯拓撲包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="0b889-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="0b889-156">跨網站1和2的持久聊天集區，包含伺服器1到8。</span><span class="sxs-lookup"><span data-stu-id="0b889-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="0b889-157">前端伺服器集區、持久聊天資料庫、鏡像資料庫，以及（選擇性） (不會顯示在實際位於網站1上的圖表) 中。</span><span class="sxs-lookup"><span data-stu-id="0b889-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="0b889-158">第二部前端伺服器集區和備份資料庫位於網站2的實際位置。</span><span class="sxs-lookup"><span data-stu-id="0b889-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="0b889-159">實體拓撲包含網站1和2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0b889-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="0b889-160">在網站1上，包含伺服器1到4（所有使用中）的持久聊天集區。</span><span class="sxs-lookup"><span data-stu-id="0b889-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="0b889-161">在網站2上，包含伺服器5到8，所有空閒的持久聊天集區。</span><span class="sxs-lookup"><span data-stu-id="0b889-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="0b889-162">在網站1上，前端伺服器集區、持久聊天資料庫、鏡像資料庫及（選擇性）的見證資料庫 (不會顯示在圖表) 中。</span><span class="sxs-lookup"><span data-stu-id="0b889-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="0b889-163">前端伺服器集區，以及備份資料庫，也就是網站2上的 SQL 記錄傳送目標。</span><span class="sxs-lookup"><span data-stu-id="0b889-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="0b889-164">**資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區**</span><span class="sxs-lookup"><span data-stu-id="0b889-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![具有低頻寬/高延遲的持續性聊天延伸集區](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

