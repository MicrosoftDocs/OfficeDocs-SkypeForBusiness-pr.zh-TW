---
title: 將多個使用者移至試驗集區
description: 將多個使用者移至試驗集區。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121509fbad863b0ce2d6cc9c7e9afaef360e2eb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571329"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="c71f1-103">將多個使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="c71f1-103">Move multiple users to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c71f1-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c71f1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c71f1-105">您可以使用 Lync server 2013 控制台或 Lync Server 2013 管理命令介面，將多個使用者從 Lync Server 2010 集區移至 Lync Server 2013 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="c71f1-105">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="c71f1-106">使用 Lync Server 2013 控制台移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="c71f1-106">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c71f1-107">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-107">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="c71f1-108">按一下 [ **使用者**]，按一下 [搜尋]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-108">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="c71f1-109">選取兩個要移至 Lync Server 2013 集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="c71f1-109">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c71f1-110">在此範例中，我們會將使用者移 Chen 陽和聖誕老人聖誕 Hansen。</span><span class="sxs-lookup"><span data-stu-id="c71f1-110">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="c71f1-111">![將使用者移至特定的註冊集區](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定的註冊集區")</span><span class="sxs-lookup"><span data-stu-id="c71f1-111">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="c71f1-112">從 [ **動作** ] 功能表中，選取 [ **將選取的使用者移至集**區]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-112">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="c71f1-113">從下拉式清單中，選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-113">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="c71f1-114">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71f1-114">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c71f1-115">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-115">Click OK.</span></span>
    
    <span data-ttu-id="c71f1-116">![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="c71f1-116">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="c71f1-117">確認使用者的 [ **報名者集** 區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="c71f1-117">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c71f1-118">使用 Lync Server 2013 管理命令介面移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="c71f1-118">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="c71f1-119">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-119">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c71f1-120">在命令列上輸入下列命令，並將**User1**和使用者2取代為您想要移動的特定使用者名稱，並將**集區 \_ FQDN** **取代為目的地**集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="c71f1-120">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="c71f1-121">在此範例中，我們會移動使用者 Hao Chen 和 Katie 約旦。</span><span class="sxs-lookup"><span data-stu-id="c71f1-121">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="c71f1-122">![PowerShell Get-CsUser Cmdlet 的範例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-CsUser Cmdlet 的範例")</span><span class="sxs-lookup"><span data-stu-id="c71f1-122">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="c71f1-123">在命令列上輸入下列命令</span><span class="sxs-lookup"><span data-stu-id="c71f1-123">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="c71f1-124">**註冊機構集**區的身分識別現在應該指向您在上一個步驟中指定為**集區 \_ FQDN**的集區。</span><span class="sxs-lookup"><span data-stu-id="c71f1-124">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="c71f1-125">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="c71f1-125">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="c71f1-126">重複步驟 **以驗證使用者2是否已移動** 。</span><span class="sxs-lookup"><span data-stu-id="c71f1-126">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="c71f1-127">![PowerShell Get-UsUser 識別指令程式的輸出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser 識別指令程式的輸出")</span><span class="sxs-lookup"><span data-stu-id="c71f1-127">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c71f1-128">使用 Lync Server 2013 管理命令介面同時移動所有使用者</span><span class="sxs-lookup"><span data-stu-id="c71f1-128">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="c71f1-129">在此範例中，所有使用者都已傳回 Lync Server 2010 集區 (pool01.contoso.net) 。</span><span class="sxs-lookup"><span data-stu-id="c71f1-129">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="c71f1-130">使用 Lync Server 2013 管理命令介面，我們會同時將所有使用者同時移至 Lync Server 2013 集區 (pool02.contoso.net) 。</span><span class="sxs-lookup"><span data-stu-id="c71f1-130">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="c71f1-131">開啟 [ **Lync Server 2013 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c71f1-131">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="c71f1-132">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c71f1-132">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="c71f1-133">![在管理命令介面中 PowerShell Cmdlet 及結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "在管理命令介面中 PowerShell Cmdlet 及結果")</span><span class="sxs-lookup"><span data-stu-id="c71f1-133">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="c71f1-134">接下來，針對其中一位試驗使用者執行 **Get-CsUser** 。</span><span class="sxs-lookup"><span data-stu-id="c71f1-134">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="c71f1-135">每個使用者的 **註冊區集** 區身分識別，都指向您 \_ 在上一個步驟中指定為「集區 FQDN」的集區。</span><span class="sxs-lookup"><span data-stu-id="c71f1-135">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="c71f1-136">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="c71f1-136">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="c71f1-137">此外，我們可以在 Lync Server 2013 控制台中查看使用者清單，並確認 [註冊機集區] 值現在是否指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c71f1-137">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="c71f1-138">![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")</span><span class="sxs-lookup"><span data-stu-id="c71f1-138">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

