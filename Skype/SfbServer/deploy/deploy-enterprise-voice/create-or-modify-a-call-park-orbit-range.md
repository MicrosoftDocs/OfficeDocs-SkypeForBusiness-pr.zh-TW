---
title: 在商務用 Skype 中建立或修改通話寄存軌道的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 在商務用 Skype Server Enterprise Voice 中建立或修改通話公園軌道的範圍表。
ms.openlocfilehash: 305404ce74d3aec26741c0e26b999f6227dabe37
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233681"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="078c7-103">在商務用 Skype 中建立或修改通話寄存軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="078c7-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="078c7-104">在商務用 Skype Server Enterprise Voice 中建立或修改通話公園軌道的範圍表。</span><span class="sxs-lookup"><span data-stu-id="078c7-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="078c7-105">通話寄存使用 [軌道式] 進行停車通話。</span><span class="sxs-lookup"><span data-stu-id="078c7-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="078c7-106">您必須先設定 [通話公園軌道] 表格, 才能停止並取回通話。</span><span class="sxs-lookup"><span data-stu-id="078c7-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="078c7-107">您必須指定貴組織將針對停車通話保留的延伸數位 (軌道式) 範圍, 並指定哪個呼叫駐留器池處理每個範圍, 以定義這些範圍的路線。</span><span class="sxs-lookup"><span data-stu-id="078c7-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="078c7-108">當您定義軌道範圍時, 目標是有足夠的 [軌道式], 所以任何一個軌道都不會過快地重複使用, 但卻不是您要限制使用者或其他服務可用的延伸數目。</span><span class="sxs-lookup"><span data-stu-id="078c7-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="078c7-109">您可以為部署通話駐留應用程式的每個商務用 Skype 伺服器池建立多個通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="078c7-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="078c7-110">每個呼叫公園的軌道範圍都必須有全域唯一的名稱, 以及一組唯一的延伸。</span><span class="sxs-lookup"><span data-stu-id="078c7-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="078c7-111">軌道範圍通常會包含100或更少的軌道式。</span><span class="sxs-lookup"><span data-stu-id="078c7-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="078c7-112">每個範圍都可以大許多, 只要它小於每個範圍的10000軌道式, 且每個池子的每個泳池不超過50000的 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="078c7-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="078c7-113">如果範圍太小, 則會更快速地重複使用 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="078c7-113">If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="078c7-114">針對您的軌道範圍, 使用虛擬延伸組塊 (沒有指派使用者或電話的延伸)。</span><span class="sxs-lookup"><span data-stu-id="078c7-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="078c7-115">在 [通話駐留軌道] 表格中, 將直向內撥 (所做的) 號碼指派為軌道編號, 不受支援。</span><span class="sxs-lookup"><span data-stu-id="078c7-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="078c7-116">使用下列其中一個程式來建立或修改通話寄存軌道的範圍。</span><span class="sxs-lookup"><span data-stu-id="078c7-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="078c7-117">使用商務用 Skype Server [控制台] 來建立或修改停車通話的數位範圍</span><span class="sxs-lookup"><span data-stu-id="078c7-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="078c7-118">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="078c7-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="078c7-119">如需詳細資訊, 請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="078c7-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="078c7-120">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="078c7-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="078c7-121">在左側導覽列中, 按一下 [**語音功能**], 然後按一下 [**通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="078c7-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="078c7-122">在 [**通話駐留**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="078c7-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="078c7-123">若要建立新的軌道範圍, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="078c7-123">To create a new orbit range, click **New**.</span></span> <span data-ttu-id="078c7-124">在 [**名稱**] 中, 輸入此數位範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="078c7-124">In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="078c7-125">在您將軌道範圍提交至資料庫之後, 您就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="078c7-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="078c7-126">若要修改現有的軌道範圍, 請在 [搜尋] 欄位中輸入所有或部分的軌道範圍名稱。</span><span class="sxs-lookup"><span data-stu-id="078c7-126">To modify an existing orbit range, type all or part of the name of the orbit range in the search field.</span></span> <span data-ttu-id="078c7-127">在 [軌道式] 的結果清單中, 按一下您想要的軌道, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="078c7-127">In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="078c7-128">在 [第一個**數位範圍**] 欄位中, 輸入此通話公園軌道的延伸範圍起始編號, 然後在第二個 [**數位範圍**] 欄位中, 輸入範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="078c7-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="078c7-129">請注意:</span><span class="sxs-lookup"><span data-stu-id="078c7-129">Be aware:</span></span>

   - <span data-ttu-id="078c7-130">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="078c7-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="078c7-131">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="078c7-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="078c7-132">軌道範圍必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="078c7-132">The orbit range must be unique.</span></span> <span data-ttu-id="078c7-133">此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="078c7-133">This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="078c7-134">如果軌道範圍是以字元\*或 # 開頭, 則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="078c7-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="078c7-135">有效值: 必須符合正則運算式字串 ([\\* | #]？ [1-9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="078c7-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="078c7-136">這表示值必須是以字元\*或 # 或數位1到 9 (第一個字元不能是零) 開頭的字串。</span><span class="sxs-lookup"><span data-stu-id="078c7-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="078c7-137">如果第一個字元是\*或 #, 則下列字元必須是1到9的數位 (不能是零)。</span><span class="sxs-lookup"><span data-stu-id="078c7-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="078c7-138">後續字元可以是從0到9的任何數位, 最多可達七個其他字元 (例如,\*"#6000"、\*"92000"、"95551212" 和 "915551212")。</span><span class="sxs-lookup"><span data-stu-id="078c7-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="078c7-139">如果第一個字元不\*是或 #, 則第一個字元必須是數位1到 9 (不能是零), 後面再加上八個字元 (例如, "915551212", "41212", "300")。</span><span class="sxs-lookup"><span data-stu-id="078c7-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="078c7-140">每個池子不應超過總計50000的 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="078c7-140">You should not have more than a total of 50,000 orbits per pool.</span></span> <span data-ttu-id="078c7-141">每個軌道範圍通常會包含100或更少的軌道式, 但只要包含超過10000的軌道式, 就能更大。</span><span class="sxs-lookup"><span data-stu-id="078c7-141">Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits.</span></span> <span data-ttu-id="078c7-142">例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="078c7-142">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="078c7-143">在 [**目的地伺服器的 FQDN**] 中, 按一下主持通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="078c7-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="078c7-144">在軌道範圍內由 start 編號和結束編號所指定範圍內的所有來電都會路由到這個伺服器或池子。</span><span class="sxs-lookup"><span data-stu-id="078c7-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="078c7-145">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="078c7-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="078c7-146">若要使用商務用 Skype Server Management Shell 來建立或修改停車通話的數位範圍</span><span class="sxs-lookup"><span data-stu-id="078c7-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="078c7-147">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="078c7-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="078c7-148">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="078c7-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="078c7-149">使用 [**新-CsCallParkOrbit** ] 建立新的軌道編號範圍。</span><span class="sxs-lookup"><span data-stu-id="078c7-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="078c7-150">使用 [**設定] CsCallParkOrbit**來修改現有的軌道編號範圍。</span><span class="sxs-lookup"><span data-stu-id="078c7-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="078c7-151">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="078c7-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="078c7-152">例如：</span><span class="sxs-lookup"><span data-stu-id="078c7-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="078c7-153">下列範例顯示如何修改現有的軌道範圍中的數位,</span><span class="sxs-lookup"><span data-stu-id="078c7-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="078c7-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="078c7-154">See also</span></span>

[<span data-ttu-id="078c7-155">新-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="078c7-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="078c7-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="078c7-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="078c7-157">刪除通話公園軌道範圍</span><span class="sxs-lookup"><span data-stu-id="078c7-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
