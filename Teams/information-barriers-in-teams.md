---
title: Microsoft Teams 的資訊障礙
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
description: 本文將說明 Microsoft Teams 中哪些是資訊障礙，以及這些障礙如何影響 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94e0117e1f0956d8e3e9ae8e6bafc7feabcdf237
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196457"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="27020-103">Microsoft Teams 的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="27020-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="27020-104">IB (資訊) 是系統管理員可設定防止個人或群組彼此通訊的政策。</span><span class="sxs-lookup"><span data-stu-id="27020-104">Information barriers (IBs) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="27020-105">例如，如果有一個部門處理不應與其他部門共用的資訊，則 IB 非常有用。</span><span class="sxs-lookup"><span data-stu-id="27020-105">IBs are useful if, for example, one department is handling information that shouldn't be shared with other departments.</span></span> <span data-ttu-id="27020-106">當群組需要被隔離或無法與群組外部的任何人通訊時，IB 也很有用。</span><span class="sxs-lookup"><span data-stu-id="27020-106">IBs are also useful when a group needs to be isolated or prevented from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="27020-107">無法跨 (建立) IB 群組的資訊障礙。</span><span class="sxs-lookup"><span data-stu-id="27020-107">Information barrier (IB) groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="27020-108">版本 1 不支援使用 Bot、Azure Active Directory (Azure AD) 應用程式，以及一些新增使用者的 API。</span><span class="sxs-lookup"><span data-stu-id="27020-108">Using bots, Azure Active Directory (Azure AD) apps, and some APIs to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="27020-109">私人頻道符合您設定之 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-109">Private channels are compliant to IB policies that you configure.</span></span>
> - <span data-ttu-id="27020-110">新增：有關連結至 Teams 之 SharePoint 網站之障礙的支援相關資訊，請參閱 [與 Microsoft Teams 網站相關聯的區段](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="27020-110">New: For information about support for barriers for SharePoint sites that are connected to Teams, see [Segments associated with Microsoft Teams sites](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="27020-111">IB 政策也會防止查詢和探索。</span><span class="sxs-lookup"><span data-stu-id="27020-111">IB policies also prevent lookups and discovery.</span></span> <span data-ttu-id="27020-112">如果您嘗試與不應通訊的人通訊，您就不會在人員選擇器中找到該使用者。</span><span class="sxs-lookup"><span data-stu-id="27020-112">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="27020-113">背景</span><span class="sxs-lookup"><span data-stu-id="27020-113">Background</span></span>

<span data-ttu-id="27020-114">IB 的主要推動者來自金融服務產業。</span><span class="sxs-lookup"><span data-stu-id="27020-114">The primary driver for IBs comes from the financial services industry.</span></span> <span data-ttu-id="27020-115">金融產業監管局 ([FINRA]( https://www.finra.org)) 會審查成員企業內部的 IB 和興趣衝突，並提供管理這類衝突的指引 (FINRA 2241，《一併研究法規聲明[15-31。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)</span><span class="sxs-lookup"><span data-stu-id="27020-115">The Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) reviews IBs and conflicts of interest within member firms and provides guidance about managing such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>


<span data-ttu-id="27020-116">不過，自推出 IB 之後，許多其他區域也發現這些十分實用。</span><span class="sxs-lookup"><span data-stu-id="27020-116">However, since introducing IBs, many other areas have found them to be useful.</span></span> <span data-ttu-id="27020-117">其他常見案例包括：</span><span class="sxs-lookup"><span data-stu-id="27020-117">Other common scenarios include:</span></span>

- <span data-ttu-id="27020-118">教育：某學校的學生無法查看其他學校學生的連絡人詳細資料。</span><span class="sxs-lookup"><span data-stu-id="27020-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>

- <span data-ttu-id="27020-119">法律：維護某位客戶之律師所取得資料的機密性，並防止代表不同客戶之同一家公司的律師存取。</span><span class="sxs-lookup"><span data-stu-id="27020-119">Legal: Maintaining the confidentiality of data that is obtained by the lawyer of one client and preventing it from being accessed by a lawyer for the same firm who represents a different client.</span></span>

- <span data-ttu-id="27020-120">政府：資訊存取與控制在部門和群組之間受到限制。</span><span class="sxs-lookup"><span data-stu-id="27020-120">Government: Information access and control are limited across departments and groups.</span></span>

- <span data-ttu-id="27020-121">專業服務：公司中的一組人員只能在客戶互動期間透過來賓存取與客戶或特定客戶聊天。</span><span class="sxs-lookup"><span data-stu-id="27020-121">Professional services: A group of people in a company is only able to chat with a client or a specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="27020-122">例如，Enrico 屬於 Banking 區段，而 P一文屬於財務顧問區段。</span><span class="sxs-lookup"><span data-stu-id="27020-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="27020-123">由於組織的IB 政策會阻止這兩個區段之間的通訊和共同合作，因此 Enrico 和 P最音節無法彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="27020-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="27020-124">不過，Enrico 和 P在 HR 中可以與 Lee 通訊。</span><span class="sxs-lookup"><span data-stu-id="27020-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![顯示資訊障礙防止區段之間通訊的範例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="27020-126">何時使用資訊障礙</span><span class="sxs-lookup"><span data-stu-id="27020-126">When to use information barriers</span></span>

<span data-ttu-id="27020-127">您可能會想要在如下所示的情況下使用 IB：</span><span class="sxs-lookup"><span data-stu-id="27020-127">You might want to use IBs in situations like these:</span></span>

- <span data-ttu-id="27020-128">必須禁止團隊與特定的其他小組通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="27020-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="27020-129">團隊不得與團隊外部的任何人通訊或共用資料。</span><span class="sxs-lookup"><span data-stu-id="27020-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="27020-130">資訊障礙政策評估服務會判斷通訊是否符合 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with IB policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="27020-131">管理資訊障礙政策</span><span class="sxs-lookup"><span data-stu-id="27020-131">Managing information barrier policies</span></span>

<span data-ttu-id="27020-132">在 Microsoft 365 合規性中心使用 PowerShell Cmdlet (SCC) 管理 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-132">IB policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="27020-133">詳細資訊請參閱定義 [資訊障礙的政策](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="27020-133">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27020-134">在設定或定義策略之前，您必須在 Microsoft Teams 中啟用範圍目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="27020-134">Before you set up or define policies, you must enable scoped directory search in Microsoft Teams.</span></span> <span data-ttu-id="27020-135">在啟用範圍目錄搜尋後，請等候至少幾個小時，再設定或定義資訊障礙的政策。</span><span class="sxs-lookup"><span data-stu-id="27020-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="27020-136">詳細資訊請參閱定義 [資訊障礙策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="27020-136">For more information, see [Define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="27020-137">資訊障礙系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="27020-137">Information barriers administrator role</span></span>

<span data-ttu-id="27020-138">IB 合規性管理角色負責管理 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-138">The IB Compliance Management role is responsible for managing IB policies.</span></span> <span data-ttu-id="27020-139">有關此角色的資訊，請參閱 [Microsoft 365 合規性中心的許可權](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="27020-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="27020-140">資訊障礙觸發因素</span><span class="sxs-lookup"><span data-stu-id="27020-140">Information barrier triggers</span></span>

<span data-ttu-id="27020-141">當下列 Teams 活動進行時，會啟用 IB 政策：</span><span class="sxs-lookup"><span data-stu-id="27020-141">IB policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="27020-142">**成員會新增到** 團隊 - 每當您將使用者新增到團隊時，使用者政策都必須根據其他小組成員的 IB 政策進行評估。</span><span class="sxs-lookup"><span data-stu-id="27020-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the IB policies of other team members.</span></span> <span data-ttu-id="27020-143">成功新增使用者之後，使用者可以在團隊中執行所有功能，無需進一步檢查。</span><span class="sxs-lookup"><span data-stu-id="27020-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="27020-144">如果使用者的群組原則阻止他們加入團隊，使用者就不會顯示在搜尋中。</span><span class="sxs-lookup"><span data-stu-id="27020-144">If the user's policy blocks them from being added to the team, the user won't show up in search.</span></span>

    ![搜尋新進成員以新加入團隊並尋找任何比對結果的螢幕擷取畫面](media/information-barriers-add-members.png)

- <span data-ttu-id="27020-146">**系統要求** 新的聊天 - 每次使用者要求與一或多個其他使用者進行新聊天時，會評估該聊天，以確保該聊天未違反任何 IB 原則。</span><span class="sxs-lookup"><span data-stu-id="27020-146">**A new chat is requested** - Each time that a user requests a new chat with one or more other users, the chat is evaluated to make sure that it isn't violating any IB policies.</span></span> <span data-ttu-id="27020-147">如果交談違反IB 原則，則交談不會開始。</span><span class="sxs-lookup"><span data-stu-id="27020-147">If the conversation violates an IB policy, then the conversation isn't started.</span></span>

    <span data-ttu-id="27020-148">以下是一對一聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-148">Here's an example of a 1:1 chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-149">![螢幕擷取畫面顯示 1 對 1 聊天中封鎖的通訊](media/information-barriers-one-one-chat.png)</span><span class="sxs-lookup"><span data-stu-id="27020-149">![Screenshot showing blocked communication in 1:1 chat](media/information-barriers-one-one-chat.png)</span></span>

    <span data-ttu-id="27020-150">以下是群組聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-150">Here's an example of a group chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-151">![顯示群組聊天的螢幕擷取畫面](media/information-barriers-group-chat.png)</span><span class="sxs-lookup"><span data-stu-id="27020-151">![Screenshot showing group chat](media/information-barriers-group-chat.png)</span></span>

- <span data-ttu-id="27020-152">**使用者受邀** 加入會議 - 當使用者受邀加入會議時，會根據適用于其他小組成員的 IB 原則評估適用于該使用者的 IB 原則。</span><span class="sxs-lookup"><span data-stu-id="27020-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the IB policy that applies to the user is evaluated against the IB policies that apply to the other team members.</span></span> <span data-ttu-id="27020-153">如果違規，則不允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-153">If there's a violation, the user won't be allowed to join the meeting.</span></span>

    ![螢幕擷取畫面顯示使用者已封鎖會議](media/information-barriers-meeting.png)

- <span data-ttu-id="27020-155">**畫面是在兩個或多個** 使用者之間共用 - 當使用者與其他使用者共用螢幕時，必須評估共用，以確保不會違反其他使用者的 IB 原則。</span><span class="sxs-lookup"><span data-stu-id="27020-155">**A screen is shared between two or more users** - When a user shares a screen with other users, the sharing must be evaluated to make sure that it doesn't violate the IB policies of other users.</span></span> <span data-ttu-id="27020-156">如果違反 IB 原則，則不允許螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="27020-156">If an IB policy is violated, the screen share won't be allowed.</span></span> 
 
    <span data-ttu-id="27020-157">以下是在原則適用之前螢幕畫面分享的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-157">Here's an example of screen share before the policy is applied.</span></span> 

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-158">![顯示使用者聊天的螢幕擷取畫面](media/ib-before-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-158">![Screenshot showing a user chat](media/ib-before-screen-share-policy.png)</span></span>

    <span data-ttu-id="27020-159">以下是原則適用後螢幕畫面分享的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-159">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="27020-160">螢幕畫面分享和通話圖示不會顯示。</span><span class="sxs-lookup"><span data-stu-id="27020-160">The screen share and call icons aren't visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-161">![螢幕擷取畫面顯示使用者 char 和封鎖的設定](media/ib-after-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-161">![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)</span></span>

- <span data-ttu-id="27020-162">使用者在 **Teams** 中撥打電話 - 每當使用者透過 VOIP) 啟動語音通話 (給另一個使用者或使用者群組時，會評估該通話，以確保不會違反其他小組成員的 IB 原則。</span><span class="sxs-lookup"><span data-stu-id="27020-162">**A user places a phone call in Teams** - Whenever a user initiates a voice call (via VOIP) to another user or group of users, the call is evaluated to make sure that it doesn't violate the IB policies of other team members.</span></span> <span data-ttu-id="27020-163">如果有任何違規，語音通話會封鎖。</span><span class="sxs-lookup"><span data-stu-id="27020-163">If there's any violation, the voice call is blocked.</span></span>

- <span data-ttu-id="27020-164">**Teams 中的來賓** - IB 原則也適用于 Teams 中的來賓。</span><span class="sxs-lookup"><span data-stu-id="27020-164">**Guests in Teams** - IB policies apply to guests in Teams, too.</span></span> <span data-ttu-id="27020-165">如果貴組織的全域通訊清單中需要可探索來賓，請參閱 [管理 Microsoft 365 群組中的來賓存取權](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="27020-165">If guests need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="27020-166">一旦來賓可找到，您可以 [定義 IB 政策](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="27020-166">Once guests are discoverable, you can [define IB policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="27020-167">變更政策對現有聊天的影響</span><span class="sxs-lookup"><span data-stu-id="27020-167">How policy changes impact existing chats</span></span>

<span data-ttu-id="27020-168">當IB 原則管理員變更原則，或因使用者個人檔案變更而啟用原則變更 (例如工作變更) 時，資訊障礙原則評估服務會自動搜尋成員，以確保他們在團隊中的成員資格不會違反任何原則。</span><span class="sxs-lookup"><span data-stu-id="27020-168">When the IB policy administrator makes changes to a policy, or when a policy change is activated because of a change to a user's profile (such as for a job change), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that their membership in the team doesn't violate any policies.</span></span>

<span data-ttu-id="27020-169">如果使用者之間有現有的聊天或其他通訊，而且已設定新的策略或變更現有的策略，服務會評估現有的通訊，以確保仍然允許通訊發生。</span><span class="sxs-lookup"><span data-stu-id="27020-169">If there's an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="27020-170">**1：1** 聊天 - 如果因為對封鎖通訊 (一或兩個使用者使用封鎖通訊之政策，不再允許兩個使用者之間的通訊) ，進一步的通訊會封鎖。</span><span class="sxs-lookup"><span data-stu-id="27020-170">**1:1 chat** - If communication between two users is no longer allowed (because of application to one or both users of a policy that blocks communication), further communication is blocked.</span></span> <span data-ttu-id="27020-171">他們現有的聊天交談會變成隻讀。</span><span class="sxs-lookup"><span data-stu-id="27020-171">Their existing chat conversations become read-only.</span></span> 

    <span data-ttu-id="27020-172">以下是顯示顯示聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-172">Here's an example that shows the chat is visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-173">![顯示使用者聊天可用的螢幕擷取畫面](media/ib-before-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-173">![Screenshot showing user chat is available](media/ib-before-1-1chat-policy.png)</span></span>

    <span data-ttu-id="27020-174">以下是顯示聊天已停用的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-174">Here's an example that shows the chat is disabled.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-175">![顯示已停用使用者聊天的螢幕擷取畫面](media/ib-after-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-175">![Screenshot showing user chat is disabled](media/ib-after-1-1chat-policy.png)</span></span>

- <span data-ttu-id="27020-176">群組聊天 **-** 如果不再允許從一個使用者與群組進行通訊 (例如，因為使用者變更了工作) ，則使用者與參與違反原則的其他使用者可能會從群組聊天中移除，且無法與群組進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="27020-176">**Group chat** - If communication from one user to a group is no longer allowed (for example, because a user changed jobs), the user—along with the other users whose participation violates the policy—may be removed from group chat, and further communication with the group won't be allowed.</span></span> <span data-ttu-id="27020-177">使用者仍然可以看到舊的交談，但無法看到或參與與群組的任何新交談。</span><span class="sxs-lookup"><span data-stu-id="27020-177">The user can still see old conversations, but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="27020-178">如果防止通訊的新原則或變更原則已適用于多個使用者，則受原則影響的使用者可能會從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="27020-178">If the new or changed policy that prevents communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="27020-179">他們還是可以看到舊的交談。</span><span class="sxs-lookup"><span data-stu-id="27020-179">They can still see old conversations.</span></span>

  <span data-ttu-id="27020-180">在此範例中，Enrico 移至組織內部的不同部門，並已從群組聊天中移除。</span><span class="sxs-lookup"><span data-stu-id="27020-180">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![已移除使用者的群組聊天螢幕擷取畫面](media/information-barriers-user-changes-job.png)

  <span data-ttu-id="27020-182">Enrico 無法再傳送訊息至群組聊天。</span><span class="sxs-lookup"><span data-stu-id="27020-182">Enrico can no longer send messages to the group chat.</span></span>

  ![由於使用者已從群組中移除，因此無法傳送訊息至群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="27020-184">**團隊** - 已從群組中移除的任何使用者，會從團隊中移除，且無法查看或參與現有或新的交談。</span><span class="sxs-lookup"><span data-stu-id="27020-184">**Team** - Any users who have been removed from the group are removed from the team and won't be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="27020-185">案例：現有聊天中的使用者被封鎖</span><span class="sxs-lookup"><span data-stu-id="27020-185">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="27020-186">目前，如果 IB 政策會阻止其他使用者，使用者會遇到下列情況：</span><span class="sxs-lookup"><span data-stu-id="27020-186">Currently, users experience the following scenarios if an IB policy blocks another user:</span></span>

- <span data-ttu-id="27020-187">**人員 Tab** - 使用者在人員選項卡上看不到 **封鎖的使用者。**</span><span class="sxs-lookup"><span data-stu-id="27020-187">**People tab** - A user can't see blocked users on the **People** tab.</span></span>

- <span data-ttu-id="27020-188">**人員選擇** 器 - 封鎖的使用者不會顯示在人員選擇器中。</span><span class="sxs-lookup"><span data-stu-id="27020-188">**People Picker** - Blocked users won't be visible in the people picker.</span></span>

    ![Teams 的螢幕擷取畫面，提醒使用者該政策禁止顯示其他使用者的資訊](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="27020-190">**活動製表** 位 - 如果使用者前往封鎖使用者的活動選項卡，系統不會顯示任何文章。</span><span class="sxs-lookup"><span data-stu-id="27020-190">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="27020-191"> (**活動選項卡** 只會顯示頻道文章，而且兩個使用者之間沒有常見的頻道。) </span><span class="sxs-lookup"><span data-stu-id="27020-191">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="27020-192">以下是封鎖的活動選項卡視圖範例。</span><span class="sxs-lookup"><span data-stu-id="27020-192">Here's an example of the activity tab view that is blocked.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-193">![顯示已封鎖的活動選項卡的螢幕擷取畫面](media/ib-after-activity-tab-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-193">![Screenshot showing the activity tab that is blocked](media/ib-after-activity-tab-policy.png)</span></span>


- <span data-ttu-id="27020-194">**組織結構** - 如果使用者存取出現封鎖使用者的組織結構，則封鎖的使用者不會出現在組織結構上。</span><span class="sxs-lookup"><span data-stu-id="27020-194">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart.</span></span> <span data-ttu-id="27020-195">而是會出現錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="27020-195">Instead, an error message will appear.</span></span>

- <span data-ttu-id="27020-196">**人員** 卡片 - 如果使用者參與交談，但使用者稍後被封鎖，當其他使用者將游標停留在封鎖的使用者名稱上時，會看到錯誤訊息，而不是人員卡片。</span><span class="sxs-lookup"><span data-stu-id="27020-196">**People card** - If a user participates in a conversation and the user is later blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="27020-197">卡片上所列的動作 (例如通話和聊天) 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="27020-197">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>

- <span data-ttu-id="27020-198">**建議的連絡人** - 被封鎖的使用者不會出現在建議連絡人清單 (新使用者顯示的初始連絡人清單中) 。</span><span class="sxs-lookup"><span data-stu-id="27020-198">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>

- <span data-ttu-id="27020-199">**聊天連絡人** - 使用者可以在聊天連絡人清單上看到封鎖的使用者，但系統將會識別封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="27020-199">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="27020-200">使用者可以對封鎖的使用者執行的唯一動作是刪除他們。</span><span class="sxs-lookup"><span data-stu-id="27020-200">The only action that the user can perform on the blocked users is to delete them.</span></span> <span data-ttu-id="27020-201">使用者也可以按一下他們來查看過去的交談。</span><span class="sxs-lookup"><span data-stu-id="27020-201">The user can also click on them to view their past conversation.</span></span>

- <span data-ttu-id="27020-202">**通話連絡人** - 使用者可以在通話連絡人清單上看到封鎖的使用者，但系統將會識別封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="27020-202">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="27020-203">使用者可以在封鎖使用者上執行的唯一動作是刪除他們。</span><span class="sxs-lookup"><span data-stu-id="27020-203">The only action that the user can perform on the block users is to delete them.</span></span>

    <span data-ttu-id="27020-204">以下是通話連絡人清單中封鎖使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-204">Here's an example of a blocked user in the calls contact list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-205">![顯示使用者使用者聊天的螢幕擷取畫面](media/ib-before-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-205">![Screenshot showing user user chat](media/ib-before-chat-contacts-policy.png)</span></span>

    <span data-ttu-id="27020-206">以下是針對通話內容清單使用者停用聊天的範例。</span><span class="sxs-lookup"><span data-stu-id="27020-206">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27020-207">![顯示使用者已封鎖聊天的螢幕擷取畫面](media/ib-after-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="27020-207">![Screenshot showing user blocked from chat](media/ib-after-chat-contacts-policy.png)</span></span>

- <span data-ttu-id="27020-208">**Skype 到 Teams** 移移 - 在從商務用 Skype 移至 Teams 期間，所有使用者 ，甚至是受到 IB 政策封鎖的使用者，都會移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="27020-208">**Skype to Teams migration** - During a migration from Skype for Business to Teams, all users—even those users who are blocked by IB policies—will be migrated to Teams.</span></span> <span data-ttu-id="27020-209">然後按照上述步驟處理這些使用者。</span><span class="sxs-lookup"><span data-stu-id="27020-209">Those users are then handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="27020-210">Teams 策略和 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="27020-210">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="27020-211">建立團隊時，會針對檔案體驗來設定 SharePoint 網站，並與 Microsoft Teams 建立關聯。</span><span class="sxs-lookup"><span data-stu-id="27020-211">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="27020-212">根據預設，此 SharePoint 網站和檔案中不會遵守 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-212">IB policies aren't honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="27020-213">若要啟用 IB 政策，系統管理員已填寫表單，要求在 SharePoint 和 OneDrive 上啟用 IB (請參閱資訊障礙中[先決條件) 。 [](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="27020-213">To enable IB policies, the administrator has already filled out a form, requesting that IB policies be enabled on SharePoint and OneDrive (see the *Prerequisites* section in [Information barriers](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)).</span></span> <span data-ttu-id="27020-214">如果在 SharePoint 和 OneDrive 中開啟了 IB 政策，則當使用 Microsoft Teams 建立團隊時，在 SharePoint 網站上就會使用 IB 政策。</span><span class="sxs-lookup"><span data-stu-id="27020-214">If the IB policy is turned on in SharePoint and OneDrive, then the IB policies will work on SharePoint sites that are provisioned when a team is created with Microsoft Teams.</span></span>

<span data-ttu-id="27020-215">小組 **SharePoint** 網站上之 IB 政策範例：在 Contoso Bank corporation 中，使用者的 Sesha@contosobank.onmicrosoft.com' 屬於 Investment Banking 區段，而使用者的 Nikita@contosobank.onmicrosoft.com' 則屬於顧問區段。</span><span class="sxs-lookup"><span data-stu-id="27020-215">**Example of IB policies on SharePoint site of a team**: In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to the Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to the Advisory segment.</span></span> <span data-ttu-id="27020-216">組織的IB 政策會阻止這兩個區段之間的通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="27020-216">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="27020-217">當使用者 Sesha 為 Investment Banking 區段建立團隊時，只有 Investment Banking 使用者才能使用支援小組的小組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="27020-217">When user Sesha creates a team for the Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking users.</span></span> <span data-ttu-id="27020-218">即使使用者 Nik分有網站連結，她也無法存取該網站。</span><span class="sxs-lookup"><span data-stu-id="27020-218">User Nikita can't access that site even if she has the site link.</span></span>

<span data-ttu-id="27020-219">詳細資訊請參閱使用 [SharePoint 的資訊障礙](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="27020-219">For more information, see [Use information barriers with SharePoint](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="27020-220">必要的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="27020-220">Required licenses and permissions</span></span>

<span data-ttu-id="27020-221">有關授權和許可權的詳細資訊 ，包括方案與價格，請參閱 [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全性與合規性&指南。</span><span class="sxs-lookup"><span data-stu-id="27020-221">For more information on licenses and permissions, including plans and pricing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="27020-222">已知問題</span><span class="sxs-lookup"><span data-stu-id="27020-222">Known Issues</span></span>
- <span data-ttu-id="27020-223">**使用者無法** 加入臨時會議：如果啟用 IB 政策，如果會議名冊的大小大於會議出席限制，使用者即無法加入 [會議](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="27020-223">**Users can't join ad-hoc meetings**: If IB policies are enabled, users aren't allowed to join meetings if the size of the meeting roster is greater than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="27020-224">其根本原因是，IB 檢查取決於是否可以將使用者新增到會議聊天名單，而且只有當使用者可以加入名冊時，他們才能加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-224">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="27020-225">加入會議的使用者一旦將該使用者加入名冊;如此一來，名冊就可以快速填入。</span><span class="sxs-lookup"><span data-stu-id="27020-225">A user joining a meeting once adds that user to the roster; hence for recurring meetings, the roster can fill up fast.</span></span> <span data-ttu-id="27020-226">一旦聊天名冊到達 [會議出席](limits-specifications-teams.md)限制，即不允許將其他使用者新加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-226">Once the chat roster reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting.</span></span> <span data-ttu-id="27020-227">如果租使用者已啟用 IB 且聊天名冊已滿，則新使用者 (那些不在名冊上的使用者) 不得加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-227">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those users who aren't already on the roster) aren't allowed to join the meeting.</span></span> <span data-ttu-id="27020-228">但如果租使用者未啟用IB，且會議聊天名冊已滿，新使用者 (那些尚未加入名冊) 的使用者可以加入會議，雖然他們不會在會議看到聊天選項。</span><span class="sxs-lookup"><span data-stu-id="27020-228">But if IB isn't enabled for the tenant and the meeting chat roster is full, new users (those users who aren't already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="27020-229">短期解決方案是從會議聊天名單中移除非使用中成員，以讓新使用者有空間。</span><span class="sxs-lookup"><span data-stu-id="27020-229">A short-term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="27020-230">不過，我們日後將會增加會議聊天名冊的大小。</span><span class="sxs-lookup"><span data-stu-id="27020-230">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>

- <span data-ttu-id="27020-231">**使用者無法加入頻道會議**：如果已啟用 IB 政策，如果使用者不是團隊的成員，則不允許他們加入頻道會議。</span><span class="sxs-lookup"><span data-stu-id="27020-231">**Users can't join channel meetings**: If IB policies are enabled, users aren't allowed to join channel meetings if they're not a member of the team.</span></span> <span data-ttu-id="27020-232">其根本原因是，IB 檢查取決於是否可以將使用者新增到會議聊天名單，而且只有當使用者可以加入名冊時，他們才能加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-232">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="27020-233">頻道會議中的聊天對話僅適用于團隊/頻道成員，非成員無法查看或存取聊天對話。</span><span class="sxs-lookup"><span data-stu-id="27020-233">The chat thread in a channel meeting is available to Team/Channel members only, and non-members can't see or access the chat thread.</span></span> <span data-ttu-id="27020-234">如果租使用者已啟用 IB，且非團隊成員嘗試加入頻道會議，則不允許該使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="27020-234">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, that user isn't allowed to join the meeting.</span></span> <span data-ttu-id="27020-235">不過，如果租使用者未啟用 IB，且非團隊成員嘗試加入頻道會議，則允許使用者加入會議，但他們不會在會議看到聊天選項。</span><span class="sxs-lookup"><span data-stu-id="27020-235">However, if IB is _not_ enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting—but they won't see the chat option in the meeting.</span></span>

## <a name="more-information"></a><span data-ttu-id="27020-236">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="27020-236">More information</span></span>

- <span data-ttu-id="27020-237">若要深入瞭解 IB，請參閱 [資訊障礙](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="27020-237">To learn more about IBs, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="27020-238">若要設定IB 政策，請參閱 [定義資訊障礙的政策](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="27020-238">To set up IB policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="27020-239">若要編輯或移除IB 政策，請參閱編輯 ([或移除) 障礙政策](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="27020-239">To edit or remove IB policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>

## <a name="availability"></a><span data-ttu-id="27020-240">可用 性</span><span class="sxs-lookup"><span data-stu-id="27020-240">Availability</span></span>
- <span data-ttu-id="27020-241">此功能可在我們的公用雲端使用;我們已在 2021 年 1 月推出 GCC 雲端的資訊障礙。</span><span class="sxs-lookup"><span data-stu-id="27020-241">The feature is available in our public cloud; in January 2021, we rolled out Information Barriers in the GCC cloud.</span></span>
- <span data-ttu-id="27020-242">這項功能尚未在 GCCH 和 DOD 雲端中提供。</span><span class="sxs-lookup"><span data-stu-id="27020-242">The feature is not yet available in the GCCH and DOD clouds.</span></span>
