---
title: Microsoft 團隊中的資訊障礙
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
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
ms.openlocfilehash: ce71f0c0f2621253698cd250372624ded638dcec
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083183"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="11d80-103">Microsoft 團隊中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="11d80-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="11d80-104">資訊壁壘（IB）是系統管理員可以設定的原則，以避免個人或群組彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="11d80-104">Information barriers (IB) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="11d80-105">例如，如果某個部門處理的資訊不應與其他部門共用，或者必須防止或獨立地與該群組外的任何人通訊，這就很有用。</span><span class="sxs-lookup"><span data-stu-id="11d80-105">This is useful if, for example, one department is handling information that shouldn't be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="11d80-106">資訊屏障群組無法跨承租人建立。</span><span class="sxs-lookup"><span data-stu-id="11d80-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="11d80-107">在版本1中不支援使用 bot 來新增使用者。</span><span class="sxs-lookup"><span data-stu-id="11d80-107">Using bots to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="11d80-108">專用通道符合您設定的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-108">Private channels are compliant to information barrier policies that you configure.</span></span>
> - <span data-ttu-id="11d80-109">[新增]：連線至團隊之 SharePoint 網站的資訊障礙支援現已成為私人預覽。</span><span class="sxs-lookup"><span data-stu-id="11d80-109">New: Information barrier support for SharePoint site connected to Teams is now in Private Preview.</span></span> <span data-ttu-id="11d80-110">按一下[這裡](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u)以參與私人預覽。</span><span class="sxs-lookup"><span data-stu-id="11d80-110">Click [here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) to participate in the private preview.</span></span>

<span data-ttu-id="11d80-111">資訊屏障原則也會防止查閱和探索。</span><span class="sxs-lookup"><span data-stu-id="11d80-111">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="11d80-112">這表示如果您嘗試與您不應該與之通訊的人通訊，就不會在人員選擇器中找到該使用者。</span><span class="sxs-lookup"><span data-stu-id="11d80-112">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="11d80-113">背景</span><span class="sxs-lookup"><span data-stu-id="11d80-113">Background</span></span>

<span data-ttu-id="11d80-114">資訊障礙的主要驅動因素是來自金融服務行業。</span><span class="sxs-lookup"><span data-stu-id="11d80-114">The primary driver for information barriers comes from the financial services industry.</span></span> <span data-ttu-id="11d80-115">財務行業監管機構（[FINRA]( http://www.finra.org)）會在成員公司內審查資訊的壁壘與利益衝突，並提供如何管理此類衝突（FINRA 2241、[債務研究規章注意事項 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)）的指導方針。</span><span class="sxs-lookup"><span data-stu-id="11d80-115">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

<span data-ttu-id="11d80-116">不過，由於資訊障礙的推出，許多其他區域都會發現它們很有用。</span><span class="sxs-lookup"><span data-stu-id="11d80-116">However, since introducing information barriers, many other areas have found them to be useful.</span></span> <span data-ttu-id="11d80-117">其他常見的案例包括：</span><span class="sxs-lookup"><span data-stu-id="11d80-117">Other common scenarios include:</span></span>

- <span data-ttu-id="11d80-118">教育：一學校的學生無法查詢其他學校學生的連絡人詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d80-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>
- <span data-ttu-id="11d80-119">法律：維護一個用戶端的律師所取得之資料的機密性，不受代表不同用戶端之同一事務所的律師存取。</span><span class="sxs-lookup"><span data-stu-id="11d80-119">Legal: Maintaining confidentiality of data obtained by the lawyer of one client from being accessed by a lawyer for the same firm representing a different client.</span></span>
- <span data-ttu-id="11d80-120">政府：資訊存取和控制限制在各個部門和群組中。</span><span class="sxs-lookup"><span data-stu-id="11d80-120">Government: Information access and control is limited across departments and groups.</span></span>
- <span data-ttu-id="11d80-121">[專業服務]：公司中的一組人員只能透過同盟或來賓存取權在客戶合作期間與用戶端或特定客戶進行交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-121">Professional services: A group of people in a company is only able to chat with a client or specific customer via federation or guest access during a customer engagement.</span></span>

<span data-ttu-id="11d80-122">例如，Enrico 屬於 [銀行] 區段，而 Pradeep 屬於 [財務顧問] 區段。</span><span class="sxs-lookup"><span data-stu-id="11d80-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="11d80-123">Enrico 和 Pradeep 無法彼此通訊，因為組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="11d80-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="11d80-124">不過，Enrico 和 Pradeep 可以與 HR 中的 [人力資源] 進行溝通。</span><span class="sxs-lookup"><span data-stu-id="11d80-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![此範例顯示資訊障礙，避免在區段之間通訊](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="11d80-126">何時使用資訊障礙</span><span class="sxs-lookup"><span data-stu-id="11d80-126">When to use information barriers</span></span>

<span data-ttu-id="11d80-127">在下列情況下，您可能會想要使用資訊障礙：</span><span class="sxs-lookup"><span data-stu-id="11d80-127">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="11d80-128">小組必須防止與特定其他團隊進行通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="11d80-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="11d80-129">小組不能與團隊以外的任何人通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="11d80-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="11d80-130">資訊屏障原則評估服務會判斷通訊是否符合資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="11d80-131">管理資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="11d80-131">Managing information barrier policies</span></span>

<span data-ttu-id="11d80-132">資訊屏障原則是在 Microsoft 365 規範中心（SCC）中使用 PowerShell Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="11d80-132">Information barrier policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="11d80-133">如需詳細資訊，請參閱[定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="11d80-133">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11d80-134">在您設定或定義原則之前，**您必須在 Microsoft 團隊中啟用範圍目錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="11d80-134">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="11d80-135">在您設定或定義資訊屏障的原則之前，請先等待至少幾小時後再啟用範圍目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="11d80-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="11d80-136">[深入瞭解資訊障礙的先決條件](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="11d80-136">[Learn more about prerequisites for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="11d80-137">資訊障礙管理員角色</span><span class="sxs-lookup"><span data-stu-id="11d80-137">Information barriers administrator role</span></span>

<span data-ttu-id="11d80-138">IB 相容性管理角色負責管理資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-138">The IB Compliance Management role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="11d80-139">如需有關此角色的詳細資訊，請參閱[Microsoft 365 規範中心中的許可權](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="11d80-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="11d80-140">資訊屏障觸發程式</span><span class="sxs-lookup"><span data-stu-id="11d80-140">Information barrier triggers</span></span>

<span data-ttu-id="11d80-141">資訊屏障原則會在下列團隊事件發生時啟用：</span><span class="sxs-lookup"><span data-stu-id="11d80-141">Information barrier policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="11d80-142">**成員會新增至團隊**-每當您將使用者新增至團隊時，必須針對其他團隊成員的資訊屏障原則評估使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="11d80-143">成功新增使用者之後，使用者就可以執行團隊中的所有職能，而不需要進一步檢查。</span><span class="sxs-lookup"><span data-stu-id="11d80-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="11d80-144">如果使用者的原則禁止將他們加入小組，使用者就不會顯示在搜尋中。</span><span class="sxs-lookup"><span data-stu-id="11d80-144">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-add-members.png)

- <span data-ttu-id="11d80-146">**要求新的聊天**：每次在兩個或多個使用者之間要求新的交談時，就會評估聊天，以確保它不違反任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-146">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn't violating any information barrier policies.</span></span> <span data-ttu-id="11d80-147">如果交談違反資訊屏障原則，就不會啟動交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-147">If the conversation violates an information barrier policy, then the conversation isn't initiated.</span></span>

    <span data-ttu-id="11d80-148">以下是1:1 聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-148">Here's an example of a 1:1 chat.</span></span>

     ![顯示1:1 聊天中封鎖通訊的螢幕擷取畫面](media/information-barriers-one-one-chat.png)

    <span data-ttu-id="11d80-150">以下是群組聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-150">Here's an example of a group chat.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-group-chat.png)

- <span data-ttu-id="11d80-152">**使用者受邀加入會議**-當使用者受邀加入會議時，系統會針對其他團隊成員的原則評估使用者的原則，如果發生衝突，就不允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="11d80-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there's a violation, the user will not be allowed to join the meeting.</span></span>

    ![顯示使用者已封鎖會議的螢幕擷取畫面](media/information-barriers-meeting.png)

- <span data-ttu-id="11d80-154">**在兩個以上的使用者之間共用螢幕**-只要兩個或多個使用者共用畫面，就必須評估畫面共用，以確保它不會違反其他使用者的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-154">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn't violate the information barrier policies of other users.</span></span> <span data-ttu-id="11d80-155">如果違反資訊屏障原則，就不允許使用螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="11d80-155">If an information barrier policy is violated, the screen share won't be allowed.</span></span> 
 
    <span data-ttu-id="11d80-156">以下是在套用原則之前的螢幕共用範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-156">Here's an example of screen share before the policy is applied.</span></span> 

    ![螢幕擷取畫面顯示使用者聊天](media/ib-before-screen-share-policy.png)

    <span data-ttu-id="11d80-158">以下是套用原則後的螢幕共用範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-158">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="11d80-159">看不到 [畫面共用] 和 [通話] 圖示。</span><span class="sxs-lookup"><span data-stu-id="11d80-159">The screen share and call icons aren't visible.</span></span>

    ![螢幕擷取畫面顯示有封鎖設定的使用者字元](media/ib-after-screen-share-policy.png)

- <span data-ttu-id="11d80-161">**使用者將電話撥打電話（VOIP）放在團隊中**，只要使用者向其他使用者或群組使用者啟動語音通話，就會評估通話，確定它不會違反其他小組成員的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-161">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn't violate the information barrier policies of other team members.</span></span> <span data-ttu-id="11d80-162">如果有任何侵犯，語音通話會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="11d80-162">If there is any violation, the voice call is blocked.</span></span>
- <span data-ttu-id="11d80-163">**小組中的來賓使用者**也可以在小組中的來賓使用者也套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="11d80-163">**Guest users in Teams** - Information barrier policies apply to guest users in Teams too.</span></span> <span data-ttu-id="11d80-164">如果在貴組織的全域通訊清單中，有來賓使用者需要可發現的，請參閱[在 Microsoft 365 群組中管理來賓存取](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="11d80-164">If guest users need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="11d80-165">一旦訪客使用者可被發現，您就可以[定義資訊屏障原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="11d80-165">Once guest users are discoverable, you can [define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="11d80-166">原則變更對現有聊天有何影響</span><span class="sxs-lookup"><span data-stu-id="11d80-166">How policy changes impact existing chats</span></span>

<span data-ttu-id="11d80-167">當資訊屏障原則管理員對原則進行變更，或由於使用者的設定檔變更（例如作業變更或類似的原因），資訊屏障原則評估服務會自動搜尋成員，以確保小組成員不會違反任何原則的情況。</span><span class="sxs-lookup"><span data-stu-id="11d80-167">When the information barrier policy administrator makes changes to a policy, or a policy change kicks into effect because of a change to a user's profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="11d80-168">如果使用者之間已有聊天或其他通訊，且已設定新的原則，或是已變更現有的原則，此服務會評估現有的通訊，以確保仍允許進行通訊。</span><span class="sxs-lookup"><span data-stu-id="11d80-168">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="11d80-169">**1:1 聊天**-如果已不再允許兩個使用者之間的通訊（如果原則封鎖通訊已套用至一或兩個使用者），系統會封鎖進一步通訊，聊天交談就會變成隻讀狀態。</span><span class="sxs-lookup"><span data-stu-id="11d80-169">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span> 

    <span data-ttu-id="11d80-170">以下是顯示 [聊天] 的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-170">Here's an example that shows the chat is visible.</span></span>

    ![螢幕擷取畫面顯示 [使用者聊天] 可供使用](media/ib-before-1-1chat-policy.png)

    <span data-ttu-id="11d80-172">以下範例顯示 [聊天] 已停用。</span><span class="sxs-lookup"><span data-stu-id="11d80-172">Here's an example that shows the chat is disabled.</span></span>

    ![顯示已停用使用者聊天的螢幕擷取畫面](media/ib-after-1-1chat-policy.png)

- <span data-ttu-id="11d80-174">**群組聊天**-如果已不再允許來自某個使用者的通訊（例如，如果使用者變更了工作），則該使用者與違反該原則的其他使用者都可能會從群組聊天中移除，且不允許進一步與群組通訊。</span><span class="sxs-lookup"><span data-stu-id="11d80-174">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="11d80-175">使用者仍然可以看到舊的交談（這會是唯讀的），但無法看到或參與與群組的任何新交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-175">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="11d80-176">如果新的或已變更的原則將通訊套用到多個使用者，則受該原則影響的使用者可能會從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="11d80-176">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="11d80-177">他們仍能看到舊的交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-177">They can still see old conversations.</span></span>

<span data-ttu-id="11d80-178">在這個範例中，Enrico 移至組織內的不同部門，並從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="11d80-178">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job.png)

<span data-ttu-id="11d80-180">Enrico 無法再傳送訊息到群組聊天。</span><span class="sxs-lookup"><span data-stu-id="11d80-180">Enrico can no longer send messages to the group chat.</span></span>

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="11d80-182">**小組**-已從群組中移除的任何使用者都會從小組中移除，而且將無法查看或參與現有或新的交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-182">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="11d80-183">案例：現有聊天中的使用者遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="11d80-183">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="11d80-184">目前，如果資訊屏障原則封鎖其他使用者，使用者就會遇到下列問題：</span><span class="sxs-lookup"><span data-stu-id="11d80-184">Currently, users experience the following if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="11d80-185">[**人員]** 索引標籤-使用者無法在 [**人員**] 索引標籤上看到封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="11d80-185">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="11d80-186">**人員選擇器**-在 [人員選擇器] 中不會顯示封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="11d80-186">**People Picker** - Blocked users will not be visible in the people picker.</span></span>

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="11d80-188">[**活動]** 索引標籤-如果使用者要造訪封鎖使用者的 [**活動**] 索引標籤，就不會顯示任何文章。</span><span class="sxs-lookup"><span data-stu-id="11d80-188">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="11d80-189">（[**活動**] 索引標籤只會顯示頻道發佈，而在兩個使用者之間則不會有任何常見頻道。）</span><span class="sxs-lookup"><span data-stu-id="11d80-189">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="11d80-190">以下是已封鎖之 [活動] 索引標籤視圖的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-190">Here's an example of the activity tab view that is blocked.</span></span>

    ![顯示已封鎖 [活動] 索引標籤的螢幕擷取畫面](media/ib-after-activity-tab-policy.png)


- <span data-ttu-id="11d80-192">**組織**結構-如果使用者存取的組織結構中出現封鎖的使用者，則封鎖的使用者不會出現在組織結構上，而是會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="11d80-192">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user will not appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="11d80-193">**連絡人卡片**-如果使用者參與交談，且隨後遭到封鎖，當使用者將游標移到封鎖的使用者名稱上時，其他使用者就會看到錯誤訊息，而不是連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="11d80-193">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="11d80-194">在卡片上所列的動作（例如 [通話與聊天]）將無法使用。</span><span class="sxs-lookup"><span data-stu-id="11d80-194">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="11d80-195">[**建議的連絡人**]：封鎖的使用者不會出現在 [建議的連絡人] 清單中（針對新使用者顯示的初始連絡人清單）。</span><span class="sxs-lookup"><span data-stu-id="11d80-195">**Suggested contacts** - Blocked users do not appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="11d80-196">[**聊天連絡人**]-使用者可以在聊天連絡人清單中看到封鎖的使用者，但會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。</span><span class="sxs-lookup"><span data-stu-id="11d80-196">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span> <span data-ttu-id="11d80-197">使用者也可以按一下他們來查看其過去的交談。</span><span class="sxs-lookup"><span data-stu-id="11d80-197">The user can also click on them to view their past conversation.</span></span>
- <span data-ttu-id="11d80-198">[**通話連絡人**]-使用者可以在通話連絡人清單中看到封鎖的使用者，但系統會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。</span><span class="sxs-lookup"><span data-stu-id="11d80-198">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>

    <span data-ttu-id="11d80-199">以下是通話連絡人清單中封鎖使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-199">Here's an example of a blocked user in the calls contact list.</span></span>

    ![螢幕擷取畫面顯示使用者使用者聊天](media/ib-before-chat-contacts-policy.png)

    <span data-ttu-id="11d80-201">以下是針對 [通話內容] 清單中的使用者停用聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="11d80-201">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    ![螢幕擷取畫面顯示使用者已從聊天中封鎖](media/ib-after-chat-contacts-policy.png)

- <span data-ttu-id="11d80-203">**Skype 至團隊遷移**-在商務用 skype 中進行團隊遷移期間，所有使用者（即使是資訊屏障原則所封鎖），都會將它遷移至小組，然後將按照上述步驟進行處理。</span><span class="sxs-lookup"><span data-stu-id="11d80-203">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="11d80-204">團隊原則與 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="11d80-204">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="11d80-205">建立小組後，SharePoint 網站就會提供給小組，並與 [檔案體驗] 相關聯。</span><span class="sxs-lookup"><span data-stu-id="11d80-205">When a team is created, a SharePoint site is provisioned and associated with the Team for the files experience.</span></span> <span data-ttu-id="11d80-206">此 SharePoint 網站和檔案的存取權會採用組織的 IB，亦即，只有其針對每個 IB 原則的 IB 區段相符的使用者才能存取。</span><span class="sxs-lookup"><span data-stu-id="11d80-206">Access to this SharePoint site and files honors the organization's IB, i.e., only the users whose IB segment matches per IB policy are allowed access.</span></span> <span data-ttu-id="11d80-207">即使在檔案共用時，IB 原則也會生效。</span><span class="sxs-lookup"><span data-stu-id="11d80-207">Even at the time of file sharing, the IB policy is honored.</span></span>

<span data-ttu-id="11d80-208">例如：在 Contoso 銀行公司中，使用者「Sesha@contosobank.onmicrosoft.com」屬於投資銀行區段，而使用者 ' Nikita@contosobank.onmicrosoft.com ' 屬於區段建議。</span><span class="sxs-lookup"><span data-stu-id="11d80-208">For example: In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to segment Advisory.</span></span> <span data-ttu-id="11d80-209">組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="11d80-209">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="11d80-210">當使用者 Sesha 建立投資銀行區段的小組時，只有投資銀行區段使用者才能存取該小組和支援該小組的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="11d80-210">When user Sesha creates a team for Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking segment users.</span></span> <span data-ttu-id="11d80-211">即使她擁有 [網站] 連結，使用者 Nikita 還是無法存取該網站。</span><span class="sxs-lookup"><span data-stu-id="11d80-211">User Nikita can't access that site even if she has the site link.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="11d80-212">所需的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="11d80-212">Required licenses and permissions</span></span>

<span data-ttu-id="11d80-213">如需詳細資訊（包括方案和定價），請參閱[授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="11d80-213">For more details, including plans and pricing, see [Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="more-information"></a><span data-ttu-id="11d80-214">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="11d80-214">More information</span></span>

- <span data-ttu-id="11d80-215">若要深入瞭解資訊障礙，請參閱[資訊障礙](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="11d80-215">To learn more about information barriers, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="11d80-216">若要設定資訊屏障原則，請參閱[定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="11d80-216">To set up information barrier policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="11d80-217">若要編輯或移除資訊屏障原則，請參閱[編輯（或移除）資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="11d80-217">To edit or remove information barrier policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>
