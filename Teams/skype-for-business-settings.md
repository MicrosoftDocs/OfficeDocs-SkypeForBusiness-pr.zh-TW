---
title: 在 商務用 Skype 系統管理中心管理Microsoft Teams設定
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在系統管理中心管理商務用 Skype功能Microsoft Teams設定。
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117001"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a3f3e-103">在 商務用 Skype 系統管理中心管理Microsoft Teams設定</span><span class="sxs-lookup"><span data-stu-id="a3f3e-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="a3f3e-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f3e-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="a3f3e-105">作為系統管理員，Microsoft Teams管理中心就是您管理組織中商務用 Skype使用者商務用 Skype功能的地方。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="a3f3e-106">您可以管理組織[在](#manage-skype-for-business-settings-for-your-organization)商務用 Skype 頁面上的設定，以及使用者詳細資料[](#manage-skype-for-business-settings-for-individual-users)頁面的 商務用 Skype索引商務用 Skype個別使用者的設定。 </span><span class="sxs-lookup"><span data-stu-id="a3f3e-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="a3f3e-107">如果貴組織的共存商務用 Skype未設為只顯示 ，您只會看到 Teams **頁面**。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="a3f3e-108">同樣地，您只會看到使用者的商務用 Skype，如果使用者的共存模式不是只Teams **的。**</span><span class="sxs-lookup"><span data-stu-id="a3f3e-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="a3f3e-109">若要深入瞭解共存模式，請參閱瞭解Teams及商務用 Skype及互通性，[以及](teams-and-skypeforbusiness-coexistence-and-interoperability.md)設定[您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3f3e-110">商務用 Skype系統管理中心的舊版入口網站中Microsoft Teams設定。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a3f3e-111">舊版入口網站已停用後，我們已將設定移Teams系統管理商務用 Skype位置。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="a3f3e-112">您必須被指派全域系統管理員或系統管理員的[Azure AD](/azure/active-directory/roles/permissions-reference)系統管理員商務用 Skype，才能商務用 Skype系統管理中心Microsoft Teams功能。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="a3f3e-113">管理商務用 Skype的設定</span><span class="sxs-lookup"><span data-stu-id="a3f3e-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="a3f3e-114">在系統管理中心的左側導Microsoft Teams，請前往整個 **組織設定**  >  商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="a3f3e-115">您可以在這裡為貴組織Skype使用者設定及管理會議廣播、目前狀態隱私權商務用 Skype行動裝置通知。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="a3f3e-116">Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="a3f3e-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="a3f3e-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f3e-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="a3f3e-118">使用下列設定來管理[Skype會議](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)廣播。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="系統管理Skype會議廣播設定螢幕擷取畫面":::

- <span data-ttu-id="a3f3e-120">**Skype會議廣播**：開啟此選項，Skype組織的會議廣播。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="a3f3e-121">啟用這項功能後，您必須設定您的網路以Skype[廣播](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="a3f3e-122">**請參閱預覽功能**：開啟此功能以提早存取新功能。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="a3f3e-123">**召集人可以排程匿名會議**：如果您想要讓召集人建立廣播活動，讓組織外部的任何人無需登錄即可加入，請開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="a3f3e-124">**錄製Skype廣播會議**：開啟此選項，讓召集人和簡報者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="a3f3e-125">**出席者的支援 URL：** 輸入貴組織的支援 URL，如果出席者在會議期間需要協助，可以使用該 URL。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="a3f3e-126">目前狀態與行動通知</span><span class="sxs-lookup"><span data-stu-id="a3f3e-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="a3f3e-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f3e-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="a3f3e-128">使用下列設定來管理商務用 Skype目前狀態隱私權和行動通知。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="系統管理中心目前狀態設定螢幕擷取畫面":::

#### <a name="presence"></a><span data-ttu-id="a3f3e-130">目前狀態</span><span class="sxs-lookup"><span data-stu-id="a3f3e-130">Presence</span></span>

<span data-ttu-id="a3f3e-131">根據預設，商務用 Skype使用者可以看到其他 (使用者的目前狀態，例如可用、忙碌) 離開商務用 Skype狀態。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="a3f3e-132">選擇下列其中一項來設定誰可以看到您的商務用 Skype使用者。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="a3f3e-133">**自動顯示目前狀態** 資訊：商務用 Skype組織中尚未新增到使用者的外部或封鎖清單的任何使用者，都可以看到該使用者的目前狀態。 </span><span class="sxs-lookup"><span data-stu-id="a3f3e-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="a3f3e-134">**只向** 使用者的連絡人顯示目前狀態資訊：商務用 Skype連絡人清單中未新增到其外部或封鎖清單中的任何 商務用 Skype 使用者，都能看到該使用者的目前狀態。  </span><span class="sxs-lookup"><span data-stu-id="a3f3e-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="a3f3e-135">使用者可以在工具選項商務用 Skype中設定  >  **此**  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="a3f3e-136">行動通知</span><span class="sxs-lookup"><span data-stu-id="a3f3e-136">Mobile notifications</span></span>

<span data-ttu-id="a3f3e-137">您可以設定您的行動商務用 Skype使用者是否透過推入通知服務收到有關傳入和未接立即訊息、語音信箱訊息和未接來電的提醒。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="a3f3e-138">視貴組織中所使用的行動裝置不同，您可以使用 Microsoft 推入通知 **服務\*\*\*\*、Apple 推入通知服務**，或兩者同時使用。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="a3f3e-139">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="a3f3e-139">Keep the following in mind:</span></span>

- <span data-ttu-id="a3f3e-140">如果您關閉推入通知，使用者下次在行動裝置上商務用 Skype就會收到所有通知。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="a3f3e-141">根據預設，推入通知會開啟。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="a3f3e-142">個別使用者可以在行動裝置上商務用 Skype關閉這些裝置。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="a3f3e-143">當您關閉推入通知時，使用者無法重新開啟。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a3f3e-144">Microsoft 會使用其他公司為商務用 Skype使用者提供即時Windows Phone、iPhone iPad通知。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="a3f3e-145">請參閱本 [隱私權聲明](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="a3f3e-146">管理商務用 Skype使用者的設定</span><span class="sxs-lookup"><span data-stu-id="a3f3e-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="a3f3e-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f3e-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="a3f3e-148">若要管理商務用 Skype的使用者設定，請在 Teams 系統管理中心的左側流覽中，前往 [使用者」，按一下使用者的顯示名稱以開啟使用者詳細資料頁面，然後選取 [商務用 Skype **設定>** 定位點。您可以在這裡為使用者設定外部存取和會議設定。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="使用者詳細資料頁面上商務用 Skype的螢幕擷取畫面":::

### <a name="external-access-settings"></a><span data-ttu-id="a3f3e-150">外部存取設定</span><span class="sxs-lookup"><span data-stu-id="a3f3e-150">External access settings</span></span>

<span data-ttu-id="a3f3e-151">您可以選擇性地允許或封鎖使用者是否能與組織外部人員通訊。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="a3f3e-152">**外部商務用 Skype** 使用者：如果您想要允許使用者與商務用 Skype網域的使用者通訊，請開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="a3f3e-153">**外部Skype** 使用者：如果您想要允許使用者與使用者通訊，請開啟Skype。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="a3f3e-154">會議設定</span><span class="sxs-lookup"><span data-stu-id="a3f3e-154">Meeting settings</span></span>

<span data-ttu-id="a3f3e-155">您可以為使用者設定下列會議設定。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="a3f3e-156">**音訊&視訊**：選擇下列其中一個音訊和視訊設定：</span><span class="sxs-lookup"><span data-stu-id="a3f3e-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="a3f3e-157">**無**：使用者無法使用音訊或視訊。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="a3f3e-158">**僅音訊**：使用者可以使用音訊，但不得使用視訊。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="a3f3e-159">**音訊和視訊**：使用者可以使用音訊和視訊。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="a3f3e-160">**音訊和視訊 (HD) ：** 使用者可以使用音訊和高畫質視訊。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="a3f3e-161">**錄製&** 交談：開啟此選項以允許使用者錄製交談和會議。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="a3f3e-162">**合規性**：如果您依法需要保留以電子方式儲存的資訊，請開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="a3f3e-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>