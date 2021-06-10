---
title: IT 系統管理員的升級策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文適用于 IT 系統管理員，並說明從企業升級商務用 Skype升級Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e4bfb5594b64eb06041e7f761eb0d85cec8c3e5
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306037"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="f5b11-103">IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="f5b11-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="f5b11-104">![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="f5b11-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f5b11-105">本文適用于想要從 Teams 升級至 商務用 Skype 的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f5b11-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="f5b11-106">在執行升級之前，我們建議您閱讀下列文章，說明重要的升級概念和共存行為：</span><span class="sxs-lookup"><span data-stu-id="f5b11-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f5b11-107">瞭解Microsoft Teams商務用 Skype及互通性</span><span class="sxs-lookup"><span data-stu-id="f5b11-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f5b11-108">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="f5b11-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f5b11-109">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="f5b11-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="f5b11-110">升級選項</span><span class="sxs-lookup"><span data-stu-id="f5b11-110">Upgrade options</span></span>

<span data-ttu-id="f5b11-111">本節說明如何使用下列其中一個升級選項來實施升級：</span><span class="sxs-lookup"><span data-stu-id="f5b11-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="f5b11-112">使用群島模式 (功能更新) </span><span class="sxs-lookup"><span data-stu-id="f5b11-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="f5b11-113">尚未開始使用新版Teams</span><span class="sxs-lookup"><span data-stu-id="f5b11-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="f5b11-114">針對已在群島模式中使用Teams的選取功能更新</span><span class="sxs-lookup"><span data-stu-id="f5b11-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="f5b11-115">如果您需要有關選項的詳細資訊，請確定您已經閱讀過選擇從 商務用 Skype[到 Teams 的升級Teams。](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f5b11-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="f5b11-116">使用群島模式 (功能更新) </span><span class="sxs-lookup"><span data-stu-id="f5b11-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="f5b11-117">針對重迭功能更新選項：</span><span class="sxs-lookup"><span data-stu-id="f5b11-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="f5b11-118">如果您能針對整個組織執行快速升級，請考慮使用此選項。</span><span class="sxs-lookup"><span data-stu-id="f5b11-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="f5b11-119">由於執行這兩個用戶端的使用者有可能會混淆，因此最好能將使用者必須同時執行這兩個用戶端的時段降到最低。</span><span class="sxs-lookup"><span data-stu-id="f5b11-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="f5b11-120">您應該確保您的使用者知道要執行這兩個用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5b11-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="f5b11-121">此選項是開箱即用模型，不需要系統管理員動作，Teams指派授權或Microsoft 365 Office 365授權。</span><span class="sxs-lookup"><span data-stu-id="f5b11-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="f5b11-122">如果您的使用者已經有 商務用 Skype Online，您可能已經在這個模型中。</span><span class="sxs-lookup"><span data-stu-id="f5b11-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="f5b11-123">若要擺脫重迭的功能模式，並移往 TeamsOnly，可能會非常困難。</span><span class="sxs-lookup"><span data-stu-id="f5b11-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="f5b11-124">因為升級的使用者只會透過Teams通訊，因此組織中與該使用者通訊的其他使用者必須使用Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="f5b11-125">如果您的使用者尚未開始使用Teams，他們將會暴露在遺失的郵件中。</span><span class="sxs-lookup"><span data-stu-id="f5b11-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="f5b11-126">此外，他們也不會在 商務用 Skype 中看到 TeamsOnly 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="f5b11-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="f5b11-127">有些組織選擇使用租使用者全域原則執行整個租使用者升級，以避免這種情況，不過這需要預先規劃，並等到所有使用者準備好升級。</span><span class="sxs-lookup"><span data-stu-id="f5b11-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="f5b11-128">尚未開始使用新版Teams</span><span class="sxs-lookup"><span data-stu-id="f5b11-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="f5b11-129">如果貴組織尚未在 Teams 中有任何作用中使用者，第一個步驟是將 TeamsUpgradePolicy 的預設租使用者範圍政策設定為 商務用 Skype 模式之一，例如 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="f5b11-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f5b11-130">尚未開始使用此Teams不會注意到行為有任何差異。</span><span class="sxs-lookup"><span data-stu-id="f5b11-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="f5b11-131">不過，在租使用者層級設定此策略，就可以開始將使用者升級至 TeamsOnly 模式，並確保升級的使用者仍然可以與未升級的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="f5b11-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="f5b11-132">一旦找出您的試驗使用者，就可以將它們升級至 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="f5b11-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="f5b11-133">如果是內部部署，請使用 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="f5b11-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="f5b11-134">如果他們在線上，只要使用 Grant-CsTeamsUpgradePolicy 指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="f5b11-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="f5b11-135">根據預設，商務用 Skype使用者排定的任何會議都會移Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="f5b11-136">以下是關鍵命令：</span><span class="sxs-lookup"><span data-stu-id="f5b11-136">Following are the key commands:</span></span>

1. <span data-ttu-id="f5b11-137">將整個租使用者的預設設定為模式 SfbWithTeamsCollab，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5b11-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="f5b11-138">將試驗使用者升級至 TeamsOnly，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5b11-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="f5b11-139">適用于線上使用者：</span><span class="sxs-lookup"><span data-stu-id="f5b11-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="f5b11-140">適用于內部部署的使用者：</span><span class="sxs-lookup"><span data-stu-id="f5b11-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="f5b11-141">注釋</span><span class="sxs-lookup"><span data-stu-id="f5b11-141">Notes</span></span>
 
- <span data-ttu-id="f5b11-142">您可以設定 SfbWithTeamsCollabs，而不是將整個租使用者的政策設定為 SfbWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="f5b11-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="f5b11-143">這會使所有使用者在會議中排程Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="f5b11-144">`Move-CsUser` 是內部部署工具中的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5b11-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="f5b11-145">切換 `MoveToTeams` 需要 2019 商務用 Skype Server 2015 或 2015 商務用 Skype Server CU8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f5b11-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="f5b11-146">如果您使用的是先前版本，您可以先將使用者移至 商務用 Skype，然後將 TeamsOnly 模式授予該使用者。</span><span class="sxs-lookup"><span data-stu-id="f5b11-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="f5b11-147">根據預設，商務用 Skype升級至 TeamsOnly 模式Teams或指派 SfbWithTeamsCollabAndMeetings 模式時，會議會移至其他會議。</span><span class="sxs-lookup"><span data-stu-id="f5b11-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5b11-148">為了準備即將商務用 Skype Online，Microsoft 將會簡化組織在近期內Teams如何移至線上。</span><span class="sxs-lookup"><span data-stu-id="f5b11-148">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future.</span></span> <span data-ttu-id="f5b11-149">將使用者從內部部署移至Teams，很快就會不再需要指定移入，將使用者直接從內部部署移至 `-MoveToTeams` `Move-CsUser` TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="f5b11-149">When moving a user from on-premises to Teams, it will soon no longer be required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises to TeamsOnly.</span></span> <span data-ttu-id="f5b11-150">目前如果未指定此切換，使用者會從內部部署中的商務用 Skype Server切換到 商務用 Skype Online，其模式會維持不變。</span><span class="sxs-lookup"><span data-stu-id="f5b11-150">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged.</span></span> <span data-ttu-id="f5b11-151">停用之後，將使用者從內部部署移動到雲端時，系統會自動將使用者指派 TeamsOnly 模式，而他們的會議從內部部署會自動轉換成 Teams 會議，就像無論實際指定切換是否一樣。 `Move-CsUser` `-MoveToTeams switch had been specified`</span><span class="sxs-lookup"><span data-stu-id="f5b11-151">After retirement, when moving a user from on-premises to the cloud with `Move-CsUser`, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="f5b11-152">我們預期在 2021 年 7 月 31 日實際停用之前發行此功能。</span><span class="sxs-lookup"><span data-stu-id="f5b11-152">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>


<span data-ttu-id="f5b11-153">下圖顯示組織中未事先使用特定功能之組織之選取功能更新的概念Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-153">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="f5b11-154">長條的高度代表使用者數目。</span><span class="sxs-lookup"><span data-stu-id="f5b11-154">The height of the bars represents number of users.</span></span> <span data-ttu-id="f5b11-155">在升級的任何階段，所有使用者都可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="f5b11-155">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f5b11-156">商務用 Skype使用 Interop 與 TeamsOnly 使用者通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f5b11-156">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="f5b11-157">在群島模式中的使用者必須確定要同時執行這兩個用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5b11-157">Users in Islands mode must be sure to run both clients.</span></span>

![顯示選取功能更新的圖表，無需事先Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="f5b11-159">針對已在群島模式中使用Teams的選取功能更新</span><span class="sxs-lookup"><span data-stu-id="f5b11-159">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="f5b11-160">如果貴組織中某些使用者Teams群島模式使用此功能，您可能不想移除現有使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="f5b11-160">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="f5b11-161">因此，變更整個租使用者的政策之前，需要額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="f5b11-161">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="f5b11-162">解決方案是先將這些現有的使用中使用者「Teams群島模式」，然後再將租使用者範圍的政策設定為 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="f5b11-162">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f5b11-163">完成之後，您可以繼續如上所述進行部署，不過，您將有兩組使用者正在移往 TeamsOnly：使用 Teams 的使用者會位於群島模式，而其餘的使用者將位於 SfbWithTeamsCollab 模式中。</span><span class="sxs-lookup"><span data-stu-id="f5b11-163">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="f5b11-164">您可以逐步將這些使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="f5b11-164">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="f5b11-165">尋找使用中使用者Teams如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5b11-165">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="f5b11-166">從 Microsoft 365系統管理中心，在左側流覽中，前往報告，然後前往使用狀況。</span><span class="sxs-lookup"><span data-stu-id="f5b11-166">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="f5b11-167">在 「選取報表」下拉Microsoft Teams，然後選擇 「使用者活動」。</span><span class="sxs-lookup"><span data-stu-id="f5b11-167">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="f5b11-168">這會提供一個可匯出的使用者資料表，這些使用者已在 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-168">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="f5b11-169">按一下 [匯出Excel，然後篩選，只顯示使用中Teams。</span><span class="sxs-lookup"><span data-stu-id="f5b11-169">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="f5b11-170">針對步驟 1 Teams找到的每個使用中使用者，在遠端 PowerShell 中指派其群島模式。</span><span class="sxs-lookup"><span data-stu-id="f5b11-170">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="f5b11-171">這可讓您前往下一個步驟，並確保您不會變更使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="f5b11-171">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="f5b11-172">將租使用者範圍的政策設定為 SfbWithTeamsCollab：</span><span class="sxs-lookup"><span data-stu-id="f5b11-172">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="f5b11-173">將選取的使用者升級至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="f5b11-173">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="f5b11-174">您可以選擇在群島模式或 SfbWithTeamsCollab 模式中升級使用者，不過您可能想要先優先在群島模式中升級使用者，以將使用者進入群島模式時可能會出現的混淆降到最低。</span><span class="sxs-lookup"><span data-stu-id="f5b11-174">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="f5b11-175">適用于在 商務用 Skype Online 中商務用 Skype的使用者：</span><span class="sxs-lookup"><span data-stu-id="f5b11-175">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="f5b11-176">對於位於內部部署商務用 Skype Server的使用者：</span><span class="sxs-lookup"><span data-stu-id="f5b11-176">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="f5b11-177">下圖顯示選取功能轉換的概念階段，其中一開始有使用中的群島使用者。</span><span class="sxs-lookup"><span data-stu-id="f5b11-177">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="f5b11-178">長條的高度代表使用者數目。</span><span class="sxs-lookup"><span data-stu-id="f5b11-178">The height of the bars represents the number of users.</span></span> <span data-ttu-id="f5b11-179">在升級的任何階段，所有使用者都可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="f5b11-179">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f5b11-180">商務用 Skype使用交互操作與 TeamsOnly 使用者通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f5b11-180">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![顯示在群島模式中與使用中使用者進行選取功能更新的圖表](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="f5b11-182">相關連結</span><span class="sxs-lookup"><span data-stu-id="f5b11-182">Related links</span></span>

[<span data-ttu-id="f5b11-183">適用于與應用程式一起使用Teams的移商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f5b11-183">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f5b11-184">設定商務用 Skype Server或Microsoft 365之間的Office 365</span><span class="sxs-lookup"><span data-stu-id="f5b11-184">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f5b11-185">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="f5b11-185">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f5b11-186">設定您的共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="f5b11-186">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f5b11-187">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f5b11-187">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f5b11-188">使用會議移 (MMS) </span><span class="sxs-lookup"><span data-stu-id="f5b11-188">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
