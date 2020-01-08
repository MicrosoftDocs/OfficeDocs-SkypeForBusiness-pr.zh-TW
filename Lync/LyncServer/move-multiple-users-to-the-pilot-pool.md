---
title: 將多個使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="c30a2-102">將多個使用者移至 [試驗] 池</span><span class="sxs-lookup"><span data-stu-id="c30a2-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c30a2-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c30a2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c30a2-104">您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將多個使用者從 Lync Server 2010 池中移至 Lync Server 2013 試驗區。</span><span class="sxs-lookup"><span data-stu-id="c30a2-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="c30a2-105">使用 Lync Server 2013 [控制台] 移動多個使用者</span><span class="sxs-lookup"><span data-stu-id="c30a2-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c30a2-106">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="c30a2-107">按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="c30a2-108">選取兩個您要移至 Lync Server 2013 池的使用者。</span><span class="sxs-lookup"><span data-stu-id="c30a2-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c30a2-109">在這個範例中，我們會將使用者唐到 [陽入] 和 [Claus Hansen]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="c30a2-110">![將使用者移至特定的註冊池](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定的註冊池")</span><span class="sxs-lookup"><span data-stu-id="c30a2-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="c30a2-111">從 [**動作**] 功能表中，選取 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="c30a2-112">從下拉式清單中，選取 [Lync Server 2013] 池。</span><span class="sxs-lookup"><span data-stu-id="c30a2-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="c30a2-113">按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c30a2-114">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-114">Click OK.</span></span>
    
    <span data-ttu-id="c30a2-115">[![移動使用者]、[目的地註冊機構池] 對話方塊][(images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者]、[目的地註冊員池] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="c30a2-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="c30a2-116">確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="c30a2-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c30a2-117">使用 Lync Server 2013 管理命令介面來移動多個使用者</span><span class="sxs-lookup"><span data-stu-id="c30a2-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="c30a2-118">開啟 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c30a2-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c30a2-119">在命令列中，輸入下列內容，並將 [ **User1** ] 和 [使用者 2] 替換為您想要**移動的特定**使用者名稱，並將 [**池\_FQDN** ] 取代為目的地池的名稱。</span><span class="sxs-lookup"><span data-stu-id="c30a2-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="c30a2-120">在這個範例中，我們會將使用者 Hao 唐和她約旦。</span><span class="sxs-lookup"><span data-stu-id="c30a2-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="c30a2-121">(images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Powershell move-csuser Cmdlet 範例") ![move-csuser Cmdlet]範例</span><span class="sxs-lookup"><span data-stu-id="c30a2-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="c30a2-122">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="c30a2-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="c30a2-123">**註冊機構池**標識現在應該指向您在上一個步驟中指定為 [ \*\* \_池 FQDN\*\* ] 的 [池]。</span><span class="sxs-lookup"><span data-stu-id="c30a2-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="c30a2-124">此身分識別的狀態會確認使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="c30a2-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="c30a2-125">重複步驟**以驗證您**的操作2已移動。</span><span class="sxs-lookup"><span data-stu-id="c30a2-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="c30a2-126">Powershell 取得![UsUser 身分識別 Cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "輸出的 Powershell UsUser 身分識別 Cmdlet")</span><span class="sxs-lookup"><span data-stu-id="c30a2-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c30a2-127">使用 Lync Server 2013 管理命令介面，同時移動所有使用者</span><span class="sxs-lookup"><span data-stu-id="c30a2-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="c30a2-128">在這個範例中，所有使用者都已傳回 Lync Server 2010 pool （pool01.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="c30a2-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="c30a2-129">使用 Lync Server 2013 管理命令介面時，我們會同時將所有使用者移至 Lync Server 2013 池（pool02.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="c30a2-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="c30a2-130">開啟**Lync Server 2013 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="c30a2-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="c30a2-131">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="c30a2-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="c30a2-132">![Powershell Cmdlet，並產生管理命令]介面(images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell Cmdlet，並產生管理命令")介面</span><span class="sxs-lookup"><span data-stu-id="c30a2-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="c30a2-133">接下來，針對其中一個試驗使用者執行**move-csuser** 。</span><span class="sxs-lookup"><span data-stu-id="c30a2-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="c30a2-134">每個使用者的**註冊機構池**標識現在會指向您在上一個步驟中\_指定為 "pool FQDN" 的池。</span><span class="sxs-lookup"><span data-stu-id="c30a2-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="c30a2-135">此身分識別的狀態會確認使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="c30a2-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="c30a2-136">此外，我們還可以在 Lync Server 2013 的 [控制台] 中查看使用者清單，並確認 [註冊機構] 池值現在會指向 [Lync Server 2013] 池。</span><span class="sxs-lookup"><span data-stu-id="c30a2-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="c30a2-137">![Lync server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync server 2013 控制台使用者清單")</span><span class="sxs-lookup"><span data-stu-id="c30a2-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

