---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955900"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ef2c5-103">從商務用 Skype 升級至 &mdash; 適用于 IT 系統管理員的小組</span><span class="sxs-lookup"><span data-stu-id="ef2c5-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="ef2c5-104">本文說明如何實現升級。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="ef2c5-105">本文是說明 IT 系統管理員升級概念與實現的第五個專案。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ef2c5-106">概觀</span><span class="sxs-lookup"><span data-stu-id="ef2c5-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ef2c5-107">升級方法</span><span class="sxs-lookup"><span data-stu-id="ef2c5-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ef2c5-108">管理升級的工具</span><span class="sxs-lookup"><span data-stu-id="ef2c5-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="ef2c5-109">使用商務用 Skype 內部部署之組織的其他考慮事項</span><span class="sxs-lookup"><span data-stu-id="ef2c5-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="ef2c5-110">**在本文中執行升級** () </span><span class="sxs-lookup"><span data-stu-id="ef2c5-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="ef2c5-111">公用交換電話網絡 (PSTN) 考慮</span><span class="sxs-lookup"><span data-stu-id="ef2c5-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ef2c5-112">此外，下列文章說明重要的升級概念與共存行為：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ef2c5-113">團隊與商務用 Skype 的共存</span><span class="sxs-lookup"><span data-stu-id="ef2c5-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ef2c5-114">共存模式-參考</span><span class="sxs-lookup"><span data-stu-id="ef2c5-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ef2c5-115">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="ef2c5-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="ef2c5-116">升級選項</span><span class="sxs-lookup"><span data-stu-id="ef2c5-116">Upgrade options</span></span>

<span data-ttu-id="ef2c5-117">本節說明如何使用下列其中一個升級選項來實現升級：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="ef2c5-118">使用孤島模式的重迭功能更新 () </span><span class="sxs-lookup"><span data-stu-id="ef2c5-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- <span data-ttu-id="ef2c5-119">[尚未使用團隊開始的組織的 [選取功能更新]](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)</span><span class="sxs-lookup"><span data-stu-id="ef2c5-119">[A select capabilities upgrade for an organization that has not yet started using Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)</span></span>
- <span data-ttu-id="ef2c5-120">[已在孤島模式中使用團隊之組織的 [選取功能更新]](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)</span><span class="sxs-lookup"><span data-stu-id="ef2c5-120">[A select capabilities upgrade for an organization that is already using Teams in Islands mode](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)</span></span>

<span data-ttu-id="ef2c5-121">如果您需要更多選項的相關資訊，請確定您已閱讀 [升級的方法](upgrade-to-teams-on-prem-upgrade-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="ef2c5-122">使用孤島模式的重迭功能更新 () </span><span class="sxs-lookup"><span data-stu-id="ef2c5-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="ef2c5-123">針對 [重迭的功能更新] 選項：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="ef2c5-124">如果您可以為整體組織執行快速升級，請考慮此選項。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="ef2c5-125">由於對執行這兩個用戶端的使用者而言，可能會造成混淆，因此最好將使用者必須執行兩個用戶端期間的時段最小化。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="ef2c5-126">您應該確保您的使用者知道同時執行這兩個用戶端。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="ef2c5-127">此選項是現成的模型，而且不需要系統管理員指令即可開始使用小組，除非指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="ef2c5-128">如果您的使用者已經有商務用 Skype Online，您可能已經在這個模型中了。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="ef2c5-129">在重迭功能模式並移至 TeamsOnly 時，可能會造成困難。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="ef2c5-130">由於升級的使用者只透過團隊進行通訊，組織中與該使用者進行通訊的任何其他使用者都必須使用團隊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="ef2c5-131">如果您有尚未開始使用小組的使用者，他們會面臨遺失的郵件。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="ef2c5-132">此外，他們在商務用 Skype 中不會看到 TeamsOnly 使用者的線上狀態。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="ef2c5-133">有些組織會選擇使用租使用者全域原則來執行租使用者範圍的升級，以避免這種情況，但需要前期規劃，並等到所有使用者都準備好進行升級。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="ef2c5-134">尚未使用團隊開始的組織的 [選取功能更新]</span><span class="sxs-lookup"><span data-stu-id="ef2c5-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="ef2c5-135">如果您的組織在團隊中還沒有任何作用中的使用者，第一個步驟是將 TeamsUpgradePolicy 的預設租使用者範圍原則設定為其中一個商務用 Skype 模式，例如 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ef2c5-136">尚未開始使用團隊的使用者，將不會注意到行為的任何差異。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="ef2c5-137">不過，在租使用者層級設定此原則，就可以開始將使用者升級至 TeamsOnly 模式，並確保升級後的使用者仍可與未升級的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="ef2c5-138">一旦您發現您的試驗使用者，您就可以將其升級至 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="ef2c5-139">如果他們是內部部署，請使用 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="ef2c5-140">如果它們是線上的，只要使用授與 CsTeamsUpgradePolicy，即可將其 TeamsOnly 模式指派給他們。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="ef2c5-141">根據預設，由這些使用者排程的任何商務用 Skype 會議都會遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="ef2c5-142">下列是按鍵命令：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-142">Following are the key commands:</span></span>

1. <span data-ttu-id="ef2c5-143">將 [租使用者範圍] 的預設值設定為 mode SfbWithTeamsCollab，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="ef2c5-144">將試驗使用者升級為 TeamsOnly，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="ef2c5-145">針對處於線上狀態的使用者：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="ef2c5-146">針對內部部署的使用者：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="ef2c5-147">筆記</span><span class="sxs-lookup"><span data-stu-id="ef2c5-147">Notes</span></span>
 
- <span data-ttu-id="ef2c5-148">您可以將整個租使用者的原則設定為 SfbWithTeamsCollabAndMeetings，而不是將它設定為 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="ef2c5-149">這會讓所有使用者排程團隊中的所有新會議。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="ef2c5-150">`Move-CsUser` 是內部部署工具中的一個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="ef2c5-151">`MoveToTeams`切換開關需要有 CU8 或更新版本的商務用 Skype server 2019 或商務用 Skype server 2015。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="ef2c5-152">如果您使用的是先前的版本，您可以先將使用者移至商務用 Skype Online，然後將 TeamsOnly 模式授與該使用者。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="ef2c5-153">根據預設，當您升級至 TeamsOnly 模式或指派 SfbWithTeamsCollabAndMeetings 模式時，商務用 Skype 會議會遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="ef2c5-154">下圖顯示的是沒有預先使用團隊之組織之 [選取功能更新] 的概念性階段。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="ef2c5-155">橫條圖的高度代表使用者數目。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="ef2c5-156">在升級的任何階段中，所有使用者都可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ef2c5-157">商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="ef2c5-158">[孤島] 模式中的使用者必須務必同時執行這兩個用戶端。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-158">Users in Islands mode must be sure to run both clients.</span></span>

![顯示 [沒有預先使用團隊的選取功能更新的圖表]](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="ef2c5-160">已在孤島模式中使用團隊之組織的 [選取功能更新]</span><span class="sxs-lookup"><span data-stu-id="ef2c5-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="ef2c5-161">如果貴組織中的部分使用者積極地在孤島模式中使用團隊，您可能不想移除現有使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="ef2c5-162">因此，您必須先執行額外步驟，才能變更租使用者範圍的原則。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="ef2c5-163">解決方案是在將租使用者範圍的原則設定為 SfbWithTeamsCollab 之前，將這些現有的活動團隊使用者「grandfather」成孤島模式。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ef2c5-164">完成之後，您就可以繼續進行部署，不過，您將會有兩個使用者群組會移至 TeamsOnly：在團隊中使用中的使用者將會處於孤島模式，其餘的使用者將處於 SfbWithTeamsCollab 模式。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="ef2c5-165">您可以逐步將這些使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="ef2c5-166">在團隊中尋找活躍的使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="ef2c5-167">從 Microsoft 365 系統管理中心的左側導覽中，移至 [報表]，然後移至 [使用方式]。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="ef2c5-168">在 [選取報表] 下拉式清單中，選擇 [Microsoft 團隊]，然後選擇 [使用者活動]。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="ef2c5-169">這將提供已在團隊中使用中的使用者可匯出的資料表。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="ef2c5-170">按一下 [匯出]、[開啟 Excel] 和 [篩選]，只顯示在團隊中作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="ef2c5-171">針對在步驟1中找到的每個作用中團隊使用者，在遠端 PowerShell 中指派其孤島模式。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="ef2c5-172">這可讓您移至下一個步驟，並確保您不會變更使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="ef2c5-173">將租使用者的原則設定為 SfbWithTeamsCollab：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="ef2c5-174">將選取的使用者升級至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="ef2c5-175">您可以選擇在 [孤島模式] 或 [SfbWithTeamsCollab] 模式中升級使用者，不過，您可能會想要優先處理在 [孤島] 模式中升級使用者的優先順序，以便將使用者處於 [孤島] 模式時所發生的混淆可能性降至最低。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="ef2c5-176">針對駐留在商務用 Skype Online 的使用者：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="ef2c5-177">針對駐留在內部部署的商務用 Skype 伺服器的使用者：</span><span class="sxs-lookup"><span data-stu-id="ef2c5-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="ef2c5-178">下圖顯示的是選取功能轉換的概念性階段，在開始時，有活躍的孤島使用者。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="ef2c5-179">橫條圖的高度代表使用者數目。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="ef2c5-180">在升級的任何階段中，所有使用者都可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ef2c5-181">商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ef2c5-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![圖表顯示在孤島模式中使用 [選取功能更新] 的活動使用者](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="ef2c5-183">相關連結</span><span class="sxs-lookup"><span data-stu-id="ef2c5-183">Related links</span></span>

[<span data-ttu-id="ef2c5-184">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="ef2c5-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ef2c5-185">在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="ef2c5-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ef2c5-186">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="ef2c5-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ef2c5-187">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="ef2c5-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ef2c5-188">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ef2c5-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ef2c5-189">使用會議遷移服務 (MMS) </span><span class="sxs-lookup"><span data-stu-id="ef2c5-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

