---
title: 升級至商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '摘要: 瞭解如何從 Lync Server 2013 升級到商務用 Skype Server 2015。 從 Microsoft 評估中心 (網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 下載商務用 Skype Server 2015 免費試用版。'
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237858"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="89d0a-104">升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="89d0a-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89d0a-105">**摘要:** 瞭解如何從 Lync Server 2013 升級到商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="89d0a-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="89d0a-106">從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 2015 的免費試用版。</span><span class="sxs-lookup"><span data-stu-id="89d0a-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="89d0a-107">使用本檔中的程式, 從 Lync Server 2013 升級到2015商務用 skype server 的 [商務用 Skype 伺服器拓撲結構], 以及新的就地升級功能。</span><span class="sxs-lookup"><span data-stu-id="89d0a-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="89d0a-108">如果您想要從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 升級, 請參閱[規劃升級到商務用 Skype server 2015](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="89d0a-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89d0a-109">商務用 Skype Server 2015 提供就地升級, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="89d0a-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="89d0a-110">支援並排 coexistance, 如需詳細資訊, 請參閱[遷移到商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="89d0a-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="89d0a-111">從 Lync Server 2013 升級</span><span class="sxs-lookup"><span data-stu-id="89d0a-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="89d0a-112">將 Lync Server 2013 升級到商務用 Skype Server 2015 需要安裝必備軟體, 使用商務用 Skype Server 拓撲產生器來升級池中的資料庫, 並使用商務用 Skype Server 就地升級與該池相關聯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="89d0a-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="89d0a-113">若要完成升級, 請參閱本主題中的八個步驟。</span><span class="sxs-lookup"><span data-stu-id="89d0a-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="89d0a-114">開始之前</span><span class="sxs-lookup"><span data-stu-id="89d0a-114">Before you begin</span></span>

- <span data-ttu-id="89d0a-115">查看[要升級至商務用 Skype Server 2015 的方案](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="89d0a-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="89d0a-116">查看[商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89d0a-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="89d0a-117">[安裝商務用 Skype Server 2015 的先決條件](install/install-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="89d0a-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="89d0a-118">[安裝商務用 Skype Server 2015](install/install.md) 。</span><span class="sxs-lookup"><span data-stu-id="89d0a-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="89d0a-119">步驟 1: 安裝系統管理員工具和下載拓撲</span><span class="sxs-lookup"><span data-stu-id="89d0a-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="89d0a-120">在未安裝 Lync OCSCore 或任何其他 Lync 元件的拓撲中, 連線到電腦。</span><span class="sxs-lookup"><span data-stu-id="89d0a-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="89d0a-121">從商務用 Skype Server 2015 安裝媒體, 從\*\*\*\* **OCS_Volume\Setup\AMD64**執行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="89d0a-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="89d0a-122">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="89d0a-123">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="89d0a-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="89d0a-124">在 [部署] 嚮導中, 按一下 [**安裝系統管理員工具**], 然後依照步驟進行安裝。</span><span class="sxs-lookup"><span data-stu-id="89d0a-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![[部署嚮導] 的螢幕擷取畫面, 其中包含已稱為 [安裝管理員工具] 的連結。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="89d0a-126">在 Windows [開始] 畫面中, 開啟 [商務用 Skype Server 拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="89d0a-127">按一下 [**從現有部署下載拓朴**], 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89d0a-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="89d0a-128">輸入拓朴的名稱, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="89d0a-129">移至您儲存拓撲結構的位置, 然後建立拓撲複本。</span><span class="sxs-lookup"><span data-stu-id="89d0a-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="89d0a-130">步驟 2: 使用拓撲產生器升級及發佈拓撲</span><span class="sxs-lookup"><span data-stu-id="89d0a-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="89d0a-131">開始升級程式之前, 必須針對您規劃要升級的池執行所有服務。</span><span class="sxs-lookup"><span data-stu-id="89d0a-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="89d0a-132">如此一來, 拓撲變更將會複製到池中伺服器的本機資料庫。</span><span class="sxs-lookup"><span data-stu-id="89d0a-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="89d0a-133">在升級前, 請先儲存拓撲檔案複本。</span><span class="sxs-lookup"><span data-stu-id="89d0a-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="89d0a-134">升級之後, 您將無法降級拓朴。 > 如果您的服務與您的資料庫在相同的伺服器上, 例如 Persistent 聊天服務與持續聊天資料庫位於同一台伺服器上, 請跳過此步驟, 然後移至步驟4。</span><span class="sxs-lookup"><span data-stu-id="89d0a-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="89d0a-135">停止服務之後, 請在每個伺服器上執行就地升級設定, 以升級本機資料庫。</span><span class="sxs-lookup"><span data-stu-id="89d0a-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89d0a-136">如果拓撲具有已鏡像的後端資料庫, 當您使用 [拓撲建立器]**發佈拓撲時**, 就會看到主體和鏡像資料庫都會顯示。</span><span class="sxs-lookup"><span data-stu-id="89d0a-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="89d0a-137">在發佈拓撲時, 請確定所有資料庫都在執行, 而不是選取主體 (而不是鏡像), 否則您會在發佈拓撲後看到警告。</span><span class="sxs-lookup"><span data-stu-id="89d0a-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="89d0a-138">選擇下列其中一個選項, 以使用商務用 Skype Server 2015 拓撲建立器來升級及發佈新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="89d0a-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="89d0a-139">完成步驟併發布更新後的拓撲之後, 請移至本主題中的步驟3。</span><span class="sxs-lookup"><span data-stu-id="89d0a-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="89d0a-140">選項 1: 升級獨立的 [前端] 池及相關聯的 [封存及監視] 存放區</span><span class="sxs-lookup"><span data-stu-id="89d0a-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="89d0a-141">如果您要升級的池有 [封存與監控] 儲存相依性, 當您使用下列步驟時, [封存與監視] 存放區也將會升級。</span><span class="sxs-lookup"><span data-stu-id="89d0a-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="89d0a-142">在拓撲建立器中, 以滑鼠右鍵按一下 Lync Server 2013 池, 然後選取 [**升級至商務用 Skype server 2015**], 然後依照步驟進行。</span><span class="sxs-lookup"><span data-stu-id="89d0a-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="89d0a-144">在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![[拓撲建立器] 中 [發佈拓撲] 選項的 [動作] 功能表螢幕擷取畫面。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="89d0a-146">在發佈期間, 選擇要在 [封存與監控] 存放區上安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="89d0a-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="89d0a-147">選項 2: 升級 [前端] 池而不升級封存與監控存放區</span><span class="sxs-lookup"><span data-stu-id="89d0a-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="89d0a-148">如果您使用下列步驟, 則會停用所選池的封存和監控。</span><span class="sxs-lookup"><span data-stu-id="89d0a-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="89d0a-149">升級之後, 該池將不會有 [封存及監視] 儲存。</span><span class="sxs-lookup"><span data-stu-id="89d0a-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="89d0a-150">在 [拓撲建立器] 中, 選取您要升級的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="89d0a-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="89d0a-151">移除 Lync Server 2013 [封存與監控] 存放區的相依性。</span><span class="sxs-lookup"><span data-stu-id="89d0a-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="89d0a-152">移至 [**動作** > **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="89d0a-153">清除 [ \*\*\*\* 封存] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-153">Clear the **Archiving** check box.</span></span>
    
     ![[編輯屬性] 對話方塊上的 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="89d0a-155">清除 [**監視**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-155">Clear the **Monitoring** check box.</span></span>
    
     ![Showsr [監視] 核取方塊的 [編輯屬性] 對話方塊的螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="89d0a-157">以滑鼠右鍵按一下 Lync Server 2013 池, 選取 [**升級至商務用 Skype server 2015**], 然後遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="89d0a-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="89d0a-159">在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="89d0a-160">選項 3: 升級前端池並將其與新的商務用 Skype Server 2015 (歸檔及監視存放區) 關聯</span><span class="sxs-lookup"><span data-stu-id="89d0a-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="89d0a-161">如果您使用下列步驟, 則會在前一位商店停止封存和監控, 並在您建立的新商店開始。</span><span class="sxs-lookup"><span data-stu-id="89d0a-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="89d0a-162">在 [拓撲建立器] 中, 選取您要升級的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="89d0a-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="89d0a-163">移除 Lync Server 2013 [封存與監控] 存放區的相依性。</span><span class="sxs-lookup"><span data-stu-id="89d0a-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="89d0a-164">移至 [**動作** > **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="89d0a-165">清除 [ \*\*\*\* 封存] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-165">Clear the **Archiving** check box.</span></span>
    
     ![[編輯屬性] 對話方塊上的 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="89d0a-167">清除 [**監視**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-167">Clear the **Monitoring** check box.</span></span>
    
     ![Showsr [監視] 核取方塊的 [編輯屬性] 對話方塊的螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="89d0a-169">以滑鼠右鍵按一下 Lync Server 2013 池, 選取 [**升級至商務用 Skype server 2015**], 然後遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="89d0a-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="89d0a-171">建立新的 SQL store 以進行封存。</span><span class="sxs-lookup"><span data-stu-id="89d0a-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="89d0a-172">選取 [泳池] 和 [**動作** > **編輯] 屬性**。</span><span class="sxs-lookup"><span data-stu-id="89d0a-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="89d0a-173">選取 [**存檔**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="89d0a-174">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-174">Click **New**.</span></span>
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面, 顯示 [存檔] 區段下的 [新增] 按鈕。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="89d0a-176">建立新的 SQL store 進行監視。</span><span class="sxs-lookup"><span data-stu-id="89d0a-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="89d0a-177">選取 [泳池] 和 [**動作** > **編輯] 屬性**。</span><span class="sxs-lookup"><span data-stu-id="89d0a-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="89d0a-178">選取 [**監視**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89d0a-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="89d0a-179">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-179">Click **New**.</span></span>
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面, 顯示 [監視] 區段底下的 [新增] 按鈕。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="89d0a-181">在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="89d0a-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="89d0a-182">在發佈期間, 請選擇在新的 [存檔及監視] 存放區上安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="89d0a-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="89d0a-183">步驟 3: 等待複製</span><span class="sxs-lookup"><span data-stu-id="89d0a-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="89d0a-184">給予複製一些時間, 將更新的拓撲發佈至環境中的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="89d0a-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="89d0a-185">步驟 4: 停止要升級的池中所有服務</span><span class="sxs-lookup"><span data-stu-id="89d0a-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="89d0a-186">在正在處理您要升級之池的每個伺服器上, 在 PowerShell 中執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="89d0a-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="89d0a-187">我們建議您使用 Disable CsComputer, 因為您可能需要在就地升級程式期間重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="89d0a-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="89d0a-188">如果您使用 CsWindowsService, 某些服務可能會在重新開機後自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="89d0a-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="89d0a-189">這可能會導致就地升級失敗。</span><span class="sxs-lookup"><span data-stu-id="89d0a-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="89d0a-190">步驟 5: 升級前端池與非前端池伺服器</span><span class="sxs-lookup"><span data-stu-id="89d0a-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="89d0a-191">升級之前, 請先安裝商務用 Skype Server 2015 所需的所有新必備元件, 包括: 在嘗試升級前, 請先 > 至少32GB 的可用空間。</span><span class="sxs-lookup"><span data-stu-id="89d0a-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="89d0a-192">此外, 請確定此磁碟機是固定的本機磁片磁碟機, 且未透過 USB 或 Firewire 進行格式化、未壓縮, 且不含頁面檔案。 > PowerShell 版本6.2.9200.0 或更新版本。 > 最新的 Lync Server 2013已安裝累積更新。已安裝 > SQL Server 2012 SP1。 > 下列 KB 的安裝 (如果使用 Microsoft Update, 就會自動安裝): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windowsServer 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="89d0a-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="89d0a-193">在每個伺服器上使用就地升級來更新前端池、邊緣池、中繼伺服器, 以及持久聊天池。</span><span class="sxs-lookup"><span data-stu-id="89d0a-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="89d0a-194">在每個伺服器上\*\*\*\* , 從商務用 Skype server 2015 安裝媒體上的**OCS_Volume\Setup\amd64**執行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="89d0a-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="89d0a-195">接受授權合約, 然後依照提示進行就地升級。</span><span class="sxs-lookup"><span data-stu-id="89d0a-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="89d0a-196">針對前端池中的每個伺服器以及在每個非前端的 [池伺服器] 上, 重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="89d0a-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="89d0a-197">在就地升級期間, 系統可能會提示您重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="89d0a-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="89d0a-198">沒關係。</span><span class="sxs-lookup"><span data-stu-id="89d0a-198">That's ok.</span></span> <span data-ttu-id="89d0a-199">重新開機之後, 就地升級就會從停止的位置繼續。</span><span class="sxs-lookup"><span data-stu-id="89d0a-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="89d0a-200">當就地升級順利完成時, 您會看到下列訊息。</span><span class="sxs-lookup"><span data-stu-id="89d0a-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![螢幕擷取畫面顯示就地升級順利完成。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="89d0a-202">步驟 6: 重新開機所有已升級伺服器上的服務</span><span class="sxs-lookup"><span data-stu-id="89d0a-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="89d0a-203">重新開機服務之前, 請確定%ProgramData%\WindowsFabric 並不存在於所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="89d0a-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="89d0a-204">如果它存在, 請先將它刪除, 然後再啟動服務。</span><span class="sxs-lookup"><span data-stu-id="89d0a-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="89d0a-205">在您升級完前端池中的所有伺服器之後, 請使用下列 PowerShell 命令重新開機服務:</span><span class="sxs-lookup"><span data-stu-id="89d0a-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="89d0a-206">如果您在開始執行就地升級前需要重新開機待執行的系統, 則就地升級不會要求您在安裝結束時重新開機。</span><span class="sxs-lookup"><span data-stu-id="89d0a-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="89d0a-207">當您嘗試使用 CSPool Cmdlet 啟動服務時, 會針對第一個前端伺服器引發一些元件例外狀況。</span><span class="sxs-lookup"><span data-stu-id="89d0a-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="89d0a-208">若要解決這些錯誤, 請重新開機池中的所有伺服器, 然後再次執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89d0a-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="89d0a-209">在非前端的 [池伺服器] 上, 使用下列命令重新開機服務:</span><span class="sxs-lookup"><span data-stu-id="89d0a-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="89d0a-210">按一下 [就地升級] 頁面上的 **[確定]** 後, 您會看到下列提醒, 以完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="89d0a-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![螢幕擷取畫面顯示就地升級順利完成後的後續步驟。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="89d0a-212">步驟 7: 驗證商務用 Skype 的功能是否正常運作</span><span class="sxs-lookup"><span data-stu-id="89d0a-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="89d0a-213">若要確保升級成功, 請在已升級的池中測試商務用 Skype, 以確保功能如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="89d0a-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="89d0a-214">步驟 8: 升級次要池</span><span class="sxs-lookup"><span data-stu-id="89d0a-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="89d0a-215">重複本主題中的步驟, 以升級您在您的環境中所擁有的任何其他池。</span><span class="sxs-lookup"><span data-stu-id="89d0a-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="89d0a-216">針對就地升級的問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="89d0a-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="89d0a-217">如果就地升級失敗, 您可能會看到類似下列影像中的訊息。</span><span class="sxs-lookup"><span data-stu-id="89d0a-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![螢幕擷取畫面顯示就地升級失敗, 因為未安裝所需的累加更新。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="89d0a-219">查看頁面底部的完整訊息, 以協助您對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="89d0a-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="89d0a-220">按一下 [**查看記錄**] 以取得更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89d0a-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="89d0a-221">如果就地升級在**驗證升級準備情況**或**安裝缺少的先決條件**時失敗, 請確認伺服器已套用所有最新的 Windows server、Lync server 及 SQL server 更新, 且所有必要的軟體和角色都是安裝.</span><span class="sxs-lookup"><span data-stu-id="89d0a-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="89d0a-222">如需必要的清單, 請參閱[商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md), 以及[安裝商務用 skype server 2015 的先決條件](install/install-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="89d0a-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89d0a-223">另請參閱</span><span class="sxs-lookup"><span data-stu-id="89d0a-223">See also</span></span>

[<span data-ttu-id="89d0a-224">規劃升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="89d0a-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="89d0a-225">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="89d0a-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="89d0a-226">安裝商務用 Skype Server 2015 的先決條件</span><span class="sxs-lookup"><span data-stu-id="89d0a-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="89d0a-227">安裝商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="89d0a-227">Install Skype for Business Server 2015</span></span>](install/install.md)
