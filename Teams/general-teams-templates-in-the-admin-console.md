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
ms.openlocfilehash: a158850a70a0410c9be7cb434d6f0868d68218f5
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655500"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a><span data-ttu-id="a76cd-103">在系統管理中心使用一般團隊範本</span><span class="sxs-lookup"><span data-stu-id="a76cd-103">Use general Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="a76cd-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="a76cd-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a76cd-105">團隊範本有預先建立的小組結構定義，專為圍繞財務需求而設計。</span><span class="sxs-lookup"><span data-stu-id="a76cd-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="a76cd-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="a76cd-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="a76cd-107">在本文中，我們將介紹每個團隊範本，並建議如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="a76cd-107">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="a76cd-108">如果您負責規劃、部署及管理整個財務組織中的多個小組，本文將適合您。</span><span class="sxs-lookup"><span data-stu-id="a76cd-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="a76cd-109">您已在組織中部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="a76cd-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="a76cd-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a76cd-110">If you haven't rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="a76cd-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="a76cd-111">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="a76cd-112">全球危機或活動</span><span class="sxs-lookup"><span data-stu-id="a76cd-112">Global crisis or event</span></span>

<span data-ttu-id="a76cd-113">針對您的危機小組集中共同作業，協助建立業務連續性方案、共用遠端工作秘訣、追蹤客戶通訊，以及使用宣告和新聞讓每個人都保持在迴圈中。</span><span class="sxs-lookup"><span data-stu-id="a76cd-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="a76cd-114">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-114">Base template type</span></span> |<span data-ttu-id="a76cd-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-115">baseTemplateId</span></span>| <span data-ttu-id="a76cd-116">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-116">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------------|
| <span data-ttu-id="a76cd-117">在全球危機或活動上共同作業</span><span class="sxs-lookup"><span data-stu-id="a76cd-117">Collaborate on global crisis or event</span></span> |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="a76cd-118">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-118">Channels:</span></span> <ul><li><span data-ttu-id="a76cd-119">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-119">General</span></span><li><span data-ttu-id="a76cd-120">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-120">Announcements</span></span></li><li><span data-ttu-id="a76cd-121">世界新聞</span><span class="sxs-lookup"><span data-stu-id="a76cd-121">World news</span></span></li><li><span data-ttu-id="a76cd-122">業務連續性</span><span class="sxs-lookup"><span data-stu-id="a76cd-122">Business continuity</span></span></li><li><span data-ttu-id="a76cd-123">遠端作業</span><span class="sxs-lookup"><span data-stu-id="a76cd-123">Remote working</span></span></li><li><span data-ttu-id="a76cd-124">內部 comms</span><span class="sxs-lookup"><span data-stu-id="a76cd-124">Internal comms</span></span></li><li><span data-ttu-id="a76cd-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="a76cd-125">External comms</span></span></li><li><span data-ttu-id="a76cd-126">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="a76cd-126">Customer complaints</span></span></li><li><span data-ttu-id="a76cd-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="a76cd-127">Kudos</span></span></li><li><span data-ttu-id="a76cd-128">主管更新</span><span class="sxs-lookup"><span data-stu-id="a76cd-128">Executive update</span></span></li></ul><span data-ttu-id="a76cd-129">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-129">Apps:</span></span> <ul><li><span data-ttu-id="a76cd-130">稱讚</span><span class="sxs-lookup"><span data-stu-id="a76cd-130">Praise</span></span></li><li><span data-ttu-id="a76cd-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-131">Wiki</span></span></li><li><span data-ttu-id="a76cd-132">Web</span><span class="sxs-lookup"><span data-stu-id="a76cd-132">Website</span></span></li></ul>|
||||

## <a name="adopt-office-365"></a><span data-ttu-id="a76cd-133">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="a76cd-133">Adopt Office 365</span></span>

<span data-ttu-id="a76cd-134">透過宣揚及協助對等新技術，協助您建立、擴大及維持您的擁護者社區推出。</span><span class="sxs-lookup"><span data-stu-id="a76cd-134">Help build, grow, and sustain your Champions community rollout by evangelizing and helping your peers with the new technology.</span></span>

| <span data-ttu-id="a76cd-135">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-135">Base template type</span></span> |<span data-ttu-id="a76cd-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-136">baseTemplateId</span></span>| <span data-ttu-id="a76cd-137">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-137">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
| <span data-ttu-id="a76cd-138">採納 Office 365</span><span class="sxs-lookup"><span data-stu-id="a76cd-138">Adopt Office 365</span></span> | `com.microsoft.teams.template.AdoptOffice365` |  <span data-ttu-id="a76cd-139">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-139">Channels:</span></span> <ul><li><span data-ttu-id="a76cd-140">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-140">General</span></span></li> <li><span data-ttu-id="a76cd-141">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-141">Announcements</span></span></li> <li><span data-ttu-id="a76cd-142">擁護方角落</span><span class="sxs-lookup"><span data-stu-id="a76cd-142">Champions corner</span></span></li> <li><span data-ttu-id="a76cd-143">小組表單</span><span class="sxs-lookup"><span data-stu-id="a76cd-143">Team forms</span></span></li></ul> <span data-ttu-id="a76cd-144">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-144">Apps:</span></span> <ul><li><span data-ttu-id="a76cd-145">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-145">Wiki</span></span></li>  <li><span data-ttu-id="a76cd-146">行事曆</span><span class="sxs-lookup"><span data-stu-id="a76cd-146">Calendar</span></span></li><li><span data-ttu-id="a76cd-147">技能開發</span><span class="sxs-lookup"><span data-stu-id="a76cd-147">Skills development</span></span></li><li><span data-ttu-id="a76cd-148">貸款處理</span><span class="sxs-lookup"><span data-stu-id="a76cd-148">Loan processing</span></span></li><li><span data-ttu-id="a76cd-149">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="a76cd-149">Customer complaints</span></span></li><li><span data-ttu-id="a76cd-150">Kudos</span><span class="sxs-lookup"><span data-stu-id="a76cd-150">Kudos</span></span></li><li><span data-ttu-id="a76cd-151">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="a76cd-151">Fun stuff</span></span></li><li><span data-ttu-id="a76cd-152">合規性</span><span class="sxs-lookup"><span data-stu-id="a76cd-152">Compliance</span></span></li></ul>|
||||

## <a name="manage-a-project"></a><span data-ttu-id="a76cd-153">管理專案</span><span class="sxs-lookup"><span data-stu-id="a76cd-153">Manage a project</span></span>

<span data-ttu-id="a76cd-154">使用此範本管理一般專案管理的工作、共用文件、執行專案會議及記錄風險與決策。</span><span class="sxs-lookup"><span data-stu-id="a76cd-154">Manage tasks, share documents, conduct project meetings and document risks and decisions with this template for general project management.</span></span>

| <span data-ttu-id="a76cd-155">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-155">Base template type</span></span>| <span data-ttu-id="a76cd-156">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-156">baseTemplateId</span></span>| <span data-ttu-id="a76cd-157">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-157">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
| <span data-ttu-id="a76cd-158">管理專案</span><span class="sxs-lookup"><span data-stu-id="a76cd-158">Manage a project</span></span>| <span data-ttu-id="a76cd-159">ManageAProject 中的 [.com] 範本</span><span class="sxs-lookup"><span data-stu-id="a76cd-159">com.microsoft.teams.template.ManageAProject</span></span>  | <span data-ttu-id="a76cd-160">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-160">Channels:</span></span> <ul><li><span data-ttu-id="a76cd-161">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-161">General</span></span></li> <li><span data-ttu-id="a76cd-162">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-162">Announcements</span></span></li> <li><span data-ttu-id="a76cd-163">資源清單</span><span class="sxs-lookup"><span data-stu-id="a76cd-163">Resources</span></span></li> <li><span data-ttu-id="a76cd-164">規劃</span><span class="sxs-lookup"><span data-stu-id="a76cd-164">Planning</span></span></li></ul> <span data-ttu-id="a76cd-165">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-165">Apps:</span></span><ul><li><span data-ttu-id="a76cd-166">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-166">Wiki</span></span></li><li><span data-ttu-id="a76cd-167">OneNote</span><span class="sxs-lookup"><span data-stu-id="a76cd-167">OneNote</span></span></li></ul> |
||||

## <a name="manage-an-event"></a><span data-ttu-id="a76cd-168">管理活動</span><span class="sxs-lookup"><span data-stu-id="a76cd-168">Manage an event</span></span>

<span data-ttu-id="a76cd-169">管理工作、檔，以及共同作業，以提供引人注目的活動所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="a76cd-169">Manage tasks, documents, and collaborate on everything you need to deliver a compelling event.</span></span> <span data-ttu-id="a76cd-170">邀請來賓使用者在貴公司內部和外部都能安全地共同作業。</span><span class="sxs-lookup"><span data-stu-id="a76cd-170">Invite guests users to have secure collaboration inside and outside of your company.</span></span>

<span data-ttu-id="a76cd-171">您可能無法以應用程式許可權原則存取某些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a76cd-171">You might not have access to certain apps based on your app permission policy.</span></span>

| <span data-ttu-id="a76cd-172">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-172">Base template type</span></span> | <span data-ttu-id="a76cd-173">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-173">baseTemplateId</span></span>| <span data-ttu-id="a76cd-174">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-174">Properties that come with this base template</span></span> |
| ------------------ |--|-----------------------------------------------------------|
| <span data-ttu-id="a76cd-175">管理活動</span><span class="sxs-lookup"><span data-stu-id="a76cd-175">Manage an event</span></span>| `com.microsoft.teams.template.ManageAnEvent` | <span data-ttu-id="a76cd-176">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-176">Channels:</span></span> <ul><li><span data-ttu-id="a76cd-177">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-177">General</span></span></li> <li><span data-ttu-id="a76cd-178">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-178">Announcements</span></span></li> <li><span data-ttu-id="a76cd-179">預算</span><span class="sxs-lookup"><span data-stu-id="a76cd-179">Budget</span></span></li> <li><span data-ttu-id="a76cd-180">內容</span><span class="sxs-lookup"><span data-stu-id="a76cd-180">Content</span></span></li><li><span data-ttu-id="a76cd-181">物流</span><span class="sxs-lookup"><span data-stu-id="a76cd-181">Logistics</span></span></li> <li><span data-ttu-id="a76cd-182">規劃</span><span class="sxs-lookup"><span data-stu-id="a76cd-182">Planning</span></span></li> <li> <span data-ttu-id="a76cd-183">行銷與 PR</span><span class="sxs-lookup"><span data-stu-id="a76cd-183">Marketing and PR</span></span></li></ul> <span data-ttu-id="a76cd-184">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-184">Apps:</span></span><ul><li><span data-ttu-id="a76cd-185">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-185">Wiki</span></span></li><li><span data-ttu-id="a76cd-186">Web</span><span class="sxs-lookup"><span data-stu-id="a76cd-186">Website</span></span></li> <li><span data-ttu-id="a76cd-187">YouTube</span><span class="sxs-lookup"><span data-stu-id="a76cd-187">YouTube</span></span></li> <li><span data-ttu-id="a76cd-188">Planner</span><span class="sxs-lookup"><span data-stu-id="a76cd-188">Planner</span></span></li> <li><span data-ttu-id="a76cd-189">OneNote</span><span class="sxs-lookup"><span data-stu-id="a76cd-189">OneNote</span></span></li></ul> |
||||

## <a name="onboard-employees"></a><span data-ttu-id="a76cd-190">板載員工</span><span class="sxs-lookup"><span data-stu-id="a76cd-190">Onboard employees</span></span>

<span data-ttu-id="a76cd-191">利用此中心小組的資源、問題及有趣的樂趣，改善您的文化，並簡化您的員工加入。</span><span class="sxs-lookup"><span data-stu-id="a76cd-191">Improve your culture and streamline your employee onboarding with this central team for resources, questions, and a bit of fun.</span></span>

| <span data-ttu-id="a76cd-192">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-192">Base template type</span></span> |<span data-ttu-id="a76cd-193">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-193">baseTemplateId</span></span>| <span data-ttu-id="a76cd-194">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-194">Properties that come with this base template</span></span> |
| ------------------|--|-----------------------------------------------------------|
|<span data-ttu-id="a76cd-195">板載員工</span><span class="sxs-lookup"><span data-stu-id="a76cd-195">Onboard employees</span></span>|`com.microsoft.teams.template.OnboardEmployees`  | <span data-ttu-id="a76cd-196">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-196">Channels:</span></span> <ul><li><span data-ttu-id="a76cd-197">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-197">General</span></span></li> <li><span data-ttu-id="a76cd-198">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-198">Announcements</span></span></li> <li><span data-ttu-id="a76cd-199">員工聊天</span><span class="sxs-lookup"><span data-stu-id="a76cd-199">Employee chat</span></span></li> <li><span data-ttu-id="a76cd-200">訓練</span><span class="sxs-lookup"><span data-stu-id="a76cd-200">Training</span></span></li></ul><span data-ttu-id="a76cd-201">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-201">Apps:</span></span><ul><li><span data-ttu-id="a76cd-202">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-202">Wiki</span></span></li><li><span data-ttu-id="a76cd-203">社區</span><span class="sxs-lookup"><span data-stu-id="a76cd-203">Communities</span></span></li></ul>|
||||

## <a name="organize-a-help-desk"></a><span data-ttu-id="a76cd-204">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="a76cd-204">Organize a help desk</span></span>

<span data-ttu-id="a76cd-205">在支援您的支援人員的檔、原則及流程上共同作業。</span><span class="sxs-lookup"><span data-stu-id="a76cd-205">Collaborate on documentation, policy, and processes that support your helpdesk.</span></span> <span data-ttu-id="a76cd-206">整合現有的票證發放系統，或使用我們的範本來管理要求。</span><span class="sxs-lookup"><span data-stu-id="a76cd-206">Integrate your existing ticketing system or use our template to manage requests.</span></span>

| <span data-ttu-id="a76cd-207">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="a76cd-207">Base template type</span></span> |<span data-ttu-id="a76cd-208">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a76cd-208">baseTemplateId</span></span>| <span data-ttu-id="a76cd-209">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="a76cd-209">Properties that come with this base template</span></span> |
| ------------------|--|------------------------------------------------------------|
|<span data-ttu-id="a76cd-210">組織技術支援中心</span><span class="sxs-lookup"><span data-stu-id="a76cd-210">Organize help desk</span></span>|`com.microsoft.teams.template.OrganizeHelpDesk`| <span data-ttu-id="a76cd-211">管道</span><span class="sxs-lookup"><span data-stu-id="a76cd-211">Channels:</span></span><ul><li><span data-ttu-id="a76cd-212">一般</span><span class="sxs-lookup"><span data-stu-id="a76cd-212">General</span></span></li><li><span data-ttu-id="a76cd-213">公告</span><span class="sxs-lookup"><span data-stu-id="a76cd-213">Announcements</span></span></li><li><span data-ttu-id="a76cd-214">常見問題集</span><span class="sxs-lookup"><span data-stu-id="a76cd-214">FAQ</span></span></li></ul><span data-ttu-id="a76cd-215">應用</span><span class="sxs-lookup"><span data-stu-id="a76cd-215">Apps:</span></span><ul><li><span data-ttu-id="a76cd-216">Wiki</span><span class="sxs-lookup"><span data-stu-id="a76cd-216">Wiki</span></span></li><li><span data-ttu-id="a76cd-217">OneNote</span><span class="sxs-lookup"><span data-stu-id="a76cd-217">OneNote</span></span></li></ul> |
||||
