---
title: Lync Server 2013：部署成對的前端集區以進行嚴重損壞修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309c8f7ac7da4e40f2b16e5d13015330b2d9b611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514521"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="940c7-102">在 Lync Server 2013 中為嚴重損壞修復部署成對的前端集區</span><span class="sxs-lookup"><span data-stu-id="940c7-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="940c7-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="940c7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="940c7-104">您可以使用拓撲產生器，輕鬆地部署成對前端集區的嚴重損壞修復拓撲。</span><span class="sxs-lookup"><span data-stu-id="940c7-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="940c7-105">部署一對前端集區</span><span class="sxs-lookup"><span data-stu-id="940c7-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="940c7-106">如果集區是新的，且尚未定義，請使用拓撲產生器建立集區。</span><span class="sxs-lookup"><span data-stu-id="940c7-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="940c7-107">在 [拓撲產生器] 中，以滑鼠右鍵按一下兩個集區中的其中一個，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="940c7-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="940c7-108">按一下左窗格中的 [恢復]\*\*\*\*，然後選取右窗格中的 [關聯的備份集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="940c7-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="940c7-p101">在下方 [關聯的備份集區]\*\*\*\* 中，選取您要與此集區配對的集區。您僅能選取尚未與其他集區配對的現有集區。</span><span class="sxs-lookup"><span data-stu-id="940c7-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="940c7-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="940c7-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="940c7-112">選取 [語音自動容錯移轉和容錯回復]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="940c7-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="940c7-113">現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復]\*\*\*\* 中顯示關聯的集區。</span><span class="sxs-lookup"><span data-stu-id="940c7-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="940c7-114">使用拓撲產生器發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="940c7-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="940c7-p102">若尚未部署這兩個集區，請立即部署，以完成組態。您可在此程序中略過最後這兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="940c7-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="940c7-117">然而，若在您定義成對關聯之前，就已部署了集區，您就必須完成下列兩個最後步驟。</span><span class="sxs-lookup"><span data-stu-id="940c7-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="940c7-118">在兩個集區中的每部前端伺服器上，執行下列項目：</span><span class="sxs-lookup"><span data-stu-id="940c7-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="940c7-119">這會設定使備份配對順利運作所需的其他服務。</span><span class="sxs-lookup"><span data-stu-id="940c7-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="940c7-120">從 Lync Server 管理命令介面命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="940c7-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="940c7-121">使用下列 Cmdlet，強制兩個集區的使用者及會議資料互相進行同步處理：</span><span class="sxs-lookup"><span data-stu-id="940c7-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="940c7-122">同步處理資料可能需要花費一些時間。</span><span class="sxs-lookup"><span data-stu-id="940c7-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="940c7-123">您可以使用下列 Cmdlet 檢查狀態。</span><span class="sxs-lookup"><span data-stu-id="940c7-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="940c7-124">請確定這兩個方向的狀態為穩定狀態。</span><span class="sxs-lookup"><span data-stu-id="940c7-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="940c7-125">[！注意事項] 的 <STRONG>自動容錯移轉和容錯回復</STRONG> ] 選項和拓撲產生器中相關聯的時間間隔，只適用于 Lync Server 2010 中引進的語音恢復功能。</span><span class="sxs-lookup"><span data-stu-id="940c7-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="940c7-126">選取此選項不表示會自動使用本文件中討論的集區容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="940c7-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="940c7-127">集區容錯移轉和容錯回復一律需要管理員以手動方式分別呼叫容錯移轉和容錯回復 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="940c7-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

