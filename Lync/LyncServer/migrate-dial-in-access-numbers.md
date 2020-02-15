---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a56dbb90c65bdbb4e26d289c289b6ccc9054d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="1f7a8-102">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="1f7a8-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f7a8-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="1f7a8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1f7a8-104">從 Lync Server 2010 移轉的撥入存取號碼，以 Lync Server 2013 需要執行**Move-csapplicationendpoint** cmdlet 來移轉連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="1f7a8-105">在 Lync Server 2010 和 Lync Server 2013 共存期間，您在 Lync Server 2013 中建立的撥入存取號碼的運作方式類似您在 Lync Server 2010 中建立的撥入存取號碼本節所述。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="1f7a8-106">找出您在 Lync Server 2010 中建立，但已移至 Lync Server 2013 或期間或之後移轉之前，Lync Server 2013 中建立的撥入存取號碼具備下列特性：</span><span class="sxs-lookup"><span data-stu-id="1f7a8-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="1f7a8-107">不會出現在 Office Communications Server 2007 R2 會議邀請及撥入存取號碼頁面。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="1f7a8-108">出現在 Lync Server 2010 會議邀請及撥入存取號碼頁面。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="1f7a8-109">出現在 Lync Server 2013 會議邀請及撥入存取號碼頁面。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="1f7a8-110">無法檢視或在 Office Communications Server 2007 R2 系統管理工具中修改。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="1f7a8-111">可檢視及修改 Lync Server 2010 控制台和以 Lync Server 2010 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="1f7a8-112">可檢視及修改 Lync Server 2013 控制台和以 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="1f7a8-113">可以進行重新排序的區域內使用 Set-csdialinconferencingaccessnumber cmdlet 搭配 Priority 參數。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="1f7a8-114">您必須完成移轉撥入存取號碼，指向 [Lync Server 2010 集區之前您解除委任 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="1f7a8-115">如果您未完成下列程序所述撥入存取號碼移轉，將會失敗的存取號碼的傳入呼叫。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f7a8-116">您必須執行此程序在解除委任 Lync Server 2010 集區之前。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1f7a8-117">我們建議您在網路使用量較低，以防沒有在短時間內服務中斷時移動撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="1f7a8-118">**識別及移動撥入存取號碼**</span><span class="sxs-lookup"><span data-stu-id="1f7a8-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="1f7a8-119">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1f7a8-120">若要將每組撥入存取號碼移至 Lync Server 2013 上裝載的集區，從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="1f7a8-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="1f7a8-121">開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="1f7a8-122">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="1f7a8-123">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="1f7a8-124">不確認您要從中移轉的 Lync Server 2010 集區無任何撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f7a8-125">當所有撥入存取號碼都移至 Lync Server 2013 集區時，您即可解除委任 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="1f7a8-126">**撥入存取號碼使用驗證移轉的 Lync Server Control Panel**</span><span class="sxs-lookup"><span data-stu-id="1f7a8-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="1f7a8-127">指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1f7a8-128">開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1f7a8-129">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="1f7a8-130">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="1f7a8-131">確認所有撥入存取號碼均已移轉至 Lync Server 2013 上裝載的集區。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="1f7a8-132">**撥入存取號碼使用驗證移轉的 Lync Server 管理命令介面**</span><span class="sxs-lookup"><span data-stu-id="1f7a8-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="1f7a8-133">開啟 [Lync Server 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1f7a8-134">若要傳回所有撥入式會議存取號碼移轉，從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="1f7a8-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="1f7a8-135">確認所有撥入存取號碼將會都移轉至 Lync Server 2013 上裝載的集區。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

