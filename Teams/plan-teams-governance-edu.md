---
title: 適用于 IT 專業人員的 microsoft 教育管理常見問題-Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 針對使用團隊之 Microsoft 教育小組之系統管理員的常見問題的解答。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f9429d49dfef7a21670c67bad96c9e26c993e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837433"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="67065-103">適用於系統管理員的 Microsoft 教育版控管常見問題集</span><span class="sxs-lookup"><span data-stu-id="67065-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="67065-104">請觀看下列會話，以深入瞭解 Microsoft 團隊中的管理： microsoft 團隊中的管理[、管理與生命週期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="67065-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="67065-105">如何控制小組建立？</span><span class="sxs-lookup"><span data-stu-id="67065-105">How do I control team creation?</span></span> <span data-ttu-id="67065-106">我擔心學生會建立不適當的小組。</span><span class="sxs-lookup"><span data-stu-id="67065-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="67065-107">若要避免不適當或誤導的名稱，或只是為了提供更多有關團隊命名方式的結構，您可以使用 Office 365 群組命名原則（目前在預覽中）：</span><span class="sxs-lookup"><span data-stu-id="67065-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Office 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="67065-108">**前置詞尾碼命名原則**您可以使用 [首碼] 或 [尾碼] 定義小組（群組）的命名慣例，例如**GRP_US_My Group_Engineering**]。</span><span class="sxs-lookup"><span data-stu-id="67065-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="67065-109">首碼和尾碼可以是固定字串或使用者屬性（例如 **[部門]**），根據建立小組的使用者，新增到名稱中。</span><span class="sxs-lookup"><span data-stu-id="67065-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who’s creating the team.</span></span>
-   <span data-ttu-id="67065-110">**自訂封鎖的單字**您可以上傳特定組織中的使用者在其建立的小組名稱中封鎖的一組字。</span><span class="sxs-lookup"><span data-stu-id="67065-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="67065-111">例如，您可以封鎖條款**CEO**、**工資**與**HR**在小組名稱中用於不適用的群組。</span><span class="sxs-lookup"><span data-stu-id="67065-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don’t apply to.</span></span>
-   <span data-ttu-id="67065-112">**分類**您可以建立組織中的使用者在建立 Office 365 群組時可以設定的分類。</span><span class="sxs-lookup"><span data-stu-id="67065-112">**Classification** You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="67065-113">使用 Office 365 群組命名原則時，必須具備 Azure Active Directory Premium P1 授權或 Azure AD 基本 EDU 授權，以提供一或多個 Office 365 群組成員的每個唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="67065-113">Using the Office 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="67065-114">如需詳細指示，請參閱[Office 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="67065-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="67065-115">如果您是使用來自另一個系統的輸入（例如學校資料同步處理）自動建立團隊，請確認輸入資料符合您所設定的命名原則;如果不是，小組建立就會失敗。</span><span class="sxs-lookup"><span data-stu-id="67065-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you’ve configured; if it doesn’t, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="67065-116">我可以看到誰建立了團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="67065-116">Can I see who created a team?</span></span>

<span data-ttu-id="67065-117">若要瞭解建立特定團隊的人員，請參閱在[[審核記錄] 中搜尋 Microsoft 團隊中的事件](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="67065-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="67065-118">我可以控制誰可以建立團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="67065-118">Can I control who can create teams?</span></span>

<span data-ttu-id="67065-119">一般來說，建議您不要從任何人都能建立小組。</span><span class="sxs-lookup"><span data-stu-id="67065-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="67065-120">如果每個人都能建立小組，就很可能會廣泛採用團隊。</span><span class="sxs-lookup"><span data-stu-id="67065-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="67065-121">教職員、教師或學生可以使用團隊來建立研究群組或特殊的興趣小組。</span><span class="sxs-lookup"><span data-stu-id="67065-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="67065-122">這將協助在教室內和外部接受團隊。</span><span class="sxs-lookup"><span data-stu-id="67065-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="67065-123">在我們的經驗中，使用者教育有助於確保責任團隊的使用。</span><span class="sxs-lookup"><span data-stu-id="67065-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="67065-124">只要使用者瞭解建立團隊不是匿名的，他們就能瞭解 carelessly 建立小組的意義，並傾向于 shy 離開工具。</span><span class="sxs-lookup"><span data-stu-id="67065-124">As soon as users understand that creating teams isn’t anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="67065-125">如果您確定要控制誰可以建立團隊，請參閱[管理可建立 Office 365 群組的人員](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="67065-125">If you’re sure you want to control who can create teams, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="67065-126">如何在學期或季開始時為每個課程自動建立小組？</span><span class="sxs-lookup"><span data-stu-id="67065-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="67065-127">在每個學期或季的開始，您需要有許多新團隊。</span><span class="sxs-lookup"><span data-stu-id="67065-127">At the start of each semester or quarter, you’ll need a number of new teams.</span></span> <span data-ttu-id="67065-128">您可以採取自動化方法來自動建立這些團隊、使用正確的使用者進行填充，並設定正確的許可權：</span><span class="sxs-lookup"><span data-stu-id="67065-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="67065-129">學校資料同步處理可建立適用于 Exchange Online 和 SharePoint Online 的 Office 365 群組、Microsoft 團隊的課程小組以及 OneNote 課程筆記本、學校用來進行教育的學校小組，以及 rostering 及單一登入（SSO）整合許多其他功能協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="67065-129">School Data Sync can create Office 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="67065-130">深入瞭解[學校資料同步處理的概覽](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="67065-130">Learn more at [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="67065-131">您可以使用 PowerShell 建立團隊和頻道，並自動設定設定。</span><span class="sxs-lookup"><span data-stu-id="67065-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="67065-132">如需詳細資訊，請參閱[Microsoft 團隊 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。</span><span class="sxs-lookup"><span data-stu-id="67065-132">See [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="67065-133">您可以使用 Microsoft Graph API （目前在 Beta 版）來建立、設定、克隆及封存小組。</span><span class="sxs-lookup"><span data-stu-id="67065-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="67065-134">如需詳細資訊，請參閱[使用 Microsoft GRAPH API 與 Microsoft 團隊共同作業](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。</span><span class="sxs-lookup"><span data-stu-id="67065-134">See [Use the Microsoft Graph API to work with Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="67065-135">學校資料同步處理會針對同步處理的每個類別建立 Office 365 群組，並[啟用隱藏的群組成員資格](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)，因此只有班級中的教師與學生才能看到該類別的成員。</span><span class="sxs-lookup"><span data-stu-id="67065-135">School Data Sync creates an Office 365 group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="67065-136">如果您使用不同的程式來建立班級群組，請使用新的-UnifiedGroup Cmdlet 的 HiddenGroupMembershipEnabled 參數，以符合相同的隱私權需求。</span><span class="sxs-lookup"><span data-stu-id="67065-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="67065-137">如何在學期或季結束時處理團隊？</span><span class="sxs-lookup"><span data-stu-id="67065-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="67065-138">我們建議您先思考，在學校學期或季結束時，您想要如何處理團隊資料：不論是要刪除，還是在學生完成課程後仍可供學生使用。</span><span class="sxs-lookup"><span data-stu-id="67065-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they’ve completed the course.</span></span> <span data-ttu-id="67065-139">您可能會想要保留學校行事曆，因此您設定的任何原則都不會與假日發生衝突。</span><span class="sxs-lookup"><span data-stu-id="67065-139">You’ll want to keep the school calendar in mind so any policies you set don’t conflict with holidays.</span></span> <span data-ttu-id="67065-140">您可以使用下列工具來實施您的戰略：</span><span class="sxs-lookup"><span data-stu-id="67065-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="67065-141">**保留原則：** 使用此功能刪除您指定之期限之前的所有資料，以確定舊資料已從聊天中移除（適用于所有或部分使用者）和頻道。</span><span class="sxs-lookup"><span data-stu-id="67065-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="67065-142">您也可以設定團隊保留內容，使其無法刪除。</span><span class="sxs-lookup"><span data-stu-id="67065-142">You can also configure Teams to retain content so it can’t be deleted.</span></span> <span data-ttu-id="67065-143">如需詳細資訊，請參閱[Microsoft 團隊的保留原則](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。</span><span class="sxs-lookup"><span data-stu-id="67065-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="67065-144">**到期原則：** 將團隊設定為在特定天數後到期。</span><span class="sxs-lookup"><span data-stu-id="67065-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="67065-145">到期前三十天之前，小組的所有擁有者都會收到通知，指出他們的小組需要更新，否則將會被刪除（即使系統管理員可以在30天內復原已刪除的小組）。</span><span class="sxs-lookup"><span data-stu-id="67065-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="67065-146">這個設定對確定未使用的團隊有 sunsetted 是非常實用的。</span><span class="sxs-lookup"><span data-stu-id="67065-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="67065-147">若要深入瞭解，請參閱[Office 365 群組過期原則](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。</span><span class="sxs-lookup"><span data-stu-id="67065-147">Learn more at [Office 365 Group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="67065-148">封存**團隊：** 此設定會將團隊放入唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="67065-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="67065-149">他們仍然可以流覽和搜尋，但沒有人可以新增任何新的文章。</span><span class="sxs-lookup"><span data-stu-id="67065-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="67065-150">封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)說明團隊擁有者如何封存團隊;小組擁有者也可以使用[圖形 API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)來封存或還原團隊。</span><span class="sxs-lookup"><span data-stu-id="67065-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="67065-151">使用 Office 365 群組過期原則，對於屬於一或多個 Office 365 群組的每個唯一使用者，都需要 Azure Active Directory Premium P1 授權。</span><span class="sxs-lookup"><span data-stu-id="67065-151">Using the Office 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="67065-152">在建立小組時，是否有供教職員成員使用的小組範本？</span><span class="sxs-lookup"><span data-stu-id="67065-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="67065-153">是。</span><span class="sxs-lookup"><span data-stu-id="67065-153">Yes.</span></span> <span data-ttu-id="67065-154">使用者可以在建立新的小組時，選取 [**從現有的範本建立小組**]，而團隊擁有者也可以使用[圖形 API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)從可用的範本建立新的小組。</span><span class="sxs-lookup"><span data-stu-id="67065-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="67065-155">我可以透過 PowerShell 或圖形自動執行哪些任務？</span><span class="sxs-lookup"><span data-stu-id="67065-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="67065-156">[Microsoft GRAPH API （Beta 版）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="67065-156">The [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) can do the following:</span></span>

-   <span data-ttu-id="67065-157">建立小組。</span><span class="sxs-lookup"><span data-stu-id="67065-157">Create a team.</span></span>
-   <span data-ttu-id="67065-158">新增成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="67065-158">Add members and owners.</span></span>
-   <span data-ttu-id="67065-159">新增頻道。</span><span class="sxs-lookup"><span data-stu-id="67065-159">Add channels.</span></span>
-   <span data-ttu-id="67065-160">新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="67065-160">Add apps.</span></span>
-   <span data-ttu-id="67065-161">您可以將現有的團隊克隆並取得索引標籤，以快捷方式執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="67065-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="67065-162">為使用者提供您剛建立之小組的連結。</span><span class="sxs-lookup"><span data-stu-id="67065-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="67065-163">當您不再需要成員、擁有者、頻道和應用程式時，可以將它們移除。</span><span class="sxs-lookup"><span data-stu-id="67065-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="67065-164">封存團隊不再使用中的時間。</span><span class="sxs-lookup"><span data-stu-id="67065-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="67065-165">刪除小組。</span><span class="sxs-lookup"><span data-stu-id="67065-165">Delete the team.</span></span>
-   <span data-ttu-id="67065-166">建立通道執行緒</span><span class="sxs-lookup"><span data-stu-id="67065-166">Create a channel thread</span></span>

<span data-ttu-id="67065-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="67065-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="67065-168">建立小組。</span><span class="sxs-lookup"><span data-stu-id="67065-168">Create a team.</span></span>
-   <span data-ttu-id="67065-169">新增成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="67065-169">Add members and owners.</span></span>
-   <span data-ttu-id="67065-170">新增頻道。</span><span class="sxs-lookup"><span data-stu-id="67065-170">Add channels.</span></span>
-   <span data-ttu-id="67065-171">當您不再需要成員、擁有者和頻道時，可以將它們移除。</span><span class="sxs-lookup"><span data-stu-id="67065-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="67065-172">刪除小組。</span><span class="sxs-lookup"><span data-stu-id="67065-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="67065-173">圖形 API 和 PowerShell Cmdlet 會持續新增功能。</span><span class="sxs-lookup"><span data-stu-id="67065-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="67065-174">請務必檢查[Microsoft GRAPH API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章，以瞭解功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="67065-174">Make sure to check the [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) and [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="67065-175">我可以控制教職員和學生能存取的小組功能嗎？</span><span class="sxs-lookup"><span data-stu-id="67065-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="67065-176">是。</span><span class="sxs-lookup"><span data-stu-id="67065-176">Yes.</span></span> <span data-ttu-id="67065-177">您可以使用原則來控制使用者可以存取的特定訊息、會議、通話及即時事件功能。</span><span class="sxs-lookup"><span data-stu-id="67065-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="67065-178">您可以使用整個租使用者的設定，將相同的設定套用至全部，或在必要時套用使用者層級原則。</span><span class="sxs-lookup"><span data-stu-id="67065-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="67065-179">如需團隊原則的詳細資訊，請參閱[管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="67065-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="67065-180">我可以控制教職員和學生共同作業的外部參與方嗎？</span><span class="sxs-lookup"><span data-stu-id="67065-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="67065-181">您可以使用來賓存取來邀請來自您租使用者以外的使用者，這對於研究共同作業或訪客講座很有用：</span><span class="sxs-lookup"><span data-stu-id="67065-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="67065-182">使用網域 whitelisting 根據其網域來允許或封鎖來賓。</span><span class="sxs-lookup"><span data-stu-id="67065-182">Use domain whitelisting to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="67065-183">針對特定的 Office 365 群組和團隊開啟和關閉來賓存取權，以控制哪些團隊可以（且不能）邀請來賓。</span><span class="sxs-lookup"><span data-stu-id="67065-183">Turn guest access on and off for particular Office 365 Groups and teams, to control which teams can (and can’t) invite guests.</span></span>
-   <span data-ttu-id="67065-184">使用審核記錄來查看哪些通知已傳送給受邀的來賓。</span><span class="sxs-lookup"><span data-stu-id="67065-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="67065-185">如需詳細資訊，請參閱[Office 365 群組中的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。</span><span class="sxs-lookup"><span data-stu-id="67065-185">For more information, see [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="67065-186">我可以查看現有團隊的哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="67065-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="67065-187">您可以查看 [審核記錄]，查看：</span><span class="sxs-lookup"><span data-stu-id="67065-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="67065-188">受邀者成為哪個團隊的來賓。</span><span class="sxs-lookup"><span data-stu-id="67065-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="67065-189">建立哪個團隊。</span><span class="sxs-lookup"><span data-stu-id="67065-189">Who created which team.</span></span>

<span data-ttu-id="67065-190">如需詳細資訊，請參閱在[[審核記錄] 中搜尋 Microsoft 團隊中的事件](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="67065-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="67065-191">小組會快速演變成如此。</span><span class="sxs-lookup"><span data-stu-id="67065-191">Teams evolves so quickly.</span></span> <span data-ttu-id="67065-192">我要如何掌握最新資訊？</span><span class="sxs-lookup"><span data-stu-id="67065-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="67065-193">我們建議您在下列資源中取得小組的最新更新：</span><span class="sxs-lookup"><span data-stu-id="67065-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="67065-194">Microsoft 團隊的新功能</span><span class="sxs-lookup"><span data-stu-id="67065-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="67065-195">Microsoft 團隊博客</span><span class="sxs-lookup"><span data-stu-id="67065-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
