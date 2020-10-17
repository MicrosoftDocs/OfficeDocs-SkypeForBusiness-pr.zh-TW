---
title: Lync Server 2013：升級或更新前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530320"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="dc653-102">在 Lync Server 2013 中升級或更新前端伺服器</span><span class="sxs-lookup"><span data-stu-id="dc653-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc653-103">_**主題上次修改日期：** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="dc653-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="dc653-104">Enterprise Edition 集區中的前端伺服器會組織成 *升級網域*。</span><span class="sxs-lookup"><span data-stu-id="dc653-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="dc653-105">這些是集區中的前端伺服器的子集。</span><span class="sxs-lookup"><span data-stu-id="dc653-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="dc653-106">升級網域是透過拓撲產生器自動建立的。</span><span class="sxs-lookup"><span data-stu-id="dc653-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="dc653-107">當您升級伺服器時，您必須一次執行一個升級網域。</span><span class="sxs-lookup"><span data-stu-id="dc653-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="dc653-108">將每一部伺服器放在一個升級網域中，進行升級，然後重新開機，再移至另一個升級網域。</span><span class="sxs-lookup"><span data-stu-id="dc653-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="dc653-109">請務必追蹤迄今為止已升級的升級網域和伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc653-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="dc653-110">在升級每一部伺服器時，請使用下列流程圖圖表。</span><span class="sxs-lookup"><span data-stu-id="dc653-110">Use the following flowchart diagram when upgrading each server.</span></span>

![升級或更新前端伺服器](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="dc653-112">將升級套用至集區中的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="dc653-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="dc653-113">在集區中的前端伺服器上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dc653-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="dc653-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="dc653-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="dc653-115">如果 *PoolUpgradeState* 的值 **占線**，請等候10分鐘，然後再 **Get-CsPoolUpgradeReadinessState** 一次。</span><span class="sxs-lookup"><span data-stu-id="dc653-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="dc653-116">如果您在每次嘗試之間等候10分鐘之後，又至少看到三次**繁忙**，或是您看到**PoolUpgradeState** **的任何**結果，則集區發生問題。</span><span class="sxs-lookup"><span data-stu-id="dc653-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="dc653-117">如果此集區與嚴重損壞修復拓撲中的另一個前端集區配對，您應該將集區失敗至備份組區，然後更新此集區中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc653-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="dc653-118">如需詳細資訊，請參閱 [在 Lync Server 2013 中容錯移轉集](lync-server-2013-failing-over-a-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="dc653-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="dc653-119">如果 *PoolUpgradeState* 的值已 **準備好**，請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="dc653-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="dc653-120">**Get-CsPoolUpgradeReadinessState** Cmdlet 也會傳回集區中每個升級網域的相關資訊，以及每個升級網域中的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc653-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="dc653-121">如果包含您要升級之伺服器或伺服器的升級網域， **ReadyforUpgrade** 值為 **True** ，您就可以立即安全升級這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc653-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="dc653-122">若要這麼做，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dc653-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="dc653-123">使用 Cmdlet，停止與您要升級的前端伺服器的新連線 `Stop-CsWindowsService -Graceful -Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="dc653-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dc653-124">若要在排程的伺服器停機期間執行這些伺服器升級，您可以執行此指令程式，但不含 '-<STRONG>寬容</STRONG>」參數，如下所示： <STRONG>Stop-CsWindowsService</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dc653-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="dc653-125">這會立即關閉服務，而不會等候所有現有的服務要求填滿。</span><span class="sxs-lookup"><span data-stu-id="dc653-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="dc653-126">升級與此升級網域相關聯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc653-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="dc653-127">重新開機伺服器，確定他們接受新的連線。</span><span class="sxs-lookup"><span data-stu-id="dc653-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="dc653-128">針對集區中的每個其他升級網域重複步驟1和2，直到所有前端伺服器都升級為止。</span><span class="sxs-lookup"><span data-stu-id="dc653-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

