---
title: 在商務用 Skype 中建立或修改群組呼叫收取號碼範圍
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫收取號碼範圍。
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822403"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="4df3b-103">在商務用 Skype 中建立或修改群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="4df3b-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="4df3b-104">在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="4df3b-105">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="4df3b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="4df3b-106">當您部署群組呼叫收取時，您必須使用指定為呼叫收取群組號碼的電話號碼範圍來設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="4df3b-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="4df3b-107">這些群組號碼是使用者在撥打其他使用者所撥打之來電時所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="4df3b-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="4df3b-108">與通話駐留軌道號碼類似，來電收取群組數目必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="4df3b-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="4df3b-109">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="4df3b-110">群組號碼範圍在您的部署中必須是全域唯一的，而且必須被指派為 **GroupPickup** 類型。</span><span class="sxs-lookup"><span data-stu-id="4df3b-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="4df3b-111">使用下列程式可建立或修改通話駐留軌道表格中的呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="4df3b-112">您必須使用商務用 Skype Server 管理命令介面來建立、修改、移除及查看通話駐留軌道表格中的群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="4df3b-113">在商務用 Skype Server [控制台] 中無法使用群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="4df3b-114">呼叫收取群組號碼範圍必須符合下列規則：</span><span class="sxs-lookup"><span data-stu-id="4df3b-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="4df3b-115">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="4df3b-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="4df3b-116">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="4df3b-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="4df3b-117">號碼範圍必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4df3b-117">The number range must be unique.</span></span> <span data-ttu-id="4df3b-118">此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="4df3b-118">This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="4df3b-119">如果號碼範圍開頭為字元 \* 或 #，則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="4df3b-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="4df3b-120">有效的值：必須符合正則運算式字串 ( [ \\ \* | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="4df3b-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="4df3b-121">這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="4df3b-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="4df3b-122">如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="4df3b-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="4df3b-123">後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="4df3b-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="4df3b-124">如果第一個字元不是 \* 或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如，"915551212"，"41212"，"300" ) 。</span><span class="sxs-lookup"><span data-stu-id="4df3b-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="4df3b-125">若要建立或修改呼叫收取群組範圍</span><span class="sxs-lookup"><span data-stu-id="4df3b-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="4df3b-126">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="4df3b-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="4df3b-127">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="4df3b-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="4df3b-128">使用 **get-cscallparkorbit** 來建立新的呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="4df3b-129">使用 **get-cscallparkorbit** 可修改現有的呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="4df3b-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="4df3b-130">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="4df3b-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="4df3b-131">例如：</span><span class="sxs-lookup"><span data-stu-id="4df3b-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="4df3b-132">下列範例顯示如何將號碼範圍從通話駐留軌道變更為呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="4df3b-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="4df3b-133">若最初指定的類型不正確，而且群組範圍尚未使用中，請使用此 Cmdlet 變更指派給號碼範圍的類型。</span><span class="sxs-lookup"><span data-stu-id="4df3b-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="4df3b-134">如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPickup，反之亦然，而且號碼範圍已在使用中，則通話駐留或群組通話收取會停止該號碼範圍的工作。</span><span class="sxs-lookup"><span data-stu-id="4df3b-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="4df3b-135">例如，如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPick，則通話駐留應用程式無法再將此範圍的軌道式用於寄存通話。</span><span class="sxs-lookup"><span data-stu-id="4df3b-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="4df3b-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4df3b-136">See also</span></span>

[<span data-ttu-id="4df3b-137">新 Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="4df3b-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="4df3b-138">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="4df3b-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="4df3b-139">刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="4df3b-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
