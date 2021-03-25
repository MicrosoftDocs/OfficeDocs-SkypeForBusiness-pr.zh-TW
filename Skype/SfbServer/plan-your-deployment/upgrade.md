---
title: 規劃升級至商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 摘要：瞭解當您規劃升級至商務用 Skype Server 2015 時，應考慮的事項。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server 2015，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: 742a582c9945e495bf150a174f8bc80101f61f7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122367"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="77e30-104">規劃升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="77e30-104">Plan to upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="77e30-105">摘要：瞭解當您規劃升級至商務用 Skype Server 2015 時，應考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="77e30-105">Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-106">從 Microsoft 評估中心下載免費試用版的商務用 Skype Server 2015，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。</span><span class="sxs-lookup"><span data-stu-id="77e30-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="77e30-107">在您計畫升級至商務用 Skype Server 2015 的過程中，請使用本主題來瞭解對商務用 Skype Server 2015 推薦的升級路徑、In-Place 升級的運作方式、支援的共存案例，以及升級程式的外觀。</span><span class="sxs-lookup"><span data-stu-id="77e30-107">As part of your plan to upgrade to Skype for Business Server 2015, use this topic to understand the recommended upgrade paths to Skype for Business Server 2015, how the In-Place Upgrade works, what the supported coexistence scenarios are, and what the upgrade process looks like.</span></span>

> [!NOTE]
> <span data-ttu-id="77e30-108">您可以在商務用 Skype 2015 Server 中取得就地升級，但在商務用 Skype Server 2019 中已不再支援就地升級。</span><span class="sxs-lookup"><span data-stu-id="77e30-108">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="77e30-109">受支援的並排 coexistance，請參閱 [遷移至商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="77e30-109">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a><span data-ttu-id="77e30-110">商務用 Skype Server 2015 的建議升級路徑</span><span class="sxs-lookup"><span data-stu-id="77e30-110">Recommended upgrade paths to Skype for Business Server 2015</span></span>

 <span data-ttu-id="77e30-111">若要從 Lync Server 2013、Lync Server 2010 或 Office 通訊伺服器 2007 R2 升級至商務用 Skype Server 2015，請使用下列升級路徑：</span><span class="sxs-lookup"><span data-stu-id="77e30-111">To upgrade from Lync Server 2013, Lync Server 2010, or Office Communications Server 2007 R2 to Skype for Business Server 2015, use the following upgrade paths:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="77e30-112">In-Place 升級會自動將會議目錄從 Lync Server 2013 移至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-112">In-Place Upgrade automatically moves conference directories from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-113">不過，如果您計畫手動移動會議目錄，使用商務用 Skype Server 2015 管理命令介面非常重要。</span><span class="sxs-lookup"><span data-stu-id="77e30-113">However, if you plan to manually move conference directories it is very important to use the Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="77e30-114">如果您嘗試使用 Lync Server 2013 管理命令介面將會議目錄從 Lync Server 2013 移至商務用 Skype Server 2015，可能會發生資料遺失。</span><span class="sxs-lookup"><span data-stu-id="77e30-114">If you try to use the Lync Server 2013 Management Shell to move conference directories from Lync Server 2013 to Skype for Business Server 2015 then data loss can occur.</span></span> <span data-ttu-id="77e30-115">一般而言，每當您使用商務用 Skype Server 2015 時，您應該使用商務用 Skype Server 2015 工具集。</span><span class="sxs-lookup"><span data-stu-id="77e30-115">In general, whenever you are working with Skype for Business Server 2015 in any capacity you should use the Skype for Business Server 2015 tool set.</span></span>  
  
|<span data-ttu-id="77e30-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="77e30-116">**Version**</span></span>|<span data-ttu-id="77e30-117">**建議**</span><span class="sxs-lookup"><span data-stu-id="77e30-117">**Recommendations**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77e30-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77e30-118">Lync Server 2013</span></span>  <br/> | <span data-ttu-id="77e30-119">若要升級，請在與集區相關聯的每個伺服器上，使用商務用 Skype Server 拓撲產生器和新的 In-Place 升級功能。</span><span class="sxs-lookup"><span data-stu-id="77e30-119">To upgrade, use the Skype for Business Server Topology Builder and the new In-Place Upgrade feature on each of the servers associated with the pool.</span></span> <span data-ttu-id="77e30-120">如需詳細步驟，請參閱 [Plan to upgrade From Lync server 2013 To 商務用 Skype server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) 及 [upgrade To 商務用 skype server 2015](../deploy/upgrade-to-skype-for-business-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="77e30-120">see [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps.</span></span> <br/> |
|<span data-ttu-id="77e30-121">Lync Server 2010 + Lync Server 2013 (雙模式) </span><span class="sxs-lookup"><span data-stu-id="77e30-121">Lync Server 2010 + Lync Server 2013 (dual-mode)</span></span>  <br/> |<span data-ttu-id="77e30-122">首先，升級至 Lync Server 2013，然後使用新的 In-Place 升級功能，升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-122">First, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="77e30-123">不過，如果您的拓撲是主要的 Lync Server 2010，您也可以將 Lync Server 2013 元件回復至 Lync Server 2010，然後直接升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-123">However, if your topology is primary Lync Server 2010 you can also roll back the Lync Server 2013 components to Lync Server 2010 and then upgrade directly to Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-124">在此情況下，您將無法利用 In-Place 升級，並會在 Lync Server 2010 和商務用 Skype Server 2015 之間使用直聯存在性。</span><span class="sxs-lookup"><span data-stu-id="77e30-124">In this case you would not be able to take advantage of In-Place Upgrade and would use straight co-existence between Lync Server 2010 and Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-125">不支援基本存在，但支援共存。</span><span class="sxs-lookup"><span data-stu-id="77e30-125">Tri-existence is not supported but co-existence is supported.</span></span>  <br/> |
|<span data-ttu-id="77e30-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="77e30-126">Lync Server 2010</span></span>  <br/> |<span data-ttu-id="77e30-127">開啟新的商務用 Skype Server 2015 集區，然後將使用者遷移至此新的集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-127">Bring up a new Skype for Business Server 2015 pool and then migrate users to this new pool.</span></span> <span data-ttu-id="77e30-128">然後，您就可以解除委任舊的 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-128">You can then decommission the old Lync Server 2010 pool.</span></span> <span data-ttu-id="77e30-129">從 Lync Server 2010 升級為商務用 Skype Server 2015 類似于從 Lync Server 2010 升級至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77e30-129">Upgrading from Lync Server 2010 to Skype for Business Server 2015 is similar to upgrading from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="77e30-130">請參閱 [從 Lync server 2010 遷移至 Lync server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="77e30-130">See [Migration from Lync Server 2010 to Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).</span></span>  <br/> |
|<span data-ttu-id="77e30-131">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="77e30-131">Office Communications Server 2007 R2</span></span>  <br/> | <span data-ttu-id="77e30-132">挑選下列兩個選項之一：</span><span class="sxs-lookup"><span data-stu-id="77e30-132">Pick one of two options:</span></span> <br/>  <span data-ttu-id="77e30-133">設定新的商務用 Skype Server 2015 環境。</span><span class="sxs-lookup"><span data-stu-id="77e30-133">Set up a new Skype for Business Server 2015 environment.</span></span> <br/>  <span data-ttu-id="77e30-134">或者，如果您的硬體和軟體符合商務用 Skype Server 2015 的需求，請升級至 Lync Server 2013，然後使用新的 In-Place 升級功能更新至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-134">Or if your hardware and software meet the requirements for Skype for Business Server 2015, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="77e30-135">如需詳細資訊，請參閱 [商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md) 及 [從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="77e30-135">For more information, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013).</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="77e30-136">商務用 Skype Server 2015 支援 SQL Server 2014，但在 Lync Server 2013 中不支援。</span><span class="sxs-lookup"><span data-stu-id="77e30-136">SQL Server 2014 is supported in Skype for Business Server 2015 but is not supported in Lync Server 2013.</span></span> <span data-ttu-id="77e30-137">如果您想要從 SQL Server 2012 升級至 SQL Server 2014，集區必須先升級為商務用 Skype Server 2015，如本檔中所述 In-Place 升級方法。</span><span class="sxs-lookup"><span data-stu-id="77e30-137">If you want to upgrade from SQL Server 2012 to SQL Server 2014 then the pool must first be upgraded to Skype for Business Server 2015 using the In-Place Upgrade method as described in this document.</span></span> <span data-ttu-id="77e30-138">然後您可以從 SQL Server 2012 升級至 SQL Server 2014，請參閱 [upgrade TO SQL server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)。</span><span class="sxs-lookup"><span data-stu-id="77e30-138">You can then upgrade from SQL Server 2012 to SQL Server 2014, see [Upgrade to SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014).</span></span> <span data-ttu-id="77e30-139">若要深入瞭解資料庫需求，請參閱 [商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77e30-139">To learn more about database requirements, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md).</span></span> 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a><span data-ttu-id="77e30-140">規劃從 Lync Server 2013 升級為商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="77e30-140">Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015</span></span>
<span data-ttu-id="77e30-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="77e30-142">您可以使用「新增 In-Place 升級」功能，將 Lync Server 2013 系統升級為商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-142">You can upgrade Lync Server 2013 systems to Skype for Business Server 2015 using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="77e30-143">就地升級提供一次按一下解決方案，以備份憑證、卸載伺服器元件、升級本機資料庫，以及安裝商務用 Skype Server 2015 角色。</span><span class="sxs-lookup"><span data-stu-id="77e30-143">In-place upgrade provides a one-click solution that backs up certificates, uninstalls server components, upgrades local databases, and installs the Skype for Business Server 2015 roles.</span></span> <span data-ttu-id="77e30-144">就地升級搜尋以保留現有的硬體和伺服器投資，減少部署商務用 Skype Server 2015 的整體成本。</span><span class="sxs-lookup"><span data-stu-id="77e30-144">In-place upgrade seeks to preserve existing hardware and server investments, reducing the overall cost to deploy Skype for Business Server 2015.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e30-145">In-Place 升級可讓您在升級至商務用 Skype 伺服器時使用相同的硬體。</span><span class="sxs-lookup"><span data-stu-id="77e30-145">In-Place Upgrade allows you to use the same hardware when upgrading to Skype for Business Server.</span></span> <span data-ttu-id="77e30-146">不過，重複使用相同的硬體並不會轉化成相同的效能容量。</span><span class="sxs-lookup"><span data-stu-id="77e30-146">However, reusing the same hardware does not translate into the same performance capacity.</span></span> <span data-ttu-id="77e30-147">您不應該期望 Lync Server 2013 和商務用 Skype Server 2015 的效能負載相同。</span><span class="sxs-lookup"><span data-stu-id="77e30-147">You should not expect the performance loads for Lync Server 2013 and Skype for Business Server 2015 to be identical.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="77e30-148">In-Place 升級不支援商務用 Skype 伺服器的高可用性或嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="77e30-148">In-Place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> 
  
<span data-ttu-id="77e30-149">就地升級包括讓 Lync Server 2013 集區離線，並將其升級為商務用 Skype Server 2015 集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-149">In-place upgrade involves taking the Lync Server 2013 pool offline and upgrading it to a Skype for Business Server 2015 pool.</span></span> 
  
### <a name="create-an-in-place-upgrade-plan"></a><span data-ttu-id="77e30-150">建立 In-Place 升級計畫</span><span class="sxs-lookup"><span data-stu-id="77e30-150">Create an In-Place Upgrade plan</span></span>

<span data-ttu-id="77e30-151">制定包含下列專案的計畫：</span><span class="sxs-lookup"><span data-stu-id="77e30-151">Make a plan that includes:</span></span>
  
1. <span data-ttu-id="77e30-152">瞭解您目前的拓撲。</span><span class="sxs-lookup"><span data-stu-id="77e30-152">An understanding of your current topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77e30-153">在執行 In-Place 升級之前，請務必先卸載 Lync Server 2013 的 LRS 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="77e30-153">Be sure to uninstall LRS Admin tool for Lync Server 2013 before running In-Place Upgrade.</span></span> <span data-ttu-id="77e30-154">Lync Server 2013 的 LRS 系統管理工具無法與商務用 Skype Server 2015 共存。</span><span class="sxs-lookup"><span data-stu-id="77e30-154">The LRS Admin Tool for Lync Server 2013 cannot coexist with Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-155">在執行 In-Place 升級之後，請安裝新的 LRS 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="77e30-155">After running In-Place Upgrade install the new LRS Admin tool.</span></span> <span data-ttu-id="77e30-156">如需詳細資訊，請參閱 [Microsoft Lync 會議室系統管理 Web 入口網站（適用于商務用 Skype Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) ）。</span><span class="sxs-lookup"><span data-stu-id="77e30-156">See [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) for more details.</span></span>
  
2. <span data-ttu-id="77e30-157">升級的主要集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-157">The primary pool for the upgrade.</span></span>
    
3. <span data-ttu-id="77e30-158">您是否要升級封存與監控資料庫或建立新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="77e30-158">Whether you'll upgrade the Archiving and Monitoring databases or create new ones.</span></span>
    
4. <span data-ttu-id="77e30-159">您將使用 In-Place 升級方法： [離線] 或 [移動使用者]。</span><span class="sxs-lookup"><span data-stu-id="77e30-159">The In-Place Upgrade method you'll use: Offline or Move Users.</span></span> <span data-ttu-id="77e30-160">在移動使用者的一部分，您也需要遷移與主要集區相關聯的全域會議目錄。</span><span class="sxs-lookup"><span data-stu-id="77e30-160">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> 
    
5. <span data-ttu-id="77e30-161">受影響使用者的溝通計畫。</span><span class="sxs-lookup"><span data-stu-id="77e30-161">A communication plan for impacted users.</span></span>
    
6. <span data-ttu-id="77e30-162">升級失敗時的備份計畫。</span><span class="sxs-lookup"><span data-stu-id="77e30-162">A backup plan in case the upgrades fails.</span></span>
    
<span data-ttu-id="77e30-163">在升級時，主要集區中的任何使用者將無法使用服務，直到升級完成為止。</span><span class="sxs-lookup"><span data-stu-id="77e30-163">Any users that are in the primary pool while it's being upgraded won't be able to use the services until the upgrade is complete.</span></span> <span data-ttu-id="77e30-164">如果您有一個工作中的輔助集區，您可以在升級前將使用者移至輔助集區，以避免影響使用者。</span><span class="sxs-lookup"><span data-stu-id="77e30-164">If you have a working secondary pool, you can avoid impacting users by moving them to the secondary pool before the upgrade.</span></span> <span data-ttu-id="77e30-165">升級之後，請將使用者移回到主要集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-165">After the upgrade, move the users back to the primary pool.</span></span>
  
### <a name="in-place-upgrade-methods"></a><span data-ttu-id="77e30-166">就地升級方法</span><span class="sxs-lookup"><span data-stu-id="77e30-166">In-place upgrade methods</span></span>

<span data-ttu-id="77e30-167">In-Place 升級的情形有兩種：</span><span class="sxs-lookup"><span data-stu-id="77e30-167">There are two scenarios for In-Place Upgrade:</span></span> 
  
- <span data-ttu-id="77e30-168">移動使用者方法，不需要使用者停機。</span><span class="sxs-lookup"><span data-stu-id="77e30-168">The Move User method, which requires no downtime for users.</span></span> 
    
- <span data-ttu-id="77e30-169">離線方法，需要停機時間。</span><span class="sxs-lookup"><span data-stu-id="77e30-169">The Offline method, which requires downtime.</span></span>
    
<span data-ttu-id="77e30-170">建議您在維護時段內排程離線方法升級，並通知使用者停機時間。</span><span class="sxs-lookup"><span data-stu-id="77e30-170">We recommend that an Offline method upgrade be scheduled during a maintenance window and users are notified of the downtime.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e30-171">在 Lync Server 2013 上升級配對集區時，若要將這兩個集區升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-171">When upgrading a paired pool on Lync Server 2013 and you want to upgrade both pools to Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-172">在升級第一個集區之後，請務必立即升級第二個集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-172">Make sure to upgrade the second pool immediately after upgrading the first pool.</span></span> <span data-ttu-id="77e30-173">當其中一個集區執行 Lync Server 2013，而第二個集區執行商務用 Skype Server 2015 時，會將嚴重損壞修復選項降到最低的狀態。</span><span class="sxs-lookup"><span data-stu-id="77e30-173">When one pool is running Lync Server 2013 and the second pool is running Skype for Business Server 2015 then disaster recovery options are minimized.</span></span> <span data-ttu-id="77e30-174">例如，如果有一個集區執行2013，第二個集區是2015，而且發生嚴重損壞，由於當成對集區不是相同的版本時，在嚴重損壞模式中不支援集區容錯移轉，所以您會遇到資料遺失。</span><span class="sxs-lookup"><span data-stu-id="77e30-174">For example, if one pool is running 2013 and the second is 2015 and there is a disaster then you could experience data loss because pool failover is not supported in disaster mode when paired pools are not the same version.</span></span> 
  
#### <a name="in-place-upgrade-offline-method"></a><span data-ttu-id="77e30-175">就地升級離線方法</span><span class="sxs-lookup"><span data-stu-id="77e30-175">In-place upgrade Offline method</span></span>

<span data-ttu-id="77e30-176">如果您不想要在使用者集區之間移動使用者，請使用此方法。</span><span class="sxs-lookup"><span data-stu-id="77e30-176">Use this method if you don't want to move users between user pools.</span></span> <span data-ttu-id="77e30-177">在升級期間，使用者將無法使用 Lync 或商務用 Skype 服務。</span><span class="sxs-lookup"><span data-stu-id="77e30-177">During the upgrade, users will not be able to use Lync or Skype for Business services.</span></span> 
  
<span data-ttu-id="77e30-178">下圖顯示此程式的概述。</span><span class="sxs-lookup"><span data-stu-id="77e30-178">The following diagram shows an overview of this process.</span></span>
  
![Lync 2013 至離線的 Skype 使用者](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> <span data-ttu-id="77e30-180">如果您有配對的集區，請不要在升級之前 unpair 這些集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-180">If you have paired pools, do not unpair them before the upgrade.</span></span> 
  
<span data-ttu-id="77e30-181">在您開始升級伺服器集區之後，您必須完成整個集區的升級。</span><span class="sxs-lookup"><span data-stu-id="77e30-181">Once you start to upgrade a server pool, you must complete the upgrade of the entire pool.</span></span> <span data-ttu-id="77e30-182">商務用 Skype 伺服器不支援只有一部分已升級的集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-182">Skype for Business Server doesn't support having only a portion of the pool upgraded.</span></span> 
  
#### <a name="move-users-method-no-user-downtime"></a><span data-ttu-id="77e30-183">移動使用者方法 (無使用者停機時間) </span><span class="sxs-lookup"><span data-stu-id="77e30-183">Move Users method (no user downtime)</span></span>
<span data-ttu-id="77e30-184"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-184"><a name="bkmk_MoveUsersMethod"> </a></span></span>

<span data-ttu-id="77e30-185">若要使用此方法，您可以將使用者移至另一個集區，然後再開始升級。</span><span class="sxs-lookup"><span data-stu-id="77e30-185">To use this method, you move users to another pool before you start the upgrade.</span></span> <span data-ttu-id="77e30-186">在升級期間，使用者可以使用 Lync 服務。</span><span class="sxs-lookup"><span data-stu-id="77e30-186">During the upgrade, users can use Lync services.</span></span> <span data-ttu-id="77e30-187">移至已升級的集區之後，即可使用商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="77e30-187">After they're moved to the upgraded pool, they can use Skype for Business.</span></span> <span data-ttu-id="77e30-188">下圖顯示此程式的概述。</span><span class="sxs-lookup"><span data-stu-id="77e30-188">The following diagram shows an overview of this process.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77e30-189">在移動使用者的一部分，您也需要遷移與主要集區相關聯的全域會議目錄。</span><span class="sxs-lookup"><span data-stu-id="77e30-189">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> <span data-ttu-id="77e30-190">PSTN 電話撥入式會議仍然會將 ConferenceID 解析為要升級的集區，而不是配對的集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-190">PSTN dial-in conferencing will still resolve ConferenceID to the pool being upgraded, instead of the paired pool.</span></span> <span data-ttu-id="77e30-191">因此，如果您仍然想要在集區中安排 PSTN 會議，以在升級期間存取，您需要移動會議目錄。</span><span class="sxs-lookup"><span data-stu-id="77e30-191">So you need to move Conference Directories, if you still want PSTN conferences scheduled in the pool to be accessible during upgrade.</span></span> 
  
![泳道圖表，顯示在升級集區之前，將使用者移至另一個集區，以及在升級後移回集區。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a><span data-ttu-id="77e30-193">移動使用者以進行硬體升級</span><span class="sxs-lookup"><span data-stu-id="77e30-193">Move users for hardware upgrade</span></span>
<span data-ttu-id="77e30-194"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-194"><a name="bkmk_MoveUsersMethod"> </a></span></span>

 <span data-ttu-id="77e30-195">如果您的硬體未滿足 [商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)，請設定新的商務用 skype server 2015 環境，並在那裡移動使用者。</span><span class="sxs-lookup"><span data-stu-id="77e30-195">If your hardware doesn't meet the [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md), set up a new Skype for Business Server 2015 environment, and move users there.</span></span> <span data-ttu-id="77e30-196">下圖顯示從 Lync Server 2010 升級此程式的概述。</span><span class="sxs-lookup"><span data-stu-id="77e30-196">The following diagram shows an overview of this process for upgrade from Lync Server 2010.</span></span> 
  
![泳道圖表，顯示移至商務用 Skype Server 2015 和 Lync Server 集區的 Lync Server 主要前端集區中的使用者。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a><span data-ttu-id="77e30-198">就地升級程序</span><span class="sxs-lookup"><span data-stu-id="77e30-198">In-place upgrade process</span></span>

 <span data-ttu-id="77e30-199">使用下列步驟，從 Lync Server 2013 升級為商務用 Skype Server 2015：</span><span class="sxs-lookup"><span data-stu-id="77e30-199">Upgrade from Lync Server 2013 to Skype for Business Server 2015 using the following steps:</span></span>
  
1. <span data-ttu-id="77e30-200">在升級之前，請先備份所有資料庫。</span><span class="sxs-lookup"><span data-stu-id="77e30-200">Back up all databases before the upgrade.</span></span>
    
2. <span data-ttu-id="77e30-201">請確定要升級的所有服務都處於執行中狀態。</span><span class="sxs-lookup"><span data-stu-id="77e30-201">Make sure all services that are to be upgraded are in a running state.</span></span>
    
3. <span data-ttu-id="77e30-202">使用拓撲產生器升級及發行拓撲檔案。</span><span class="sxs-lookup"><span data-stu-id="77e30-202">Upgrade and publish the topology file using the topology builder.</span></span>
    
4. <span data-ttu-id="77e30-203">停止所有前端伺服器上的所有服務。</span><span class="sxs-lookup"><span data-stu-id="77e30-203">Stop all services on all Front End servers.</span></span>
    
5. <span data-ttu-id="77e30-204">安裝商務用 Skype Server 所需的新必要條件。</span><span class="sxs-lookup"><span data-stu-id="77e30-204">Install new prerequisites required for Skype for Business Server.</span></span>
    
6. <span data-ttu-id="77e30-205">在每一部前端伺服器上，啟動 [In-Place 升級]。</span><span class="sxs-lookup"><span data-stu-id="77e30-205">On each Front End server, start the In-Place Upgrade.</span></span>
    
7. <span data-ttu-id="77e30-206">升級完成後，請重新開機所有服務。</span><span class="sxs-lookup"><span data-stu-id="77e30-206">When the upgrade is complete, restart all services.</span></span>
    
   - <span data-ttu-id="77e30-207">針對前端集區，使用命令 Get-cspool 重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="77e30-207">For the Front End pool, restart services using the command Start-CsPool.</span></span>
    
   - <span data-ttu-id="77e30-208">若為非前端伺服器，請使用 Get-cswindowsservice。</span><span class="sxs-lookup"><span data-stu-id="77e30-208">For non-Front End servers, use Start-CSWindowsService.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="77e30-209">如果您不想升級現有的封存及監控資料庫，請在升級拓撲之前，先移除相依性。</span><span class="sxs-lookup"><span data-stu-id="77e30-209">If you don't want to upgrade your existing Archiving and Monitoring databases, remove the dependency before you upgrade the topology.</span></span> <span data-ttu-id="77e30-210">如果您想要建立新的封存與監控資料庫，在升級期間，您可以建立新的 SQL 存放區，並將它與集區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="77e30-210">If you want to create new Archiving and Monitoring databases, during the upgrade, you can create a new SQL store and associate it with the pool.</span></span> <span data-ttu-id="77e30-211">您可以在主題中找到執行這項作業的步驟，[升級至商務用 Skype Server 2015](../deploy/upgrade-to-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="77e30-211">You can find the steps on how to do this in the topic,[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md).</span></span> <span data-ttu-id="77e30-212">> 就地升級不支援商務用 Skype 伺服器的高可用性或災難修復。</span><span class="sxs-lookup"><span data-stu-id="77e30-212">>  In-place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> <span data-ttu-id="77e30-213">若要避免中斷使用者的服務，請使用 [ [移動使用者] 方法 (無使用者停機時間) ](upgrade.md#bkmk_MoveUsersMethod) 升級 >。在升級程式期間，xds 副本會放在具有最多可用空間的磁片磁碟機上的本機共用資料夾中。</span><span class="sxs-lookup"><span data-stu-id="77e30-213">To avoid interrupting users' services, use the [Move Users method (no user downtime)](upgrade.md#bkmk_MoveUsersMethod) to upgrade.>  During the upgrade process the xds-replica is placed in the local shared folder on the disk drive with the most free space.</span></span> <span data-ttu-id="77e30-214">若後來移除該磁片，您可以執行問題，例如服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="77e30-214">If that disk is later removed then you can run into issues such as services not starting.</span></span>
  
### <a name="upgrade-order"></a><span data-ttu-id="77e30-215">升級順序</span><span class="sxs-lookup"><span data-stu-id="77e30-215">Upgrade order</span></span>

<span data-ttu-id="77e30-216">從內部向外升級拓撲。</span><span class="sxs-lookup"><span data-stu-id="77e30-216">Upgrade the topology from the inside to the outside.</span></span> <span data-ttu-id="77e30-217">先升級所有集區，然後再升級 edge server，最後是中央管理存放區 (CMS) 集區。</span><span class="sxs-lookup"><span data-stu-id="77e30-217">Upgrade all your pools first, then the edge servers, and finally the Central Management Store (CMS) pool.</span></span> 
  
### <a name="kerberos-authentication-considerations"></a><span data-ttu-id="77e30-218">Kerberos 驗證考慮</span><span class="sxs-lookup"><span data-stu-id="77e30-218">Kerberos authentication considerations</span></span>

<span data-ttu-id="77e30-219">如果您對 Web 服務使用 Kerberos 驗證，您必須在 In-Place 升級完成後，重新指派 Kerberos 帳戶並重設密碼。</span><span class="sxs-lookup"><span data-stu-id="77e30-219">If you use Kerberos authentication for Web Services, you must reassign Kerberos accounts and reset the password after the In-Place Upgrade is complete.</span></span> <span data-ttu-id="77e30-220">若要瞭解如何執行這項操作，請參閱 [設定 Kerberos 驗證](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication)。</span><span class="sxs-lookup"><span data-stu-id="77e30-220">To learn how to do this, see [Setting up Kerberos authentication](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication).</span></span>
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a><span data-ttu-id="77e30-221">支援 Lync Server 2013 和 Lync Server 2010 共存</span><span class="sxs-lookup"><span data-stu-id="77e30-221">Support for coexistence with Lync Server 2013 and Lync Server 2010</span></span>
<span data-ttu-id="77e30-222"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-222"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="77e30-223">您可以在與 Lync Server 2013 或 Lync Server 2010 相同的拓撲中執行商務用 Skype Server 2015，但您無法在相同的拓撲中全部三個。</span><span class="sxs-lookup"><span data-stu-id="77e30-223">You can run Skype for Business Server 2015 in the same topology as Lync Server 2013 or Lync Server 2010, but you can't have all three in the same topology.</span></span>
  
<span data-ttu-id="77e30-224">如果您在 Lync Server 2010 和 Lync Server 2013 之間有共同存在，建議您將整個拓撲升級至 Lync Server 2013，然後使用 In-Place 升級升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-224">If you have a co-existence between Lync Server 2010 and Lync Server 2013, it is recommended to upgrade the entire topology to Lync Server 2013, and then upgrade to Skype for Business Server 2015 using the In-Place Upgrade.</span></span> <span data-ttu-id="77e30-225">如需詳細資訊，請參閱 [從 Lync server 2010 遷移至 Lync server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="77e30-225">For more information, see [Migration from Lync Server 2010 to Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).</span></span>
  
<span data-ttu-id="77e30-226">如果拓撲主要是 Lync Server 2010，請先將 Lync Server 2013 元件還原至 Lync Server 2010，再將拓撲升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="77e30-226">If your topology is primarily Lync Server 2010, roll back the Lync Server 2013 components to Lync Server 2010 before upgrading the topology to Skype for Business Server 2015.</span></span> <span data-ttu-id="77e30-227">在此情況下，您會失去 In-Place 升級的優點，並在 Lync Server 2010 和商務用 Skype Server 2015 之間具有共同存在的拓撲。</span><span class="sxs-lookup"><span data-stu-id="77e30-227">In this case, you lose the benefit of the In-Place Upgrade and have a co-existence topology between Lync Server 2010 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="77e30-228">下圖顯示商務用 Skype Server 2015 與 Lync Server 2013 和 Lync Server 2010 的共存支援。</span><span class="sxs-lookup"><span data-stu-id="77e30-228">The following diagram shows the coexistence support of Skype for Business Server 2015 with Lync Server 2013 and Lync Server 2010.</span></span>
  
![圖表顯示商務用 Skype Server 2015 的 coexistance 支援，含 Lync Server 2013 或 Lync Server 2010。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a><span data-ttu-id="77e30-230">與現有 Survivable 分支裝置和伺服器的升級程式</span><span class="sxs-lookup"><span data-stu-id="77e30-230">Upgrade process with existing Survivable Branch Appliance and Server</span></span>
<span data-ttu-id="77e30-231"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-231"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="77e30-232">商務用 Skype Server 2015 不支援 Survivable 分支裝置的 In-Place 升級 (SBA) 或 Survivable 的分支伺服器 (SBS) 。</span><span class="sxs-lookup"><span data-stu-id="77e30-232">Skype for Business Server 2015 doesn't support an In-Place Upgrade of a Survivable Branch Appliance (SBA) or a Survivable Branch Server (SBS).</span></span>
  
<span data-ttu-id="77e30-233">不過，我們確實支援 Lync Server 2010 或 Lync Server 2013 SBA/SBS 的商務用 Skype Server 資料中心共存。</span><span class="sxs-lookup"><span data-stu-id="77e30-233">However, we do support coexistence of Skype for Business Server datacenters with Lync Server 2010 or Lync Server 2013 SBA/SBS.</span></span> 
  
<span data-ttu-id="77e30-234">在規劃使用關聯的分支的 Lync Server 2013 前端 (FE) 集區的 In-Place 升級時，您可以將現有的使用者保留在 Lync Server 2013 SBA/SBS 上。</span><span class="sxs-lookup"><span data-stu-id="77e30-234">When planning for an In-Place Upgrade of a Lync Server 2013 Front End (FE) pool with an associated branch, you can leave the existing users on the Lync Server 2013 SBA/SBS.</span></span> <span data-ttu-id="77e30-235">在升級期間，SBA/SBS 使用者將會進入復原模式，並將在升級完成後回到一般功能。</span><span class="sxs-lookup"><span data-stu-id="77e30-235">During the upgrade, the SBA/SBS users will go in resiliency mode and will return to normal functionality after the upgrade has completed.</span></span> <span data-ttu-id="77e30-236">如需使用者在復原模式中的經驗的詳細資訊，請參閱 [Lync Server 2013 中的分支網站恢復功能](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features)。</span><span class="sxs-lookup"><span data-stu-id="77e30-236">For more information about the users' experience during the resiliency mode, please see [Branch-site resiliency features in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features).</span></span>
  
<span data-ttu-id="77e30-237">將 Lync Server 2010 拓撲遷移至商務用 Skype Server 2015 時，必須將 SBA/SBS 重新加入至拓撲，類似遷移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77e30-237">When migrating a Lync Server 2010 topology to Skype for Business Server 2015, the SBA/SBS must re-added to the topology, similar to the migration to Lync Server 2013.</span></span> <span data-ttu-id="77e30-238">如需必要的步驟，請參閱 [將 Survivable Branch 裝置連線至 Lync Server 2013 前端集](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool)區。</span><span class="sxs-lookup"><span data-stu-id="77e30-238">For the required steps, please read [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool).</span></span>
  
<span data-ttu-id="77e30-239">對於 Lync Server 2010 和 Lync Server 2013 的共存拓撲，請先將「支援 Lync Server 2013 和 Lync 2010 Server 的共存」區段中所做的建議對齊。</span><span class="sxs-lookup"><span data-stu-id="77e30-239">For co-existence topologies of Lync Server 2010 and Lync Server 2013, align first to the recommendations made in the section 'Support for coexistence with Lync Server 2013 and Lync Server 2010'.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77e30-240">另請參閱</span><span class="sxs-lookup"><span data-stu-id="77e30-240">See also</span></span>
<span data-ttu-id="77e30-241"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="77e30-241"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

[<span data-ttu-id="77e30-242">升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="77e30-242">Upgrade to Skype for Business Server 2015</span></span>](../deploy/upgrade-to-skype-for-business-server.md)
  
[<span data-ttu-id="77e30-243">商務用 Skype Server 2015 的環境需求</span><span class="sxs-lookup"><span data-stu-id="77e30-243">Environmental requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/environmental-requirements.md)
  
[<span data-ttu-id="77e30-244">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="77e30-244">Server requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/server-requirements.md)