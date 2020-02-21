---
title: 移動多位使用者至試驗集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657c6e001fa15fa6c1c70076a257a620f0cef790
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="afa6a-102">移動多位使用者至試驗集區</span><span class="sxs-lookup"><span data-stu-id="afa6a-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afa6a-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="afa6a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="afa6a-104">您可以將多個使用者從 Office Communications Server 2007 R2 集區移至 Lync Server 2013 試驗集區使用 Lync Server 2013 Control Panel] 或 [Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="afa6a-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="afa6a-105">若要使用 Lync Server 2013 Control Panel 移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="afa6a-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="afa6a-106">開啟**Lync Server 控制台**。</span><span class="sxs-lookup"><span data-stu-id="afa6a-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="afa6a-107">從 [使用者搜尋]\*\*\*\* 索引標籤，按一下 [搜尋]\*\*\*\* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="afa6a-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="afa6a-108">接著，按一下 [新增篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afa6a-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="afa6a-109">建立篩選，其中的 [Office Communications Server 使用者]\*\*\*\* 等於 [True]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afa6a-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="afa6a-110">按一下 [**尋找**] 搜尋舊版 Office Communications Server 2007 R2 使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="afa6a-111">選取您想要將移至 Lync Server 2013 集區的兩個使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="afa6a-112">在這個範例中，我們會將使用者 Chen Yang 和聖誕老人 Hansen 移。</span><span class="sxs-lookup"><span data-stu-id="afa6a-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="afa6a-113">![顯示從 NM-OCS-13-2ND 使用者搜尋的使用者清單](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "顯示從 NM-OCS-13-2ND 使用者搜尋的使用者清單")</span><span class="sxs-lookup"><span data-stu-id="afa6a-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="afa6a-114">從 [**動作**] 功能表中，選取 [**移至集區選取的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="afa6a-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="afa6a-115">從下拉式清單中，選取 [Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="afa6a-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="afa6a-116">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afa6a-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="afa6a-117">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="afa6a-117">Click OK.</span></span>
    
    <span data-ttu-id="afa6a-118">![移動使用者，目的地登錄器集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者，目的地登錄器集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="afa6a-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="afa6a-119">請確認使用者的 [**登錄器集區**] 欄現在包含 Lync Server 2013 集區，即表示使用者已成功移動。</span><span class="sxs-lookup"><span data-stu-id="afa6a-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="afa6a-120">若要使用 Lync Server 2013 管理命令介面時，移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="afa6a-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="afa6a-121">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="afa6a-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="afa6a-122">在命令列中，輸入下列命令，並使用您想要移動，並取代的特定使用者名稱取代**User1**和**User2** **集區\_FQDN**目的地集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="afa6a-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="afa6a-123">在這個範例中我們將會移動 Hao Chen 和 Katie Jordan 的使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="afa6a-124">![若要移動舊版使用者的範例指令程式](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "若要移動舊版使用者的範例指令程式")</span><span class="sxs-lookup"><span data-stu-id="afa6a-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="afa6a-125">在命令列上輸入下列命令</span><span class="sxs-lookup"><span data-stu-id="afa6a-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="afa6a-126">**登錄器集區**身分識別現在應指向您指定為集區**集區\_FQDN**在先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="afa6a-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="afa6a-127">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="afa6a-128">重複步驟，以確認已移動**使用者 2** 。</span><span class="sxs-lookup"><span data-stu-id="afa6a-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="afa6a-129">![輸出的 PowerShell Get-UsUser 中-Identity 指令程式](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "輸出的 PowerShell Get-UsUser 中-Identity 指令程式")</span><span class="sxs-lookup"><span data-stu-id="afa6a-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="afa6a-130">若要使用 Lync Server 2013 管理命令介面同時移動所有使用者</span><span class="sxs-lookup"><span data-stu-id="afa6a-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="afa6a-131">在這個範例中，所有使用者都回到 Office Communications Server 2007 R2 集區 (pool01.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="afa6a-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="afa6a-132">使用 Lync Server 2013 管理命令介面，我們會將所有使用者同時都移至 Lync Server 2013 集區 (pool02.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="afa6a-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="afa6a-133">開啟 [ **Lync Server 2013 管理命令介面**]。</span><span class="sxs-lookup"><span data-stu-id="afa6a-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="afa6a-134">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="afa6a-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="afa6a-135">![若要移動所有舊版使用者的集區中的範例指令程式](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "若要移動所有舊版使用者的集區中的範例指令程式")</span><span class="sxs-lookup"><span data-stu-id="afa6a-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="afa6a-136">接著，執行**Get-csuser**為一位試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="afa6a-137">每位使用者的**登錄器集區**身分識別現在指向集區您指定為 「 集區\_FQDN 」 在先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="afa6a-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="afa6a-138">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="afa6a-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="afa6a-139">此外，我們可以在 Lync Server 2013 Control Panel 中檢視的使用者清單，並確認登錄器集區值現在指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="afa6a-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="afa6a-140">![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")</span><span class="sxs-lookup"><span data-stu-id="afa6a-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

