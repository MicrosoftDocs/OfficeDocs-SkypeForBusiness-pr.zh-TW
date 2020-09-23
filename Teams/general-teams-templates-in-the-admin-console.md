---
title: 在管理員主控台中使用一般團隊範本
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用一般團隊範本，透過使用管理主控台提供預先定義的設定、通道及預先安裝 app 來建立小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 39debd0b184109a55686977f27ba1262d5d65641
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216694"
---
# <a name="use-general-teams-templates-in-the-admin-console"></a><span data-ttu-id="cc578-103">在管理員主控台中使用一般團隊範本</span><span class="sxs-lookup"><span data-stu-id="cc578-103">Use general Teams templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="cc578-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="cc578-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="cc578-105">團隊範本有預先建立的小組結構定義，專為圍繞財務需求而設計。</span><span class="sxs-lookup"><span data-stu-id="cc578-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="cc578-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="cc578-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="cc578-107">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="cc578-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="cc578-108">如果您負責規劃、部署及管理整個財務組織中的多個小組，本文將適合您。</span><span class="sxs-lookup"><span data-stu-id="cc578-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="cc578-109">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="cc578-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="cc578-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc578-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="cc578-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="cc578-111">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="cc578-112">全球危機或活動</span><span class="sxs-lookup"><span data-stu-id="cc578-112">Global crisis or event</span></span>

<span data-ttu-id="cc578-113">針對您的危機小組集中共同作業，協助建立業務連續性方案、共用遠端工作秘訣、追蹤客戶通訊，以及使用宣告和新聞讓每個人都保持在迴圈中。</span><span class="sxs-lookup"><span data-stu-id="cc578-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="cc578-114">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-114">Base template type</span></span> |<span data-ttu-id="cc578-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cc578-115">baseTemplateId</span></span> | <span data-ttu-id="cc578-116">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-116">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="cc578-117">在全球危機或活動上共同作業</span><span class="sxs-lookup"><span data-stu-id="cc578-117">Collaborate on global crisis or event</span></span> |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="cc578-118">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-118">Channels:</span></span> <ul><li><span data-ttu-id="cc578-119">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-119">General</span></span><li><span data-ttu-id="cc578-120">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-120">Announcements</span></span></li><li><span data-ttu-id="cc578-121">世界新聞</span><span class="sxs-lookup"><span data-stu-id="cc578-121">World news</span></span></li><li><span data-ttu-id="cc578-122">業務連續性</span><span class="sxs-lookup"><span data-stu-id="cc578-122">Business continuity</span></span></li><li><span data-ttu-id="cc578-123">遠端作業</span><span class="sxs-lookup"><span data-stu-id="cc578-123">Remote working</span></span></li><li><span data-ttu-id="cc578-124">內部 comms</span><span class="sxs-lookup"><span data-stu-id="cc578-124">Internal comms</span></span></li><li><span data-ttu-id="cc578-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="cc578-125">External comms</span></span></li><li><span data-ttu-id="cc578-126">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="cc578-126">Customer complaints</span></span></li><li><span data-ttu-id="cc578-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="cc578-127">Kudos</span></span></li><li><span data-ttu-id="cc578-128">主管更新</span><span class="sxs-lookup"><span data-stu-id="cc578-128">Executive update</span></span></li></ul><span data-ttu-id="cc578-129">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-129">Apps:</span></span> <ul><li><span data-ttu-id="cc578-130">稱讚</span><span class="sxs-lookup"><span data-stu-id="cc578-130">Praise</span></span></li><li><span data-ttu-id="cc578-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-131">Wiki</span></span></li><li><span data-ttu-id="cc578-132">Web</span><span class="sxs-lookup"><span data-stu-id="cc578-132">Website</span></span></li></ul>|
||||

## <a name="adopt-office-365"></a><span data-ttu-id="cc578-133">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="cc578-133">Adopt Office 365</span></span>

<span data-ttu-id="cc578-134">透過宣揚及協助對等新技術，協助您建立、擴大及維持您的擁護者社區推出。</span><span class="sxs-lookup"><span data-stu-id="cc578-134">Help build, grow, and sustain your Champions community rollout by evangelizing and helping your peers with the new technology.</span></span>

| <span data-ttu-id="cc578-135">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-135">Base template type</span></span> |<span data-ttu-id="cc578-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cc578-136">baseTemplateId</span></span> | <span data-ttu-id="cc578-137">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-137">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="cc578-138">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="cc578-138">Adopt Office 365</span></span> | `com.microsoft.teams.template.AdoptOffice365` |  <span data-ttu-id="cc578-139">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-139">Channels:</span></span> <ul><li><span data-ttu-id="cc578-140">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-140">General</span></span></li> <li><span data-ttu-id="cc578-141">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-141">Announcements</span></span></li> <li><span data-ttu-id="cc578-142">擁護方角落</span><span class="sxs-lookup"><span data-stu-id="cc578-142">Champions corner</span></span></li> <li><span data-ttu-id="cc578-143">小組表單</span><span class="sxs-lookup"><span data-stu-id="cc578-143">Team forms</span></span></li></ul> <span data-ttu-id="cc578-144">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-144">Apps:</span></span> <ul><li><span data-ttu-id="cc578-145">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-145">Wiki</span></span></li>  <li><span data-ttu-id="cc578-146">行事曆</span><span class="sxs-lookup"><span data-stu-id="cc578-146">Calendar</span></span></li> |<span data-ttu-id="cc578-147">li></span><span class="sxs-lookup"><span data-stu-id="cc578-147">li></span></span><li><span data-ttu-id="cc578-148">技能開發</span><span class="sxs-lookup"><span data-stu-id="cc578-148">Skills development</span></span></li><li><span data-ttu-id="cc578-149">貸款處理</span><span class="sxs-lookup"><span data-stu-id="cc578-149">Loan processing</span></span></li><li><span data-ttu-id="cc578-150">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="cc578-150">Customer complaints</span></span></li><li><span data-ttu-id="cc578-151">Kudos</span><span class="sxs-lookup"><span data-stu-id="cc578-151">Kudos</span></span></li><li><span data-ttu-id="cc578-152">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="cc578-152">Fun stuff</span></span></li><li><span data-ttu-id="cc578-153">合規性</span><span class="sxs-lookup"><span data-stu-id="cc578-153">Compliance</span></span></li></ul>|
||||

## <a name="manage-a-project"></a><span data-ttu-id="cc578-154">管理專案</span><span class="sxs-lookup"><span data-stu-id="cc578-154">Manage a project</span></span>

<span data-ttu-id="cc578-155">使用此範本管理一般專案管理的工作、共用文件、執行專案會議及記錄風險與決策。</span><span class="sxs-lookup"><span data-stu-id="cc578-155">Manage tasks, share documents, conduct project meetings and document risks and decisions with this template for general project management.</span></span>

| <span data-ttu-id="cc578-156">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-156">Base template type</span></span>| <span data-ttu-id="cc578-157">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cc578-157">baseTemplateId</span></span> | <span data-ttu-id="cc578-158">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-158">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="cc578-159">管理專案</span><span class="sxs-lookup"><span data-stu-id="cc578-159">Manage a project</span></span>| <span data-ttu-id="cc578-160">ManageAProject 中的 [.com] 範本</span><span class="sxs-lookup"><span data-stu-id="cc578-160">com.microsoft.teams.template.ManageAProject</span></span>  | <span data-ttu-id="cc578-161">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-161">Channels:</span></span> <ul><li><span data-ttu-id="cc578-162">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-162">General</span></span></li> <li><span data-ttu-id="cc578-163">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-163">Announcements</span></span></li> <li><span data-ttu-id="cc578-164">資源清單</span><span class="sxs-lookup"><span data-stu-id="cc578-164">Resources</span></span></li> <li><span data-ttu-id="cc578-165">規劃</span><span class="sxs-lookup"><span data-stu-id="cc578-165">Planning</span></span></li></ul> <span data-ttu-id="cc578-166">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-166">Apps:</span></span><ul><li><span data-ttu-id="cc578-167">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-167">Wiki</span></span></li><li><span data-ttu-id="cc578-168">OneNote</span><span class="sxs-lookup"><span data-stu-id="cc578-168">OneNote</span></span></li></ul> |
||||

## <a name="manage-an-event"></a><span data-ttu-id="cc578-169">管理活動</span><span class="sxs-lookup"><span data-stu-id="cc578-169">Manage an event</span></span>

<span data-ttu-id="cc578-170">管理工作、檔，以及在您所需的所有專案上共同作業，以傳送引人注目的活動。</span><span class="sxs-lookup"><span data-stu-id="cc578-170">Manage tasks, documents and collaborate on everything you need to deliver a compelling event.</span></span> <span data-ttu-id="cc578-171">邀請來賓使用者在貴公司內部和外部都能安全地共同作業。</span><span class="sxs-lookup"><span data-stu-id="cc578-171">Invite guests users to have secure collaboration inside and outside of your company.</span></span>

<span data-ttu-id="cc578-172">您可能無法以您的應用程式許可權原則存取某些應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc578-172">You may not have access to certain apps based on your app permission policy.</span></span>

| <span data-ttu-id="cc578-173">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-173">Base template type</span></span> | <span data-ttu-id="cc578-174">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cc578-174">baseTemplateId</span></span>| <span data-ttu-id="cc578-175">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-175">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="cc578-176">管理活動</span><span class="sxs-lookup"><span data-stu-id="cc578-176">Manage an event</span></span>| `com.microsoft.teams.template.ManageAnEvent` | <span data-ttu-id="cc578-177">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-177">Channels:</span></span> <ul><li><span data-ttu-id="cc578-178">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-178">General</span></span></li> <li><span data-ttu-id="cc578-179">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-179">Announcements</span></span></li> <li><span data-ttu-id="cc578-180">預算</span><span class="sxs-lookup"><span data-stu-id="cc578-180">Budget</span></span></li> <li><span data-ttu-id="cc578-181">內容</span><span class="sxs-lookup"><span data-stu-id="cc578-181">Content</span></span></li><li><span data-ttu-id="cc578-182">物流</span><span class="sxs-lookup"><span data-stu-id="cc578-182">Logistics</span></span></li> <li><span data-ttu-id="cc578-183">規劃</span><span class="sxs-lookup"><span data-stu-id="cc578-183">Planning</span></span></li> <li> <span data-ttu-id="cc578-184">行銷與 PR</span><span class="sxs-lookup"><span data-stu-id="cc578-184">Marketing and PR</span></span></li></ul> <span data-ttu-id="cc578-185">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-185">Apps:</span></span><ul><li><span data-ttu-id="cc578-186">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-186">Wiki</span></span></li><li><span data-ttu-id="cc578-187">Web</span><span class="sxs-lookup"><span data-stu-id="cc578-187">Website</span></span></li> <li><span data-ttu-id="cc578-188">YouTube</span><span class="sxs-lookup"><span data-stu-id="cc578-188">YouTube</span></span></li> <li><span data-ttu-id="cc578-189">Planner</span><span class="sxs-lookup"><span data-stu-id="cc578-189">Planner</span></span></li> <li><span data-ttu-id="cc578-190">OneNote</span><span class="sxs-lookup"><span data-stu-id="cc578-190">OneNote</span></span></li></ul> |
||||

## <a name="onboard-employees"></a><span data-ttu-id="cc578-191">板載員工</span><span class="sxs-lookup"><span data-stu-id="cc578-191">Onboard employees</span></span>

<span data-ttu-id="cc578-192">利用此中心小組的資源、問題及有趣的樂趣，改善您的文化，並簡化您的員工加入。</span><span class="sxs-lookup"><span data-stu-id="cc578-192">Improve your culture and streamline your employee onboarding with this central team for resources, questions, and a bit of fun.</span></span>

| <span data-ttu-id="cc578-193">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-193">Base template type</span></span> |<span data-ttu-id="cc578-194">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cc578-194">baseTemplateId</span></span> | <span data-ttu-id="cc578-195">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-195">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="cc578-196">板載員工</span><span class="sxs-lookup"><span data-stu-id="cc578-196">Onboard employees</span></span>|`com.microsoft.teams.template.OnboardEmployees`  | <span data-ttu-id="cc578-197">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-197">Channels:</span></span> <ul><li><span data-ttu-id="cc578-198">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-198">General</span></span></li> <li><span data-ttu-id="cc578-199">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-199">Announcements</span></span></li> <li><span data-ttu-id="cc578-200">員工聊天</span><span class="sxs-lookup"><span data-stu-id="cc578-200">Employee chat</span></span></li> <li><span data-ttu-id="cc578-201">訓練</span><span class="sxs-lookup"><span data-stu-id="cc578-201">Training</span></span></li></ul><span data-ttu-id="cc578-202">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-202">Apps:</span></span><ul><li><span data-ttu-id="cc578-203">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-203">Wiki</span></span></li><li><span data-ttu-id="cc578-204">社區</span><span class="sxs-lookup"><span data-stu-id="cc578-204">Communities</span></span></li></ul>|
||||

## <a name="organize-a-help-desk"></a><span data-ttu-id="cc578-205">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="cc578-205">Organize a help desk</span></span>

<span data-ttu-id="cc578-206">在支援您的支援人員的檔、原則及流程上共同作業。</span><span class="sxs-lookup"><span data-stu-id="cc578-206">Collaborate on documentation, policy, and processes that support your helpdesk.</span></span> <span data-ttu-id="cc578-207">整合現有的票證發放系統，或使用我們的範本來管理要求。</span><span class="sxs-lookup"><span data-stu-id="cc578-207">Integrate your existing ticketing system or use our template to manage requests.</span></span>

| <span data-ttu-id="cc578-208">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="cc578-208">Base template type</span></span> | | <span data-ttu-id="cc578-209">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="cc578-209">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="cc578-210">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="cc578-210">Organize help desk</span></span>|`com.microsoft.teams.template.OrganizeHelpDesk`| <span data-ttu-id="cc578-211">管道</span><span class="sxs-lookup"><span data-stu-id="cc578-211">Channels:</span></span><ul><li><span data-ttu-id="cc578-212">一般</span><span class="sxs-lookup"><span data-stu-id="cc578-212">General</span></span></li><li><span data-ttu-id="cc578-213">公告</span><span class="sxs-lookup"><span data-stu-id="cc578-213">Announcements</span></span></li><li><span data-ttu-id="cc578-214">常見問題集</span><span class="sxs-lookup"><span data-stu-id="cc578-214">FAQ</span></span></li></ul><span data-ttu-id="cc578-215">應用</span><span class="sxs-lookup"><span data-stu-id="cc578-215">Apps:</span></span><ul><li><span data-ttu-id="cc578-216">Wiki</span><span class="sxs-lookup"><span data-stu-id="cc578-216">Wiki</span></span></li><li><span data-ttu-id="cc578-217">OneNote</span><span class="sxs-lookup"><span data-stu-id="cc578-217">OneNote</span></span></li></ul> |
||||
