---
title: 從商務用 Skype Online 升級至 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從商務用 Skype Online 部署將貴組織升級至 Microsoft Teams。
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104009"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="3d043-103">從商務用 Skype Online 升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="3d043-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="3d043-104">![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="3d043-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3d043-105">本文是升級歷程的部署與執行階段之一。</span><span class="sxs-lookup"><span data-stu-id="3d043-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3d043-106">繼續進行之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="3d043-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="3d043-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="3d043-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3d043-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="3d043-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="3d043-109">瞭解商務用 Skype 和 Teams 的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="3d043-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="3d043-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="3d043-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3d043-111">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="3d043-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="3d043-112">準備您的組織</span><span class="sxs-lookup"><span data-stu-id="3d043-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="3d043-113">進行試驗</span><span class="sxs-lookup"><span data-stu-id="3d043-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="3d043-114">如果您已完全部署商務用 Skype Online，並想要將使用者從商務用 Skype 升級至 Teams，請遵循本文中的指引。</span><span class="sxs-lookup"><span data-stu-id="3d043-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="3d043-115">您可以根據貴組織所選擇的升級歷程，將適當的共存和升級模式指派給使用者，選擇性或全面升級使用者。</span><span class="sxs-lookup"><span data-stu-id="3d043-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d043-116">商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。</span><span class="sxs-lookup"><span data-stu-id="3d043-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="3d043-117">為了最大化權益實現，並確保貴組織有適當的時間實做升級，我們鼓勵您立即開始 Microsoft Teams 之旅。</span><span class="sxs-lookup"><span data-stu-id="3d043-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="3d043-118">請記住，成功的升級會符合技術和使用者的準備狀態，因此請務必在流覽 Microsoft Teams 的歷程時，運用本文的指引。</span><span class="sxs-lookup"><span data-stu-id="3d043-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="3d043-119">指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="3d043-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="3d043-120">您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例，以將使用者升級至 TeamsOnly 模式，此實例可以使用 Microsoft Teams 系統管理中心或商務用 Skype 遠端 Windows PowerShell 會話執行。</span><span class="sxs-lookup"><span data-stu-id="3d043-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="3d043-121">若要在單一步驟中升級整個租使用者，您可以依據每個使用者或整個租使用者執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="3d043-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="3d043-122">詳細資訊，請參閱設定 [您的共存和升級設定](./setting-your-coexistence-and-upgrade-settings.md) 及 [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3d043-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="3d043-123">一次將所有使用者升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="3d043-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="3d043-124">請遵循下列步驟，一次將所有使用者升級至 Teams。</span><span class="sxs-lookup"><span data-stu-id="3d043-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="3d043-125">步驟 1：將變更通知使用者 (選擇) </span><span class="sxs-lookup"><span data-stu-id="3d043-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="3d043-126">在 Microsoft Teams 系統管理中心，選取 **全組織** 設定  >  **Teams 升級**。</span><span class="sxs-lookup"><span data-stu-id="3d043-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="3d043-127">在 **共存模式中**，將通知 **商務用 Skype 使用者升級** 至 Teams 時，切換到 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="3d043-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="3d043-128">步驟 2：為組織將共存模式設定為 TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="3d043-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="3d043-129">在 Microsoft Teams 系統管理中心中，選取 **全組織設定**。</span><span class="sxs-lookup"><span data-stu-id="3d043-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="3d043-130">從 **共存模式** 下拉式清單中選取僅 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="3d043-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="3d043-131">階段升級使用者</span><span class="sxs-lookup"><span data-stu-id="3d043-131">Upgrade users in stages</span></span>

<span data-ttu-id="3d043-132">如果您想要將使用者逐步升級至 TeamsOnly，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="3d043-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="3d043-133">步驟 1：識別要升級的使用者群組</span><span class="sxs-lookup"><span data-stu-id="3d043-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="3d043-134">組織通常會選擇在成功的使用者潮中升級其組織。</span><span class="sxs-lookup"><span data-stu-id="3d043-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="3d043-135">您首先會想要識別這些使用者，以便您可以在 Microsoft Teams 系統管理中心輕鬆搜尋這些使用者。</span><span class="sxs-lookup"><span data-stu-id="3d043-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3d043-136">或者，您可能想要使用 PowerShell 更有效率地執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="3d043-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="3d043-137">一旦為一組使用者識別了一組給定的升級波，請繼續執行其餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="3d043-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="3d043-138">步驟 2：為目前升級波中的使用者設定通知， (選項) </span><span class="sxs-lookup"><span data-stu-id="3d043-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="3d043-139">如果您使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="3d043-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="3d043-140">在 Microsoft Teams 系統管理中心中，選取 **使用者，然後** 針對最多 20 個應該升級的使用者尋找並多重選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3d043-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="3d043-141">選取 **清單視圖** 左上角的編輯設定。</span><span class="sxs-lookup"><span data-stu-id="3d043-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="3d043-142">在右側 **編輯設定** 窗格的 **Teams 升級** 下，將 **通知商務用 Skype 使用者** 切換到 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="3d043-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="3d043-143">注意：如果共存模式的值是「使用全組織設定」，您就不會看到此開關，因此您必須先將這些使用者的共存模式明確設定為組織的預設值。</span><span class="sxs-lookup"><span data-stu-id="3d043-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="3d043-144">或者，您可能會發現使用 PowerShell 一次為使用者群組啟用通知會更容易。</span><span class="sxs-lookup"><span data-stu-id="3d043-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="3d043-145">步驟 3：將使用者的共存模式設定為 Teams Only</span><span class="sxs-lookup"><span data-stu-id="3d043-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="3d043-146">當您準備好將目前波中的使用者升級為使用 Teams 做為他們的唯一應用程式時，請設定使用者的共存模式至 Teams Only。</span><span class="sxs-lookup"><span data-stu-id="3d043-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="3d043-147">如果您使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="3d043-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="3d043-148">在 Microsoft Teams 系統管理中心中，選取 **使用者**，然後選取最多 20 位使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3d043-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="3d043-149">選取 **清單視圖** 左上角的編輯設定。</span><span class="sxs-lookup"><span data-stu-id="3d043-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="3d043-150">在右邊 **的編輯設定** 窗格的 **Teams** 升級區段下，將共存模式設定為下拉式 **清單中的 Teams** Only。</span><span class="sxs-lookup"><span data-stu-id="3d043-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="3d043-151">或者，您可能會發現使用 PowerShell 一次升級使用者群組會更容易。</span><span class="sxs-lookup"><span data-stu-id="3d043-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="3d043-152">步驟 4：針對連續的使用者波重複步驟 1-3</span><span class="sxs-lookup"><span data-stu-id="3d043-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="3d043-153">當您驗證升級至 Teams Only 模式並準備好展開時，請重複上述步驟，將 TeamsOnly 適用于更多使用者。</span><span class="sxs-lookup"><span data-stu-id="3d043-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="3d043-154">電話系統與 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="3d043-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="3d043-155">使用者進入 TeamsOnly 模式後，支援 Teams 電話系統。</span><span class="sxs-lookup"><span data-stu-id="3d043-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="3d043-156"> (如果使用者位於群島模式，則只有商務用 Skype 才支援電話系統) </span><span class="sxs-lookup"><span data-stu-id="3d043-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="3d043-157">PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="3d043-157">PSTN connectivity options</span></span>

<span data-ttu-id="3d043-158">考慮使用公用交換式電話 (PSTN) 連線選項時，從商務用 Skype Online 切換到 TeamsOnly 模式時，有兩種可能的情況：</span><span class="sxs-lookup"><span data-stu-id="3d043-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="3d043-159">商務用 Skype Online 中的使用者，具有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="3d043-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="3d043-160">升級後，該使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="3d043-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="3d043-161">這是只需要幾個步驟最簡單的案例。</span><span class="sxs-lookup"><span data-stu-id="3d043-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="3d043-162">詳細資訊，請參閱 [從商務用 Skype Online 與 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="3d043-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="3d043-163">商務用 Skype Online 中的使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。</span><span class="sxs-lookup"><span data-stu-id="3d043-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="3d043-164">使用者升級至 Teams 時，必須協調使用者的移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="3d043-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="3d043-165">詳細資訊請參閱從 [商務用 Skype Online 與內部部署語音](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。</span><span class="sxs-lookup"><span data-stu-id="3d043-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>