---
title: Microsoft 團隊中的資訊障礙
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 本文說明 Microsoft 團隊中的資訊障礙，以及他們會如何影響團隊。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c545b6289cd1a40fdf9ca967ebd44cd2d781605d
ms.sourcegitcommit: 950c04ce49064209ee04880e7c7473a4f931df50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996014"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="87f51-103">Microsoft 團隊中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="87f51-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="87f51-104"> (IB) 的資訊障礙是系統管理員可以設定以防止個人或群組彼此通訊的原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-104">Information barriers (IB) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="87f51-105">例如，如果某個部門處理的資訊不應與其他部門共用，或者必須防止或獨立地與該群組外的任何人通訊，則 IB 就很有用。</span><span class="sxs-lookup"><span data-stu-id="87f51-105">IB is useful if, for example, one department is handling information that shouldn't be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="87f51-106">資訊屏障群組無法跨承租人建立。</span><span class="sxs-lookup"><span data-stu-id="87f51-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="87f51-107">在版本1中不支援使用 bot、AAD app 及部分 Api 來新增使用者。</span><span class="sxs-lookup"><span data-stu-id="87f51-107">Using bots, AAD apps, and some APIs to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="87f51-108">專用通道符合您設定的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-108">Private channels are compliant to information barrier policies that you configure.</span></span>
> - <span data-ttu-id="87f51-109">[新增]：如需有關連線至團隊之 SharePoint 網站障礙支援的相關資訊，請按一下 [這裡](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="87f51-109">New: For Information about barriers support for SharePoint site connected to Teams, click [here](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="87f51-110">資訊屏障原則也會防止查閱和探索。</span><span class="sxs-lookup"><span data-stu-id="87f51-110">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="87f51-111">如果您嘗試與您不應該與之通訊的人通訊，您就不會在人員選擇器中找到該使用者。</span><span class="sxs-lookup"><span data-stu-id="87f51-111">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="87f51-112">背景</span><span class="sxs-lookup"><span data-stu-id="87f51-112">Background</span></span>

<span data-ttu-id="87f51-113">資訊障礙的主要驅動因素是來自金融服務行業。</span><span class="sxs-lookup"><span data-stu-id="87f51-113">The primary driver for information barriers comes from the financial services industry.</span></span> <span data-ttu-id="87f51-114">財務行業監管機構 ([FINRA]( http://www.finra.org)) 審查成員公司內的資訊壁壘與利益衝突，並提供有關如何 (FINRA 2241、 [債務研究規章注意事項 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)的相關指導方針。</span><span class="sxs-lookup"><span data-stu-id="87f51-114">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

<span data-ttu-id="87f51-115">不過，由於資訊障礙的推出，許多其他區域都會發現它們很有用。</span><span class="sxs-lookup"><span data-stu-id="87f51-115">However, since introducing information barriers, many other areas have found them to be useful.</span></span> <span data-ttu-id="87f51-116">其他常見的案例包括：</span><span class="sxs-lookup"><span data-stu-id="87f51-116">Other common scenarios include:</span></span>

- <span data-ttu-id="87f51-117">教育：一學校的學生無法查詢其他學校學生的連絡人詳細資料。</span><span class="sxs-lookup"><span data-stu-id="87f51-117">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>
- <span data-ttu-id="87f51-118">法律：維護一個用戶端的律師所取得之資料的機密性，不受代表不同用戶端之同一事務所的律師存取。</span><span class="sxs-lookup"><span data-stu-id="87f51-118">Legal: Maintaining confidentiality of data obtained by the lawyer of one client from being accessed by a lawyer for the same firm representing a different client.</span></span>
- <span data-ttu-id="87f51-119">政府：資訊存取和控制限制在各個部門和群組中。</span><span class="sxs-lookup"><span data-stu-id="87f51-119">Government: Information access and control are limited across departments and groups.</span></span>
- <span data-ttu-id="87f51-120">專業服務：公司中的人員群組只能在客戶接洽期間透過來賓存取權與用戶端或特定客戶交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-120">Professional services: A group of people in a company is only able to chat with a client or specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="87f51-121">例如，Enrico 屬於 [銀行] 區段，而 Pradeep 屬於 [財務顧問] 區段。</span><span class="sxs-lookup"><span data-stu-id="87f51-121">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="87f51-122">Enrico 和 Pradeep 無法彼此通訊，因為組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="87f51-122">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="87f51-123">不過，Enrico 和 Pradeep 可以與 HR 中的 [人力資源] 進行溝通。</span><span class="sxs-lookup"><span data-stu-id="87f51-123">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![此範例顯示資訊障礙，避免在區段之間通訊](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="87f51-125">何時使用資訊障礙</span><span class="sxs-lookup"><span data-stu-id="87f51-125">When to use information barriers</span></span>

<span data-ttu-id="87f51-126">在下列情況下，您可能會想要使用資訊障礙：</span><span class="sxs-lookup"><span data-stu-id="87f51-126">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="87f51-127">小組必須防止與特定其他團隊進行通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="87f51-127">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="87f51-128">小組不能與團隊以外的任何人通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="87f51-128">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="87f51-129">資訊屏障原則評估服務會判斷通訊是否符合資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-129">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="87f51-130">管理資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="87f51-130">Managing information barrier policies</span></span>

<span data-ttu-id="87f51-131">資訊屏障原則是在 Microsoft 365 合規性中心 (SCC) 使用 PowerShell Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="87f51-131">Information barrier policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="87f51-132">如需詳細資訊，請參閱 [定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="87f51-132">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87f51-133">在您設定或定義原則之前， **您必須在 Microsoft 團隊中啟用範圍目錄搜尋** 。</span><span class="sxs-lookup"><span data-stu-id="87f51-133">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="87f51-134">在您設定或定義資訊屏障的原則之前，請先等待至少幾小時後再啟用範圍目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="87f51-134">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="87f51-135">[深入瞭解資訊障礙的先決條件](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="87f51-135">[Learn more about prerequisites for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="87f51-136">資訊障礙管理員角色</span><span class="sxs-lookup"><span data-stu-id="87f51-136">Information barriers administrator role</span></span>

<span data-ttu-id="87f51-137">IB 相容性管理角色負責管理資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-137">The IB Compliance Management role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="87f51-138">如需有關此角色的詳細資訊，請參閱 [Microsoft 365 規範中心中的許可權](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="87f51-138">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="87f51-139">資訊屏障觸發程式</span><span class="sxs-lookup"><span data-stu-id="87f51-139">Information barrier triggers</span></span>

<span data-ttu-id="87f51-140">資訊屏障原則會在下列團隊事件發生時啟用：</span><span class="sxs-lookup"><span data-stu-id="87f51-140">Information barrier policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="87f51-141">**成員會新增至團隊** -每當您將使用者新增至團隊時，必須針對其他團隊成員的資訊屏障原則評估使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-141">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="87f51-142">成功新增使用者之後，使用者就可以執行團隊中的所有職能，而不需要進一步檢查。</span><span class="sxs-lookup"><span data-stu-id="87f51-142">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="87f51-143">如果使用者的原則禁止將他們加入小組，使用者就不會顯示在搜尋中。</span><span class="sxs-lookup"><span data-stu-id="87f51-143">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-add-members.png)

- <span data-ttu-id="87f51-145">**要求新的聊天** ：每次在兩個或多個使用者之間要求新的交談時，就會評估聊天，以確保它不違反任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-145">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn't violating any information barrier policies.</span></span> <span data-ttu-id="87f51-146">如果交談違反資訊屏障原則，就不會啟動交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-146">If the conversation violates an information barrier policy, then the conversation isn't initiated.</span></span>

    <span data-ttu-id="87f51-147">以下是1:1 聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-147">Here's an example of a 1:1 chat.</span></span>

     ![顯示1:1 聊天中封鎖通訊的螢幕擷取畫面](media/information-barriers-one-one-chat.png)

    <span data-ttu-id="87f51-149">以下是群組聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-149">Here's an example of a group chat.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-group-chat.png)

- <span data-ttu-id="87f51-151">**使用者受邀加入會議** -當使用者受邀加入會議時，系統會針對其他團隊成員的原則評估使用者的原則，如果發生衝突，就不允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-151">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there's a violation, the user will not be allowed to join the meeting.</span></span>

    ![顯示使用者已封鎖會議的螢幕擷取畫面](media/information-barriers-meeting.png)

- <span data-ttu-id="87f51-153">在 **兩個或多個使用者之間共用螢幕** -當螢幕在兩個或多個使用者之間共用時，必須評估畫面共用，以確保它不會違反其他使用者的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-153">**A screen is shared between two or more users** - When a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn't violate the information barrier policies of other users.</span></span> <span data-ttu-id="87f51-154">如果違反資訊屏障原則，就不允許使用螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="87f51-154">If an information barrier policy is violated, the screen share won't be allowed.</span></span> 
 
    <span data-ttu-id="87f51-155">以下是在套用原則之前的螢幕共用範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-155">Here's an example of screen share before the policy is applied.</span></span> 

    ![螢幕擷取畫面顯示使用者聊天](media/ib-before-screen-share-policy.png)

    <span data-ttu-id="87f51-157">以下是套用原則後的螢幕共用範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-157">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="87f51-158">看不到 [畫面共用] 和 [通話] 圖示。</span><span class="sxs-lookup"><span data-stu-id="87f51-158">The screen share and call icons aren't visible.</span></span>

    ![螢幕擷取畫面顯示有封鎖設定的使用者字元](media/ib-after-screen-share-policy.png)

- <span data-ttu-id="87f51-160">**使用者將電話撥打電話給團隊中 () VOIP** ，只要使用者向另一個使用者或群組使用者發起語音通話，就會評估通話，確定它不會違反其他小組成員的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-160">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn't violate the information barrier policies of other team members.</span></span> <span data-ttu-id="87f51-161">如果有任何侵犯，語音通話會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="87f51-161">If there is any violation, the voice call is blocked.</span></span>
- <span data-ttu-id="87f51-162">**小組中的來賓使用者** 也可以在小組中的來賓使用者也套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-162">**Guest users in Teams** - Information barrier policies apply to guest users in Teams too.</span></span> <span data-ttu-id="87f51-163">如果在貴組織的全域通訊清單中，有來賓使用者需要可發現的，請參閱 [在 Microsoft 365 群組中管理來賓存取](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="87f51-163">If guest users need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="87f51-164">一旦訪客使用者可被發現，您就可以 [定義資訊屏障原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="87f51-164">Once guest users are discoverable, you can [define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="87f51-165">原則變更對現有聊天有何影響</span><span class="sxs-lookup"><span data-stu-id="87f51-165">How policy changes impact existing chats</span></span>

<span data-ttu-id="87f51-166">當資訊屏障原則管理員對原則進行變更，或原則變更因使用者設定檔變更 (（例如作業變更或類似的原因) ），資訊屏障原則評估服務會自動搜尋成員，以確保小組成員不違反任何原則。</span><span class="sxs-lookup"><span data-stu-id="87f51-166">When the information barrier policy administrator makes changes to a policy, or a policy change kicks into effect because of a change to a user's profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="87f51-167">如果使用者之間已有聊天或其他通訊，且已設定新的原則，或是已變更現有的原則，此服務會評估現有的通訊，以確保仍允許進行通訊。</span><span class="sxs-lookup"><span data-stu-id="87f51-167">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="87f51-168">**1:1 聊天** -如果已不允許兩個使用者之間的通訊 (如果原則封鎖通訊已套用至其中一或兩個使用者) ，系統會封鎖進一步通訊，聊天交談就會變成隻讀狀態。</span><span class="sxs-lookup"><span data-stu-id="87f51-168">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span> 

    <span data-ttu-id="87f51-169">以下是顯示 [聊天] 的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-169">Here's an example that shows the chat is visible.</span></span>

    ![螢幕擷取畫面顯示 [使用者聊天] 可供使用](media/ib-before-1-1chat-policy.png)

    <span data-ttu-id="87f51-171">以下範例顯示 [聊天] 已停用。</span><span class="sxs-lookup"><span data-stu-id="87f51-171">Here's an example that shows the chat is disabled.</span></span>

    ![顯示已停用使用者聊天的螢幕擷取畫面](media/ib-after-1-1chat-policy.png)

- <span data-ttu-id="87f51-173">**群組聊天** -如果已不再允許來自某個使用者的通訊 (例如，如果使用者變更作業) ，就可能會從群組聊天中移除該使用者以及違反該原則的其他使用者，而不允許其他人與該群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="87f51-173">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="87f51-174">使用者仍然可以查看舊的交談 (唯讀) ，但無法看到或參與與群組的任何新交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-174">The user can still see old conversations (read-only), but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="87f51-175">如果新的或已變更的原則將通訊套用到多個使用者，則受該原則影響的使用者可能會從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="87f51-175">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="87f51-176">他們仍能看到舊的交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-176">They can still see old conversations.</span></span>

<span data-ttu-id="87f51-177">在這個範例中，Enrico 移至組織內的不同部門，並從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="87f51-177">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job.png)

<span data-ttu-id="87f51-179">Enrico 無法再傳送訊息到群組聊天。</span><span class="sxs-lookup"><span data-stu-id="87f51-179">Enrico can no longer send messages to the group chat.</span></span>

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="87f51-181">**小組** -已從群組中移除的任何使用者都會從小組中移除，而且將無法查看或參與現有或新的交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-181">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="87f51-182">案例：現有聊天中的使用者遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="87f51-182">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="87f51-183">目前，如果資訊屏障原則封鎖其他使用者，使用者就會遇到下列情況：</span><span class="sxs-lookup"><span data-stu-id="87f51-183">Currently, users experience the following scenarios if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="87f51-184">[ **人員]** 索引標籤-使用者無法在 [ **人員** ] 索引標籤上看到封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="87f51-184">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="87f51-185">**人員選擇器** -在 [人員選擇器] 中不會顯示封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="87f51-185">**People Picker** - Blocked users will not be visible in the people picker.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="87f51-187">[ **活動]** 索引標籤-如果使用者要造訪封鎖使用者的 [ **活動** ] 索引標籤，就不會顯示任何文章。</span><span class="sxs-lookup"><span data-stu-id="87f51-187">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="87f51-188"> ([ **活動** ] 索引標籤只會顯示頻道發佈，而兩個使用者之間則不會有任何常見頻道。 ) </span><span class="sxs-lookup"><span data-stu-id="87f51-188">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="87f51-189">以下是已封鎖之 [活動] 索引標籤視圖的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-189">Here's an example of the activity tab view that is blocked.</span></span>

    ![顯示已封鎖 [活動] 索引標籤的螢幕擷取畫面](media/ib-after-activity-tab-policy.png)


- <span data-ttu-id="87f51-191">**組織** 結構-如果使用者存取的組織結構中出現封鎖的使用者，則封鎖的使用者不會出現在組織結構中，也會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="87f51-191">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="87f51-192">**連絡人卡片** -如果使用者參與交談，且隨後遭到封鎖，當使用者將游標移到封鎖的使用者名稱上時，其他使用者就會看到錯誤訊息，而不是連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="87f51-192">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="87f51-193">在卡片上所列的動作 (例如通話和聊天) 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="87f51-193">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="87f51-194">[ **建議的連絡人** ]：封鎖的使用者不會出現在 [建議的連絡人] 清單中， (為新使用者顯示的初始連絡人清單) 。</span><span class="sxs-lookup"><span data-stu-id="87f51-194">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="87f51-195">[ **聊天連絡人** ]-使用者可以在聊天連絡人清單中看到封鎖的使用者，但會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。</span><span class="sxs-lookup"><span data-stu-id="87f51-195">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span> <span data-ttu-id="87f51-196">使用者也可以按一下他們來查看其過去的交談。</span><span class="sxs-lookup"><span data-stu-id="87f51-196">The user can also click on them to view their past conversation.</span></span>
- <span data-ttu-id="87f51-197">[ **通話連絡人** ]-使用者可以在通話連絡人清單中看到封鎖的使用者，但系統會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。</span><span class="sxs-lookup"><span data-stu-id="87f51-197">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>

    <span data-ttu-id="87f51-198">以下是通話連絡人清單中封鎖使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-198">Here's an example of a blocked user in the calls contact list.</span></span>

    ![螢幕擷取畫面顯示使用者使用者聊天](media/ib-before-chat-contacts-policy.png)

    <span data-ttu-id="87f51-200">以下是針對 [通話內容] 清單中的使用者停用聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="87f51-200">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    ![螢幕擷取畫面顯示使用者已從聊天中封鎖](media/ib-after-chat-contacts-policy.png)

- <span data-ttu-id="87f51-202">**Skype 至團隊遷移** -在商務用 skype 中進行團隊遷移期間，所有使用者（即使是資訊屏障原則所封鎖），都會將它遷移至小組，然後將按照上述步驟進行處理。</span><span class="sxs-lookup"><span data-stu-id="87f51-202">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="87f51-203">團隊原則與 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="87f51-203">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="87f51-204">建立小組後，就會建立 SharePoint 網站，並與 Microsoft 團隊取得檔案體驗的相關專案。</span><span class="sxs-lookup"><span data-stu-id="87f51-204">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="87f51-205">依預設，資訊屏障原則不會在此 SharePoint 網站和檔案上生效。</span><span class="sxs-lookup"><span data-stu-id="87f51-205">Information barrier policies are not honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="87f51-206">若要啟用資訊屏障原則，系統管理員已填寫完表單，要求在 SharePoint 和 OneDrive 上啟用 IB 原則 (請參閱 [資訊壁壘](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)) 中的 *必備* 區段。</span><span class="sxs-lookup"><span data-stu-id="87f51-206">To enable Information Barrier policies, the administrator has already filled out a form, requesting that IB policies be enabled on SharePoint and OneDrive (see the *Prerequisite* section in [Information barriers](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)).</span></span> <span data-ttu-id="87f51-207">如果資訊屏障原則已在 SharePoint 和 OneDrive 中開啟，則在使用 Microsoft 團隊建立小組時，IB 原則會在已提供的 SharePoint 網站上運作。</span><span class="sxs-lookup"><span data-stu-id="87f51-207">If the Information Barrier policy is turned on in SharePoint and OneDrive, then the IB policies will work on SharePoint sites provisioned when a team is created with Microsoft Teams.</span></span>

<span data-ttu-id="87f51-208">**小組 SharePoint 網站上的 IB 原則範例** ：在 Contoso 銀行公司中，使用者「Sesha@contosobank.onmicrosoft.com」屬於投資銀行區段，而使用者 ' Nikita@contosobank.onmicrosoft.com ' 屬於區段建議。</span><span class="sxs-lookup"><span data-stu-id="87f51-208">**Example of IB policies on SharePoint site of a team** : In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to segment Advisory.</span></span> <span data-ttu-id="87f51-209">組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="87f51-209">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="87f51-210">當使用者 Sesha 建立投資銀行區段的小組時，只有投資銀行區段使用者才能存取該小組和支援該小組的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="87f51-210">When user Sesha creates a team for Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking segment users.</span></span> <span data-ttu-id="87f51-211">即使她擁有 [網站] 連結，使用者 Nikita 還是無法存取該網站。</span><span class="sxs-lookup"><span data-stu-id="87f51-211">User Nikita can't access that site even if she has the site link.</span></span>

<span data-ttu-id="87f51-212">如需詳細資訊，請參閱 [資訊障礙](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) 文章。</span><span class="sxs-lookup"><span data-stu-id="87f51-212">See the [Information barriers](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) article for more details.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="87f51-213">所需的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="87f51-213">Required licenses and permissions</span></span>

<span data-ttu-id="87f51-214">如需詳細資訊（包括方案和定價），請參閱 [授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="87f51-214">For more information, including plans and pricing, see [Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="87f51-215">已知問題</span><span class="sxs-lookup"><span data-stu-id="87f51-215">Known Issues</span></span>
- <span data-ttu-id="87f51-216">**使用者無法加入即席會議** ：如果已啟用 IB 原則，則不允許使用者加入會議（如果會議內名單的大小大於 [會議出席限制](limits-specifications-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="87f51-216">**Users can't join ad-hoc meetings** : If IB policies are enabled, users are not allowed to join meetings IF the meeting roster size is more than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="87f51-217">根本原因是 IB 檢查會依據是否可將使用者新增至會議聊天的名單，並接受該信號以允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-217">The root cause is that IB checks rely on whether users can be added to a meeting chat roster and takes that signal to allow users to join meetings.</span></span> <span data-ttu-id="87f51-218">加入會議一次會將該使用者新增至名單，因此，如果是定期會議，該使用者會以最快的方式填滿會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-218">Joining a meeting once will add that user to the roster, hence for recurring meetings, the roster fills up fast.</span></span> <span data-ttu-id="87f51-219">在達到 [會議出席限制](limits-specifications-teams.md)後，就不允許其他使用者新增至會議聊天名單。</span><span class="sxs-lookup"><span data-stu-id="87f51-219">Once it reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting chat roster.</span></span> <span data-ttu-id="87f51-220">如果已為租使用者啟用 IB，且聊天名單已充滿會議，則不允許新使用者 (不在) 名單中的使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-220">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those not already on the roster) are not allowed to join the meeting.</span></span> <span data-ttu-id="87f51-221">但如果沒有為租使用者啟用 IB，且會議聊天的名單已滿，新的使用者 (不在) 名單中的使用者，即使他們在會議中看不到聊天選項，也能加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-221">But if IB is not enabled for the tenant and the meeting chat roster is full, new users (those not already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="87f51-222">短期解決方案是從會議聊天中移除非作用中的成員，為新使用者騰出空間。</span><span class="sxs-lookup"><span data-stu-id="87f51-222">A short term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="87f51-223">不過，我們會在稍後的日期增加會議聊天 rosters 的大小。</span><span class="sxs-lookup"><span data-stu-id="87f51-223">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>

- <span data-ttu-id="87f51-224">**使用者無法加入頻道會議** ：如果已啟用 IB 原則，則不允許使用者加入頻道會議（如果他們不是團隊的成員）。</span><span class="sxs-lookup"><span data-stu-id="87f51-224">**Users can't join channel meetings** : If IB policies are enabled, users are not allowed to join channel meetings IF they are not a member of the team.</span></span> <span data-ttu-id="87f51-225">根本原因是 IB 檢查會依據是否可將使用者新增至會議聊天的名單，並接受該信號以允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-225">The root cause is that IB checks rely on whether users can be added to a meeting chat roster and takes that signal to allow users to join meetings.</span></span> <span data-ttu-id="87f51-226">頻道會議中的聊天線程只適用于小組/頻道成員，非成員無法查看/存取聊天線程。</span><span class="sxs-lookup"><span data-stu-id="87f51-226">The chat thread in a channel meeting is available to Team/Channel members only, and non-members cannot see/access the chat thread.</span></span> <span data-ttu-id="87f51-227">如果已為租使用者啟用 IB，且非團隊成員嘗試加入頻道會議，則不允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="87f51-227">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, the user is not allowed to join the meeting.</span></span> <span data-ttu-id="87f51-228">但如果沒有為租使用者啟用 IB，且非團隊成員試圖加入頻道會議，則允許使用者加入會議，但在會議中看不到 [聊天] 選項。</span><span class="sxs-lookup"><span data-stu-id="87f51-228">But if IB is not enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting, however, they won't see the chat option in the meeting.</span></span>

## <a name="more-information"></a><span data-ttu-id="87f51-229">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="87f51-229">More information</span></span>

- <span data-ttu-id="87f51-230">若要深入瞭解資訊障礙，請參閱 [資訊障礙](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="87f51-230">To learn more about information barriers, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="87f51-231">若要設定資訊屏障原則，請參閱 [定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="87f51-231">To set up information barrier policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="87f51-232">若要編輯或移除資訊屏障原則，請參閱 [編輯 (或移除) 資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="87f51-232">To edit or remove information barrier policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>
