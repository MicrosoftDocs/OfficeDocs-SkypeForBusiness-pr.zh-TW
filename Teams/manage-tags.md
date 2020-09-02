---
title: 管理 Microsoft 團隊中的標記
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中管理組織中使用標記的方式。
ms.openlocfilehash: 9295d03aecb6c0bc6a4f667214869fe698d4eaab
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324010"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="dcca0-103">管理 Microsoft 團隊中的標記</span><span class="sxs-lookup"><span data-stu-id="dcca0-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="dcca0-104">本文中討論的其中一個功能，請 **按 shift 進行標記**，但尚未放開。</span><span class="sxs-lookup"><span data-stu-id="dcca0-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="dcca0-105">我們已宣佈推出，即將推出。</span><span class="sxs-lookup"><span data-stu-id="dcca0-105">It's been announced, and it's coming soon.</span></span><span data-ttu-id="dcca0-106">如果您是系統管理員，您可以在 [ [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) ]) 的 [訊息中心] (，找出這項功能的發行時間。</span><span class="sxs-lookup"><span data-stu-id="dcca0-106"> If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="dcca0-107">若要維持在即將到來的小組功能上，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="dcca0-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="dcca0-108">概觀</span><span class="sxs-lookup"><span data-stu-id="dcca0-108">Overview</span></span>

<span data-ttu-id="dcca0-109">Microsoft 團隊中的標記可讓使用者快速且輕鬆地與團隊中的部分人員連線。</span><span class="sxs-lookup"><span data-stu-id="dcca0-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="dcca0-110">您可以建立並指派自訂標籤，以根據屬性（例如角色、專案、技能或位置）來分類人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="dcca0-111">或者，您會在 [ [倒班] 應用程式](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 中根據其排程和倒班資訊，自動將標籤指派給人員 (即將) 。</span><span class="sxs-lookup"><span data-stu-id="dcca0-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="dcca0-112">將標籤新增至一或多個小組成員之後，就可以 @mentions 在您的頻道文章中，由小組中的任何人使用，或只與分派該標記的人員開始交談。</span><span class="sxs-lookup"><span data-stu-id="dcca0-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="dcca0-113">如前文所述，小組中有兩種不同的標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="dcca0-114">**自訂**標籤：團隊擁有者和小組成員 (如果已為其啟用功能) 可以手動建立並指派標籤給人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="dcca0-115">例如，「設計工具」或「Radiologist」標記會在小組中找到這些人員組，而不需要輸入他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="dcca0-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="dcca0-116">使用 (即將推出**的 shift 進行標記**) ：您可以使用此功能，在團隊中的 [[倒班] 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)中，系統會自動指派與其排程和班次群組名稱相符的標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="dcca0-117">例如，當您在聊天或頻道文章中使用標籤時，「EngineerOnCall」標記會達到所有排程的專案。</span><span class="sxs-lookup"><span data-stu-id="dcca0-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="dcca0-118">當使用者需要快速轉接資訊時，您可以使用 [依班來標記]，讓團隊不知道隨班的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="dcca0-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="dcca0-119">依倒班進行標記，主要工作力管理系統（例如 JDA、Kronos 和 AMiON）也可以透過團隊中的倒班來整合。</span><span class="sxs-lookup"><span data-stu-id="dcca0-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="dcca0-120">若要深入瞭解如何設定此功能，請參閱 [依倒班設定標記](#set-up-tagging-by-shift-coming-soon)。</span><span class="sxs-lookup"><span data-stu-id="dcca0-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="dcca0-121">在私有通道中尚不支援標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="dcca0-122">您尚無法在美國政府社區雲端 (GCC) 、GCC 高或國防 (DoD) 組織中提供標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="dcca0-123">標記的運作方式</span><span class="sxs-lookup"><span data-stu-id="dcca0-123">How tags work</span></span>

<span data-ttu-id="dcca0-124">您可以手動新增或自動將標記指派給特定小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="dcca0-125">然後，就可以在聊天中的 [ **至** ] 行或在團隊任何標準頻道的文章中 @mentions 使用。</span><span class="sxs-lookup"><span data-stu-id="dcca0-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="dcca0-126">以下是如何在團隊中使用標記的一些範例：</span><span class="sxs-lookup"><span data-stu-id="dcca0-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="dcca0-127">商店主管將公告張貼到頻道，以通知所有出納。</span><span class="sxs-lookup"><span data-stu-id="dcca0-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="dcca0-128">醫院管理員會將訊息傳送給頻道中的所有 radiologists。</span><span class="sxs-lookup"><span data-stu-id="dcca0-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="dcca0-129">行銷管理員會開始與所有設計人員進行群組聊天。</span><span class="sxs-lookup"><span data-stu-id="dcca0-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="dcca0-130">護士會將訊息傳送給所有的通話 cardiologists。</span><span class="sxs-lookup"><span data-stu-id="dcca0-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="dcca0-131">即將推出 () </span><span class="sxs-lookup"><span data-stu-id="dcca0-131">(coming soon)</span></span>
- <span data-ttu-id="dcca0-132">系統工程師將公告發布至頻道，以通知所有的現場工程人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="dcca0-133">即將推出 () </span><span class="sxs-lookup"><span data-stu-id="dcca0-133">(coming soon)</span></span>

<span data-ttu-id="dcca0-134">當您在頻道交談中 @mentioned 標籤時，與標籤相關聯的小組成員就會收到通知，就像任何其他的 @mention 一樣。</span><span class="sxs-lookup"><span data-stu-id="dcca0-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="dcca0-135">管理貴組織的自訂標籤</span><span class="sxs-lookup"><span data-stu-id="dcca0-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="dcca0-136">身為系統管理員，您可以控制在 Microsoft 團隊系統管理中心的整個組織中使用標記的方式。</span><span class="sxs-lookup"><span data-stu-id="dcca0-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

<span data-ttu-id="dcca0-138">團隊最多可以有100個標籤，最多可將100個小組成員指派給一個標籤，而且最多25個標籤可以指派給單一使用者。</span><span class="sxs-lookup"><span data-stu-id="dcca0-138">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="dcca0-139">設定誰可以新增自訂標籤</span><span class="sxs-lookup"><span data-stu-id="dcca0-139">Set who can add custom tags</span></span>

<span data-ttu-id="dcca0-140">根據預設，小組擁有者可以新增自訂標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-140">By default, team owners can add custom tags.</span></span> <span data-ttu-id="dcca0-141">您可以變更此設定，以允許小組擁有者和小組成員建立、編輯、刪除及管理標籤，或者您可以關閉貴組織的標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-141">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="dcca0-142">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="dcca0-142">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="dcca0-143">在 [ **標記**] 底下 **的 [** 標籤] 旁，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="dcca0-143">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="dcca0-144">**小組擁有者和成員**：允許團隊擁有者和成員管理標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-144">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="dcca0-145">**小組擁有**者：允許團隊擁有者管理標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-145">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="dcca0-146">[**已停用**]：關閉標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-146">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="dcca0-147">設定自訂標記設定</span><span class="sxs-lookup"><span data-stu-id="dcca0-147">Configure custom tags settings</span></span>

<span data-ttu-id="dcca0-148">您可以設定下列標記設定，以控制如何在整個組織中使用自訂標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-148">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="dcca0-149">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="dcca0-149">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="dcca0-150">根據貴組織的需求，在 [ **標記**] 底下設定下列各項。</span><span class="sxs-lookup"><span data-stu-id="dcca0-150">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="dcca0-151">**讓小組擁有者覆寫誰能管理**標籤：當您開啟此設定時，小組擁有者可以設定小組成員是否可以在小組中建立及管理標籤，而標記的值是 **由 set 管理** ，這是每個團隊的預設值。</span><span class="sxs-lookup"><span data-stu-id="dcca0-151">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="dcca0-152">如果您關閉此設定，就無法依每個小組的設定來變更 **標記** 。</span><span class="sxs-lookup"><span data-stu-id="dcca0-152">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="dcca0-153">**建議的預設**標籤：使用這個功能來新增一組預設的標籤。</span><span class="sxs-lookup"><span data-stu-id="dcca0-153">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="dcca0-154">您可以新增最多25個標籤，每個標籤最多可包含25個字元。</span><span class="sxs-lookup"><span data-stu-id="dcca0-154">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="dcca0-155">小組擁有者和成員 (如果已針對其啟用該功能) 可以使用這些建議、新增到他們，或建立一組新的標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-155">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="dcca0-156">[**建立自訂**標籤]：開啟此設定可讓其他人新增您所設定的預設標記以外的標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-156">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="dcca0-157">如果您關閉此功能，人員只能使用建議的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="dcca0-157">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="dcca0-158">如果您關閉此功能，請務必新增一個或多個預設標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-158">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="dcca0-159">管理團隊的自訂標記設定</span><span class="sxs-lookup"><span data-stu-id="dcca0-159">Manage custom tags settings for a team</span></span>

<span data-ttu-id="dcca0-160">如果您在 Microsoft 團隊系統管理中心開啟了 [ **讓小組擁有者覆蓋誰可以管理** 標籤] 設定，小組擁有者可以設定成員是否可以在小組層級新增標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-160">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="dcca0-161">若要這樣做，請在團隊的 [ **設定** ] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-161">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="dcca0-163">使用標記</span><span class="sxs-lookup"><span data-stu-id="dcca0-163">Use tags</span></span>

<span data-ttu-id="dcca0-164">以下說明如何新增自訂標籤，以及如何在您使用 [團隊) 中的 [倒班] 應用程式時，依 shift (設定標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-164">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="dcca0-165">若要深入瞭解，請參閱 [在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="dcca0-165">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="dcca0-166">建立及指派自訂標記</span><span class="sxs-lookup"><span data-stu-id="dcca0-166">Create and assign custom tags</span></span>

<span data-ttu-id="dcca0-167">若要建立及指派自訂標籤，請選取應用程式左側的 [ **小組** ]，然後在清單中尋找您的小組。</span><span class="sxs-lookup"><span data-stu-id="dcca0-167">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="dcca0-168">選取 [ **更多選項**]，然後選擇 [ **管理**標籤]。</span><span class="sxs-lookup"><span data-stu-id="dcca0-168">Select **More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="dcca0-169">您可以在這裡建立標籤，並將其指派給小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-169">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="dcca0-170">如何在團隊用戶端套用標記的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="dcca0-170">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="dcca0-171">若要刪除標記，請移除與標籤相關聯的所有小組成員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-171">To delete a tag, remove all team members associated with the tag.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="dcca0-172">在即將推出的情況中設定標記 () </span><span class="sxs-lookup"><span data-stu-id="dcca0-172">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="dcca0-173">在 [團隊] 中，移至 [ [倒班] app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="dcca0-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="dcca0-174">建立 [倒班群組](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，並將其命名為一個屬性（例如角色）。</span><span class="sxs-lookup"><span data-stu-id="dcca0-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="dcca0-175">例如，EngineerOnCall。</span><span class="sxs-lookup"><span data-stu-id="dcca0-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="dcca0-176">[倒班] 組名就是標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="dcca0-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="dcca0-177">將倒班指派給您的小組成員，即可[填入排程](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)。</span><span class="sxs-lookup"><span data-stu-id="dcca0-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="dcca0-178">完成時，請在 [倒班] app 的右上角，選取 [ **與團隊共用**]。</span><span class="sxs-lookup"><span data-stu-id="dcca0-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="dcca0-179">請等候15分鐘，讓排程的倒班填入標記服務。</span><span class="sxs-lookup"><span data-stu-id="dcca0-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="dcca0-180">在團隊中您使用標籤的任何位置使用標記。</span><span class="sxs-lookup"><span data-stu-id="dcca0-180">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="dcca0-181">[依倒班進行標記] 可讓您的使用者即時與其他人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="dcca0-181">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="dcca0-182">通知只會傳送給在使用標籤來啟動聊天或頻道文章時，有班次的人員。</span><span class="sxs-lookup"><span data-stu-id="dcca0-182">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dcca0-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="dcca0-183">Related topics</span></span>

[<span data-ttu-id="dcca0-184">在團隊中使用標記</span><span class="sxs-lookup"><span data-stu-id="dcca0-184">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="dcca0-185">在 Teams 中管理貴組織的 Shifts 應用程式</span><span class="sxs-lookup"><span data-stu-id="dcca0-185">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="dcca0-186">班次協助檔</span><span class="sxs-lookup"><span data-stu-id="dcca0-186">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
