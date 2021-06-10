---
title: 開始使用零售團隊範本
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用小組範本，提供預先定義的設定、頻道和預先安裝的應用程式，以建立專為零售商需求設計的團隊結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684551"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="b2af5-103">使用零售小組範本建立團隊</span><span class="sxs-lookup"><span data-stu-id="b2af5-103">Create a team using retail team templates</span></span>

<span data-ttu-id="b2af5-104">Microsoft 小組範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="b2af5-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b2af5-105">小組範本有預先建立的團隊結構定義，專為零售商需求所設計。</span><span class="sxs-lookup"><span data-stu-id="b2af5-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="b2af5-106">您可以使用小組範本，快速建立適合零售商的團隊類型，並在整個組織中部署。</span><span class="sxs-lookup"><span data-stu-id="b2af5-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="b2af5-107">您也可以擴充小組範本，以建立符合您特定組織需求的團隊。</span><span class="sxs-lookup"><span data-stu-id="b2af5-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b2af5-108">本文將介紹每個小組範本，並建議如何使用這些範本。</span><span class="sxs-lookup"><span data-stu-id="b2af5-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="b2af5-109">如果您負責規劃、部署和管理整個零售組織的多個團隊，本文適合您。</span><span class="sxs-lookup"><span data-stu-id="b2af5-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="b2af5-110">您已在組織中部署 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="b2af5-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b2af5-111">如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b2af5-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="b2af5-112">若要深入瞭解一般小組範本，請參閱開始使用 [小組範本](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="b2af5-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="b2af5-113">誰</span><span class="sxs-lookup"><span data-stu-id="b2af5-113">Who</span></span> | <span data-ttu-id="b2af5-114">使用方法：</span><span class="sxs-lookup"><span data-stu-id="b2af5-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="b2af5-115">系統管理員和 IT 專業人員</span><span class="sxs-lookup"><span data-stu-id="b2af5-115">Admins and IT Professionals</span></span> | <span data-ttu-id="b2af5-116">[使用 Teams系統](#use-the-team-templates-in-the-teams-admin-center)管理中心，根據零售小組範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="b2af5-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="b2af5-117">開發人員和系統整合者</span><span class="sxs-lookup"><span data-stu-id="b2af5-117">Developers and systems integrators</span></span> | <span data-ttu-id="b2af5-118">[使用 Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph)根據零售小組範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="b2af5-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="b2af5-119">使用系統管理中心Teams範本</span><span class="sxs-lookup"><span data-stu-id="b2af5-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="b2af5-120">組織商店</span><span class="sxs-lookup"><span data-stu-id="b2af5-120">Organize a store</span></span>

<span data-ttu-id="b2af5-121">將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。</span><span class="sxs-lookup"><span data-stu-id="b2af5-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="b2af5-122">整合其他應用程式，以簡化班次的開始與結束程序。</span><span class="sxs-lookup"><span data-stu-id="b2af5-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="b2af5-123">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="b2af5-123">Base template type</span></span> |<span data-ttu-id="b2af5-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2af5-124">baseTemplateId</span></span> | <span data-ttu-id="b2af5-125">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b2af5-126">組織商店</span><span class="sxs-lookup"><span data-stu-id="b2af5-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="b2af5-127">頻道：</span><span class="sxs-lookup"><span data-stu-id="b2af5-127">Channels:</span></span> <ul><li><span data-ttu-id="b2af5-128">一般</span><span class="sxs-lookup"><span data-stu-id="b2af5-128">General</span></span><li><span data-ttu-id="b2af5-129">班次交班</span><span class="sxs-lookup"><span data-stu-id="b2af5-129">Shift handoff</span></span></li><li><span data-ttu-id="b2af5-130">學習</span><span class="sxs-lookup"><span data-stu-id="b2af5-130">Learning</span></span></li></ul> <span data-ttu-id="b2af5-131">應用程式：</span><span class="sxs-lookup"><span data-stu-id="b2af5-131">Apps:</span></span> <ul><li><span data-ttu-id="b2af5-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="b2af5-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="b2af5-133">主管共同作業</span><span class="sxs-lookup"><span data-stu-id="b2af5-133">Manager Collaboration</span></span>

<span data-ttu-id="b2af5-134">管理員共同合作範本是建立團隊，讓一組主管跨市/地區共同合作的理想範本。例如，如果貴組織有地區，您可以為加州地區建立管理員共同合作小組，並包含該區域的所有商店管理員，以及該地區的地區管理員。</span><span class="sxs-lookup"><span data-stu-id="b2af5-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="b2af5-135">範本類型</span><span class="sxs-lookup"><span data-stu-id="b2af5-135">Base template type</span></span>| <span data-ttu-id="b2af5-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2af5-136">baseTemplateId</span></span> | <span data-ttu-id="b2af5-137">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="b2af5-138">零售 - 主管共同作業</span><span class="sxs-lookup"><span data-stu-id="b2af5-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="b2af5-139">頻道：</span><span class="sxs-lookup"><span data-stu-id="b2af5-139">Channels:</span></span> <ul><li><span data-ttu-id="b2af5-140">一般</span><span class="sxs-lookup"><span data-stu-id="b2af5-140">General</span></span><li><span data-ttu-id="b2af5-141">營運</span><span class="sxs-lookup"><span data-stu-id="b2af5-141">Operations</span></span></li><li><span data-ttu-id="b2af5-142">學習</span><span class="sxs-lookup"><span data-stu-id="b2af5-142">Learning</span></span></li></ul> <span data-ttu-id="b2af5-143">應用程式：</span><span class="sxs-lookup"><span data-stu-id="b2af5-143">Apps:</span></span> <ul><li><span data-ttu-id="b2af5-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="b2af5-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="b2af5-145">使用小組範本與 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b2af5-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="b2af5-146">商店範本</span><span class="sxs-lookup"><span data-stu-id="b2af5-146">Store template</span></span>

<span data-ttu-id="b2af5-147">商店範本很適合用來建立團隊，以代表個體零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="b2af5-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="b2af5-148">使用商店範本，您可以為組織的每個零售商店位置建立團隊。</span><span class="sxs-lookup"><span data-stu-id="b2af5-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="b2af5-149">基礎範本類型</span><span class="sxs-lookup"><span data-stu-id="b2af5-149">Base template type</span></span> | <span data-ttu-id="b2af5-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2af5-150">baseTemplateId</span></span> | <span data-ttu-id="b2af5-151">此基礎範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b2af5-152">零售業 -</span><span class="sxs-lookup"><span data-stu-id="b2af5-152">Retail -</span></span> <br><span data-ttu-id="b2af5-153">商店</span><span class="sxs-lookup"><span data-stu-id="b2af5-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="b2af5-154">頻道</span><span class="sxs-lookup"><span data-stu-id="b2af5-154">Channels</span></span> <ul><li><span data-ttu-id="b2af5-155">班次交班\*</span><span class="sxs-lookup"><span data-stu-id="b2af5-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="b2af5-156">學習\*</span><span class="sxs-lookup"><span data-stu-id="b2af5-156">Learning\*</span></span></li></ul><span data-ttu-id="b2af5-157">\*自動將頻道加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="b2af5-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b2af5-158">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-158">Team properties</span></span> <ul><li><span data-ttu-id="b2af5-159">團隊可見度設定為公開</span><span class="sxs-lookup"><span data-stu-id="b2af5-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="b2af5-160">成員權限</span><span class="sxs-lookup"><span data-stu-id="b2af5-160">Member permissions</span></span> <ul><li><span data-ttu-id="b2af5-161">無法建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="b2af5-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="b2af5-162">無法新增/移除應用程式</span><span class="sxs-lookup"><span data-stu-id="b2af5-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="b2af5-163">無法建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="b2af5-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="b2af5-164">無法建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="b2af5-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b2af5-165">為貴組織自訂商店範本的建議方法：</span><span class="sxs-lookup"><span data-stu-id="b2af5-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="b2af5-166">如果貴組織在每個商店中都有部門，請為每個部門新增頻道。</span><span class="sxs-lookup"><span data-stu-id="b2af5-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="b2af5-167">新增頻道有助於在部門內進行通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="b2af5-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="b2af5-168">如果貴組織有任何內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b2af5-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="b2af5-169">請參閱開始使用 [小組範本以](get-started-with-teams-templates.md) 取得指示。</span><span class="sxs-lookup"><span data-stu-id="b2af5-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="b2af5-170">主管共同作業範本</span><span class="sxs-lookup"><span data-stu-id="b2af5-170">Manager Collaboration template</span></span>

<span data-ttu-id="b2af5-171">Manager 共同合作範本是另一種團隊範本，專為零售商需求所設計。</span><span class="sxs-lookup"><span data-stu-id="b2af5-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="b2af5-172">主管共同作業範本很適合建立團隊，讓一組主管跨商店/地區共同作業等等。</span><span class="sxs-lookup"><span data-stu-id="b2af5-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="b2af5-173">例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。</span><span class="sxs-lookup"><span data-stu-id="b2af5-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="b2af5-174">基礎範本類型</span><span class="sxs-lookup"><span data-stu-id="b2af5-174">Base template type</span></span> | <span data-ttu-id="b2af5-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2af5-175">baseTemplateId</span></span> | <span data-ttu-id="b2af5-176">此基礎範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b2af5-177">零售業 -</span><span class="sxs-lookup"><span data-stu-id="b2af5-177">Retail -</span></span> <br><span data-ttu-id="b2af5-178">商店</span><span class="sxs-lookup"><span data-stu-id="b2af5-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="b2af5-179">頻道</span><span class="sxs-lookup"><span data-stu-id="b2af5-179">Channels</span></span> <ul><li><span data-ttu-id="b2af5-180">作業\*</span><span class="sxs-lookup"><span data-stu-id="b2af5-180">Operations\*</span></span></li><li><span data-ttu-id="b2af5-181">學習\*</span><span class="sxs-lookup"><span data-stu-id="b2af5-181">Learning\*</span></span></li></ul><span data-ttu-id="b2af5-182">\*自動將頻道加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="b2af5-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b2af5-183">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="b2af5-183">Team properties</span></span> <ul><li><span data-ttu-id="b2af5-184">團隊可見度設定為私人</span><span class="sxs-lookup"><span data-stu-id="b2af5-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="b2af5-185">成員權限</span><span class="sxs-lookup"><span data-stu-id="b2af5-185">Member permissions</span></span> <ul><li><span data-ttu-id="b2af5-186">可以建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="b2af5-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="b2af5-187">可以新增/移除應用程式</span><span class="sxs-lookup"><span data-stu-id="b2af5-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="b2af5-188">可以建立/更新/移除定位字元</span><span class="sxs-lookup"><span data-stu-id="b2af5-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="b2af5-189">可以建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="b2af5-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b2af5-190">為貴組織自訂主管共同作業範本的建議方法：</span><span class="sxs-lookup"><span data-stu-id="b2af5-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="b2af5-191">如果貴組織有任何與主管相關的內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b2af5-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="b2af5-192">您可以查看 Microsoft 小組範本檔 [以](get-started-with-teams-templates.md) 尋找相關指示。</span><span class="sxs-lookup"><span data-stu-id="b2af5-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="b2af5-193">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="b2af5-193">How to use first-party templates</span></span>

<span data-ttu-id="b2af5-194">若要使用這些範本，請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateDs。</span><span class="sxs-lookup"><span data-stu-id="b2af5-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="b2af5-195">若要瞭解如何部署小組範本，請參閱 Microsoft Graph如何[建立小組一](/graph/api/team-post?view=graph-rest-beta)文。</span><span class="sxs-lookup"><span data-stu-id="b2af5-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="b2af5-196">範本中的頻道會自動在 [一般] 索引標籤下建立。</span><span class="sxs-lookup"><span data-stu-id="b2af5-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="b2af5-197">範例：商店範本延伸模組指令碼</span><span class="sxs-lookup"><span data-stu-id="b2af5-197">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
