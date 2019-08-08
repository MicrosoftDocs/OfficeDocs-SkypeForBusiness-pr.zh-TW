---
title: 將您的 StaffHub 團隊移至 Microsoft 團隊中的倒班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何移動 Microsoft StaffHub 小組, 並安排資料在 Microsoft 團隊中的變化。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef8c6fbfd5ed0b19d6762b7508b311413d11066
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233280"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="bd927-103">將 Microsoft StaffHub 小組移至 Microsoft 團隊中的倒班</span><span class="sxs-lookup"><span data-stu-id="bd927-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd927-104">2019年10月1日生效, Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="bd927-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="bd927-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="bd927-106">今天, 小組包含針對排程管理的倒班應用程式, 而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="bd927-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="bd927-107">StaffHub 將會停止針對2019年10月1日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bd927-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="bd927-108">任何試圖開啟 StaffHub 的人, 都會顯示一則訊息, 讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="bd927-109">若要深入瞭解, 請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="bd927-110">團隊中的 [倒班] 應用程式提供簡單的方法來管理排程, 以及每天發生的 shift 交換與取消轉移的持續流程。</span><span class="sxs-lookup"><span data-stu-id="bd927-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="bd927-111">小組成員可以直接在應用程式和其裝置上存取其排程及轉移資訊, 以設定其喜好設定、管理其排程, 並要求下班時間。</span><span class="sxs-lookup"><span data-stu-id="bd927-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="bd927-112">本文將引導您瞭解如何移動貴組織的 StaffHub 小組, 並排程資料給小組中的倒班。</span><span class="sxs-lookup"><span data-stu-id="bd927-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="bd927-113">包括:</span><span class="sxs-lookup"><span data-stu-id="bd927-113">It covers:</span></span>

- [<span data-ttu-id="bd927-114">移至團隊所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="bd927-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="bd927-115">製作</span><span class="sxs-lookup"><span data-stu-id="bd927-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="bd927-116">進行試驗</span><span class="sxs-lookup"><span data-stu-id="bd927-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="bd927-117">超越您的試驗並移動所有 StaffHub 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="bd927-118">監視團隊使用量</span><span class="sxs-lookup"><span data-stu-id="bd927-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="bd927-119">疑難排解</span><span class="sxs-lookup"><span data-stu-id="bd927-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="bd927-120">無論您是有一個或兩個 StaffHub 小組的小型企業, 還是有數百個 StaffHub 團隊的大型企業, 在這裡, 您會發現您需要的系統管理指導方針, 以協助您的團隊順利轉至團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="bd927-121">您必須是全域系統管理員, 才能執行本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="bd927-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="bd927-122">如果您尚未這麼做, 請參閱[StaffHub 退休常見問題](microsoft-staffhub-to-be-retired.md), 以取得您可能遇到的任何問題的解答。</span><span class="sxs-lookup"><span data-stu-id="bd927-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="bd927-123">移至團隊所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="bd927-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="bd927-124">移至團隊的時機</span><span class="sxs-lookup"><span data-stu-id="bd927-124">When to move to Teams</span></span>

<span data-ttu-id="bd927-125">2019年10月1日生效, StaffHub 將會停用。</span><span class="sxs-lookup"><span data-stu-id="bd927-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="bd927-126">我們鼓勵您立即開始使用團隊, 並開始從 StaffHub 轉變貴組織的小組和使用者。</span><span class="sxs-lookup"><span data-stu-id="bd927-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="bd927-127">在 StaffHub 中, 如果 [排程管理] 是最常用的功能, 建議您在小組中使用 [倒班] app。</span><span class="sxs-lookup"><span data-stu-id="bd927-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="bd927-128">移至團隊的專案</span><span class="sxs-lookup"><span data-stu-id="bd927-128">What is moved to Teams</span></span>

<span data-ttu-id="bd927-129">當您移動 StaffHub 小組時, 小組成員資格、使用者詳細資料、小組排程及聊天資料都會移至團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="bd927-130">當您移動 StaffHub 小組時, 檔案不會移動。</span><span class="sxs-lookup"><span data-stu-id="bd927-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="bd927-131">如果 StaffHub 小組包含您也想要移至團隊的檔案, 您可以在個別步驟中移動檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="bd927-132">每個 StaffHub 小組都需要對應的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="bd927-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="bd927-133">如果 StaffHub 小組沒有與它相關聯的 Office 365 群組, 系統會自動為您建立一個支援轉場的功能。</span><span class="sxs-lookup"><span data-stu-id="bd927-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="bd927-134">考慮到團隊與 StaffHub 之間的小組和群組命名差異, 您可能會在團隊中看到不同的團隊名稱。</span><span class="sxs-lookup"><span data-stu-id="bd927-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="bd927-135">當您將團隊從 StaffHub 轉至團隊時, 使用者將無法再存取其在 StaffHub 中的排程, 且會重新導向團隊中的時間。</span><span class="sxs-lookup"><span data-stu-id="bd927-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="bd927-136">我們建議您在組織中溝通此變更, 以減少中斷並鼓勵使用者採納和探索團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="bd927-137">如果您有 Azure AD Premium, 您可以[執行報告](run-report-to-show-staffhub-usage.md), 以取得貴組織中需要瞭解此變更的 StaffHub 使用者清單。</span><span class="sxs-lookup"><span data-stu-id="bd927-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="bd927-138">將 StaffHub 小組移至團隊之後, 沒有回滾選項。</span><span class="sxs-lookup"><span data-stu-id="bd927-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="bd927-139">移動團隊時的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="bd927-139">User experience when you move a team</span></span>

<span data-ttu-id="bd927-140">當使用者的小組從 StaffHub 切換至團隊中時, 會有最少的停機時間 (只要有的話)。</span><span class="sxs-lookup"><span data-stu-id="bd927-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="bd927-141">使用者可以繼續使用 StaffHub, 直到完成 [移至] 團隊為止。</span><span class="sxs-lookup"><span data-stu-id="bd927-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="bd927-142">完成移動後, 小組成員會看到一則訊息, 讓他們知道他們需要開始使用小組中的倒班來存取其小組排程。</span><span class="sxs-lookup"><span data-stu-id="bd927-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="bd927-143">以下是使用者在 StaffHub 團隊移至團隊之後, 在 StaffHub 中看到的訊息範例。</span><span class="sxs-lookup"><span data-stu-id="bd927-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="bd927-144">![使用者看到的訊息範例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "在 StaffHub 團隊移至團隊之後, 使用者在 StaffHub 中看到的訊息範例")</span><span class="sxs-lookup"><span data-stu-id="bd927-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="bd927-145">製作</span><span class="sxs-lookup"><span data-stu-id="bd927-145">Prepare</span></span>

<span data-ttu-id="bd927-146">以下說明如何準備移至團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="bd927-147">檢查是否符合先決條件</span><span class="sxs-lookup"><span data-stu-id="bd927-147">Check that prerequisites are met</span></span>

<span data-ttu-id="bd927-148">在您將 StaffHub 小組移至團隊之前, 請確認下列事項:</span><span class="sxs-lookup"><span data-stu-id="bd927-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="bd927-149">已登入的使用者是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bd927-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="bd927-150">已針對租使用者中的所有使用者啟用團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="bd927-151">已在租使用者啟用 Office 365 群組建立。</span><span class="sxs-lookup"><span data-stu-id="bd927-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="bd927-152">StaffHub teamId 是有效的。</span><span class="sxs-lookup"><span data-stu-id="bd927-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="bd927-153">StaffHub 小組包含成員。</span><span class="sxs-lookup"><span data-stu-id="bd927-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="bd927-154">所有 StaffHub 小組成員都連結至 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="bd927-155">如果不符合這些先決條件, 移動要求將會失敗。</span><span class="sxs-lookup"><span data-stu-id="bd927-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="bd927-156">指派團隊授權</span><span class="sxs-lookup"><span data-stu-id="bd927-156">Assign Teams licenses</span></span>

<span data-ttu-id="bd927-157">每個使用者都必須從[符合資格的方案](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)中擁有有效的 Microsoft 365 或 Office 365 授權, 且必須指派團隊授權。</span><span class="sxs-lookup"><span data-stu-id="bd927-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="bd927-158">指派團隊授權給使用者可讓他們存取小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="bd927-159">您可以在 Microsoft 365 系統管理中心管理團隊授權。</span><span class="sxs-lookup"><span data-stu-id="bd927-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bd927-160">若要深入瞭解, 請參閱[管理使用者對團隊的存取權](../../user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd927-161">如果您的組織使用商務用 Skype, 而您還沒有準備好將您的所有使用者移至團隊, 您可以為第一線員工工作人員啟用團隊, 然後在商務用 Skype 中執行團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="bd927-162">在此共存模式 (稱為*孤島*) 中, 每個用戶端應用程式都是以個別的解決方案的方式運作。</span><span class="sxs-lookup"><span data-stu-id="bd927-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="bd927-163">若要深入瞭解, 請參閱[瞭解團隊及商務用 Skype 共存與互通性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="bd927-164">安裝 StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="bd927-164">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="bd927-165">如果您尚未安裝, 請[安裝 StaffHub PowerShell 模組](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-165">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="bd927-166">連結 Azure AD 帳戶給沒有 StaffHub 小組成員的人員</span><span class="sxs-lookup"><span data-stu-id="bd927-166">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="bd927-167">每個 StaffHub 小組成員都必須連結至 Azure Active Directory (Azure AD) 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-167">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="bd927-168">如果下列任何一種情況適用, 貴組織中的使用者將無法連結至 Azure AD 帳戶:</span><span class="sxs-lookup"><span data-stu-id="bd927-168">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="bd927-169">小組擁有者已新增沒有 Azure AD 帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd927-169">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="bd927-170">小組擁有者受邀使用者加入 StaffHub 小組, 而該使用者並未接受邀請。</span><span class="sxs-lookup"><span data-stu-id="bd927-170">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="bd927-171">您可以連結這些使用者的 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-171">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="bd927-172">方法如下。</span><span class="sxs-lookup"><span data-stu-id="bd927-172">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="bd927-173">取得 StaffHub 小組中所有使用者的清單, 這些使用者的小組成員未連結至 Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="bd927-173">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="bd927-174">執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="bd927-174">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="bd927-175">連結帳戶</span><span class="sxs-lookup"><span data-stu-id="bd927-175">Link the account</span></span>

<span data-ttu-id="bd927-176">請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="bd927-176">Do one of the following:</span></span>

- <span data-ttu-id="bd927-177">轉換及連結帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-177">Convert and link the account.</span></span>

  <span data-ttu-id="bd927-178">StaffHub 小組擁有者和管理員可以轉換非作用中的帳戶, 並將其連結至 StaffHub 中的 Azure AD 帳戶, 做法是將使用者的電子郵件地址變更為 [StaffHub 小組設定] 頁面上的有效 UPN。</span><span class="sxs-lookup"><span data-stu-id="bd927-178">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="bd927-179">移除未連結的帳戶, 然後使用 UPN 重新加入該帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-179">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="bd927-180">執行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) Cmdlet, 以從 StaffHub 團隊中移除未預配的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-180">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="bd927-181">執行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) Cmdlet, 以使用 UPN 將帳戶重新新增到 StaffHub 小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-181">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="bd927-182">移除未連結的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-182">Remove the unlinked user account.</span></span> <span data-ttu-id="bd927-183">使用這個選項已不再需要使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd927-183">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="bd927-184">將 FirstlineWorker 應用程式設定原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="bd927-184">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="bd927-185">團隊包含內建的 FirstlineWorker 應用程式設定原則, 您可以用來自訂小組, 以醒目提示貴組織中的第一線員工工人最重要的 app。</span><span class="sxs-lookup"><span data-stu-id="bd927-185">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="bd927-186">當您將此原則指派給使用者時, 原則中的應用程式會釘選在團隊中的應用程式行上, 以便快速且輕鬆地存取。</span><span class="sxs-lookup"><span data-stu-id="bd927-186">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="bd927-187">您可以在應用程式行中, 按一下 [...], 在應用程式行中找到新增至團隊的其他 app。 \*\*\*\* 小組桌面及網頁用戶端中的其他應用程式, 以及在小組行動用戶端中向上輕掃。</span><span class="sxs-lookup"><span data-stu-id="bd927-187">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="bd927-188">根據預設, FirstlineWorker 應用程式的設定原則包括活動、班次、聊天及呼叫 app。</span><span class="sxs-lookup"><span data-stu-id="bd927-188">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="bd927-189">如需如何將 FirstlineWorker 應用程式設定原則指派給使用者的步驟, 請參閱[使用 FirstlineWorker 應用程式設定原則將倒班移至團隊](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="bd927-189">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="bd927-190">指派原則之後, 最多可能需要24小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="bd927-190">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="bd927-191">我們建議您至少在一周完成此步驟, 然後再將您的 StaffHub 團隊和使用者移至團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-191">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="bd927-192">當使用者在團隊中時, 請確認他們可以查看和存取倒班 app。</span><span class="sxs-lookup"><span data-stu-id="bd927-192">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="bd927-193">您也可以建立自訂應用程式設定原則, 並編輯全域 app 設定原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="bd927-193">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="bd927-194">若要深入瞭解, 請參閱[管理團隊中的 app 設定原則](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-194">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="bd927-195">在團隊中的使用者</span><span class="sxs-lookup"><span data-stu-id="bd927-195">Onboard users to Teams</span></span>

<span data-ttu-id="bd927-196">在您的加入戰略中, 請為使用者提供訓練與指導方針, 以協助他們熟悉團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-196">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="bd927-197">與使用者共用下列資源, 讓他們知道要取得團隊用戶端、訓練及支援的位置:</span><span class="sxs-lookup"><span data-stu-id="bd927-197">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="bd927-198">團隊網頁用戶端</span><span class="sxs-lookup"><span data-stu-id="bd927-198">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="bd927-199">桌面和行動用戶端下載連結</span><span class="sxs-lookup"><span data-stu-id="bd927-199">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="bd927-200">團隊訓練影片</span><span class="sxs-lookup"><span data-stu-id="bd927-200">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="bd927-201">團隊說明文件</span><span class="sxs-lookup"><span data-stu-id="bd927-201">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="bd927-202">如需部署團隊及促進團隊採納的指導方針, 請參閱[如何推出](../../How-to-roll-out-teams.md)團隊並[採用團隊](../../adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-202">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="bd927-203">進行試驗</span><span class="sxs-lookup"><span data-stu-id="bd927-203">Conduct a pilot</span></span>

<span data-ttu-id="bd927-204">我們建議您先將兩個或三個 StaffHub 小組移出一組早期採用者的選取群組。</span><span class="sxs-lookup"><span data-stu-id="bd927-204">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="bd927-205">執行試驗可協助您調整轉場計畫, 並確保您已準備好將貴組織的所有 StaffHub 小組移至團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-205">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="bd927-206">它也會識別可協助推動整個組織採用的擁護者。</span><span class="sxs-lookup"><span data-stu-id="bd927-206">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="bd927-207">如果您是小型企業, 且不需要分階段的方法, 本節中的步驟可能就是, 您必須從 StaffHub 到團隊進行切換。</span><span class="sxs-lookup"><span data-stu-id="bd927-207">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="bd927-208">找出試生產團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-208">Identify pilot teams</span></span>

<span data-ttu-id="bd927-209">向外延伸以找出兩個或三個試驗小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-209">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="bd927-210">所有小組成員都應該承諾使用小組中的倒班來管理自己的排程, 並相互溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="bd927-210">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="bd927-211">識別團隊擁護人員</span><span class="sxs-lookup"><span data-stu-id="bd927-211">Identify team champions</span></span>

<span data-ttu-id="bd927-212">在試驗小組中找出擁護者, 並登記它們以協助 evangelize 倒班。</span><span class="sxs-lookup"><span data-stu-id="bd927-212">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="bd927-213">小組擁護者會熱情他們的功能, 分享自己的學習專案, 以提供給小組成員的支援與指導方針。</span><span class="sxs-lookup"><span data-stu-id="bd927-213">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="bd927-214">團隊擁護者可以是團隊擁有人或管理員。</span><span class="sxs-lookup"><span data-stu-id="bd927-214">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="bd927-215">團隊擁護者應該確保小組成員已設定為每個人[取得團隊用戶端](../../get-clients.md)所需的時間, 登入小組, 並在倒班中查看他們的排程, 並開始彼此交談。</span><span class="sxs-lookup"><span data-stu-id="bd927-215">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="bd927-216">已熟悉 StaffHub 的使用者將會在倒班中快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="bd927-216">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="bd927-217">您也可以將其指向[協助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以取得其他協助。</span><span class="sxs-lookup"><span data-stu-id="bd927-217">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="bd927-218">移動 StaffHub 小組</span><span class="sxs-lookup"><span data-stu-id="bd927-218">Move a StaffHub team</span></span>

<span data-ttu-id="bd927-219">使用這些步驟, 一次移動一個 StaffHub 小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-219">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="bd927-220">我們建議您試用版團隊採用這種方法。</span><span class="sxs-lookup"><span data-stu-id="bd927-220">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="bd927-221">之後, 當您準備好要移動您組織的所有 StaffHub 小組時, 請參閱[移動您的 StaffHub 小組](#move-your-staffhub-teams), 以取得如何一次移動多個團隊的步驟。</span><span class="sxs-lookup"><span data-stu-id="bd927-221">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="bd927-222">執行下列動作來移動 StaffHub 小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-222">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="bd927-223">範例</span><span class="sxs-lookup"><span data-stu-id="bd927-223">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="bd927-224">以下是當您提交要求以將 StaffHub 小組移至團隊時所取得的回應範例。</span><span class="sxs-lookup"><span data-stu-id="bd927-224">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="bd927-225">若要檢查移動要求的狀態, 請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="bd927-225">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="bd927-226">範例</span><span class="sxs-lookup"><span data-stu-id="bd927-226">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="bd927-227">以下是您在移動進行中時所取得的回應範例。</span><span class="sxs-lookup"><span data-stu-id="bd927-227">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="bd927-228">將檔案從 StaffHub 小組移至團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-228">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="bd927-229">此步驟僅適用于您移至團隊的 StaffHub 小組是否有您想要移至團隊的檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-229">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="bd927-230">您可以直接在 SharePoint Online 或使用 PowerShell 中移動檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-230">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="bd927-231">在 SharePoint Online 中</span><span class="sxs-lookup"><span data-stu-id="bd927-231">In SharePoint Online</span></span>

<span data-ttu-id="bd927-232">瞭解[如何在 SharePoint Online 中移動](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-232">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="bd927-233">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd927-233">Using PowerShell</span></span>

<span data-ttu-id="bd927-234">如果您尚未下載並安裝[SharePoint Online 管理命令](https://www.microsoft.com/download/details.aspx?id=35588)介面, 請先下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="bd927-234">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="bd927-235">它包含您要移動檔案所需的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd927-235">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="bd927-236">使用[PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) Cmdlet 連線至 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="bd927-236">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="bd927-237">針對您要從 StaffHub 移至 [團隊] 的每個檔案, 請使用[PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) Cmdlet 來移動檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-237">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="bd927-238">若要移動多個檔案, 請迴圈流覽檔案, 然後在迴圈上執行第二個命令。</span><span class="sxs-lookup"><span data-stu-id="bd927-238">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="bd927-239">如果會話保持作用中, 您就不需要重複第一個命令。</span><span class="sxs-lookup"><span data-stu-id="bd927-239">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="bd927-240">超越您的試驗並移動所有 StaffHub 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-240">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="bd927-241">提高知名度</span><span class="sxs-lookup"><span data-stu-id="bd927-241">Raise awareness</span></span>

<span data-ttu-id="bd927-242">當您準備好超越您的試驗小組, 並將貴組織的 StaffHub 小組移至團隊時, 請務必先在組織中溝通所做的變更。</span><span class="sxs-lookup"><span data-stu-id="bd927-242">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="bd927-243">將有關倒班與轉場的相關資訊散佈在團隊中, 以提高知名度、產生驚喜, 以及推動採用。</span><span class="sxs-lookup"><span data-stu-id="bd927-243">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="bd927-244">移動您的 StaffHub 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-244">Move your StaffHub teams</span></span>

<span data-ttu-id="bd927-245">使用這些步驟來大量移動 StaffHub 團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-245">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="bd927-246">您可以選擇移動您組織的所有 StaffHub 小組, 或移動特定的 StaffHub 團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-246">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="bd927-247">如果您想要一次移動一個 StaffHub 小組, 請參閱[移動 StaffHub 團隊](#move-a-staffhub-team)。</span><span class="sxs-lookup"><span data-stu-id="bd927-247">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="bd927-248">移動所有 StaffHub 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-248">Move all StaffHub teams</span></span>

<span data-ttu-id="bd927-249">執行下列動作, 取得貴組織中所有 StaffHub 小組的清單。</span><span class="sxs-lookup"><span data-stu-id="bd927-249">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="bd927-250">然後, 執行下列動作來移動所有團隊。</span><span class="sxs-lookup"><span data-stu-id="bd927-250">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="bd927-251">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="bd927-251">Here's an example of the response.</span></span>

<span data-ttu-id="bd927-252">針對已移至團隊或已存在於團隊中的任何小組, 該作業將會是 "null", 因為工作不需要提交就能移動該小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-252">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="bd927-253">移動特定的 StaffHub 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-253">Move specific StaffHub teams</span></span>

<span data-ttu-id="bd927-254">執行下列動作, 取得貴組織中所有 StaffHub 小組識別碼的清單。</span><span class="sxs-lookup"><span data-stu-id="bd927-254">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="bd927-255">在您先前執行的`Get-StaffHubteamsForTenant` Cmdlet 所傳回的結果中, 選取您要移動的團隊識別碼, 然後將它們新增到逗號分隔值 (CSV) 檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-255">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="bd927-256">以下是如何格式化 CSV 檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="bd927-256">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="bd927-257">標識號</span><span class="sxs-lookup"><span data-stu-id="bd927-257">Id</span></span>  |
|---------|
|<span data-ttu-id="bd927-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="bd927-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="bd927-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="bd927-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="bd927-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="bd927-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="bd927-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="bd927-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="bd927-262">建立 CSV 檔案之後, 請執行下列動作, 以移動您在 CSV 檔案中指定的小組。</span><span class="sxs-lookup"><span data-stu-id="bd927-262">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="bd927-263">確認您的 StaffHub 小組已移至團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-263">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="bd927-264">執行下列動作, 以取得貴組織中所有團隊成員的清單。</span><span class="sxs-lookup"><span data-stu-id="bd927-264">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="bd927-265">將檔案從您的 StaffHub 團隊移至團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-265">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="bd927-266">如果您移動的 StaffHub 小組包含您也想要移至團隊的檔案, 請參閱[將檔案從 StaffHub 團隊移至 [小組](#move-files-from-a-staffhub-team-to-teams)]。</span><span class="sxs-lookup"><span data-stu-id="bd927-266">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="bd927-267">監視團隊使用量</span><span class="sxs-lookup"><span data-stu-id="bd927-267">Monitor Teams usage</span></span>

<span data-ttu-id="bd927-268">使用方式報告可協助您更好地瞭解使用模式, 並讓您深入瞭解組織中的訓練和溝通工作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bd927-268">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="bd927-269">您可以執行報表, 顯示整體團隊的使用量、使用者在團隊中執行的活動類型、使用者連線至團隊的方式等等。</span><span class="sxs-lookup"><span data-stu-id="bd927-269">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="bd927-270">如需詳細資訊, 請參閱 microsoft[團隊系統管理中心的團隊報告](../../teams-analytics-and-reports/teams-reporting-reference.md), 以及[microsoft 365 系統管理中心的小組活動報告](../../teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="bd927-270">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bd927-271">疑難排解</span><span class="sxs-lookup"><span data-stu-id="bd927-271">Troubleshooting</span></span>

<span data-ttu-id="bd927-272">**當您嘗試將檔案從 StaffHub 移至 [團隊] 時, 您會收到「許可權被拒絕」錯誤訊息。**</span><span class="sxs-lookup"><span data-stu-id="bd927-272">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="bd927-273">如果您嘗試將檔案移動到您不是其成員的私人 Office 365 群組中, 可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="bd927-273">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="bd927-274">如果是這種情況, 請使用[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) Cmdlet 將自己新增至 StaffHub 小組, 然後移動檔案。</span><span class="sxs-lookup"><span data-stu-id="bd927-274">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="bd927-275">移動檔案之後, 請使用[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) Cmdlet 將自己從團隊中移除。</span><span class="sxs-lookup"><span data-stu-id="bd927-275">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="bd927-276">**當您嘗試將檔案從 StaffHub 移至 [團隊] 時, 會出現錯誤, 指出一般資料夾不存在。**</span><span class="sxs-lookup"><span data-stu-id="bd927-276">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="bd927-277">執行下列命令以將一般資料夾新增至 SharePoint, 然後再試一次:</span><span class="sxs-lookup"><span data-stu-id="bd927-277">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="bd927-278">相關主題</span><span class="sxs-lookup"><span data-stu-id="bd927-278">Related topics</span></span>
- [<span data-ttu-id="bd927-279">如何推出 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="bd927-279">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="bd927-280">Microsoft StaffHub 停用</span><span class="sxs-lookup"><span data-stu-id="bd927-280">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="bd927-281">在 Microsoft 團隊中為您的組織管理倒班應用程式</span><span class="sxs-lookup"><span data-stu-id="bd927-281">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="bd927-282">StaffHub PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="bd927-282">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
