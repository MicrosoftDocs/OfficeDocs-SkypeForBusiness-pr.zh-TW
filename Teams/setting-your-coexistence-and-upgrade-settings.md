---
title: 設定共存和升級設定
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 瞭解如何一次為貴組織中所有使用者或貴組織中單一或一組使用者設定共存和升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9419e8ba7339db1fb202e3b5add66935caff7486
ms.sourcegitcommit: 1a622397b5c7fe05e687bb47493fcbca63915d97
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53447971"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="1ef4e-103">設定共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="1ef4e-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="1ef4e-104">當您升級您的商務用 Skype使用者以使用Teams時，您有幾個選項可協助使用者順暢地執行此程式。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="1ef4e-105">您可以選擇一次為貴組織中所有使用者進行共存和升級設定，或者您可以針對貴組織的單一或一組使用者進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="1ef4e-106">請注意，舊版用戶端商務用 Skype可能無法遵守這些設定。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="1ef4e-107">若要進一商務用 Skype用戶端版本，請前往下載商務用 Skype[更新頁面](/skypeforbusiness/software-updates)。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="1ef4e-108">您可以閱讀瞭解與共同Microsoft Teams互通性商務用 Skype或與 商務用 Skype 共存，以[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)進一步瞭解[可用的商務用 Skype。](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="1ef4e-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="1ef4e-109">為貴組織中所有使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="1ef4e-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="1ef4e-110">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1ef4e-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1ef4e-111">在 Microsoft Teams [系統管理中心](https://admin.teams.microsoft.com/)，在左側流覽中，前往整個 **組織** 設定  >  **Teams升級**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="1ef4e-112">在升級 **頁面Teams，** 請根據需要修改下列選項。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>

    - <span data-ttu-id="1ef4e-113">設定 **共存** 模式。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="1ef4e-114">**群島**- 如果您希望使用者同時使用商務用 Skype和Teams設定。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="1ef4e-115">**商務用 Skype** - 如果您希望使用者只能使用商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="1ef4e-116">**商務用 Skype** 共同Teams - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="1ef4e-117">**商務用 Skype** 共同Teams和會議 - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 會議Teams請使用這項設定。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="1ef4e-118">**Teams** - 如果您希望使用者只使用Teams。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="1ef4e-119">請注意，即使有這項設定，使用者仍然可以加入以 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>

          > [!IMPORTANT]
          > <span data-ttu-id="1ef4e-120">完成下列兩個步驟之後，您只能將 TeamsOnly 模式指派給整個租使用者：</span><span class="sxs-lookup"><span data-stu-id="1ef4e-120">You can only assign TeamsOnly mode to the entire tenant after both of the following steps ahve been completed:</span></span>
          >  - <span data-ttu-id="1ef4e-121">所有內部部署使用者已移至 Teams，Move-CsUser內部商務用 Skype Server工具集內使用。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-121">All on-premises users have been moved to Teams Only using Move-CsUser in the Skype for Business Server on-premises toolset.</span></span>
          >  - <span data-ttu-id="1ef4e-122">您更新任何 dns 商務用 Skype，以指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-122">You have updated any Skype for Business DNS records to point to Microsoft 365.</span></span> 
          >
          > <span data-ttu-id="1ef4e-123">詳情請參閱停用混合式[組組以完成](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)移Teams 。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-123">For more detail, see [Disable your hybrid configuration to complete migration to Teams Only](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>
        
    - <span data-ttu-id="1ef4e-124">設定 **通知商務用 Skype使用者Teams升級。**</span><span class="sxs-lookup"><span data-stu-id="1ef4e-124">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="1ef4e-125">如果您開啟此選項，它會告知商務用 Skype使用者，他們很快就會升級至 Teams App。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-125">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>

    - <span data-ttu-id="1ef4e-126">設定使用者 **加入會議商務用 Skype應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-126">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="1ef4e-127">此設定會決定用於加入會議商務用 Skype應用程式，且無論共存模式的值如何，都會受到尊重。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-127">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="1ef4e-128">**Skype會議應用程式**</span><span class="sxs-lookup"><span data-stu-id="1ef4e-128">**Skype Meetings app**</span></span>
      - <span data-ttu-id="1ef4e-129">**商務用 Skype功能受限的**</span><span class="sxs-lookup"><span data-stu-id="1ef4e-129">**Skype for Business with limited features**</span></span>

    - <span data-ttu-id="1ef4e-130">設定是否要 **在背景Teams下載應用程式，商務用 Skype使用者**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-130">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="1ef4e-131">此設定會以無Teams方式下載應用程式，商務用 Skype應用程式Windows。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-131">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="1ef4e-132">只有在使用者共存模式為Teams或系統啟用擱置升級通知時，才能商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-132">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>

3. <span data-ttu-id="1ef4e-133">進行 **變更** 後，按一下 [儲存。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-133">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="1ef4e-134">為貴組織的單一使用者設定升級選項</span><span class="sxs-lookup"><span data-stu-id="1ef4e-134">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="1ef4e-135">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1ef4e-135">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1ef4e-136">在左側導覽中，前往 **使用者**，然後從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-136">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="1ef4e-137">在使用者的 **[帳戶** Teams下，按一下 **[\*\*\*\*編輯**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-137">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="1ef4e-138">您可以設定 **共存模式**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-138">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="1ef4e-139">只有 Teams 模式只能適用于內部部署 商務用 Skype Server 中的使用者，相反地，只有雲端使用者可以使用 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-139">Modes other than Teams Only can only be applied to users homed in Skype for Business Server on-premises, and conversely only users homed in the cloud can have TeamsOnly mode.</span></span>  <span data-ttu-id="1ef4e-140">從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="1ef4e-140">Choose from the following options:</span></span>
     - <span data-ttu-id="1ef4e-141">**使用全組織設定** - 如果您希望使用者使用全組織設定中的設定，請使用 **這個** 設定。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-141">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="1ef4e-142">**群島**- 如果您希望使用者同時使用商務用 Skype，請使用Teams。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-142">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="1ef4e-143">**商務用 Skype** - 如果您希望使用者使用此功能，請使用商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-143">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="1ef4e-144">**商務用 Skype** 共同Teams - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-144">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="1ef4e-145">**商務用 Skype** 共同Teams和會議 - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 會議Teams請使用這項設定。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-145">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="1ef4e-146">**Teams** - 如果您希望使用者只使用Teams。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-146">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="1ef4e-147">使用者仍然可以加入商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-147">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="1ef4e-148">如果您 **選取了使用** 全組織設定外的任何共存模式，您可以選擇在即將升級至 Teams 的使用者 商務用 Skype 應用程式中啟用通知。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-148">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="1ef4e-149">您可以開啟通知使用者選項，為使用者 **啟用商務用 Skype通知**。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-149">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="1ef4e-150">進行 **變更** 後，按一下 [儲存。</span><span class="sxs-lookup"><span data-stu-id="1ef4e-150">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="1ef4e-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="1ef4e-151">Related topics</span></span>
[<span data-ttu-id="1ef4e-152">規劃旅程</span><span class="sxs-lookup"><span data-stu-id="1ef4e-152">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="1ef4e-153">瞭解商務用 Skype和Teams</span><span class="sxs-lookup"><span data-stu-id="1ef4e-153">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="1ef4e-154">針對與應用程式一起使用Teams的移商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="1ef4e-154">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="1ef4e-155">解除內部部署商務用 Skype環境</span><span class="sxs-lookup"><span data-stu-id="1ef4e-155">Decommission your on-premises Skype for Business environment</span></span>](/skypeforbusiness/hybrid/decommission-on-prem-overview)
