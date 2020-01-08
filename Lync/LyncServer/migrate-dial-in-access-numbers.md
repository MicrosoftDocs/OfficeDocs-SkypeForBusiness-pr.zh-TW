---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="74556-102">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="74556-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74556-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="74556-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="74556-104">若要將電話撥入存取號碼從 Lync Server 2010 移植到 Lync Server 2013，必須執行**CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="74556-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="74556-105">在 lync Server 2010 和 Lync Server 2013 共存期間，您在 Lync Server 2013 中建立的撥入存取號碼與您在 Lync Server 2010 中建立的撥入存取號碼類似，如本節中所述。</span><span class="sxs-lookup"><span data-stu-id="74556-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="74556-106">您在 Lync Server 2010 中建立的撥入號碼，但移至 lync server 2013，或在遷移期間或之後，您在使用前或之後在 Lync Server 2013 中建立的電話：</span><span class="sxs-lookup"><span data-stu-id="74556-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="74556-107">不會出現在 Office 通訊伺服器 2007 R2 會議邀請和 [撥入存取號碼] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="74556-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="74556-108">出現在 Lync Server 2010 會議邀請和 [撥入存取號碼] 頁面。</span><span class="sxs-lookup"><span data-stu-id="74556-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="74556-109">出現在 Lync Server 2013 會議邀請和 [撥入存取號碼] 頁面。</span><span class="sxs-lookup"><span data-stu-id="74556-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="74556-110">無法在 Office 通訊伺服器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="74556-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="74556-111">您可以在 Lync Server 2010 [控制台] 和 Lync Server 2010 管理命令介面中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="74556-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="74556-112">您可以在 Lync Server 2013 [控制台] 和 Lync Server 2013 管理命令介面中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="74556-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="74556-113">可在區域內使用 CsDialinConferencingAccessNumber Cmdlet 與 Priority 參數重新排序。</span><span class="sxs-lookup"><span data-stu-id="74556-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="74556-114">在您解除 Lync Server 2010 池之前，您必須先完成指向 Lync Server 2010 池的撥入存取號碼的遷移。</span><span class="sxs-lookup"><span data-stu-id="74556-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="74556-115">如果您沒有完成撥入存取號碼遷移，請參閱以下程式中所述的接入號碼來電將會失敗。</span><span class="sxs-lookup"><span data-stu-id="74556-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74556-116">您必須先執行此程式，然後才能解除 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="74556-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="74556-117">我們建議您在網路使用量較低時移動撥入存取號碼（如果有短暫的服務停機時間）。</span><span class="sxs-lookup"><span data-stu-id="74556-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="74556-118">**識別及移動撥入存取號碼**</span><span class="sxs-lookup"><span data-stu-id="74556-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="74556-119">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="74556-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="74556-120">若要將每個撥入存取號碼移至 Lync Server 2013 上託管的池中，請從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="74556-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="74556-121">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="74556-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="74556-122">在左側導覽列中，按一下 [**會議**]。</span><span class="sxs-lookup"><span data-stu-id="74556-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="74556-123">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="74556-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="74556-124">確認您要從中遷移的 Lync Server 2010 pool 不會保留撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="74556-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74556-125">當所有撥入存取號碼都指向 Lync Server 2013 池時，您就可以解除 Lync Server 2010 池的授權。</span><span class="sxs-lookup"><span data-stu-id="74556-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="74556-126">**使用 Lync Server [控制台] 驗證撥入存取號碼遷移**</span><span class="sxs-lookup"><span data-stu-id="74556-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="74556-127">從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="74556-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74556-128">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="74556-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="74556-129">在左側導覽列中，按一下 [**會議**]。</span><span class="sxs-lookup"><span data-stu-id="74556-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="74556-130">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="74556-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="74556-131">確認所有撥入存取號碼都已遷移至 Lync Server 2013 上託管的池中。</span><span class="sxs-lookup"><span data-stu-id="74556-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="74556-132">**使用 Lync Server 管理命令介面驗證撥入存取號碼遷移**</span><span class="sxs-lookup"><span data-stu-id="74556-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="74556-133">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="74556-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="74556-134">若要從命令列中傳回已轉移的所有電話撥入式會議存取電話號碼，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="74556-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="74556-135">確認所有撥入存取號碼都已遷移至 Lync Server 2013 上託管的池中。</span><span class="sxs-lookup"><span data-stu-id="74556-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

