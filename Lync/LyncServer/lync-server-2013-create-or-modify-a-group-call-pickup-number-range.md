---
title: Lync Server 2013：建立或修改群組呼叫挑選編號範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="a8ffe-102">在 Lync Server 2013 中建立或修改群組呼叫挑選號碼範圍</span><span class="sxs-lookup"><span data-stu-id="a8ffe-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8ffe-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a8ffe-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a8ffe-104">使用下列程式來建立或修改 [通話駐留軌道] 表格中的 [通話挑選] 群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8ffe-105">您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看 [通話寄存軌道] 表格中的 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="a8ffe-106">在 Lync Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a8ffe-107">必須為呼叫挑選群組編號範圍指派 GroupPickup 類型。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="a8ffe-108">只有在指派給使用者的群組號碼為 GroupPickup 時，才會啟用群組呼叫挑選。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="a8ffe-109">呼叫挑選群組編號範圍必須符合下列規則：</span><span class="sxs-lookup"><span data-stu-id="a8ffe-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="a8ffe-110">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="a8ffe-111">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="a8ffe-p103">號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="a8ffe-114">如果數位範圍是以字元\*開頭，或\#範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="a8ffe-115">有效值：必須符合正則運算式字串（\[\\\*|\#\]？\[1-9\]\\d{0,7}） |（\[1-9\]\\d{0,8}）。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="a8ffe-116">這表示值必須是以字元\*或\#數位1到9（第一個字元不能是零）開頭的字串。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="a8ffe-117">如果第一個字元是\*或\#，則下列字元必須是1到9的數位（不能是零）。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="a8ffe-118">後續字元可以是從0到9的任何數位，最多可達七個其他\#字元（例如，\*"6000"，\*"92000"，"95551212"，"915551212"）。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="a8ffe-119">如果第一個字元不\*是或\#，則第一個字元必須是數位1到9（不能是零），然後再加上最多八個字元（例如，"915551212"，"41212"，"300"）。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="a8ffe-120">建立或修改通話挑選群組範圍</span><span class="sxs-lookup"><span data-stu-id="a8ffe-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="a8ffe-121">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a8ffe-122">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a8ffe-123">使用 [**新-CsCallParkOrbit** ] 建立呼叫挑選群組編號的新範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="a8ffe-124">使用 [**設定] CsCallParkOrbit**來修改現有的電話挑選號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="a8ffe-125">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="a8ffe-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="a8ffe-126">例如：</span><span class="sxs-lookup"><span data-stu-id="a8ffe-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="a8ffe-127">下列範例示範如何將通話駐留軌道式的數位範圍變更為呼叫挑選群組。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a8ffe-128">如果您最初指定的類型不正確，且尚未使用群組範圍，請使用這個 Cmdlet 來變更指派給數位範圍的類型。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="a8ffe-129">如果您將數位範圍從 CallPark 變更為 GroupPickup 或反之，而數位範圍已在使用中，則通話駐留或群組通話拾取將會停止處理該數位範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="a8ffe-130">例如，如果您將數位範圍從 CallPark 變更為 GroupPick，則通話駐留應用程式將無法再使用該轉到寄存通話的範圍。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8ffe-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="a8ffe-131">See Also</span></span>


[<span data-ttu-id="a8ffe-132">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="a8ffe-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="a8ffe-133">新-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a8ffe-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="a8ffe-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a8ffe-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

