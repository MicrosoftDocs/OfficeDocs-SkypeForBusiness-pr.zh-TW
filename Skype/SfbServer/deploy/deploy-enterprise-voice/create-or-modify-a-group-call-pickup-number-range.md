---
title: 在商務用 Skype 中建立或修改群組呼叫裝貨號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫挑選號碼範圍。
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767876"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="baddf-103">在商務用 Skype 中建立或修改群組呼叫裝貨號碼範圍</span><span class="sxs-lookup"><span data-stu-id="baddf-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="baddf-104">在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫挑選號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="baddf-105">[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="baddf-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="baddf-106">當您部署群組呼叫挑選時，您必須設定 [通話公園軌道] 表格，並將指定為 [呼叫挑選] 群組號碼的電話號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="baddf-107">這些群組號碼是使用者撥打電話給另一個使用者所撥打的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="baddf-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="baddf-108">如同通話公園軌道編號，呼叫挑選群組的號碼必須是沒有指派給他們的使用者或電話的虛擬延伸。</span><span class="sxs-lookup"><span data-stu-id="baddf-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="baddf-109">您在其中部署 [群組呼叫挑選] 的每個前端池都可以有一或多個呼叫挑選群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="baddf-110">群組編號範圍在您的部署中必須是全域唯一的，而且必須指派為**GroupPickup**類型。</span><span class="sxs-lookup"><span data-stu-id="baddf-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="baddf-111">使用下列程式來建立或修改 [通話駐留軌道] 表格中的 [通話挑選] 群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="baddf-112">您必須使用商務用 Skype Server Management Shell 來建立、修改、移除及查看 [通話公園軌道] 表格中的 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="baddf-113">在商務用 Skype Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="baddf-114">呼叫挑選群組編號範圍必須符合下列規則：</span><span class="sxs-lookup"><span data-stu-id="baddf-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="baddf-115">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="baddf-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="baddf-116">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="baddf-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="baddf-p104">號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="baddf-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="baddf-119">如果數位範圍是以字元\*或 # 開頭，則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="baddf-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="baddf-120">有效值：必須符合正則運算式字串（[\\* | #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。</span><span class="sxs-lookup"><span data-stu-id="baddf-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="baddf-121">這表示值必須是以字元\*或 # 或數位1到9（第一個字元不能是零）開頭的字串。</span><span class="sxs-lookup"><span data-stu-id="baddf-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="baddf-122">如果第一個字元是\*或 #，則下列字元必須是1到9的數位（不能是零）。</span><span class="sxs-lookup"><span data-stu-id="baddf-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="baddf-123">後續字元可以是從0到9的任何數位，最多可達七個其他字元（例如，\*"#6000"、\*"92000"、"95551212" 和 "915551212"）。</span><span class="sxs-lookup"><span data-stu-id="baddf-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="baddf-124">如果第一個字元不\*是或 #，則第一個字元必須是數位1到9（不能是零），後面再加上八個字元（例如，"915551212"，"41212"，"300"）。</span><span class="sxs-lookup"><span data-stu-id="baddf-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="baddf-125">建立或修改通話挑選群組範圍</span><span class="sxs-lookup"><span data-stu-id="baddf-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="baddf-126">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝，如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="baddf-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="baddf-127">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="baddf-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="baddf-128">使用 [**新-CsCallParkOrbit** ] 建立呼叫挑選群組編號的新範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="baddf-129">使用 [**設定] CsCallParkOrbit**來修改現有的電話挑選號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="baddf-130">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="baddf-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="baddf-131">例如：</span><span class="sxs-lookup"><span data-stu-id="baddf-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="baddf-132">下列範例示範如何將通話駐留軌道式的數位範圍變更為呼叫挑選群組。</span><span class="sxs-lookup"><span data-stu-id="baddf-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="baddf-133">如果您最初指定的類型不正確，且尚未使用群組範圍，請使用這個 Cmdlet 來變更指派給數位範圍的類型。</span><span class="sxs-lookup"><span data-stu-id="baddf-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="baddf-134">如果您將數位範圍從 CallPark 變更為 GroupPickup 或反之，而數位範圍已在使用中，則通話駐留或群組通話拾取將會停止處理該數位範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="baddf-135">例如，如果您將數位範圍從 CallPark 變更為 GroupPick，則通話駐留應用程式將無法再使用該轉到寄存通話的範圍。</span><span class="sxs-lookup"><span data-stu-id="baddf-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="baddf-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="baddf-136">See also</span></span>

[<span data-ttu-id="baddf-137">新-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="baddf-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="baddf-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="baddf-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="baddf-139">刪除通話公園軌道範圍</span><span class="sxs-lookup"><span data-stu-id="baddf-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
