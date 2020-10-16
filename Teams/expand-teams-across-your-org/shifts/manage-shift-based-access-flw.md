---
title: 針對團隊中的第一線員工工作者管理以倒班為基礎的存取權
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對貴組織中的第一線員工工作人員，在小組中管理以倒班為基礎的存取權。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01180f95766412b82d9df7986c3667298f24d5b4
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486851"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a><span data-ttu-id="4e241-103">針對團隊中的第一線員工工作者管理以倒班為基礎的存取權</span><span class="sxs-lookup"><span data-stu-id="4e241-103">Manage shift-based access for Firstline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e241-104">2020年6月30日生效，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="4e241-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="4e241-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="4e241-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="4e241-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="4e241-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="4e241-107">StaffHub 已停止針對2020年6月30日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4e241-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="4e241-108">任何試圖開啟 StaffHub 的人都會顯示一則訊息，讓他們下載團隊。</span><span class="sxs-lookup"><span data-stu-id="4e241-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="4e241-109">若要深入瞭解，請參閱 [Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。</span><span class="sxs-lookup"><span data-stu-id="4e241-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="4e241-110">概觀</span><span class="sxs-lookup"><span data-stu-id="4e241-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4e241-111">Microsoft 團隊中的目前狀態表示使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="4e241-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="4e241-112">與其他員工相比，目前的工作時間通常不是相同的，因此第一線員工工作者的狀態通常不會太容易被人預測。</span><span class="sxs-lookup"><span data-stu-id="4e241-112">The presence of Firstline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="4e241-113">身為系統管理員，您可以將團隊設定為顯示您組織中的第一線員工工作人員的一組班次的目前狀態，以指出他們是在何時開啟和關閉班次。</span><span class="sxs-lookup"><span data-stu-id="4e241-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Firstline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="4e241-114">這些以移動為基礎的線上狀態會以 &mdash; ![ 純綠色核取記號表示 [倒班 ](../../media/flw-presence-on-shift.png) **上**的 shift， ![ 灰色圓圈（含 x）] 表示 [向下移動] 表示 [忙碌] 的 [忙碌] 與 ](../../media/flw-presence-off-shift.png) **Off shift** ![ ](../../media/flw-presence-busy.png) **Busy** &mdash; [團隊中的目前[狀態] 狀態](../../presence-admins.md)是分開的。</span><span class="sxs-lookup"><span data-stu-id="4e241-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="4e241-115">在這兩組目前狀態的狀態中，您可以根據組織中的人員角色來設定不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="4e241-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="4e241-116">使用值班式存取時，您可以在第一線員工工作人員離開班次時管理團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="4e241-116">With shift-based access, you can manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="4e241-117">例如，您可以將團隊設定為顯示一則訊息，讓第一線員工工人必須承認，才能使用小組，而不是排定的班次。</span><span class="sxs-lookup"><span data-stu-id="4e241-117">For example, you can set Teams to display a message that Firstline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="4e241-118">案例</span><span class="sxs-lookup"><span data-stu-id="4e241-118">Scenario</span></span>

<span data-ttu-id="4e241-119">以下範例說明您的組織可以如何管理以倒班為基礎的存取。</span><span class="sxs-lookup"><span data-stu-id="4e241-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="4e241-120">您的組織中有第一線員工的工作人員，只應支付其主管排程和核准之班次所進行的工時。</span><span class="sxs-lookup"><span data-stu-id="4e241-120">You have Firstline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="4e241-121">不應針對排程班次以外的時間所花費的時間進行支付，包括使用團隊 app。</span><span class="sxs-lookup"><span data-stu-id="4e241-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="4e241-122">您設定的自訂訊息指出「當您在小組中時，您的時間不會計算在應付時數」，這會在第一線員工工作人員嘗試在關閉班次時存取團隊時顯示。</span><span class="sxs-lookup"><span data-stu-id="4e241-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Firstline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="4e241-123">如果他們選擇使用團隊，按一下 [ **我接受** ]，就能瞭解他們目前不會支付。</span><span class="sxs-lookup"><span data-stu-id="4e241-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="4e241-124">您的組織中也有資訊工作者正在 salaried，而其他人不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="4e241-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="4e241-125">您可以將您的資訊工作者設定為在團隊中使用預設的目前狀態狀態，而提供您的第一線員工工作者輪換式的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e241-125">You configure your information workers to use the default presence states in Teams while giving your Firstline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="4e241-126">依移動狀態</span><span class="sxs-lookup"><span data-stu-id="4e241-126">Shift-based presence states</span></span>

<span data-ttu-id="4e241-127">以下是依班的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e241-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="4e241-128">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="4e241-128">App configured</span></span> |<span data-ttu-id="4e241-129">使用者設定</span><span class="sxs-lookup"><span data-stu-id="4e241-129">User configured</span></span>  |<span data-ttu-id="4e241-130">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4e241-130">More information</span></span>  |
|---------|---------|---------|
|![[實心綠色] 核取記號，代表 [倒班]](../../media/flw-presence-on-shift.png) <span data-ttu-id="4e241-132">在班次上</span><span class="sxs-lookup"><span data-stu-id="4e241-132">On shift</span></span>     |         |<span data-ttu-id="4e241-133">在班次開始時自動設定</span><span class="sxs-lookup"><span data-stu-id="4e241-133">Automatically set at the start of a shift</span></span>         |
|![含 x 的灰色圓圈表示離開班次](../../media/flw-presence-off-shift.png) <span data-ttu-id="4e241-135">關閉班次</span><span class="sxs-lookup"><span data-stu-id="4e241-135">Off shift</span></span>     |         |<span data-ttu-id="4e241-136">在班次結束時自動設定</span><span class="sxs-lookup"><span data-stu-id="4e241-136">Automatically set at the end of a shift</span></span>         |
|![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="4e241-138">忙碌</span><span class="sxs-lookup"><span data-stu-id="4e241-138">Busy</span></span>      | ![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="4e241-140">忙碌</span><span class="sxs-lookup"><span data-stu-id="4e241-140">Busy</span></span>         |<span data-ttu-id="4e241-141">自動設定。</span><span class="sxs-lookup"><span data-stu-id="4e241-141">Automatically set.</span></span> <span data-ttu-id="4e241-142">您也可以在第一線員工工人開啟倒班時手動設定。</span><span class="sxs-lookup"><span data-stu-id="4e241-142">Can also be manually set when the Firstline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="4e241-143">關閉對團隊的 shift 存取權</span><span class="sxs-lookup"><span data-stu-id="4e241-143">Off shift access to Teams</span></span>

<span data-ttu-id="4e241-144">此功能可讓您在第一線員工的工作人員關閉班次時管理團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="4e241-144">This feature lets you manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="4e241-145">您可以將團隊設定為在員工在關閉時存取小組時，顯示訊息來第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="4e241-145">You can set Teams to display a message to Firstline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="4e241-146">第一線員工工作人員必須按一下 [ **我接受** ] 來確認訊息，才能使用小組。</span><span class="sxs-lookup"><span data-stu-id="4e241-146">Firstline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="4e241-147">您可以使用預設訊息、選擇一組預先定義的郵件，或自訂郵件以顯示任何您想要的文字。</span><span class="sxs-lookup"><span data-stu-id="4e241-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="4e241-148">以下是預設訊息：</span><span class="sxs-lookup"><span data-stu-id="4e241-148">Here's the default message:</span></span>

![預設訊息的螢幕擷取畫面](../../media/shifts-presence-message.png)

<span data-ttu-id="4e241-150">您也可以在顯示訊息時設定頻率，並在第一個班次開始或最後一個班次結束時，以及在團隊存取權受到限制時，設定寬限期。</span><span class="sxs-lookup"><span data-stu-id="4e241-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="4e241-151">管理以 shift 為基礎的存取</span><span class="sxs-lookup"><span data-stu-id="4e241-151">Manage shift-based access</span></span>

<span data-ttu-id="4e241-152">做為管理員，您可以使用原則來控制貴組織中第一線員工工作人員的移動狀態。</span><span class="sxs-lookup"><span data-stu-id="4e241-152">As an admin, you use policies to control shift-based presence for Firstline Workers in your organization.</span></span> <span data-ttu-id="4e241-153">您可以使用下列 PowerShell Cmdlet 來管理這些原則：</span><span class="sxs-lookup"><span data-stu-id="4e241-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="4e241-154">新-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="4e241-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="4e241-155">CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="4e241-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="4e241-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="4e241-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="4e241-157">授與 CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="4e241-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="4e241-158">移除-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="4e241-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="4e241-159">使用 New-CsTeamsShiftsPolicy Cmdlet 來建立新的原則，設定您想要的原則設定，然後使用 Grant-CsTeamsShiftsPolicy Cmdlet 將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="4e241-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="4e241-160">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="4e241-160">Here's some examples.</span></span> <span data-ttu-id="4e241-161">如需每個原則設定與參數的詳細資訊，包括可供您選擇的預先定義的 [輪換] 訊息清單，請參閱 [新-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="4e241-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="4e241-162">範例 1</span><span class="sxs-lookup"><span data-stu-id="4e241-162">Example 1</span></span>

<span data-ttu-id="4e241-163">在這個範例中，我們會建立一個名為 [關閉班次小組] 的新原則，以存取預設的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="4e241-164">在此原則中，會開啟移動前的目前狀態，且每次獲指派此原則的使用者，都會在停用班次時，顯示預設的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="4e241-165">如果使用者接受該訊息，且在第一個班次開始或最後一個班次結束時，以及存取受到限制為10分鐘，則使用者可以在小組中使用團隊。</span><span class="sxs-lookup"><span data-stu-id="4e241-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="4e241-166">使用 **ShiftNoticeMessageType** 參數來設定您要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="4e241-167">若要查看您可以為此參數選擇的預先定義訊息清單，請參閱 [新 CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="4e241-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="4e241-168">範例 2</span><span class="sxs-lookup"><span data-stu-id="4e241-168">Example 2</span></span> 

<span data-ttu-id="4e241-169">在這個範例中，我們會建立一個名為 [登出] 的新原則，以存取自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="4e241-170">在這項原則中，會開啟移動前的目前狀態，且每次獲指派此原則的使用者在停用班次時，都會顯示自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="4e241-171">如果使用者接受該訊息，且在第一個班次開始或最後一個班次結束時，以及限制存取的時間是15分鐘，使用者就可以使用團隊來關閉班次。</span><span class="sxs-lookup"><span data-stu-id="4e241-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="4e241-172">使用 **ShiftNoticeMessageType** 參數來設定您要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="4e241-173">若要深入瞭解，請參閱 [新-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="4e241-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="4e241-174">範例 3</span><span class="sxs-lookup"><span data-stu-id="4e241-174">Example 3</span></span>

<span data-ttu-id="4e241-175">在這個範例中，我們會建立一個名為 [取消轉換團隊] 的新原則，以存取 Message1。</span><span class="sxs-lookup"><span data-stu-id="4e241-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="4e241-176">在此原則中，會開啟移動前的目前狀態，且每次獲指派此原則的使用者在關閉班次時，都會出現下列預先定義的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="4e241-177">「您的雇主不會在非工作時間內以無人豁免或每小時員工授權或核准其網路、應用程式、系統或工具的使用方式。</span><span class="sxs-lookup"><span data-stu-id="4e241-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="4e241-178">透過接受，您承認您在非授權的情況下使用您的小組，而且您不會收到報酬。</span><span class="sxs-lookup"><span data-stu-id="4e241-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="4e241-179">如果使用者接受該訊息，且在第一個班次開始或最後一個班次結束時，以及存取限制是3分鐘，則使用者可以在小組中使用團隊。</span><span class="sxs-lookup"><span data-stu-id="4e241-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="4e241-180">使用 **ShiftNoticeMessageType** 參數來設定您要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="4e241-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="4e241-181">若要查看您可以為此參數選擇的預先定義訊息清單，請參閱新 TeamsShiftPolicy。</span><span class="sxs-lookup"><span data-stu-id="4e241-181">To see a list of the pre-defined messages that you can choose from for this parameter, see New-TeamsShiftPolicy.</span></span>

### <a name="example-4"></a><span data-ttu-id="4e241-182">範例 4</span><span class="sxs-lookup"><span data-stu-id="4e241-182">Example 4</span></span>

<span data-ttu-id="4e241-183">在這個範例中，我們會將名為「取消」團隊的原則存取自訂訊息給名為 remy@contoso.com 的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e241-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="4e241-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="4e241-184">Related topics</span></span>

- [<span data-ttu-id="4e241-185">在 Teams 中管理貴組織的 Shifts 應用程式</span><span class="sxs-lookup"><span data-stu-id="4e241-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="4e241-186">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="4e241-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
