---
title: 將商務用 Skype Online 升級至 Microsoft 團隊 |部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 瞭解如何從商務用 Skype Online deployement 將您的組織升級至 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37deecdbff083718dcb5b8a16e77ac8da4b998ff
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905355"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="e93dd-103">從商務用 Skype Online 升級至團隊</span><span class="sxs-lookup"><span data-stu-id="e93dd-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="e93dd-104">![升級歷程圖表，強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="e93dd-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e93dd-105">本文是升級歷程部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="e93dd-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e93dd-106">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="e93dd-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="e93dd-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="e93dd-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e93dd-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="e93dd-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e93dd-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="e93dd-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e93dd-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="e93dd-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e93dd-111">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="e93dd-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e93dd-112">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="e93dd-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e93dd-113">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="e93dd-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="e93dd-114">如果您已部署商務用 Skype Online，且想要將您的使用者從商務用 Skype 升級至小組，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="e93dd-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="e93dd-115">您可以根據貴組織所選擇的升級歷程，將適當的共存和升級模式指派給您的使用者，以有選擇性或全式方式升級使用者。</span><span class="sxs-lookup"><span data-stu-id="e93dd-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e93dd-116">商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。</span><span class="sxs-lookup"><span data-stu-id="e93dd-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="e93dd-117">若要最大限度取得效益並確保貴組織有適當的時間來實施升級，我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="e93dd-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="e93dd-118">請記住，成功的升級會將技術與使用者的就緒性相符，因此請務必在您向 Microsoft 團隊流覽您的旅程時，在本文中利用指導方針。</span><span class="sxs-lookup"><span data-stu-id="e93dd-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="e93dd-119">指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="e93dd-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="e93dd-120">您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例，將您的使用者升級為 TeamsOnly 模式，這可以使用 Microsoft 團隊系統管理中心或商務用 Skype 遠端 Windows Powershell 會話來執行。</span><span class="sxs-lookup"><span data-stu-id="e93dd-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="e93dd-121">如果您想要在一個步驟中升級整個租使用者，您可以根據每個使用者來執行此動作，或在租使用者範圍執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e93dd-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="e93dd-122">如需詳細資訊，請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy：管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="e93dd-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="e93dd-123">一次將所有使用者升級至團隊</span><span class="sxs-lookup"><span data-stu-id="e93dd-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="e93dd-124">請按照下列步驟，一次將所有使用者升級至團隊。</span><span class="sxs-lookup"><span data-stu-id="e93dd-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="e93dd-125">步驟1：通知使用者變更（選用）</span><span class="sxs-lookup"><span data-stu-id="e93dd-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="e93dd-126">在 Microsoft [團隊管理中心] 中，選取 [**整個組織設定** > **團隊升級**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="e93dd-127">在 [**共存模式]** 下，變更 [**通知商務用 Skype] 使用者是否有升級至團隊的功能**，請切換至 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="e93dd-128">步驟2：將組織的共存模式設定為 TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="e93dd-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="e93dd-129">在 Microsoft [團隊管理中心] 中，選取 [**整個組織的設定**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="e93dd-130">從 [**共存模式**] 下拉式清單中選取 [**僅限團隊**] 模式。</span><span class="sxs-lookup"><span data-stu-id="e93dd-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="e93dd-131">以階段升級使用者</span><span class="sxs-lookup"><span data-stu-id="e93dd-131">Upgrade users in stages</span></span>

<span data-ttu-id="e93dd-132">如果您想要將您的使用者逐步升級至 TeamsOnly，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e93dd-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="e93dd-133">步驟1：識別要升級的使用者群組</span><span class="sxs-lookup"><span data-stu-id="e93dd-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="e93dd-134">組織通常可以選擇以成功的使用者波來升級其組織。</span><span class="sxs-lookup"><span data-stu-id="e93dd-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="e93dd-135">您會想先識別這些使用者，以便在 Microsoft 團隊系統管理中心輕鬆搜尋。</span><span class="sxs-lookup"><span data-stu-id="e93dd-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e93dd-136">或者，您可能會想要使用 PowerShell 來更有效率地執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e93dd-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="e93dd-137">一旦您識別出特定升級波的一組使用者，請繼續執行剩餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="e93dd-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="e93dd-138">步驟2：在目前升級波中設定使用者的通知（選用）</span><span class="sxs-lookup"><span data-stu-id="e93dd-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="e93dd-139">如果您使用的是 Microsoft 團隊系統管理中心，您可以一次為最多20名使用者設定 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="e93dd-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e93dd-140">在 Microsoft [團隊管理中心] 中，選取 [**使用者**]，然後尋找及多重選取要升級的20位使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e93dd-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="e93dd-141">選取 listview 左上角的 [**編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="e93dd-142">在右側的 [**編輯設定**] 窗格中，在 [**團隊升級**] 底下，[變更**通知商務用 Skype 使用者**] 切換至 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="e93dd-143">注意：如果共存模式的值是「使用整個組織的設定」，您就不會看到這個開關，所以您必須先將這些使用者的共存模式明確設定為該組織的預設值。</span><span class="sxs-lookup"><span data-stu-id="e93dd-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="e93dd-144">或者，您也可以使用 PowerShell，輕鬆地為使用者群組啟用通知。</span><span class="sxs-lookup"><span data-stu-id="e93dd-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="e93dd-145">步驟3：將使用者的共存模式設定為 [僅限團隊]</span><span class="sxs-lookup"><span data-stu-id="e93dd-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="e93dd-146">當您準備好要升級目前浪潮中的使用者以使用團隊作為其唯一的應用程式時，請將使用者的共存模式僅設定為 [團隊]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="e93dd-147">如果您使用的是 Microsoft 團隊系統管理中心，您可以一次為最多20名使用者設定 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="e93dd-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e93dd-148">在 Microsoft [團隊管理中心] 中，選取 [**使用者**]，然後選取最多20個使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e93dd-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="e93dd-149">選取 listview 左上角的 [**編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="e93dd-150">在右側的 [**編輯設定**] 窗格中，在 [**團隊升級**] 區段底下，將 [共存模式] 設定為 [只在下拉式清單中的**小組**]。</span><span class="sxs-lookup"><span data-stu-id="e93dd-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="e93dd-151">或者，您可能會發現使用 PowerShell 一次升級使用者群組會比較容易。</span><span class="sxs-lookup"><span data-stu-id="e93dd-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="e93dd-152">步驟4：針對連續的使用者波重複步驟1-3</span><span class="sxs-lookup"><span data-stu-id="e93dd-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="e93dd-153">當您驗證升級至 [僅限團隊] 模式並準備好要展開時，請重複上述步驟，將 TeamsOnly 套用至更多使用者。</span><span class="sxs-lookup"><span data-stu-id="e93dd-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e93dd-154">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="e93dd-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e93dd-155">如果您的商務用 Skype Online 部署包括含有通話方案的電話系統，而 Microsoft 是您的公用交換電話網絡（PSTN）提供者，則將您的使用者升級至團隊會自動將入站 PSTN 通話轉場給小組。</span><span class="sxs-lookup"><span data-stu-id="e93dd-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e93dd-156">如果您的商務用 Skype Online 部署包含含雲端連接器版本的電話系統，請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="e93dd-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
