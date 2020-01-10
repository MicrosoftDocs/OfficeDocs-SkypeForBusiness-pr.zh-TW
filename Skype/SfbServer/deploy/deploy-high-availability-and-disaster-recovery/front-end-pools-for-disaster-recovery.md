---
title: 在商務用 Skype Server 中部署已配對的前端池以進行災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可以決定使用成對的前端池來提供災害復原保護，但不需要這麼做。
ms.openlocfilehash: 73f7d7619efbfc82124507234ebea8ebbcf4a7e8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002903"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="402f2-103">在商務用 Skype Server 中部署已配對的前端池以進行災害復原</span><span class="sxs-lookup"><span data-stu-id="402f2-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="402f2-104">您可以決定使用成對的前端池來提供災害復原保護，但不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="402f2-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="402f2-105">您可以使用 [拓撲建立器] 輕鬆地部署成對的前端池災害復原拓撲。</span><span class="sxs-lookup"><span data-stu-id="402f2-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="402f2-106">部署一對前端池</span><span class="sxs-lookup"><span data-stu-id="402f2-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="402f2-107">如果池是新的且尚未定義，請使用拓撲產生器建立池。</span><span class="sxs-lookup"><span data-stu-id="402f2-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="402f2-108">在拓撲建立器中，以滑鼠右鍵按一下兩個池中的一個，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="402f2-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="402f2-109">按一下左窗格中的 [**復原**]，然後在右窗格中選取 [**關聯的備份池**]。</span><span class="sxs-lookup"><span data-stu-id="402f2-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="402f2-110">在 [關聯的**備份] 池**下方的方塊中，選取您要與此 pool 配對的池。</span><span class="sxs-lookup"><span data-stu-id="402f2-110">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool.</span></span> <span data-ttu-id="402f2-111">只有尚未與另一個池配對的現有池，才可以從中選取。</span><span class="sxs-lookup"><span data-stu-id="402f2-111">Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="402f2-112">選取 [**自動容錯移轉及語音回切**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="402f2-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="402f2-113">當您查看此池的詳細資料時，關聯的池現在會出現在右窗格中的 [**復原**] 底下。</span><span class="sxs-lookup"><span data-stu-id="402f2-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="402f2-114">使用拓撲產生器發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="402f2-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="402f2-115">如果兩個池尚未部署，請立即部署它們，設定就會完成。</span><span class="sxs-lookup"><span data-stu-id="402f2-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="402f2-116">您可以略過此程式中的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="402f2-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="402f2-117">不過，如果已在您定義成對關聯之前部署了池，您必須完成下列最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="402f2-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="402f2-118">在兩個池的每個前端伺服器上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="402f2-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="402f2-119">這會設定備份配對所需的其他服務才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="402f2-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="402f2-120">當引導程式在兩個池的每個前端伺服器上完成備份配對所需的元件安裝後，請務必重新套用先前在兩個池中的這些前端伺服器上套用的任何現有累計更新，然後再繼續下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="402f2-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="402f2-121">從商務用 Skype Server Management Shell 命令提示字元，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="402f2-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="402f2-122">使用下列 Cmdlet 強迫兩個池的使用者與會議資料彼此同步處理：</span><span class="sxs-lookup"><span data-stu-id="402f2-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="402f2-123">同步處理資料可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="402f2-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="402f2-124">您可以使用下列 Cmdlet 來檢查狀態。</span><span class="sxs-lookup"><span data-stu-id="402f2-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="402f2-125">確定兩個方向的狀態都是穩定的狀態。</span><span class="sxs-lookup"><span data-stu-id="402f2-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="402f2-126">[語音] 的 [**自動容錯移轉**] 和 [自動回復] 選項以及 [拓撲建立器] 中的關聯時間間隔，只適用于 Lync Server 中引入的語音復原功能。</span><span class="sxs-lookup"><span data-stu-id="402f2-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="402f2-127">選取此選項並不表示本檔中討論的 [池容錯移轉] 為 [自動]。</span><span class="sxs-lookup"><span data-stu-id="402f2-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="402f2-128">[池容錯移轉] 和 [回切] 總是需要系統管理員手動喚醒呼叫容錯移轉與回切 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="402f2-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="402f2-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="402f2-129">See also</span></span>

[<span data-ttu-id="402f2-130">商務用 Skype Server 中的前端池災害復原</span><span class="sxs-lookup"><span data-stu-id="402f2-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
