---
title: 在商務用 Skype 中建立或修改通話駐留軌道範圍
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 在商務用 Skype Server Enterprise Voice 中建立或修改通話駐留軌道範圍表。
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106319"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="92eca-103">在商務用 Skype 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="92eca-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="92eca-104">在商務用 Skype Server Enterprise Voice 中建立或修改通話駐留軌道範圍表。</span><span class="sxs-lookup"><span data-stu-id="92eca-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="92eca-105">通話駐留使用軌道進行停車通話。</span><span class="sxs-lookup"><span data-stu-id="92eca-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="92eca-106">您必須先設定通話駐留軌道表格，使用者才能駐留及取回通話。</span><span class="sxs-lookup"><span data-stu-id="92eca-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="92eca-107">您必須指定您的組織將保留用於停車通話的分機號碼範圍 (的軌道式) ，並指定處理每個範圍的通話駐留集區，以定義這些範圍的路由。</span><span class="sxs-lookup"><span data-stu-id="92eca-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="92eca-108">當您定義軌道範圍時，目標是具有足夠的軌道，因此，任何一個軌道都不會很快地重複使用，但卻不是這麼多的軌道來限制使用者或其他服務可使用的延伸數目。</span><span class="sxs-lookup"><span data-stu-id="92eca-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="92eca-109">您可以針對部署通話駐留應用程式的每個商務用 Skype 伺服器集區，建立多個通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="92eca-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="92eca-110">每個通話駐留軌道範圍必須具有全域唯一名稱和一組唯一的延伸。</span><span class="sxs-lookup"><span data-stu-id="92eca-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92eca-111">軌道範圍通常會包含100或更少的軌道。</span><span class="sxs-lookup"><span data-stu-id="92eca-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="92eca-112">每個範圍都可以大量增加，只要小於每個範圍的10000軌道的最大值，且每個集區的每個集數目小於50000的軌道。</span><span class="sxs-lookup"><span data-stu-id="92eca-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="92eca-113">如果範圍太小，則軌道的重複使用速度變快。</span><span class="sxs-lookup"><span data-stu-id="92eca-113">If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="92eca-114">使用虛擬分機區塊 (未獲指派使用者或電話的分機) 用於軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="92eca-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="92eca-115">指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。</span><span class="sxs-lookup"><span data-stu-id="92eca-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="92eca-116">使用下列其中一個程序來建立或修改通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="92eca-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="92eca-117">使用商務用 Skype Server 控制台建立或修改駐留通話的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="92eca-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="92eca-118">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="92eca-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="92eca-119">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="92eca-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="92eca-120">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="92eca-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="92eca-121">在左導覽列中，依序按一下 **[語音功能]**、**[通話駐留]**。</span><span class="sxs-lookup"><span data-stu-id="92eca-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="92eca-122">在 **[通話駐留]** 頁面上，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="92eca-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="92eca-p104">若要建立新的軌道範圍，可按一下 **[新增]**。在 **[名稱]** 中，輸入此號碼範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="92eca-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="92eca-125">當您將軌道範圍認可至資料庫之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="92eca-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="92eca-p105">若要修改現有的軌道範圍，可在搜尋欄位中輸入軌道範圍的所有或部分名稱。在軌道的結果清單中，按一下您想要的軌道，接著依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="92eca-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="92eca-128">在第一個 **[號碼範圍]** 欄位中，輸入此項通話駐留軌道分機號碼範圍的開頭號碼，並在第二個 **[號碼範圍]** 欄位中，輸入該範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="92eca-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="92eca-129">請注意：</span><span class="sxs-lookup"><span data-stu-id="92eca-129">Be aware:</span></span>

   - <span data-ttu-id="92eca-130">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="92eca-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="92eca-131">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="92eca-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="92eca-p107">軌道範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="92eca-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="92eca-134">如果軌道範圍的開頭為字元 \* 或 #，則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="92eca-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="92eca-135">有效的值：必須符合正則運算式字串 ( [ \\ \* | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="92eca-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="92eca-136">這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="92eca-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="92eca-137">如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="92eca-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="92eca-138">後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="92eca-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="92eca-139">如果第一個字元不是 \* 或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如，"915551212"，"41212"，"300" ) 。</span><span class="sxs-lookup"><span data-stu-id="92eca-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="92eca-p109">每個集區的軌道總數不得超過 50,000 個。每個軌道範圍通常會涵蓋 100 個以下的軌道，但只要總數不超過 10,000 個軌道，可以大一些。例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="92eca-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="92eca-p110">在 **[目的地伺服器的 FQDN]** 中，按一下裝載通話保留應用程式的應用程式服務之完整網域名稱 (FQDN) 或服務 ID。保留給軌道範圍中由開始號碼與結束號碼所指定之範圍內的號碼的所有通話，將會轉接至此伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="92eca-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="92eca-145">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="92eca-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="92eca-146">若要使用商務用 Skype Server 管理命令介面來建立或修改駐留通話的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="92eca-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="92eca-147">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="92eca-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="92eca-148">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="92eca-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="92eca-149">使用 **New-CsCallParkOrbit** 來建立新的軌道號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="92eca-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="92eca-150">使用 **Set-CsCallParkOrbit** 來修改現有的軌道號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="92eca-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="92eca-151">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="92eca-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="92eca-152">例如：</span><span class="sxs-lookup"><span data-stu-id="92eca-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="92eca-153">下列範例示範如何修改現有軌道範圍中的號碼，</span><span class="sxs-lookup"><span data-stu-id="92eca-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="92eca-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="92eca-154">See also</span></span>

[<span data-ttu-id="92eca-155">新 Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="92eca-155">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="92eca-156">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="92eca-156">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="92eca-157">刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="92eca-157">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)