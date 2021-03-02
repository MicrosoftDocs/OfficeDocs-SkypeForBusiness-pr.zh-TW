---
title: 設定共存和升級設定
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 瞭解如何一次為貴組織中所有使用者，或為貴組織中一或一組使用者設定共存和升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2dbeb4d93273aab848f1b4436b46e6b22e08e53
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397568"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="94645-103">設定共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="94645-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="94645-104">當您將商務用 Skype 使用者升級為使用 Teams 時，有幾個選項可協助使用者順暢地執行此程式。</span><span class="sxs-lookup"><span data-stu-id="94645-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="94645-105">您可以選擇一次為貴組織的所有使用者進行共存和升級設定，或者也可以對貴組織的一或一組使用者進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="94645-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="94645-106">請注意，舊版商務用 Skype 用戶端可能不會遵守這些設定。</span><span class="sxs-lookup"><span data-stu-id="94645-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="94645-107">有關商務用 Skype 用戶端版本的資訊，請前往商務用 Skype 下載 [和更新頁面](https://docs.microsoft.com/skypeforbusiness/software-updates)。</span><span class="sxs-lookup"><span data-stu-id="94645-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="94645-108">您可以閱讀瞭解 [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 和商務用 Skype 共存和互通性，或與商務用 Skype 共存，以深入瞭解可用的 [模式](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="94645-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="94645-109">為貴組織的所有使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="94645-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="94645-110">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="94645-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="94645-111">在 [Microsoft Teams 系統管理中心的](https://admin.teams.microsoft.com/)左側流覽中，前往 **整個組織設定**  >  **Teams 升級**。</span><span class="sxs-lookup"><span data-stu-id="94645-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="94645-112">在 **Teams** 升級頁面頂端，按照需要修改下列選項。</span><span class="sxs-lookup"><span data-stu-id="94645-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>
    - <span data-ttu-id="94645-113">設定 **共存** 模式。</span><span class="sxs-lookup"><span data-stu-id="94645-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="94645-114">**群島** - 如果您希望使用者同時使用商務用 Skype 和 Teams，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="94645-115">**僅適用于商務用 Skype** - 如果您希望使用者只能使用商務用 Skype，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="94645-116">**商務用 Skype 與 Teams** 共同合作 - 如果您希望您的使用者使用商務用 Skype，除了使用 Teams 進行群組共同 (頻道或頻道) 。</span><span class="sxs-lookup"><span data-stu-id="94645-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="94645-117">商務 **用 Skype** 與 Teams 共同合作與會議 - 如果您希望使用者除了使用 Teams 進行群組共同 (Teams 會議之外，) 這項設定。</span><span class="sxs-lookup"><span data-stu-id="94645-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="94645-118">**僅 Teams** - 如果您希望使用者只能使用 Teams，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="94645-119">請注意，即使有這項設定，使用者仍然可以加入商務用 Skype 所主持的會議。</span><span class="sxs-lookup"><span data-stu-id="94645-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
        
    - <span data-ttu-id="94645-120">設定 **通知商務用 Skype 使用者 Teams 可供升級**。</span><span class="sxs-lookup"><span data-stu-id="94645-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="94645-121">如果您開啟此功能，它會告訴商務用 Skype 使用者，他們即將升級至 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="94645-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="94645-122">設定使用者 **加入商務用 Skype 會議時偏好的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="94645-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="94645-123">此設定會決定用於加入商務用 Skype 會議的應用程式，且無論共存模式的值如何，都會採用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="94645-124">**Skype 會議應用程式**</span><span class="sxs-lookup"><span data-stu-id="94645-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="94645-125">**商務用 Skype 功能有限**</span><span class="sxs-lookup"><span data-stu-id="94645-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="94645-126">設定是否要 **在商務用 Skype 使用者的背景中下載 Teams 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="94645-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="94645-127">此設定會以無提示方式下載 Teams 應用程式，供在 Windows 上經營商務用 Skype 的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="94645-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="94645-128">只有在使用者的共存模式為 Teams，或商務用 Skype 中已啟用擱置升級通知時，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="94645-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="94645-129">進行 **變更** 後，按一下 [儲存。</span><span class="sxs-lookup"><span data-stu-id="94645-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="94645-130">為貴組織的單一使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="94645-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="94645-131">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="94645-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="94645-132">在左側導覽中，前往 **使用者**，然後從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="94645-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="94645-133">在使用者的 **[帳戶>** Tab 上，按一下 **Teams 升級** 下的 **[編輯**。</span><span class="sxs-lookup"><span data-stu-id="94645-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="94645-134">您可以設定 **共存模式**。</span><span class="sxs-lookup"><span data-stu-id="94645-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="94645-135">從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="94645-135">Choose from the following options:</span></span>
     - <span data-ttu-id="94645-136">**使用全組織設定** - 如果您希望使用者使用全組織設定中的設定，請使用 **此** 設定。</span><span class="sxs-lookup"><span data-stu-id="94645-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="94645-137">**群島** - 如果您希望使用者同時使用商務用 Skype 和 Teams，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="94645-138">**僅適用于商務用 Skype** - 如果您希望使用者使用商務用 Skype，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="94645-139">**商務用 Skype 與 Teams** 共同合作 - 如果您希望使用者使用商務用 Skype，除了使用 Teams 進行群組共同 (頻道，) 。</span><span class="sxs-lookup"><span data-stu-id="94645-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="94645-140">商務 **用 Skype** 與 Teams 共同合作與會議 - 如果您希望使用者除了使用 Teams 進行群組共同 (Teams 會議之外，) 使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="94645-141">**僅 Teams** - 如果您希望使用者只使用 Teams，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="94645-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="94645-142">使用者仍然可以加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="94645-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="94645-143">如果您 **選取了使用** 全組織設定外的任何共存模式，您可以選擇在即將升級至 Teams 的使用者商務用 Skype 應用程式中啟用通知。</span><span class="sxs-lookup"><span data-stu-id="94645-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="94645-144">您可以開啟商務用 Skype 使用者通知選項， **為使用者啟用此** 通知。</span><span class="sxs-lookup"><span data-stu-id="94645-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="94645-145">進行 **變更** 後，按一下 [儲存。</span><span class="sxs-lookup"><span data-stu-id="94645-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="94645-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="94645-146">Related topics</span></span>
[<span data-ttu-id="94645-147">規劃旅程</span><span class="sxs-lookup"><span data-stu-id="94645-147">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="94645-148">瞭解商務用 Skype 和 Teams 的共存與升級歷程</span><span class="sxs-lookup"><span data-stu-id="94645-148">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="94645-149">適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="94645-149">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
