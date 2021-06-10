---
title: 管理公司中前線員工以班為基礎的Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在組織中管理前線工作人員Teams班式存取權。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092541"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="a04aa-103">管理公司中前線員工以班為基礎的Teams</span><span class="sxs-lookup"><span data-stu-id="a04aa-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a04aa-104">自 2020 年 6 月 30 起，已終止對 Microsoft StaffHub 的支援。</span><span class="sxs-lookup"><span data-stu-id="a04aa-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="a04aa-105">我們正在將 StaffHub 功能建在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a04aa-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="a04aa-106">今天，Teams 包含用於排程管理的班次應用程式，並且會陸續推出其他功能。</span><span class="sxs-lookup"><span data-stu-id="a04aa-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="a04aa-107">所有使用者自 2020 年 6 月 30 日起皆無法再使用 StaffHub。</span><span class="sxs-lookup"><span data-stu-id="a04aa-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="a04aa-108">任何嘗試開啟 StaffHub 的人，都會看到一則訊息，指示他們下載 Teams。</span><span class="sxs-lookup"><span data-stu-id="a04aa-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="a04aa-109">如需深入了解，請參閱[已終止對 Microsoft StaffHub 的支援](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="a04aa-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="a04aa-110">概觀</span><span class="sxs-lookup"><span data-stu-id="a04aa-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="a04aa-111">目前Microsoft Teams表示使用者目前的可用性和狀態給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a04aa-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="a04aa-112">前線工作人員的存在通常不如其他員工預測，因為每天的工作時間通常不同。</span><span class="sxs-lookup"><span data-stu-id="a04aa-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="a04aa-113">做為系統管理員，您可以設定Teams，為貴組織的前線工作人員顯示一組以班為基礎的目前狀態，以指出他們何時上班和下班。</span><span class="sxs-lookup"><span data-stu-id="a04aa-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="a04aa-114">這些以班為基礎的目前狀態 實心綠色核取方塊，表示在班次上，灰色圓圈與 x，表示關閉班次關閉班次，實心紅色圓圈，表示忙碌狀態與 Teams 的預設目前狀態 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; 集不同[](../../presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="a04aa-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="a04aa-115">有了這兩組目前狀態，您可以根據組織人員的角色來設定不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="a04aa-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="a04aa-116">使用輪班式存取，您可以在前線工作人員Teams管理對人員的存取權限。</span><span class="sxs-lookup"><span data-stu-id="a04aa-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="a04aa-117">例如，您可以設定Teams，以顯示一則訊息，要求前線工作人員必須先確認，才能Teams排班時才能使用電話。</span><span class="sxs-lookup"><span data-stu-id="a04aa-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="a04aa-118">案例</span><span class="sxs-lookup"><span data-stu-id="a04aa-118">Scenario</span></span>

<span data-ttu-id="a04aa-119">以下是貴組織如何管理班次式存取的範例。</span><span class="sxs-lookup"><span data-stu-id="a04aa-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="a04aa-120">貴組織有前線工作人員，其工作時間只應在主管排程及核准的班中支付。</span><span class="sxs-lookup"><span data-stu-id="a04aa-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="a04aa-121">他們不應支付在排程班以外工作的時間，包括使用 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a04aa-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="a04aa-122">您設定了一則自訂訊息，指出「您的 Teams 非班時間不會計入應付時數」，當前線工作人員嘗試在輪班時存取 Teams 時，會顯示此訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="a04aa-123">如果他們選擇使用Teams，他們按一下 [我接受，瞭解這次不會支付他們費用。</span><span class="sxs-lookup"><span data-stu-id="a04aa-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="a04aa-124">您組織中也有有薪資且沒有輪班的資訊工作者。</span><span class="sxs-lookup"><span data-stu-id="a04aa-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="a04aa-125">您將資訊工作者設定為在 Teams 使用預設目前狀態，同時提供前線員工以班為基礎的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a04aa-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="a04aa-126">以班次為基礎的目前狀態</span><span class="sxs-lookup"><span data-stu-id="a04aa-126">Shift-based presence states</span></span>

<span data-ttu-id="a04aa-127">以下是以班次為基礎的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a04aa-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="a04aa-128">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="a04aa-128">App configured</span></span> |<span data-ttu-id="a04aa-129">使用者設定</span><span class="sxs-lookup"><span data-stu-id="a04aa-129">User configured</span></span>  |<span data-ttu-id="a04aa-130">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a04aa-130">More information</span></span>  |
|---------|---------|---------|
|![實心綠色核取方塊，表示正在上班](../../media/flw-presence-on-shift.png) <span data-ttu-id="a04aa-132">輪班</span><span class="sxs-lookup"><span data-stu-id="a04aa-132">On shift</span></span>     |         |<span data-ttu-id="a04aa-133">在班次開始時自動設定</span><span class="sxs-lookup"><span data-stu-id="a04aa-133">Automatically set at the start of a shift</span></span>         |
|![使用 x 的灰色圓圈，表示關閉班次](../../media/flw-presence-off-shift.png) <span data-ttu-id="a04aa-135">關閉班次</span><span class="sxs-lookup"><span data-stu-id="a04aa-135">Off shift</span></span>     |         |<span data-ttu-id="a04aa-136">在班次結束時自動設定</span><span class="sxs-lookup"><span data-stu-id="a04aa-136">Automatically set at the end of a shift</span></span>         |
|![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="a04aa-138">忙碌</span><span class="sxs-lookup"><span data-stu-id="a04aa-138">Busy</span></span>      | ![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="a04aa-140">忙碌</span><span class="sxs-lookup"><span data-stu-id="a04aa-140">Busy</span></span>         |<span data-ttu-id="a04aa-141">自動設定。</span><span class="sxs-lookup"><span data-stu-id="a04aa-141">Automatically set.</span></span> <span data-ttu-id="a04aa-142">您也可以手動設定前線工作人員輪班時。</span><span class="sxs-lookup"><span data-stu-id="a04aa-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="a04aa-143">關閉班次存取Teams</span><span class="sxs-lookup"><span data-stu-id="a04aa-143">Off shift access to Teams</span></span>

<span data-ttu-id="a04aa-144">此功能可讓您在前線工作人員Teams時管理存取權。</span><span class="sxs-lookup"><span data-stu-id="a04aa-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="a04aa-145">您可以設定Teams，讓前線工作人員在輪班時存取Teams訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="a04aa-146">前線工作人員必須先按一下 **[我接受** 才能使用Teams。</span><span class="sxs-lookup"><span data-stu-id="a04aa-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="a04aa-147">您可以使用預設郵件、從一組預先定義的郵件中選擇，或自訂郵件以顯示您想要的任何文字。</span><span class="sxs-lookup"><span data-stu-id="a04aa-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="a04aa-148">以下是預設訊息：</span><span class="sxs-lookup"><span data-stu-id="a04aa-148">Here's the default message:</span></span>

![預設訊息的螢幕擷取畫面](../../media/shifts-presence-message.png)

<span data-ttu-id="a04aa-150">您也可以設定顯示郵件的頻率，並設定第一個班次開始或最後一個班結束，以及限制Teams寬限期。</span><span class="sxs-lookup"><span data-stu-id="a04aa-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="a04aa-151">管理輪班式存取</span><span class="sxs-lookup"><span data-stu-id="a04aa-151">Manage shift-based access</span></span>

<span data-ttu-id="a04aa-152">做為系統管理員，您可以使用策略來控制組織中前線工作人員以班為基礎的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a04aa-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="a04aa-153">您可以使用下列 PowerShell Cmdlet 管理這些策略：</span><span class="sxs-lookup"><span data-stu-id="a04aa-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="a04aa-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="a04aa-154">New-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="a04aa-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="a04aa-155">Get-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="a04aa-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="a04aa-156">Set-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="a04aa-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="a04aa-157">Grant-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="a04aa-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="a04aa-158">Remove-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="a04aa-159">使用 New-CsTeamsShiftsPolicy Cmdlet 來建立新策略、設定您想要的策略設定，然後使用 Grant-CsTeamsShiftsPolicy Cmdlet 將策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a04aa-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="a04aa-160">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="a04aa-160">Here's some examples.</span></span> <span data-ttu-id="a04aa-161">請參閱 [New-CsTeamsShiftsPolicy，](/powershell/module/teams/new-csteamsshiftspolicy)瞭解每個策略設定和參數的詳細資訊，包括您可選擇之預先定義的班次外訊息清單。</span><span class="sxs-lookup"><span data-stu-id="a04aa-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="a04aa-162">範例 1</span><span class="sxs-lookup"><span data-stu-id="a04aa-162">Example 1</span></span>

<span data-ttu-id="a04aa-163">在此範例中，我們建立名為 Off Shift 的新Teams Access 預設訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="a04aa-164">在此政策中，以班為基礎的目前狀態會開啟，且每當指派此策略的使用者在輪班時存取Teams會顯示預設訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="a04aa-165">如果使用者接受Teams，可以在輪班時使用通知，而第一個班次開始或最後一個班結束時，以及限制存取權之間的寬限期為 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="a04aa-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="a04aa-166">使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。</span><span class="sxs-lookup"><span data-stu-id="a04aa-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="a04aa-167">若要查看您可以為此參數選擇之預先定義的郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a04aa-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="a04aa-168">範例 2</span><span class="sxs-lookup"><span data-stu-id="a04aa-168">Example 2</span></span> 

<span data-ttu-id="a04aa-169">在此範例中，我們建立名為 Off Shift 的新Teams Access 自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="a04aa-170">在此政策中，會開啟以班次為基礎的目前狀態，且每當指派此策略的使用者在輪班時存取Teams時，都會顯示自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="a04aa-171">如果使用者接受Teams，可以在輪班時使用此程式，而第一個班次開始或最後一個班次結束時，以及限制存取權之間的寬限期為 15 分鐘。</span><span class="sxs-lookup"><span data-stu-id="a04aa-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="a04aa-172">使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。</span><span class="sxs-lookup"><span data-stu-id="a04aa-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="a04aa-173">若要深入瞭解，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a04aa-173">To learn more, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="a04aa-174">範例 3</span><span class="sxs-lookup"><span data-stu-id="a04aa-174">Example 3</span></span>

<span data-ttu-id="a04aa-175">在此範例中，我們建立名為 Off Shift Teams Access Message1 的新策略。</span><span class="sxs-lookup"><span data-stu-id="a04aa-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="a04aa-176">在此政策中，會開啟以班為基礎的目前狀態，且每次指派此策略的使用者在輪班時存取Teams預先定義的訊息。</span><span class="sxs-lookup"><span data-stu-id="a04aa-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="a04aa-177">「您的雇主不會授權或核准非免稅或小時制員工在其非工作時間使用其網路、應用程式、系統或工具。</span><span class="sxs-lookup"><span data-stu-id="a04aa-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="a04aa-178">接受時，即表示您Teams非授權且您不會獲得補償。</span><span class="sxs-lookup"><span data-stu-id="a04aa-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="a04aa-179">如果使用者接受Teams，可以在輪班時使用，而第一個班次開始或最後一個班結束時，以及限制存取權之間的寬限期為三分鐘。</span><span class="sxs-lookup"><span data-stu-id="a04aa-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="a04aa-180">使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。</span><span class="sxs-lookup"><span data-stu-id="a04aa-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="a04aa-181">若要查看您可以為此參數選擇之預先定義的郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a04aa-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="a04aa-182">範例 4</span><span class="sxs-lookup"><span data-stu-id="a04aa-182">Example 4</span></span>

<span data-ttu-id="a04aa-183">在此範例中，我們會將名為 Off Shift Teams Access 自訂訊息的一個 remy@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a04aa-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="a04aa-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="a04aa-184">Related topics</span></span>

- [<span data-ttu-id="a04aa-185">在 Teams 中管理貴組織的 Shifts 應用程式</span><span class="sxs-lookup"><span data-stu-id="a04aa-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="a04aa-186">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="a04aa-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)