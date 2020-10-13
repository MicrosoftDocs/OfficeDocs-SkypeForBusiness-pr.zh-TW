---
title: 在零售中開始使用團隊範本
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
description: 瞭解如何使用團隊範本，透過提供預先定義的設定、通道及預先安裝的應用程式，來建立專為零售商需求而設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424633"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="9b94a-103">在零售中開始使用團隊範本</span><span class="sxs-lookup"><span data-stu-id="9b94a-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="9b94a-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="9b94a-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9b94a-105">團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="9b94a-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="9b94a-106">您可以使用團隊範本快速建立適用于零售商的團隊類型，並在整個組織中進行部署。</span><span class="sxs-lookup"><span data-stu-id="9b94a-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="9b94a-107">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="9b94a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="9b94a-108">在本文中，我們將介紹每個團隊範本，並建議如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="9b94a-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="9b94a-109">如果您負責規劃、部署及管理多個零售組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="9b94a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="9b94a-110">您已在組織中部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="9b94a-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="9b94a-111">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9b94a-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="9b94a-112">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="9b94a-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="9b94a-113">商店範本</span><span class="sxs-lookup"><span data-stu-id="9b94a-113">Store template</span></span>

<span data-ttu-id="9b94a-114">商店範本非常適合用來建立小組代表個別的零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="9b94a-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="9b94a-115">您可以使用 [商店範本]，為貴組織中的每個零售商店位置建立小組。</span><span class="sxs-lookup"><span data-stu-id="9b94a-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="9b94a-116">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="9b94a-116">Base template type</span></span> | <span data-ttu-id="9b94a-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9b94a-117">baseTemplateId</span></span> | <span data-ttu-id="9b94a-118">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="9b94a-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="9b94a-119">面向</span><span class="sxs-lookup"><span data-stu-id="9b94a-119">Retail -</span></span> <br><span data-ttu-id="9b94a-120">商店</span><span class="sxs-lookup"><span data-stu-id="9b94a-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="9b94a-121">頻道</span><span class="sxs-lookup"><span data-stu-id="9b94a-121">Channels</span></span> <ul><li><span data-ttu-id="9b94a-122">倒班切換\*</span><span class="sxs-lookup"><span data-stu-id="9b94a-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="9b94a-123">教學\*</span><span class="sxs-lookup"><span data-stu-id="9b94a-123">Learning\*</span></span></li></ul><span data-ttu-id="9b94a-124">\*自動將通道</span><span class="sxs-lookup"><span data-stu-id="9b94a-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="9b94a-125">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="9b94a-125">Team properties</span></span> <ul><li><span data-ttu-id="9b94a-126">將團隊可見度設定為 Public</span><span class="sxs-lookup"><span data-stu-id="9b94a-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="9b94a-127">成員許可權</span><span class="sxs-lookup"><span data-stu-id="9b94a-127">Member permissions</span></span> <ul><li><span data-ttu-id="9b94a-128">無法建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="9b94a-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="9b94a-129">無法新增/移除 app</span><span class="sxs-lookup"><span data-stu-id="9b94a-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="9b94a-130">無法建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="9b94a-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="9b94a-131">無法建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="9b94a-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="9b94a-132">為您的組織自訂商店範本的建議方式：</span><span class="sxs-lookup"><span data-stu-id="9b94a-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="9b94a-133">如果您的組織在每個商店中都有部門，請為每個部門新增頻道。</span><span class="sxs-lookup"><span data-stu-id="9b94a-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="9b94a-134">新增通道有利於在部門中進行通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="9b94a-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="9b94a-135">如果您的組織有任何內部網站 (例如，SharePoint 網站) ，請考慮將它們釘選為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9b94a-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="9b94a-136">請參閱 [開始使用團隊範本](get-started-with-teams-templates.md) 取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="9b94a-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="9b94a-137">Manager 共同工作範本</span><span class="sxs-lookup"><span data-stu-id="9b94a-137">Manager Collaboration template</span></span>

<span data-ttu-id="9b94a-138">Manager 共同工作範本是根據零售商的需求而設計的另一個團隊範本。</span><span class="sxs-lookup"><span data-stu-id="9b94a-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="9b94a-139">管理員共同工作範本適用于為一組主管建立小組，以便在各個商店/地區共同作業等等。</span><span class="sxs-lookup"><span data-stu-id="9b94a-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="9b94a-140">例如，如果您的組織有地區，您可以為加利福尼亞地區建立經理共同作業小組，並包含該地區的所有書店管理員，以及該地區的地區經理。</span><span class="sxs-lookup"><span data-stu-id="9b94a-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="9b94a-141">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="9b94a-141">Base template type</span></span> | <span data-ttu-id="9b94a-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9b94a-142">baseTemplateId</span></span> | <span data-ttu-id="9b94a-143">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="9b94a-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="9b94a-144">面向</span><span class="sxs-lookup"><span data-stu-id="9b94a-144">Retail -</span></span> <br><span data-ttu-id="9b94a-145">商店</span><span class="sxs-lookup"><span data-stu-id="9b94a-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="9b94a-146">頻道</span><span class="sxs-lookup"><span data-stu-id="9b94a-146">Channels</span></span> <ul><li><span data-ttu-id="9b94a-147">營運\*</span><span class="sxs-lookup"><span data-stu-id="9b94a-147">Operations\*</span></span></li><li><span data-ttu-id="9b94a-148">教學\*</span><span class="sxs-lookup"><span data-stu-id="9b94a-148">Learning\*</span></span></li></ul><span data-ttu-id="9b94a-149">\*自動將通道</span><span class="sxs-lookup"><span data-stu-id="9b94a-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="9b94a-150">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="9b94a-150">Team properties</span></span> <ul><li><span data-ttu-id="9b94a-151">[團隊可見度] 設定為 [私人]</span><span class="sxs-lookup"><span data-stu-id="9b94a-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="9b94a-152">成員許可權</span><span class="sxs-lookup"><span data-stu-id="9b94a-152">Member permissions</span></span> <ul><li><span data-ttu-id="9b94a-153">可以建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="9b94a-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="9b94a-154">可以新增/移除 app</span><span class="sxs-lookup"><span data-stu-id="9b94a-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="9b94a-155">可以建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="9b94a-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="9b94a-156">可以建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="9b94a-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="9b94a-157">為您的組織自訂管理員共同工作範本的建議方式：</span><span class="sxs-lookup"><span data-stu-id="9b94a-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="9b94a-158">如果您的組織有任何內部網站（例如 SharePoint 網站）與管理員相關，請考慮將其固定為相關小組頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9b94a-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="9b94a-159">您可以參閱 [Microsoft 團隊範本檔](get-started-with-teams-templates.md) ，以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="9b94a-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="9b94a-160">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="9b94a-160">How to use first party templates</span></span>

<span data-ttu-id="9b94a-161">若要使用這些範本，請將申請主體中的 [template@odata. bind "屬性從 [標準] 變更為上述 TemplateIDs。</span><span class="sxs-lookup"><span data-stu-id="9b94a-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="9b94a-162">如需如何部署團隊範本的詳細資訊，請參閱 Microsoft Graph 文章，瞭解如何 [建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="9b94a-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="9b94a-163">範本中的頻道會自動建立在 [一般] 索引標籤底下。</span><span class="sxs-lookup"><span data-stu-id="9b94a-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="9b94a-164">範例：儲存範本延伸腳本</span><span class="sxs-lookup"><span data-stu-id="9b94a-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="9b94a-165">關聯主題</span><span class="sxs-lookup"><span data-stu-id="9b94a-165">Relate topic</span></span>

[<span data-ttu-id="9b94a-166">在系統管理中心快速開始使用團隊範本</span><span class="sxs-lookup"><span data-stu-id="9b94a-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
