---
title: Lync Server 2013：升級或更新前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2019
ms.locfileid: "40974421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="0b2fe-102">在 Lync Server 2013 中升級或更新前端伺服器</span><span class="sxs-lookup"><span data-stu-id="0b2fe-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b2fe-103">_**主題上次修改日期：** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="0b2fe-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="0b2fe-104">企業版池中的前端伺服器會組織成*升級網域*。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="0b2fe-105">這些是池中的前端伺服器子集。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="0b2fe-106">升級網域是由拓撲產生器自動建立。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="0b2fe-107">當您升級伺服器時，您必須一次升級一個網域。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="0b2fe-108">將每個伺服器放在一個升級網域中，將其升級後再重新開機，然後再移至另一個升級網域。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="0b2fe-109">請務必追蹤目前已升級的升級網域和伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="0b2fe-110">升級每個伺服器時，請使用下列流程圖圖表。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-110">Use the following flowchart diagram when upgrading each server.</span></span>

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="升級或更新前端伺服器":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="0b2fe-112">在池中將升級套用到前端伺服器</span><span class="sxs-lookup"><span data-stu-id="0b2fe-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="0b2fe-113">在池中的前端伺服器上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0b2fe-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="0b2fe-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="0b2fe-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="0b2fe-115">如果*PoolUpgradeState*的值為 [**忙碌**]，請等候10分鐘，然後再次嘗試**CsPoolUpgradeReadinessState** 。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="0b2fe-116">如果您至少在每次嘗試之間有10分鐘後再看到 [**忙碌**]，或者如果您看到**PoolUpgradeState**的任何**InsufficientActiveFrontEnds**結果，則該池有問題。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="0b2fe-117">如果這個池與災害復原拓朴中的另一個前端池成對，您應該將該池失敗轉移至 [備份] 池，然後更新此池中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="0b2fe-118">如需詳細資訊，請參閱[在 Lync Server 2013 中轉移池失敗](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="0b2fe-119">如果*PoolUpgradeState*的值已**準備好**，請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="0b2fe-120">**CsPoolUpgradeReadinessState** Cmdlet 也會傳回有關池中每個升級網域的相關資訊，以及每個升級網域中的最上層端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="0b2fe-121">如果包含您要升級之伺服器或伺服器的升級網域的**ReadyforUpgrade**值為**True** ，您就可以立即安全地升級這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="0b2fe-122">若要這樣做，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0b2fe-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="0b2fe-123">停止使用`Stop-CsWindowsService -Graceful -Verbose` Cmdlet 來升級到前端伺服器的新連線。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0b2fe-124">如果您在排程的伺服器停機期間執行這些伺服器升級，您可以執行此不含 '-<STRONG>寬容</STRONG>」參數的 Cmdlet，如下所示：<STRONG>停止 CsWindowsService</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="0b2fe-125">這會立即關閉服務，而不需要填寫所有現有的服務要求。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="0b2fe-126">升級與此升級網域相關聯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="0b2fe-127">重新開機伺服器，並確認他們接受新的連線。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="0b2fe-128">針對池中的其他每個升級網域重複步驟1和2，直到所有前端伺服器都已升級為止。</span><span class="sxs-lookup"><span data-stu-id="0b2fe-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

