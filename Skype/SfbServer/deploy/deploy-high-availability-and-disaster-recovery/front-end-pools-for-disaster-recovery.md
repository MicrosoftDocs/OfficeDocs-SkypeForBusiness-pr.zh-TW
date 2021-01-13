---
title: 在商務用 Skype Server 中部署用於嚴重損壞修復的配對前端集區
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
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可以決定使用成對的前端集區來提供嚴重損壞修復保護，但這不是必要條件。
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830603"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="23b40-103">在商務用 Skype Server 中部署用於嚴重損壞修復的配對前端集區</span><span class="sxs-lookup"><span data-stu-id="23b40-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="23b40-104">您可以決定使用成對的前端集區來提供嚴重損壞修復保護，但這不是必要條件。</span><span class="sxs-lookup"><span data-stu-id="23b40-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="23b40-105">您可以使用拓撲產生器，輕鬆地部署成對前端集區的嚴重損壞修復拓撲。</span><span class="sxs-lookup"><span data-stu-id="23b40-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="23b40-106">部署一對前端集區</span><span class="sxs-lookup"><span data-stu-id="23b40-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="23b40-107">如果集區是新的，且尚未定義，請使用拓撲產生器建立集區。</span><span class="sxs-lookup"><span data-stu-id="23b40-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="23b40-108">在 [拓撲產生器] 中，以滑鼠右鍵按一下兩個集區中的其中一個，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="23b40-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="23b40-109">按一下左窗格中的 [恢復]，然後選取右窗格中的 [關聯的備份集區]。</span><span class="sxs-lookup"><span data-stu-id="23b40-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="23b40-p101">在下方 [關聯的備份集區] 中，選取您要與此集區配對的集區。您僅能選取尚未與其他集區配對的現有集區。</span><span class="sxs-lookup"><span data-stu-id="23b40-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="23b40-112">選取 [語音自動容錯移轉和容錯回復]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="23b40-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="23b40-113">現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復] 中顯示關聯的集區。</span><span class="sxs-lookup"><span data-stu-id="23b40-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="23b40-114">使用拓撲產生器發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="23b40-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="23b40-115">若尚未部署這兩個集區，請立即部署，以完成組態。</span><span class="sxs-lookup"><span data-stu-id="23b40-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="23b40-116">您可以略過此過程的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="23b40-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="23b40-117">不過，如果集區已經部署，您必須先完成下列最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="23b40-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="23b40-118">在兩個集區中的每部前端伺服器上，執行下列項目：</span><span class="sxs-lookup"><span data-stu-id="23b40-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="23b40-119">這會設定使備份配對順利運作所需的其他服務。</span><span class="sxs-lookup"><span data-stu-id="23b40-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="23b40-120">在兩個集區中的每一部前端伺服器上，引導程式完成安裝備份配對所需的元件後，請務必重新套用先前在這兩個集區中的前端伺服器上套用的任何現有累計更新，然後繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="23b40-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="23b40-121">從商務用 Skype Server 管理命令介面命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="23b40-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="23b40-122">使用下列 Cmdlet，強制兩個集區的使用者和會議資料相互同步處理：</span><span class="sxs-lookup"><span data-stu-id="23b40-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="23b40-123">同步處理資料可能需要花費一些時間。</span><span class="sxs-lookup"><span data-stu-id="23b40-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="23b40-124">您可以使用下列 Cmdlet 檢查狀態。</span><span class="sxs-lookup"><span data-stu-id="23b40-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="23b40-125">請確定這兩個方向的狀態為穩定狀態。</span><span class="sxs-lookup"><span data-stu-id="23b40-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="23b40-126">[！注意事項] 的 **自動容錯移轉和容錯回復** ] 選項和拓撲產生器中相關聯的時間間隔，只適用于 Lync Server 所引進的語音恢復功能。</span><span class="sxs-lookup"><span data-stu-id="23b40-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="23b40-127">選取此選項不表示會自動使用本文件中討論的集區容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="23b40-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="23b40-128">集區容錯移轉和容錯回復一律需要管理員以手動方式分別呼叫容錯移轉和容錯回復 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23b40-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23b40-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23b40-129">See also</span></span>

[<span data-ttu-id="23b40-130">商務用 Skype Server 中的前端集區嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="23b40-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
