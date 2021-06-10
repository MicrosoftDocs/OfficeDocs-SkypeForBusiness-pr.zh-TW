---
title: 適用於系統管理員的 Microsoft 教育版控管常見問題集
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft Education 群組管理員的常見問題解答，這些管理員會使用 Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ada92509adc0f066bf957ddaa8f5de8dd0c47653
ms.sourcegitcommit: 8906fc384cd13255972df53d2a07d12589154d42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52085845"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="ec199-103">適用於系統管理員的 Microsoft 教育版控管常見問題集</span><span class="sxs-lookup"><span data-stu-id="ec199-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="ec199-104">觀看下列會話以深入瞭解管理在 Microsoft Teams：管理、管理及生命週期[Microsoft Teams](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="ec199-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="ec199-105">如何控制團隊建立？</span><span class="sxs-lookup"><span data-stu-id="ec199-105">How do I control team creation?</span></span> <span data-ttu-id="ec199-106">我擔心學生會建立不當的團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="ec199-107">若要避免不當或誤導性的名稱，或只是提供團隊命名方式的更多結構，您可以使用目前預覽版中的 Microsoft 365 群組命名 (策略) ：</span><span class="sxs-lookup"><span data-stu-id="ec199-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Microsoft 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="ec199-108">**首碼 -尾碼命名策略** 您可以使用首碼或尾碼來定義團隊的命名慣例 (群組) 例如 **，GRP_US_My Group_Engineering。**</span><span class="sxs-lookup"><span data-stu-id="ec199-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="ec199-109">首碼和尾碼可以是固定字串或使用者屬性 (例如 **[部門]**) ，根據建立團隊的使用者新增到名稱。</span><span class="sxs-lookup"><span data-stu-id="ec199-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who's creating the team.</span></span>
-   <span data-ttu-id="ec199-110">**自訂封鎖的字詞** 您可以上傳一組文字，禁止特定組織的使用者使用他們建立的團隊名稱。</span><span class="sxs-lookup"><span data-stu-id="ec199-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="ec199-111">例如，您可以封鎖 CEO、**薪資** 和 **人力資源** 等字詞，禁止在團隊名稱中用於他們不適用的群組名稱。 </span><span class="sxs-lookup"><span data-stu-id="ec199-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don't apply to.</span></span>
-   <span data-ttu-id="ec199-112">**分類** 您可以建立組織中使用者在建立群組時可設定Microsoft 365分類。</span><span class="sxs-lookup"><span data-stu-id="ec199-112">**Classification** You can create classifications that the users in your organization can set when they create a Microsoft 365 Group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ec199-113">使用 Microsoft 365 群組命名政策時，每位成為一或多個群組成員的唯一使用者，都需要 Azure Active Directory 進階版 P1 授權或 Azure AD Basic EDU 授權Microsoft 365授權。</span><span class="sxs-lookup"><span data-stu-id="ec199-113">Using the Microsoft 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="ec199-114">有關詳細指示，請參閱[Office組命名政策](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="ec199-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="ec199-115">如果團隊是使用另一個系統的輸入自動建立 (例如 學校資料同步處理) ，請確認輸入資料符合您配置的命名規則;如果沒有，團隊建立將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ec199-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you've configured; if it doesn't, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="ec199-116">我可以看到誰建立了團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="ec199-116">Can I see who created a team?</span></span>

<span data-ttu-id="ec199-117">若要找出誰建立了特定小組[，請參閱搜尋](audit-log-events.md)稽核記錄，以在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ec199-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="ec199-118">我可以控制誰可以建立團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="ec199-118">Can I control who can create teams?</span></span>

<span data-ttu-id="ec199-119">一般而言，建議您禁止任何人建立團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="ec199-120">如果每個人都可以建立團隊，Teams更容易被廣泛採用。</span><span class="sxs-lookup"><span data-stu-id="ec199-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="ec199-121">教職員、教師或學生可以使用Teams建立學習群組或特殊興趣群組。</span><span class="sxs-lookup"><span data-stu-id="ec199-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="ec199-122">這可Teams課堂內外接受。</span><span class="sxs-lookup"><span data-stu-id="ec199-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="ec199-123">根據我們的經驗，使用者教育可協助確保Teams使用方式。</span><span class="sxs-lookup"><span data-stu-id="ec199-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="ec199-124">一旦使用者瞭解建立團隊並非匿名，他們就會瞭解不小心建立團隊的含意，並往往會因為誤用工具而感到圳然無味。</span><span class="sxs-lookup"><span data-stu-id="ec199-124">As soon as users understand that creating teams isn't anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="ec199-125">如果您確定要控制誰可以建立團隊，請參閱管理誰可以建立Microsoft 365[群組](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="ec199-125">If you're sure you want to control who can create teams, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="ec199-126">如何在學期或季開始時自動為每個課程建立團隊？</span><span class="sxs-lookup"><span data-stu-id="ec199-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="ec199-127">在每個學期或每季開始時，您需要一些新的團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-127">At the start of each semester or quarter, you'll need a number of new teams.</span></span> <span data-ttu-id="ec199-128">採取自動化方法自動建立這些團隊、填入正確的使用者，以及設定正確的許可權可能很合理：</span><span class="sxs-lookup"><span data-stu-id="ec199-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="ec199-129">學校資料同步處理可針對 Exchange Online 和 SharePoint Online 建立 Microsoft 365 群組、Microsoft Teams 和 OneNote 課程筆記本的班級團隊、Intune 教育版學校群組，以及名冊和單一登入 (SSO) 整合，適用于許多其他協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec199-129">School Data Sync can create Microsoft 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="ec199-130">如需深入瞭解，[請流覽 學校資料同步處理。](/schooldatasync/overview-of-school-data-sync)</span><span class="sxs-lookup"><span data-stu-id="ec199-130">Learn more at [Overview of School Data Sync](/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="ec199-131">您可以使用 PowerShell 建立團隊和頻道，並自動設定設定。</span><span class="sxs-lookup"><span data-stu-id="ec199-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="ec199-132">請參閱[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ec199-132">See [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="ec199-133">您可以使用 Microsoft Graph API (Beta) 建立、設定、複製和存檔團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="ec199-134">請參閱[使用 Microsoft Graph API 處理Microsoft Teams](/graph/api/resources/teams-api-overview)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ec199-134">See [Use the Microsoft Graph API to work with Microsoft Teams](/graph/api/resources/teams-api-overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="ec199-135">學校資料同步處理會為每個Microsoft 365建立一個群組，並啟用隱藏的群組成員資格，讓班級中的[](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)教師和學生只能看到該班級的成員。</span><span class="sxs-lookup"><span data-stu-id="ec199-135">School Data Sync creates a Microsoft 365 Group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="ec199-136">如果使用不同的程式來建立班級群組，請使用 Cmdlet 的 HiddenGroupMembershipEnabled 參數New-UnifiedGroup Cmdlet 以滿足相同的隱私權需求。</span><span class="sxs-lookup"><span data-stu-id="ec199-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="ec199-137">當學期或季結束時，我要如何處理團隊？</span><span class="sxs-lookup"><span data-stu-id="ec199-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="ec199-138">建議您先考慮在學校學期或四季結束後Teams如何處理 Teams 資料：是否要刪除資料，或讓學生即使在完成課程後也能夠使用這些資料。</span><span class="sxs-lookup"><span data-stu-id="ec199-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they've completed the course.</span></span> <span data-ttu-id="ec199-139">您一定會想要記住學校日曆，這樣您設定的任何政策都與假日不衝突。</span><span class="sxs-lookup"><span data-stu-id="ec199-139">You'll want to keep the school calendar in mind so any policies you set don't conflict with holidays.</span></span> <span data-ttu-id="ec199-140">您可以使用下列工具來實施您的策略：</span><span class="sxs-lookup"><span data-stu-id="ec199-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="ec199-141">**保留政策：** 使用此功能刪除所有超過您指定年齡的資料，以確保所有或部分使用者與頻道的聊天 (舊資料) 移除。</span><span class="sxs-lookup"><span data-stu-id="ec199-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="ec199-142">您也可以設定Teams保留內容，以便無法刪除內容。</span><span class="sxs-lookup"><span data-stu-id="ec199-142">You can also configure Teams to retain content so it can't be deleted.</span></span> <span data-ttu-id="ec199-143">詳細資訊，請參閱適用于 Microsoft Teams[的保留Microsoft Teams。](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)</span><span class="sxs-lookup"><span data-stu-id="ec199-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="ec199-144">**到期政策：** 設定團隊在特定天數後到期。</span><span class="sxs-lookup"><span data-stu-id="ec199-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="ec199-145">在到期前 30 天，團隊的所有擁有者都會收到通知，告知其小組需要續約，否則團隊會被刪除 (但系統管理員可以在) 中復原已刪除的團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="ec199-146">這項設定對於確保未使用的團隊已日落非常實用。</span><span class="sxs-lookup"><span data-stu-id="ec199-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="ec199-147">如需深入瞭解[，Microsoft 365組到期政策](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。</span><span class="sxs-lookup"><span data-stu-id="ec199-147">Learn more at [Microsoft 365 group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="ec199-148">**檔案小組：** 此設定會將團隊置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="ec199-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="ec199-149">他們仍然可以流覽和搜尋，但沒有人可以新增任何新文章。</span><span class="sxs-lookup"><span data-stu-id="ec199-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="ec199-150">[將團隊存檔或還原](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)說明團隊擁有者如何存檔團隊;團隊擁有者也可以使用 Beta Graph api ([來](/graph/api/resources/teams-api-overview)) 或還原團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="ec199-151">使用 Microsoft 365組到期政策Azure Active Directory 進階版一或多個群組成員之每個唯一使用者必須擁有 P1 Microsoft 365授權。</span><span class="sxs-lookup"><span data-stu-id="ec199-151">Using the Microsoft 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="ec199-152">建立團隊時，我的教職員成員可以使用團隊範本嗎？</span><span class="sxs-lookup"><span data-stu-id="ec199-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="ec199-153">是的。</span><span class="sxs-lookup"><span data-stu-id="ec199-153">Yes.</span></span> <span data-ttu-id="ec199-154">使用者可以在建立新團隊時，從現有的範本選取建立團隊，Teams 擁有者也可以使用 Graph API [ (Beta) ](/graph/api/resources/teams-api-overview)從可用的範本建立新團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="ec199-155">我可以透過 PowerShell 或 Graph 自動化哪些Graph？</span><span class="sxs-lookup"><span data-stu-id="ec199-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="ec199-156">[Microsoft Graph API (Beta) ](/graph/api/resources/teams-api-overview)可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ec199-156">The [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) can do the following:</span></span>

-   <span data-ttu-id="ec199-157">建立團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-157">Create a team.</span></span>
-   <span data-ttu-id="ec199-158">新增成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="ec199-158">Add members and owners.</span></span>
-   <span data-ttu-id="ec199-159">新增頻道。</span><span class="sxs-lookup"><span data-stu-id="ec199-159">Add channels.</span></span>
-   <span data-ttu-id="ec199-160">新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec199-160">Add apps.</span></span>
-   <span data-ttu-id="ec199-161">複製現有團隊以快捷方式執行這些步驟，並取得其定位停駐點。</span><span class="sxs-lookup"><span data-stu-id="ec199-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="ec199-162">提供使用者您剛剛建立團隊的連結。</span><span class="sxs-lookup"><span data-stu-id="ec199-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="ec199-163">當您不再需要成員、擁有者、頻道和應用程式時，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="ec199-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="ec199-164">當團隊不再使用中時，將其存檔。</span><span class="sxs-lookup"><span data-stu-id="ec199-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="ec199-165">刪除團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-165">Delete the team.</span></span>
-   <span data-ttu-id="ec199-166">建立頻道執行緒</span><span class="sxs-lookup"><span data-stu-id="ec199-166">Create a channel thread</span></span>

<span data-ttu-id="ec199-167">[PowerShell](/powershell/module/teams/?view=teams-ps) 可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ec199-167">[PowerShell](/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="ec199-168">建立團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-168">Create a team.</span></span>
-   <span data-ttu-id="ec199-169">新增成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="ec199-169">Add members and owners.</span></span>
-   <span data-ttu-id="ec199-170">新增頻道。</span><span class="sxs-lookup"><span data-stu-id="ec199-170">Add channels.</span></span>
-   <span data-ttu-id="ec199-171">當您不再需要成員、擁有者和頻道時，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="ec199-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="ec199-172">刪除團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="ec199-173">Graph API 和 PowerShell Cmdlet 不斷新增功能。</span><span class="sxs-lookup"><span data-stu-id="ec199-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="ec199-174">請務必檢查 Microsoft Graph [API (和](/graph/api/resources/teams-api-overview) [PowerShell](/powershell/module/teams/?view=teams-ps)) 文章，瞭解功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="ec199-174">Make sure to check the [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) and [PowerShell](/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="ec199-175">我能否控制Teams教職員和學生可存取哪些功能？</span><span class="sxs-lookup"><span data-stu-id="ec199-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="ec199-176">是的。</span><span class="sxs-lookup"><span data-stu-id="ec199-176">Yes.</span></span> <span data-ttu-id="ec199-177">您可以使用策略來控制使用者可存取的特定訊息、會議、通話和即時活動功能。</span><span class="sxs-lookup"><span data-stu-id="ec199-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="ec199-178">您可以使用整個租使用者設定來將相同的設定全部都適用，或如果需要，則適用使用者層級原則。</span><span class="sxs-lookup"><span data-stu-id="ec199-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="ec199-179">如要進一步Teams，請參閱[管理Microsoft Teams的設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ec199-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="ec199-180">我可以控制教職員與學生共同合作的外部派對嗎？</span><span class="sxs-lookup"><span data-stu-id="ec199-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="ec199-181">您可以使用來賓存取來邀請租使用者以外的使用者，這很適合研究共同研究或來賓課程：</span><span class="sxs-lookup"><span data-stu-id="ec199-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="ec199-182">使用網域允許清單，根據來賓的網域來允許或封鎖來賓。</span><span class="sxs-lookup"><span data-stu-id="ec199-182">Use a domain allowlist to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="ec199-183">開啟和關閉特定群組和Microsoft 365的來賓存取權，以控制哪些團隊可以 (，) 邀請來賓。</span><span class="sxs-lookup"><span data-stu-id="ec199-183">Turn guest access on and off for particular Microsoft 365 Groups and teams, to control which teams can (and can't) invite guests.</span></span>
-   <span data-ttu-id="ec199-184">使用稽核記錄查看哪些通知已發送給受邀來賓。</span><span class="sxs-lookup"><span data-stu-id="ec199-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="ec199-185">詳細資訊請參閱群組中的[來賓Microsoft 365存取](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。</span><span class="sxs-lookup"><span data-stu-id="ec199-185">For more information, see [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="ec199-186">我可以查看哪些現有團隊的資訊？</span><span class="sxs-lookup"><span data-stu-id="ec199-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="ec199-187">您可以檢查稽核記錄以查看：</span><span class="sxs-lookup"><span data-stu-id="ec199-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="ec199-188">神秘受邀為來賓加入哪個團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="ec199-189">神秘建立哪個團隊。</span><span class="sxs-lookup"><span data-stu-id="ec199-189">Who created which team.</span></span>

<span data-ttu-id="ec199-190">詳細資訊，請參閱在 Microsoft Teams 中[搜尋稽核Microsoft Teams。](audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="ec199-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="ec199-191">Teams變化如此快速。</span><span class="sxs-lookup"><span data-stu-id="ec199-191">Teams evolves so quickly.</span></span> <span data-ttu-id="ec199-192">如何保持最新狀態？</span><span class="sxs-lookup"><span data-stu-id="ec199-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="ec199-193">我們建議您使用下列資源取得最新Teams：</span><span class="sxs-lookup"><span data-stu-id="ec199-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="ec199-194">新功能Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec199-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="ec199-195">Microsoft Teams部落格</span><span class="sxs-lookup"><span data-stu-id="ec199-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)