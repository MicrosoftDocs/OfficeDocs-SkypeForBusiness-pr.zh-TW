---
title: Lync Server 2013：建立或修改群組呼叫收取號碼範圍
description: Lync Server 2013：建立或修改群組呼叫收取號碼範圍。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc2072a5d80e9c3b09e0c0d2275233214a21e764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577915"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="4d1ab-103">在 Lync Server 2013 中建立或修改群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="4d1ab-103">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1ab-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="4d1ab-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4d1ab-105">使用下列程式可建立或修改通話駐留軌道表格中的呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-105">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d1ab-106">您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看通話駐留軌道表格中的群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-106">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="4d1ab-107">在 Lync Server 控制台中無法使用群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-107">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d1ab-108">必須為呼叫收取群組號碼範圍指派 GroupPickup 類型。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-108">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="4d1ab-109">只有當使用者所指派的群組號碼是類型 GroupPickup 時，才會為使用者啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-109">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="4d1ab-110">呼叫收取群組號碼範圍必須符合下列規則：</span><span class="sxs-lookup"><span data-stu-id="4d1ab-110">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="4d1ab-111">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="4d1ab-112">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="4d1ab-113">號碼範圍必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-113">The number range must be unique.</span></span> <span data-ttu-id="4d1ab-114">此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-114">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="4d1ab-115">如果號碼範圍開頭為字元 \* \# ，或範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-115">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="4d1ab-116">有效的值：必須符合正則運算式字串 (\[ \\ \* | \# \] ？ \[1-9 \] \\ d {0,7}) | (\[ 1-9 \] \\ d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-116">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="4d1ab-117">這表示值必須是以字元 \* 或 \# 數位1到9為開頭的字串 (第一個字元不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-117">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="4d1ab-118">如果第一個字元是 \* 或 \# ，下列字元必須是1到9的數位， (不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-118">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="4d1ab-119">後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，" \# 6000"、" \* 92000"、" \* 95551212" 及 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="4d1ab-120">如果第一個字元不是 \* 或 \# ，第一個字元必須是數位1到 9 (它不能是零) ，然後是八個字元，每個數位都是0到 9 (例如，"915551212"，"41212"，"300" ) 。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-120">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="4d1ab-121">若要建立或修改呼叫收取群組範圍</span><span class="sxs-lookup"><span data-stu-id="4d1ab-121">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="4d1ab-122">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-122">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4d1ab-123">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4d1ab-124">使用 **get-cscallparkorbit** 來建立新的呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-124">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="4d1ab-125">使用 **get-cscallparkorbit** 可修改現有的呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-125">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="4d1ab-126">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="4d1ab-126">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="4d1ab-127">例如：</span><span class="sxs-lookup"><span data-stu-id="4d1ab-127">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="4d1ab-128">下列範例顯示如何將號碼範圍從通話駐留軌道變更為呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-128">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d1ab-129">若最初指定的類型不正確，而且群組範圍尚未使用中，請使用此 Cmdlet 變更指派給號碼範圍的類型。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-129">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="4d1ab-130">如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPickup，反之亦然，而且號碼範圍已在使用中，則通話駐留或群組通話收取會停止該號碼範圍的工作。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-130">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="4d1ab-131">例如，如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPick，則通話駐留應用程式無法再將此範圍的軌道式用於寄存通話。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-131">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d1ab-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4d1ab-132">See Also</span></span>


[<span data-ttu-id="4d1ab-133">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="4d1ab-133">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="4d1ab-134">新 Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="4d1ab-134">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="4d1ab-135">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="4d1ab-135">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

