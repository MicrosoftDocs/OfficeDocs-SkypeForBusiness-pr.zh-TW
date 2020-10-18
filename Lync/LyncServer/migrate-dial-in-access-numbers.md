---
title: 移轉撥入存取號碼
description: 遷移撥入存取號碼。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c8bd34a30bc4b3f8999144cd84a1eee62e2ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579319"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="78caf-103">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="78caf-103">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78caf-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="78caf-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="78caf-105">將撥入存取號碼從 Lync Server 2010 遷移至 Lync Server 2013 需要執行 **Move-CsApplicationEndpoint** Cmdlet 以遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="78caf-105">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="78caf-106">在 Lync Server 2010 和 Lync Server 2013 共存期間內，您在 Lync Server 2013 中建立的撥入存取號碼，與您在 Lync Server 2010 中所建立的撥入存取號碼類似，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="78caf-106">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="78caf-107">您在 Lync Server 2010 中建立的撥入存取號碼，但是會移至 Lync Server 2013，或在遷移期間或之後，您2013在遷移期間或之後所建立的撥入存取號碼具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="78caf-107">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="78caf-108">不會出現在 Office 通訊伺服器 2007 R2 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="78caf-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="78caf-109">會出現在 Lync Server 2010 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="78caf-109">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="78caf-110">會出現在 Lync Server 2013 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="78caf-110">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="78caf-111">無法在 Office 通訊伺服器 2007 R2 系統管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="78caf-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="78caf-112">可在 Lync Server 2010 控制台和 Lync Server 2010 管理命令介面中查看及修改。</span><span class="sxs-lookup"><span data-stu-id="78caf-112">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="78caf-113">可在 Lync Server 2013 控制台和 Lync Server 2013 管理命令介面中查看及修改。</span><span class="sxs-lookup"><span data-stu-id="78caf-113">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="78caf-114">可以使用具有 Priority 參數的 Set-CsDialinConferencingAccessNumber Cmdlet，在地區內重新排序。</span><span class="sxs-lookup"><span data-stu-id="78caf-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="78caf-115">在解除委任 Lync Server 2010 集區之前，您必須完成指向 Lync Server 2010 集區的撥入存取號碼遷移。</span><span class="sxs-lookup"><span data-stu-id="78caf-115">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="78caf-116">如果您未完成撥入存取號碼遷移（如下列程式所述），則對存取號碼的來電將會失敗。</span><span class="sxs-lookup"><span data-stu-id="78caf-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78caf-117">您必須在解除委任 Lync Server 2010 集區之前執行此程式。</span><span class="sxs-lookup"><span data-stu-id="78caf-117">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="78caf-118">建議您在網路使用量很低時移動撥入存取號碼，以防出現短時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="78caf-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="78caf-119">**識別並移動撥入存取號碼**</span><span class="sxs-lookup"><span data-stu-id="78caf-119">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="78caf-120">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="78caf-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="78caf-121">若要將每個撥入存取號碼移至主控于 Lync Server 2013 的集區，請從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="78caf-121">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="78caf-122">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="78caf-122">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="78caf-123">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="78caf-123">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="78caf-124">按一下 [ **撥入存取號碼** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="78caf-124">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="78caf-125">確認您要遷移的 Lync Server 2010 集區中，是否仍然保留任何撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="78caf-125">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78caf-126">當所有撥入存取號碼指向 Lync Server 2013 集區時，即可解除委任 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="78caf-126">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="78caf-127">**使用 Lync Server 控制台驗證撥入存取號碼遷移**</span><span class="sxs-lookup"><span data-stu-id="78caf-127">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="78caf-128">從指派給 **CsUserAdministrator** 角色或 **CsAdministrator** 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78caf-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78caf-129">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="78caf-129">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="78caf-130">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="78caf-130">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="78caf-131">按一下 [ **撥入存取號碼** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="78caf-131">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="78caf-132">確認所有撥入存取號碼都已遷移至 Lync Server 2013 上裝載的集區。</span><span class="sxs-lookup"><span data-stu-id="78caf-132">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="78caf-133">**使用 Lync Server 管理命令介面來驗證撥入存取號碼遷移**</span><span class="sxs-lookup"><span data-stu-id="78caf-133">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="78caf-134">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="78caf-134">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="78caf-135">若要傳回已遷移的所有電話撥入式會議存取號碼，請從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="78caf-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="78caf-136">確認所有撥入存取號碼都已遷移至 Lync Server 2013 上主控的集區。</span><span class="sxs-lookup"><span data-stu-id="78caf-136">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

