---
title: 在系統管理中心使用一般團隊範本
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
description: 瞭解如何使用一般團隊範本，透過使用系統管理中心提供預先定義的設定、頻道及預先安裝的 app 來建立小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2905fe25d3051f322630d75473597e69425e2dc0
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424703"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a><span data-ttu-id="3cf92-103">在系統管理中心使用一般團隊範本</span><span class="sxs-lookup"><span data-stu-id="3cf92-103">Use general Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3cf92-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="3cf92-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3cf92-105">團隊範本有預先建立的小組結構定義，專為圍繞財務需求而設計。</span><span class="sxs-lookup"><span data-stu-id="3cf92-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="3cf92-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="3cf92-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3cf92-107">在本文中，我們將介紹每個團隊範本，並建議如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="3cf92-107">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="3cf92-108">如果您負責規劃、部署及管理整個財務組織中的多個小組，本文將適合您。</span><span class="sxs-lookup"><span data-stu-id="3cf92-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="3cf92-109">您已在組織中部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="3cf92-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3cf92-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf92-110">If you haven't rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="3cf92-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf92-111">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="3cf92-112">全球危機或活動</span><span class="sxs-lookup"><span data-stu-id="3cf92-112">Global crisis or event</span></span>

<span data-ttu-id="3cf92-113">針對您的危機小組集中共同作業，協助建立業務連續性方案、共用遠端工作秘訣、追蹤客戶通訊，以及使用宣告和新聞讓每個人都保持在迴圈中。</span><span class="sxs-lookup"><span data-stu-id="3cf92-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="3cf92-114">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-114">Base template type</span></span> |<span data-ttu-id="3cf92-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3cf92-115">baseTemplateId</span></span> | <span data-ttu-id="3cf92-116">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-116">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="3cf92-117">在全球危機或活動上共同作業</span><span class="sxs-lookup"><span data-stu-id="3cf92-117">Collaborate on global crisis or event</span></span> |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="3cf92-118">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-118">Channels:</span></span> <ul><li><span data-ttu-id="3cf92-119">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-119">General</span></span><li><span data-ttu-id="3cf92-120">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-120">Announcements</span></span></li><li><span data-ttu-id="3cf92-121">世界新聞</span><span class="sxs-lookup"><span data-stu-id="3cf92-121">World news</span></span></li><li><span data-ttu-id="3cf92-122">業務連續性</span><span class="sxs-lookup"><span data-stu-id="3cf92-122">Business continuity</span></span></li><li><span data-ttu-id="3cf92-123">遠端作業</span><span class="sxs-lookup"><span data-stu-id="3cf92-123">Remote working</span></span></li><li><span data-ttu-id="3cf92-124">內部 comms</span><span class="sxs-lookup"><span data-stu-id="3cf92-124">Internal comms</span></span></li><li><span data-ttu-id="3cf92-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="3cf92-125">External comms</span></span></li><li><span data-ttu-id="3cf92-126">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="3cf92-126">Customer complaints</span></span></li><li><span data-ttu-id="3cf92-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="3cf92-127">Kudos</span></span></li><li><span data-ttu-id="3cf92-128">主管更新</span><span class="sxs-lookup"><span data-stu-id="3cf92-128">Executive update</span></span></li></ul><span data-ttu-id="3cf92-129">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-129">Apps:</span></span> <ul><li><span data-ttu-id="3cf92-130">稱讚</span><span class="sxs-lookup"><span data-stu-id="3cf92-130">Praise</span></span></li><li><span data-ttu-id="3cf92-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-131">Wiki</span></span></li><li><span data-ttu-id="3cf92-132">Web</span><span class="sxs-lookup"><span data-stu-id="3cf92-132">Website</span></span></li></ul>|
||||

## <a name="adopt-office-365"></a><span data-ttu-id="3cf92-133">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="3cf92-133">Adopt Office 365</span></span>

<span data-ttu-id="3cf92-134">透過宣揚及協助對等新技術，協助您建立、擴大及維持您的擁護者社區推出。</span><span class="sxs-lookup"><span data-stu-id="3cf92-134">Help build, grow, and sustain your Champions community rollout by evangelizing and helping your peers with the new technology.</span></span>

| <span data-ttu-id="3cf92-135">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-135">Base template type</span></span> |<span data-ttu-id="3cf92-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3cf92-136">baseTemplateId</span></span> | <span data-ttu-id="3cf92-137">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-137">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="3cf92-138">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="3cf92-138">Adopt Office 365</span></span> | `com.microsoft.teams.template.AdoptOffice365` |  <span data-ttu-id="3cf92-139">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-139">Channels:</span></span> <ul><li><span data-ttu-id="3cf92-140">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-140">General</span></span></li> <li><span data-ttu-id="3cf92-141">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-141">Announcements</span></span></li> <li><span data-ttu-id="3cf92-142">擁護方角落</span><span class="sxs-lookup"><span data-stu-id="3cf92-142">Champions corner</span></span></li> <li><span data-ttu-id="3cf92-143">小組表單</span><span class="sxs-lookup"><span data-stu-id="3cf92-143">Team forms</span></span></li></ul> <span data-ttu-id="3cf92-144">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-144">Apps:</span></span> <ul><li><span data-ttu-id="3cf92-145">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-145">Wiki</span></span></li>  <li><span data-ttu-id="3cf92-146">行事曆</span><span class="sxs-lookup"><span data-stu-id="3cf92-146">Calendar</span></span></li> |<span data-ttu-id="3cf92-147">li></span><span class="sxs-lookup"><span data-stu-id="3cf92-147">li></span></span><li><span data-ttu-id="3cf92-148">技能開發</span><span class="sxs-lookup"><span data-stu-id="3cf92-148">Skills development</span></span></li><li><span data-ttu-id="3cf92-149">貸款處理</span><span class="sxs-lookup"><span data-stu-id="3cf92-149">Loan processing</span></span></li><li><span data-ttu-id="3cf92-150">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="3cf92-150">Customer complaints</span></span></li><li><span data-ttu-id="3cf92-151">Kudos</span><span class="sxs-lookup"><span data-stu-id="3cf92-151">Kudos</span></span></li><li><span data-ttu-id="3cf92-152">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="3cf92-152">Fun stuff</span></span></li><li><span data-ttu-id="3cf92-153">合規性</span><span class="sxs-lookup"><span data-stu-id="3cf92-153">Compliance</span></span></li></ul>|
||||

## <a name="manage-a-project"></a><span data-ttu-id="3cf92-154">管理專案</span><span class="sxs-lookup"><span data-stu-id="3cf92-154">Manage a project</span></span>

<span data-ttu-id="3cf92-155">使用此範本管理一般專案管理的工作、共用文件、執行專案會議及記錄風險與決策。</span><span class="sxs-lookup"><span data-stu-id="3cf92-155">Manage tasks, share documents, conduct project meetings and document risks and decisions with this template for general project management.</span></span>

| <span data-ttu-id="3cf92-156">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-156">Base template type</span></span>| <span data-ttu-id="3cf92-157">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3cf92-157">baseTemplateId</span></span> | <span data-ttu-id="3cf92-158">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-158">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="3cf92-159">管理專案</span><span class="sxs-lookup"><span data-stu-id="3cf92-159">Manage a project</span></span>| <span data-ttu-id="3cf92-160">ManageAProject 中的 [.com] 範本</span><span class="sxs-lookup"><span data-stu-id="3cf92-160">com.microsoft.teams.template.ManageAProject</span></span>  | <span data-ttu-id="3cf92-161">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-161">Channels:</span></span> <ul><li><span data-ttu-id="3cf92-162">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-162">General</span></span></li> <li><span data-ttu-id="3cf92-163">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-163">Announcements</span></span></li> <li><span data-ttu-id="3cf92-164">資源清單</span><span class="sxs-lookup"><span data-stu-id="3cf92-164">Resources</span></span></li> <li><span data-ttu-id="3cf92-165">規劃</span><span class="sxs-lookup"><span data-stu-id="3cf92-165">Planning</span></span></li></ul> <span data-ttu-id="3cf92-166">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-166">Apps:</span></span><ul><li><span data-ttu-id="3cf92-167">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-167">Wiki</span></span></li><li><span data-ttu-id="3cf92-168">OneNote</span><span class="sxs-lookup"><span data-stu-id="3cf92-168">OneNote</span></span></li></ul> |
||||

## <a name="manage-an-event"></a><span data-ttu-id="3cf92-169">管理活動</span><span class="sxs-lookup"><span data-stu-id="3cf92-169">Manage an event</span></span>

<span data-ttu-id="3cf92-170">管理工作、檔，以及共同作業，以提供引人注目的活動所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="3cf92-170">Manage tasks, documents, and collaborate on everything you need to deliver a compelling event.</span></span> <span data-ttu-id="3cf92-171">邀請來賓使用者在貴公司內部和外部都能安全地共同作業。</span><span class="sxs-lookup"><span data-stu-id="3cf92-171">Invite guests users to have secure collaboration inside and outside of your company.</span></span>

<span data-ttu-id="3cf92-172">您可能無法以應用程式許可權原則存取某些應用程式。</span><span class="sxs-lookup"><span data-stu-id="3cf92-172">You might not have access to certain apps based on your app permission policy.</span></span>

| <span data-ttu-id="3cf92-173">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-173">Base template type</span></span> | <span data-ttu-id="3cf92-174">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3cf92-174">baseTemplateId</span></span>| <span data-ttu-id="3cf92-175">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-175">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
| <span data-ttu-id="3cf92-176">管理活動</span><span class="sxs-lookup"><span data-stu-id="3cf92-176">Manage an event</span></span>| `com.microsoft.teams.template.ManageAnEvent` | <span data-ttu-id="3cf92-177">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-177">Channels:</span></span> <ul><li><span data-ttu-id="3cf92-178">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-178">General</span></span></li> <li><span data-ttu-id="3cf92-179">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-179">Announcements</span></span></li> <li><span data-ttu-id="3cf92-180">預算</span><span class="sxs-lookup"><span data-stu-id="3cf92-180">Budget</span></span></li> <li><span data-ttu-id="3cf92-181">內容</span><span class="sxs-lookup"><span data-stu-id="3cf92-181">Content</span></span></li><li><span data-ttu-id="3cf92-182">物流</span><span class="sxs-lookup"><span data-stu-id="3cf92-182">Logistics</span></span></li> <li><span data-ttu-id="3cf92-183">規劃</span><span class="sxs-lookup"><span data-stu-id="3cf92-183">Planning</span></span></li> <li> <span data-ttu-id="3cf92-184">行銷與 PR</span><span class="sxs-lookup"><span data-stu-id="3cf92-184">Marketing and PR</span></span></li></ul> <span data-ttu-id="3cf92-185">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-185">Apps:</span></span><ul><li><span data-ttu-id="3cf92-186">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-186">Wiki</span></span></li><li><span data-ttu-id="3cf92-187">Web</span><span class="sxs-lookup"><span data-stu-id="3cf92-187">Website</span></span></li> <li><span data-ttu-id="3cf92-188">YouTube</span><span class="sxs-lookup"><span data-stu-id="3cf92-188">YouTube</span></span></li> <li><span data-ttu-id="3cf92-189">Planner</span><span class="sxs-lookup"><span data-stu-id="3cf92-189">Planner</span></span></li> <li><span data-ttu-id="3cf92-190">OneNote</span><span class="sxs-lookup"><span data-stu-id="3cf92-190">OneNote</span></span></li></ul> |
||||

## <a name="onboard-employees"></a><span data-ttu-id="3cf92-191">板載員工</span><span class="sxs-lookup"><span data-stu-id="3cf92-191">Onboard employees</span></span>

<span data-ttu-id="3cf92-192">利用此中心小組的資源、問題及有趣的樂趣，改善您的文化，並簡化您的員工加入。</span><span class="sxs-lookup"><span data-stu-id="3cf92-192">Improve your culture and streamline your employee onboarding with this central team for resources, questions, and a bit of fun.</span></span>

| <span data-ttu-id="3cf92-193">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-193">Base template type</span></span> |<span data-ttu-id="3cf92-194">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3cf92-194">baseTemplateId</span></span> | <span data-ttu-id="3cf92-195">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-195">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="3cf92-196">板載員工</span><span class="sxs-lookup"><span data-stu-id="3cf92-196">Onboard employees</span></span>|`com.microsoft.teams.template.OnboardEmployees`  | <span data-ttu-id="3cf92-197">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-197">Channels:</span></span> <ul><li><span data-ttu-id="3cf92-198">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-198">General</span></span></li> <li><span data-ttu-id="3cf92-199">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-199">Announcements</span></span></li> <li><span data-ttu-id="3cf92-200">員工聊天</span><span class="sxs-lookup"><span data-stu-id="3cf92-200">Employee chat</span></span></li> <li><span data-ttu-id="3cf92-201">訓練</span><span class="sxs-lookup"><span data-stu-id="3cf92-201">Training</span></span></li></ul><span data-ttu-id="3cf92-202">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-202">Apps:</span></span><ul><li><span data-ttu-id="3cf92-203">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-203">Wiki</span></span></li><li><span data-ttu-id="3cf92-204">社區</span><span class="sxs-lookup"><span data-stu-id="3cf92-204">Communities</span></span></li></ul>|
||||

## <a name="organize-a-help-desk"></a><span data-ttu-id="3cf92-205">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="3cf92-205">Organize a help desk</span></span>

<span data-ttu-id="3cf92-206">在支援您的支援人員的檔、原則及流程上共同作業。</span><span class="sxs-lookup"><span data-stu-id="3cf92-206">Collaborate on documentation, policy, and processes that support your helpdesk.</span></span> <span data-ttu-id="3cf92-207">整合現有的票證發放系統，或使用我們的範本來管理要求。</span><span class="sxs-lookup"><span data-stu-id="3cf92-207">Integrate your existing ticketing system or use our template to manage requests.</span></span>

| <span data-ttu-id="3cf92-208">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="3cf92-208">Base template type</span></span> | | <span data-ttu-id="3cf92-209">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="3cf92-209">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3cf92-210">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="3cf92-210">Organize help desk</span></span>|`com.microsoft.teams.template.OrganizeHelpDesk`| <span data-ttu-id="3cf92-211">管道</span><span class="sxs-lookup"><span data-stu-id="3cf92-211">Channels:</span></span><ul><li><span data-ttu-id="3cf92-212">一般</span><span class="sxs-lookup"><span data-stu-id="3cf92-212">General</span></span></li><li><span data-ttu-id="3cf92-213">公告</span><span class="sxs-lookup"><span data-stu-id="3cf92-213">Announcements</span></span></li><li><span data-ttu-id="3cf92-214">常見問題集</span><span class="sxs-lookup"><span data-stu-id="3cf92-214">FAQ</span></span></li></ul><span data-ttu-id="3cf92-215">應用</span><span class="sxs-lookup"><span data-stu-id="3cf92-215">Apps:</span></span><ul><li><span data-ttu-id="3cf92-216">Wiki</span><span class="sxs-lookup"><span data-stu-id="3cf92-216">Wiki</span></span></li><li><span data-ttu-id="3cf92-217">OneNote</span><span class="sxs-lookup"><span data-stu-id="3cf92-217">OneNote</span></span></li></ul> |
||||
