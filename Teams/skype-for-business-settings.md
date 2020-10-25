---
title: 管理 Microsoft 團隊系統管理中心中的商務用 Skype 設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊系統管理中心管理商務用 Skype 功能的設定。
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753558"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b85e9-103">管理 Microsoft 團隊系統管理中心中的商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="b85e9-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="b85e9-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="b85e9-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="b85e9-105">做為管理員，Microsoft [團隊管理中心] 是您在其中管理組織中商務用 Skype 使用者的商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="b85e9-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="b85e9-106">您可以在 [**商務用 skype** ] 頁面上管理[貴組織](#manage-skype-for-business-settings-for-your-organization)的設定，以及在 [使用者詳細資料] 頁面的 [**商務用 skype** ] 索引標籤上的[個別使用者](#manage-skype-for-business-settings-for-individual-users)設定。</span><span class="sxs-lookup"><span data-stu-id="b85e9-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="b85e9-107">如果貴組織的共存模式未設定為 [**僅限團隊**]，您就只會看到 [**商務用 Skype** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b85e9-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="b85e9-108">同樣地，如果使用者的共存模式不是**團隊**，您就只會看到使用者的 [**商務用 Skype** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b85e9-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="b85e9-109">若要深入瞭解共存模式，請參閱 [瞭解團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，以及 [設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b85e9-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b85e9-110">商務用 Skype 設定先前位於 Microsoft 團隊系統管理中心的 **舊版入口網站** 中。</span><span class="sxs-lookup"><span data-stu-id="b85e9-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b85e9-111">在停用舊版入口網站之後，我們會將設定遷移至 [團隊管理中心] 中的 [商務用 Skype 管理] 的新位置。</span><span class="sxs-lookup"><span data-stu-id="b85e9-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="b85e9-112">您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在 Microsoft 團隊系統管理中心管理商務用 skype 功能。</span><span class="sxs-lookup"><span data-stu-id="b85e9-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="b85e9-113">管理貴組織的商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="b85e9-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="b85e9-114">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**全組織性設定**  >  **商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="b85e9-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="b85e9-115">您可以從這裡設定及管理貴組織中所有商務用 Skype 使用者的 Skype 會議廣播、目前狀態隱私權及行動裝置通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="b85e9-116">Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="b85e9-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="b85e9-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="b85e9-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="b85e9-118">使用下列設定管理組織中的 [Skype 會議廣播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 。</span><span class="sxs-lookup"><span data-stu-id="b85e9-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="系統管理中心 Skype 會議廣播設定的螢幕擷取畫面":::

- <span data-ttu-id="b85e9-120">**Skype 會議廣播**：開啟此功能可為您的組織啟用 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="b85e9-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="b85e9-121">啟用此功能之後，您必須為 [Skype 會議廣播設定您的網路](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="b85e9-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="b85e9-122">**請參閱預覽功能**：開啟此功能可提前取得新功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="b85e9-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="b85e9-123">**召集人可以排程匿名會議**：如果您想要讓召集人建立廣播事件，讓組織外的任何人都能加入，而不需要登入，請開啟此選項。</span><span class="sxs-lookup"><span data-stu-id="b85e9-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="b85e9-124">**錄製 Skype 會議廣播會議**：開啟此功能可讓召集人和簡報者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="b85e9-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="b85e9-125">協助者**支援網址**：如果會議期間需要協助，請輸入您組織的支援 url，會議出席者就可以使用。</span><span class="sxs-lookup"><span data-stu-id="b85e9-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="b85e9-126">目前狀態與行動裝置通知</span><span class="sxs-lookup"><span data-stu-id="b85e9-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="b85e9-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="b85e9-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="b85e9-128">使用下列設定來管理貴組織中的商務用 Skype 目前狀態隱私權與行動通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="系統管理中心 [目前狀態] 設定的螢幕擷取畫面":::

#### <a name="presence"></a><span data-ttu-id="b85e9-130">目前狀態</span><span class="sxs-lookup"><span data-stu-id="b85e9-130">Presence</span></span>

<span data-ttu-id="b85e9-131">根據預設，貴組織中的商務用 Skype 使用者可以在其他商務用 Skype 使用者的 [可用]、[忙碌] 或 [離開]) 看到目前狀態 (。</span><span class="sxs-lookup"><span data-stu-id="b85e9-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="b85e9-132">選擇下列其中一項，設定誰可以查看您的商務用 Skype 使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b85e9-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="b85e9-133">**自動顯示目前狀態資訊**：貴組織中尚未新增至使用者的 **外部** 或 **封鎖** 清單的任何商務用 Skype 使用者，都可以看到該使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b85e9-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="b85e9-134">**只向使用者的連絡人顯示目前狀態資訊**：使用者連絡人清單中未新增至其 **外部** 或 **封鎖** 清單的任何商務用 Skype 使用者，都可以看到該使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b85e9-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="b85e9-135">使用者可以移至 [**設定**  >  **工具**]  >  **選項**，在商務用 Skype 中覆寫此設定。</span><span class="sxs-lookup"><span data-stu-id="b85e9-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="b85e9-136">行動裝置通知</span><span class="sxs-lookup"><span data-stu-id="b85e9-136">Mobile notifications</span></span>

<span data-ttu-id="b85e9-137">您可以設定您的商務用 Skype 行動使用者是否會透過推播通知服務接收和未接的立即訊息、語音信箱訊息和未接來電發出通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="b85e9-138">視貴組織中使用的行動裝置而定，您可以使用 **Microsoft 推播通知服務**、 **Apple 推播通知服務**，或同時使用兩者。</span><span class="sxs-lookup"><span data-stu-id="b85e9-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="b85e9-139">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="b85e9-139">Keep the following in mind:</span></span>

- <span data-ttu-id="b85e9-140">如果您關閉推播通知，當使用者下次在行動裝置上啟動商務用 Skype 時，就會收到所有通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="b85e9-141">預設會開啟推播通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="b85e9-142">個別使用者可以在行動裝置的商務用 Skype 中關閉它們。</span><span class="sxs-lookup"><span data-stu-id="b85e9-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="b85e9-143">當您關閉推播通知時，使用者將無法再次開啟推播通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b85e9-144">Microsoft 使用其他公司為 Windows Phone、iPhone 和 iPad 使用者提供即時商務用 Skype mobile 通知。</span><span class="sxs-lookup"><span data-stu-id="b85e9-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="b85e9-145">請參閱本 [隱私權聲明](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="b85e9-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="b85e9-146">管理個別使用者的商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="b85e9-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="b85e9-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="b85e9-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="b85e9-148">若要管理個別使用者的商務用 Skype 設定，請移至 [團隊管理中心] 的左導覽，移至 [ **使用者**]，按一下使用者的顯示名稱以開啟 [使用者詳細資料] 頁面，然後選取 [ **商務用 Skype 設定** ] 索引標籤。您可以從這裡設定使用者的外部存取與會議設定。</span><span class="sxs-lookup"><span data-stu-id="b85e9-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="[使用者詳細資料] 頁面的 [商務用 Skype] 索引標籤螢幕擷取畫面":::

### <a name="external-access-settings"></a><span data-ttu-id="b85e9-150">外部存取設定</span><span class="sxs-lookup"><span data-stu-id="b85e9-150">External access settings</span></span>

<span data-ttu-id="b85e9-151">您可以選擇性地允許或封鎖使用者是否能與組織外部的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b85e9-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="b85e9-152">**外部商務用 Skype 使用者**：如果您想要允許使用者與聯盟網域中的商務用 skype 使用者通訊，請開啟此選項。</span><span class="sxs-lookup"><span data-stu-id="b85e9-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="b85e9-153">**外部 Skype 使用者**：如果您想要允許使用者與 Skype 使用者通訊，請開啟此選項。</span><span class="sxs-lookup"><span data-stu-id="b85e9-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="b85e9-154">會議設定</span><span class="sxs-lookup"><span data-stu-id="b85e9-154">Meeting settings</span></span>

<span data-ttu-id="b85e9-155">您可以為使用者設定下列會議設定。</span><span class="sxs-lookup"><span data-stu-id="b85e9-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="b85e9-156">**音訊 & 影片**：選擇下列其中一個音訊和影片設定：</span><span class="sxs-lookup"><span data-stu-id="b85e9-156">**Audio & video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="b85e9-157">**None**：使用者無法使用音訊或視頻。</span><span class="sxs-lookup"><span data-stu-id="b85e9-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="b85e9-158">**僅音訊**：使用者可以使用音訊，但不能使用影片。</span><span class="sxs-lookup"><span data-stu-id="b85e9-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="b85e9-159">**音訊與影片**：使用者可以使用音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="b85e9-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="b85e9-160">\*\*音訊與影片 (高清) \*\*：使用者可以使用音訊和高清影片。</span><span class="sxs-lookup"><span data-stu-id="b85e9-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="b85e9-161">**錄製交談 & 會議**：開啟此功能可讓使用者記錄交談和會議。</span><span class="sxs-lookup"><span data-stu-id="b85e9-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="b85e9-162">**合規性**：如果您在法律上需要保留以電子方式儲存的資訊，請開啟此選項。</span><span class="sxs-lookup"><span data-stu-id="b85e9-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
