---
title: 設定您的共存與升級設定
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文將協助您挑選共存模式並設定其他共存設定。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b398a9e70d650ad2afd70c60250076f1ab9fc2
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183435"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="354c1-103">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="354c1-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="354c1-104">當您將商務用 Skype 使用者升級為使用小組時, 您有幾個選項可協助您讓您的使用者更順暢地進行處理。</span><span class="sxs-lookup"><span data-stu-id="354c1-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="354c1-105">您可以選擇一次為組織中的所有使用者建立共存和升級設定, 或者您可以針對組織中的一或一組使用者變更設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="354c1-106">請注意, 較舊版本的商務用 Skype 用戶端可能不會遵守這些設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="354c1-107">如需商務用 Skype 用戶端版本的詳細資訊, 請移至[商務用 skype 下載和更新頁面](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)。</span><span class="sxs-lookup"><span data-stu-id="354c1-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="354c1-108">您可以閱讀[瞭解 Microsoft 團隊及商務用 skype 的共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或[與商務用 skype 共存](coexistence-chat-calls-presence.md), 以更清楚地瞭解可供您使用的模式類型。</span><span class="sxs-lookup"><span data-stu-id="354c1-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="354c1-109">為組織中的所有使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="354c1-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="354c1-110">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="354c1-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="354c1-111">在左側導覽中, 移至 [**組織範圍的設定** > **小組升級**]。</span><span class="sxs-lookup"><span data-stu-id="354c1-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="354c1-112">在 [**小組升級**] 頁面的頂端, 進行下列變更 (如果他們會為您工作)。</span><span class="sxs-lookup"><span data-stu-id="354c1-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="354c1-113">設定**共存**模式。</span><span class="sxs-lookup"><span data-stu-id="354c1-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="354c1-114">**孤島**-如果您希望使用者能夠同時使用商務用 Skype 和團隊, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="354c1-115">[**僅限商務用 skype** ]-如果您希望使用者只使用商務用 skype, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="354c1-116">**僅限團隊**(在某些組織的預覽中)-如果您希望使用者只使用團隊, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="354c1-117">請注意, 即使使用這項設定, 使用者仍然可以加入在商務用 Skype 中託管的會議。</span><span class="sxs-lookup"><span data-stu-id="354c1-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="354c1-118">**針對團隊可供升級的使用者, 設定通知商務用 Skype 使用者**。</span><span class="sxs-lookup"><span data-stu-id="354c1-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="354c1-119">如果您開啟此選項, 將會告知商務用 Skype 使用者即將升級至團隊 app。</span><span class="sxs-lookup"><span data-stu-id="354c1-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="354c1-120">設定**適用于使用者加入商務用 Skype 會議的喜好 app**。</span><span class="sxs-lookup"><span data-stu-id="354c1-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="354c1-121">此設定會決定要使用哪個應用程式來加入商務用 Skype 會議, 且無論共存模式的價值為何都是有效的。</span><span class="sxs-lookup"><span data-stu-id="354c1-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="354c1-122">**Skype 會議應用程式**</span><span class="sxs-lookup"><span data-stu-id="354c1-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="354c1-123">**商務用 Skype 的功能有限**</span><span class="sxs-lookup"><span data-stu-id="354c1-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="354c1-124">**在商務用 Skype 使用者的背景中, 設定是否要下載 [小組] 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="354c1-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="354c1-125">此設定會將 [小組] app 自動下載給在 Windows 上執行商務用 Skype 的使用者。</span><span class="sxs-lookup"><span data-stu-id="354c1-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="354c1-126">只有在使用者僅限團隊或在商務用 Skype 中啟用待執行升級通知時, 才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="354c1-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="354c1-127">進行變更之後, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="354c1-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="354c1-128">為組織中的單一使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="354c1-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="354c1-129">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="354c1-129">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="354c1-130">在左側導覽中, 移至 [**使用者**], 然後從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="354c1-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="354c1-131">在使用者的 [**帳戶**] 索引標籤上, 按一下 [**團隊升級**] 底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="354c1-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="354c1-132">您可以設定**共存模式**。</span><span class="sxs-lookup"><span data-stu-id="354c1-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="354c1-133">從下列選項中選擇:</span><span class="sxs-lookup"><span data-stu-id="354c1-133">Choose from the following options:</span></span>
     - <span data-ttu-id="354c1-134">\*\*\*\* 如果您想要使用者使用**組織範圍**設定中的設定, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="354c1-135">**孤島**-如果您想讓使用者能夠使用商務用 Skype 與團隊, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="354c1-136">[**僅限商務用 skype** ]-如果您想要使用者使用商務用 skype, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="354c1-137">[**僅限團隊**]-如果您希望使用者只使用團隊, 請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="354c1-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="354c1-138">使用者仍將能加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="354c1-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="354c1-139">如果您選取 [**使用整個組織內設定**] 以外的任何**共存模式**, 您可以選擇在使用者即將推出升級至團隊的商務用 Skype app 中啟用通知。</span><span class="sxs-lookup"><span data-stu-id="354c1-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="354c1-140">您可以開啟 [**通知商務用 Skype 使用者**] 選項, 為使用者啟用此通知。</span><span class="sxs-lookup"><span data-stu-id="354c1-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="354c1-141">進行變更之後, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="354c1-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="354c1-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="354c1-142">Related topics</span></span>
[<span data-ttu-id="354c1-143">規劃歷程</span><span class="sxs-lookup"><span data-stu-id="354c1-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="354c1-144">瞭解商務用 Skype 和團隊的共存與升級歷程</span><span class="sxs-lookup"><span data-stu-id="354c1-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="354c1-145">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="354c1-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
