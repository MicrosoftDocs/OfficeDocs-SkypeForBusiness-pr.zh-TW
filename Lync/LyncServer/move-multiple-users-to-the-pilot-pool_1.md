---
title: 將多個使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c663566605529b25d9890bb31cba462364c813
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="bb00a-102">將多個使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="bb00a-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb00a-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bb00a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bb00a-104">您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將多個使用者從 Office 通訊伺服器 2007 R2 集區移至 Lync Server 2013 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="bb00a-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="bb00a-105">使用 Lync Server 2013 控制台移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="bb00a-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="bb00a-106">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="bb00a-107">從 [使用者搜尋]\*\*\*\* 索引標籤，按一下 [搜尋]\*\*\*\* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bb00a-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="bb00a-108">接著，按一下 [新增篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb00a-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="bb00a-109">建立篩選，其中的 [Office Communications Server 使用者]\*\*\*\* 等於 [True]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb00a-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="bb00a-110">按一下 [**尋找**] 搜尋舊版 Office 通訊伺服器 2007 R2 使用者。</span><span class="sxs-lookup"><span data-stu-id="bb00a-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="bb00a-111">選取兩個要移至 Lync Server 2013 集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="bb00a-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="bb00a-112">在此範例中，我們會將使用者移 Chen 陽和聖誕老人聖誕 Hansen。</span><span class="sxs-lookup"><span data-stu-id="bb00a-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="bb00a-113">![從搜尋 OCS 使用者顯示的使用者清單](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "從搜尋 OCS 使用者顯示的使用者清單")</span><span class="sxs-lookup"><span data-stu-id="bb00a-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="bb00a-114">從 [**動作**] 功能表中，選取 [**將選取的使用者移至集**區]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="bb00a-115">從下拉式清單中，選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="bb00a-116">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb00a-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="bb00a-117">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-117">Click OK.</span></span>
    
    <span data-ttu-id="bb00a-118">![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="bb00a-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="bb00a-119">確認使用者的 [**報名者集**區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="bb00a-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="bb00a-120">使用 Lync Server 2013 管理命令介面移動多位使用者</span><span class="sxs-lookup"><span data-stu-id="bb00a-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="bb00a-121">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="bb00a-122">在命令列上輸入下列命令，並將**User1**和使用者2取代為您想要移動的特定使用者名稱，並將**集區 \_ FQDN** **取代為目的地**集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="bb00a-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="bb00a-123">在此範例中，我們會移動使用者 Hao Chen 和 Katie 約旦。</span><span class="sxs-lookup"><span data-stu-id="bb00a-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="bb00a-124">![移動舊版使用者的範例 Cmdlet](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "移動舊版使用者的範例 Cmdlet")</span><span class="sxs-lookup"><span data-stu-id="bb00a-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="bb00a-125">在命令列上輸入下列命令</span><span class="sxs-lookup"><span data-stu-id="bb00a-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="bb00a-126">**註冊機構集**區的身分識別現在應該指向您在上一個步驟中指定為**集區 \_ FQDN**的集區。</span><span class="sxs-lookup"><span data-stu-id="bb00a-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="bb00a-127">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="bb00a-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="bb00a-128">重複步驟**以驗證使用者2是否已移動**。</span><span class="sxs-lookup"><span data-stu-id="bb00a-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="bb00a-129">![PowerShell Get-UsUser 識別指令程式的輸出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser 識別指令程式的輸出")</span><span class="sxs-lookup"><span data-stu-id="bb00a-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="bb00a-130">使用 Lync Server 2013 管理命令介面同時移動所有使用者</span><span class="sxs-lookup"><span data-stu-id="bb00a-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="bb00a-131">在此範例中，所有使用者都已傳回 Office 通訊伺服器 2007 R2 集區（pool01.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="bb00a-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="bb00a-132">使用 Lync Server 2013 管理命令介面時，我們會同時將所有使用者同時移至 Lync Server 2013 集區（pool02.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="bb00a-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="bb00a-133">開啟 [ **Lync Server 2013 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bb00a-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="bb00a-134">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="bb00a-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="bb00a-135">![移動集區中所有舊版使用者的範例 Cmdlet](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移動集區中所有舊版使用者的範例 Cmdlet")</span><span class="sxs-lookup"><span data-stu-id="bb00a-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="bb00a-136">接下來，針對其中一位試驗使用者執行**Get-CsUser** 。</span><span class="sxs-lookup"><span data-stu-id="bb00a-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="bb00a-137">每個使用者的**註冊區集**區身分識別，都指向您 \_ 在上一個步驟中指定為「集區 FQDN」的集區。</span><span class="sxs-lookup"><span data-stu-id="bb00a-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="bb00a-138">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="bb00a-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="bb00a-139">此外，我們可以在 Lync Server 2013 控制台中查看使用者清單，並確認 [註冊機集區] 值現在是否指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="bb00a-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="bb00a-140">![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")</span><span class="sxs-lookup"><span data-stu-id="bb00a-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

