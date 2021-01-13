---
title: 升級至商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 摘要：瞭解如何從 Lync Server 2013 升級為商務用 Skype Server 2015。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server 2015，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820423"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="6a6af-104">升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a6af-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6a6af-105">**摘要：** 瞭解如何從 Lync Server 2013 升級為商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="6a6af-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="6a6af-106">從  [Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 2015 免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6a6af-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6a6af-107">使用此檔中的程式，透過使用商務用 Skype Server 拓撲產生器和新的 In-Place 升級功能，從 Lync Server 2013 升級至商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="6a6af-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="6a6af-108">如果您想要從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 升級，請參閱 [Plan to upgrade To Business server 2015](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6af-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a6af-109">您可以在商務用 Skype 2015 Server 中取得就地升級，但在商務用 Skype Server 2019 中已不再支援就地升級。</span><span class="sxs-lookup"><span data-stu-id="6a6af-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6a6af-110">受支援的並排 coexistance，請參閱 [遷移至商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="6a6af-111">從 Lync Server 2013 升級</span><span class="sxs-lookup"><span data-stu-id="6a6af-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="6a6af-112">將 Lync Server 2013 升級為商務用 Skype Server 2015 包括安裝必要軟體，使用商務用 Skype Server 拓撲產生器升級集區中的資料庫，以及使用商務用 Skype Server In-Place 在與集區相關聯的每個伺服器上進行升級。</span><span class="sxs-lookup"><span data-stu-id="6a6af-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="6a6af-113">若要完成升級，請完成本主題中的8個步驟。</span><span class="sxs-lookup"><span data-stu-id="6a6af-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="6a6af-114">開始之前</span><span class="sxs-lookup"><span data-stu-id="6a6af-114">Before you begin</span></span>

- <span data-ttu-id="6a6af-115">檢查 [方案，以升級至商務用 Skype Server 2015](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6af-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="6a6af-116">檢查 [商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6af-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="6a6af-117">[安裝商務用 Skype Server 2015 的必要條件](install/install-prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="6a6af-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="6a6af-118">[安裝商務用 Skype Server 2015](install/install.md) 。</span><span class="sxs-lookup"><span data-stu-id="6a6af-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="6a6af-119">步驟1：安裝系統管理員工具及下載拓撲</span><span class="sxs-lookup"><span data-stu-id="6a6af-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="6a6af-120">在未安裝 Lync Ocscore.msi 或已安裝任何其他 Lync 元件的拓撲中，連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="6a6af-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="6a6af-121">從商務用 Skype Server 2015 安裝媒體，從 **OCS_Volume \setup\amd64** 執行 **Setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="6a6af-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="6a6af-122">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="6a6af-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="6a6af-123">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="6a6af-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="6a6af-124">在 [部署] 嚮導上，按一下 [ **安裝系統管理員工具**]，然後依照安裝的步驟進行安裝。</span><span class="sxs-lookup"><span data-stu-id="6a6af-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![部署嚮導的螢幕擷取畫面，其中包含稱為「安裝系統管理員」工具的連結。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="6a6af-126">在 Windows [開始] 畫面中，開啟 [商務用 Skype 伺服器拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="6a6af-127">按一下 [ **從現有的部署下載拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6a6af-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="6a6af-128">輸入拓撲的名稱，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="6a6af-129">移至您儲存拓撲的位置，並製作拓撲複本。</span><span class="sxs-lookup"><span data-stu-id="6a6af-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="6a6af-130">步驟2：使用拓撲產生器升級和發行拓撲</span><span class="sxs-lookup"><span data-stu-id="6a6af-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="6a6af-131">開始升級程式之前，所有服務必須針對您計畫升級的集區執行。</span><span class="sxs-lookup"><span data-stu-id="6a6af-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="6a6af-132">如此一來，拓撲變更將會複寫到集區中伺服器的本機資料庫。</span><span class="sxs-lookup"><span data-stu-id="6a6af-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="6a6af-133">在升級之前，請先儲存拓撲檔案的複本。</span><span class="sxs-lookup"><span data-stu-id="6a6af-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="6a6af-134">升級之後，您將無法降級拓撲。 > 如果您的服務與資料庫位於相同的伺服器上，如 Persistent Chat service 與 Persistent Chat 資料庫位於相同的伺服器上，請略過此步驟，然後移至步驟4。</span><span class="sxs-lookup"><span data-stu-id="6a6af-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="6a6af-135">停止服務之後，請在每部伺服器上執行 In-Place 升級設定，以升級本機資料庫。</span><span class="sxs-lookup"><span data-stu-id="6a6af-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a6af-136">如果拓撲具有鏡像的後端資料庫，當您使用拓撲產生器 **發行拓撲時** ，您會看到主體和鏡像資料庫都會顯示。</span><span class="sxs-lookup"><span data-stu-id="6a6af-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="6a6af-137">請確定主體上的所有資料庫都在執行中，並只在發行拓撲時選取主體，而不是鏡像，否則您會在發行拓撲之後看到一則警告。</span><span class="sxs-lookup"><span data-stu-id="6a6af-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="6a6af-138">選擇下列其中一個選項，透過使用商務用 Skype Server 2015 拓撲產生器升級及發行新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6a6af-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="6a6af-139">完成步驟併發行更新後的拓撲之後，請移至本主題中的步驟3。</span><span class="sxs-lookup"><span data-stu-id="6a6af-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="6a6af-140">選項1：升級隔離的前端集區和相關聯的封存與監控存放區</span><span class="sxs-lookup"><span data-stu-id="6a6af-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="6a6af-141">如果您要升級的集區有封存與監控存放區相依性，當您使用下列步驟時，也會升級封存與監控存放區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="6a6af-142">在 [拓撲產生器] 中，以滑鼠右鍵按一下 [Lync Server 2013 集區]，然後選取 [ **升級為商務用 Skype Server 2015**]，然後依照步驟執行。</span><span class="sxs-lookup"><span data-stu-id="6a6af-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![具有 Lync Server 2013 升級選項的右擊功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="6a6af-144">在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![[動作] 功能表的螢幕擷取畫面，具有拓撲產生器的 [發行拓撲] 選項。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="6a6af-146">在發佈過程中，請選擇在封存與監控存放區上安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="6a6af-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="6a6af-147">選項2：升級前端集區，但不升級封存與監控存放區</span><span class="sxs-lookup"><span data-stu-id="6a6af-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="6a6af-148">如果您使用下列步驟，將會停用所選集區的封存和監控。</span><span class="sxs-lookup"><span data-stu-id="6a6af-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="6a6af-149">在升級後，集區將不會有封存和監控存放區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="6a6af-150">在 [拓撲產生器] 中，選取您要升級的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="6a6af-151">移除 Lync Server 2013 封存與監控存放區的相依性。</span><span class="sxs-lookup"><span data-stu-id="6a6af-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="6a6af-152">移至 [**動作**] [  >  **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="6a6af-153">清除 [ **封存** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-153">Clear the **Archiving** check box.</span></span>
    
     ![[編輯內容] 對話方塊上的 [封存的螢幕擷取畫面] 核取方塊。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="6a6af-155">清除 [ **監視** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-155">Clear the **Monitoring** check box.</span></span>
    
     ![[編輯內容] 對話方塊的螢幕擷取畫面，showsr 監視] 核取方塊。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="6a6af-157">以滑鼠右鍵按一下 [Lync Server 2013 集區]，然後選取 [ **升級為商務用 Skype Server 2015**]，然後依照步驟執行。</span><span class="sxs-lookup"><span data-stu-id="6a6af-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![具有 Lync Server 2013 升級選項的右擊功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="6a6af-159">在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="6a6af-160">選項3：將前端集區和相關聯的更新至新的商務用 Skype Server 2015 封存與監控存放區</span><span class="sxs-lookup"><span data-stu-id="6a6af-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="6a6af-161">如果您使用下列步驟，封存和監控會停止在先前的存放區中，並在您建立的新存放區中開始。</span><span class="sxs-lookup"><span data-stu-id="6a6af-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="6a6af-162">在 [拓撲產生器] 中，選取您要升級的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="6a6af-163">移除 Lync Server 2013 封存與監控存放區的相依性。</span><span class="sxs-lookup"><span data-stu-id="6a6af-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="6a6af-164">移至 [**動作**] [  >  **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="6a6af-165">清除 [ **封存** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-165">Clear the **Archiving** check box.</span></span>
    
     ![[編輯內容] 對話方塊上的 [封存的螢幕擷取畫面] 核取方塊。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="6a6af-167">清除 [ **監視** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-167">Clear the **Monitoring** check box.</span></span>
    
     ![[編輯內容] 對話方塊的螢幕擷取畫面，showsr 監視] 核取方塊。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="6a6af-169">以滑鼠右鍵按一下 [Lync Server 2013 集區]，然後選取 [ **升級為商務用 Skype Server 2015**]，然後依照步驟執行。</span><span class="sxs-lookup"><span data-stu-id="6a6af-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![具有 Lync Server 2013 升級選項的右擊功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="6a6af-171">建立新的 SQL 存放區進行封存。</span><span class="sxs-lookup"><span data-stu-id="6a6af-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="6a6af-172">選取 [集區] 和 [**動作**  >  **編輯] 屬性**。</span><span class="sxs-lookup"><span data-stu-id="6a6af-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="6a6af-173">選取 [封存] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="6a6af-174">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-174">Click **New**.</span></span>
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面，顯示 [封存] 區段下的 [新增] 按鈕。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="6a6af-176">建立新的 SQL 存放區進行監視。</span><span class="sxs-lookup"><span data-stu-id="6a6af-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="6a6af-177">選取 [集區] 和 [**動作**  >  **編輯] 屬性**。</span><span class="sxs-lookup"><span data-stu-id="6a6af-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="6a6af-178">選取 [ **監視** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="6a6af-179">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-179">Click **New**.</span></span>
    
     ![[編輯內容] 對話方塊的螢幕擷取畫面，顯示 [監視] 區段下的 [新增] 按鈕。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="6a6af-181">在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="6a6af-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="6a6af-182">在發佈過程中，請選擇在新的封存與監控存放區上安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="6a6af-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="6a6af-183">步驟3：等候複寫</span><span class="sxs-lookup"><span data-stu-id="6a6af-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="6a6af-184">將更新的拓撲發佈至環境中的所有伺服器，提供複寫一段時間。</span><span class="sxs-lookup"><span data-stu-id="6a6af-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="6a6af-185">步驟4：停止要升級集區中的所有服務</span><span class="sxs-lookup"><span data-stu-id="6a6af-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="6a6af-186">在服務集區的每一部伺服器上，執行您要升級的下列 Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6a6af-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="6a6af-187">我們建議使用 Disable-CsComputer，因為在 In-Place 升級程式期間，您可能需要重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="6a6af-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="6a6af-188">如果您使用 Stop-CsWindowsService，一些服務可能會在重新開機後自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="6a6af-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="6a6af-189">這可能會造成 In-Place 升級失敗。</span><span class="sxs-lookup"><span data-stu-id="6a6af-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="6a6af-190">步驟5：升級前端集區和非前端集區伺服器</span><span class="sxs-lookup"><span data-stu-id="6a6af-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="6a6af-191">在升級之前，請安裝商務用 Skype Server 2015 所需的所有新必要條件，其中包括：在嘗試升級之前，請先 > 至少32GB 可用空間。</span><span class="sxs-lookup"><span data-stu-id="6a6af-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="6a6af-192">此外，請確定磁片磁碟機是固定的本機磁片磁碟機，未以 NTFS 檔案系統格式化，否則請以 NTFS 檔案系統格式化。不會壓縮，也不會包含頁面檔案。 > PowerShell 版本6.2.9200.0 或更新版本。 > 已安裝最新的 Lync Server 2013 累計更新。 > SQL Server 2012 SP1 已安裝。 > 使用 Microsoft Update (，會自動安裝下列 KB 安裝的) ： > windows server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windows Server 2012 r2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="6a6af-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="6a6af-193">在每一部伺服器上使用 In-Place 升級，以更新前端集區、Edge 集區、轉送伺服器及 Persistent Chat 集區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="6a6af-194">在每一部伺服器上，在商務用 Skype Server 2015 安裝媒體上的 **OCS_Volume \setup\amd64** 中執行 **Setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="6a6af-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="6a6af-195">接受授權合約，並遵循 In-Place 升級的提示。</span><span class="sxs-lookup"><span data-stu-id="6a6af-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="6a6af-196">針對前端集區和每個非前端集區伺服器上的每一部伺服器，重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="6a6af-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a6af-197">在 In-Place 升級期間，系統可能會提示您重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="6a6af-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="6a6af-198">沒關係。</span><span class="sxs-lookup"><span data-stu-id="6a6af-198">That's ok.</span></span> <span data-ttu-id="6a6af-199">重新開機之後，In-Place 升級將從其離開的位置繼續。</span><span class="sxs-lookup"><span data-stu-id="6a6af-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="6a6af-200">In-Place 升級順利完成時，您會看到下列訊息。</span><span class="sxs-lookup"><span data-stu-id="6a6af-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![顯示就地升級的螢幕擷取畫面成功完成。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="6a6af-202">步驟6：在所有已升級的伺服器上重新開機服務</span><span class="sxs-lookup"><span data-stu-id="6a6af-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="6a6af-203">重新開機服務之前，請確定所有前端伺服器上都不存在%ProgramData%\WindowsFabric。</span><span class="sxs-lookup"><span data-stu-id="6a6af-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="6a6af-204">若存在，請先將它刪除，然後再啟動服務。</span><span class="sxs-lookup"><span data-stu-id="6a6af-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="6a6af-205">在您升級前端集區中的所有伺服器後，請使用下列 PowerShell 命令重新開機服務：</span><span class="sxs-lookup"><span data-stu-id="6a6af-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="6a6af-206">如果在開始執行 In-Place 升級之前，需要重新開機待處理的系統，則 In-Place 升級會在安裝結束時要求重新開機。</span><span class="sxs-lookup"><span data-stu-id="6a6af-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="6a6af-207">當您嘗試使用 Start-CSPool Cmdlet 啟動服務時，會針對第一部前端伺服器引發某些元件例外狀況。</span><span class="sxs-lookup"><span data-stu-id="6a6af-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="6a6af-208">若要解決這些錯誤，請重新開機集區中的所有伺服器，然後再次執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6a6af-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="6a6af-209">在非前端集區伺服器上，使用下列命令重新開機服務：</span><span class="sxs-lookup"><span data-stu-id="6a6af-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="6a6af-210">在 [In-Place 升級] 頁面上按一下 **[確定]** 之後，您將會看到下列提醒來完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="6a6af-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![螢幕擷取畫面，顯示就地升級順利完成之後的後續步驟。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="6a6af-212">步驟7：驗證商務用 Skype 功能運作</span><span class="sxs-lookup"><span data-stu-id="6a6af-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="6a6af-213">若要確定升級成功，針對已升級的集區，請測試商務用 Skype，以確定功能如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="6a6af-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="6a6af-214">步驟8：升級輔助集區</span><span class="sxs-lookup"><span data-stu-id="6a6af-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="6a6af-215">重複本主題中的步驟，以升級環境中所具備的任何其他集區。</span><span class="sxs-lookup"><span data-stu-id="6a6af-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="6a6af-216">疑難排解 In-Place 升級的問題</span><span class="sxs-lookup"><span data-stu-id="6a6af-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="6a6af-217">如果 In-Place 升級失敗，您可能會看到類似下列圖像中的訊息。</span><span class="sxs-lookup"><span data-stu-id="6a6af-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![顯示就地升級失敗的螢幕擷取畫面，因為未安裝必要的累計更新。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="6a6af-219">複查頁面底部的完整訊息，以協助您疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="6a6af-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="6a6af-220">按一下 [ **查看記錄** 檔] 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6a6af-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="6a6af-221">如果 In-Place 升級失敗若要 **驗證升級準備情況** 或 **安裝遺漏的必要條件**，請確定伺服器已套用所有的 Windows server、Lync server 和 SQL server 更新，且已安裝所有必要的軟體和角色。</span><span class="sxs-lookup"><span data-stu-id="6a6af-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="6a6af-222">如需必要的清單，請參閱 [商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 以及 [商務用 skype Server 2015 的安裝必要條件](install/install-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6af-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a6af-223">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6a6af-223">See also</span></span>

[<span data-ttu-id="6a6af-224">規劃升級至商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a6af-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="6a6af-225">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="6a6af-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="6a6af-226">安裝商務用 Skype Server 2015 的必要條件</span><span class="sxs-lookup"><span data-stu-id="6a6af-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="6a6af-227">安裝商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a6af-227">Install Skype for Business Server 2015</span></span>](install/install.md)
