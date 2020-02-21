---
title: 移動多位使用者至試驗集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81b5ad16b36063c217d90c4c8f1e8a2e7fa3c0ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="491b5-102">移動多位使用者至試驗集區</span><span class="sxs-lookup"><span data-stu-id="491b5-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="491b5-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="491b5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="491b5-104">您可以將多個使用者與 Lync Server 2010 集區移至 Lync Server 2013 試驗集區使用 Lync Server 2013 Control Panel] 或 [Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="491b5-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="491b5-105">若要使用 Lync Server 2013 Control Panel 移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="491b5-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="491b5-106">開啟**Lync Server 控制台**。</span><span class="sxs-lookup"><span data-stu-id="491b5-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="491b5-107">按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**。</span><span class="sxs-lookup"><span data-stu-id="491b5-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="491b5-108">選取您想要將移至 Lync Server 2013 集區的兩個使用者。</span><span class="sxs-lookup"><span data-stu-id="491b5-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="491b5-109">在這個範例中，我們會將使用者 Chen Yang 和聖誕老人 Hansen 移。</span><span class="sxs-lookup"><span data-stu-id="491b5-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="491b5-110">![將使用者移至特定註冊集區](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定註冊集區")</span><span class="sxs-lookup"><span data-stu-id="491b5-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="491b5-111">從 [**動作**] 功能表中，選取 [**移至集區選取的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="491b5-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="491b5-112">從下拉式清單中，選取 [Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="491b5-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="491b5-113">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="491b5-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="491b5-114">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="491b5-114">Click OK.</span></span>
    
    <span data-ttu-id="491b5-115">![移動使用者，目的地登錄器集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者，目的地登錄器集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="491b5-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="491b5-116">請確認使用者的 [**登錄器集區**] 欄現在包含 Lync Server 2013 集區，即表示使用者已成功移動。</span><span class="sxs-lookup"><span data-stu-id="491b5-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="491b5-117">若要使用 Lync Server 2013 管理命令介面時，移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="491b5-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="491b5-118">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="491b5-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="491b5-119">在命令列中，輸入下列命令，並使用您想要移動，並取代的特定使用者名稱取代**User1**和**User2** **集區\_FQDN**目的地集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="491b5-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="491b5-120">在這個範例中我們將會移動 Hao Chen 和 Katie Jordan 的使用者。</span><span class="sxs-lookup"><span data-stu-id="491b5-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="491b5-121">![PowerShell Get-csuser cmdlet 的範例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-csuser cmdlet 的範例")</span><span class="sxs-lookup"><span data-stu-id="491b5-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="491b5-122">在命令列上輸入下列命令</span><span class="sxs-lookup"><span data-stu-id="491b5-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="491b5-123">**登錄器集區**身分識別現在應指向您指定為集區**集區\_FQDN**在先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="491b5-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="491b5-124">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="491b5-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="491b5-125">重複步驟，以確認已移動**使用者 2** 。</span><span class="sxs-lookup"><span data-stu-id="491b5-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="491b5-126">![輸出的 PowerShell Get-UsUser 中-Identity 指令程式](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "輸出的 PowerShell Get-UsUser 中-Identity 指令程式")</span><span class="sxs-lookup"><span data-stu-id="491b5-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="491b5-127">若要使用 Lync Server 2013 管理命令介面同時移動所有使用者</span><span class="sxs-lookup"><span data-stu-id="491b5-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="491b5-128">在這個範例中，所有使用者都回到 Lync Server 2010 集區 (pool01.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="491b5-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="491b5-129">使用 Lync Server 2013 管理命令介面，我們會將所有使用者同時都移至 Lync Server 2013 集區 (pool02.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="491b5-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="491b5-130">開啟 [ **Lync Server 2013 管理命令介面**]。</span><span class="sxs-lookup"><span data-stu-id="491b5-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="491b5-131">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="491b5-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="491b5-132">![PowerShell cmdlet 與管理命令介面中的結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet 與管理命令介面中的結果")</span><span class="sxs-lookup"><span data-stu-id="491b5-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="491b5-133">接著，執行**Get-csuser**為一位試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="491b5-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="491b5-134">每位使用者的**登錄器集區**身分識別現在指向集區您指定為 「 集區\_FQDN 」 在先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="491b5-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="491b5-135">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="491b5-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="491b5-136">此外，我們可以在 Lync Server 2013 Control Panel 中檢視的使用者清單，並確認登錄器集區值現在指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="491b5-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="491b5-137">![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")</span><span class="sxs-lookup"><span data-stu-id="491b5-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

