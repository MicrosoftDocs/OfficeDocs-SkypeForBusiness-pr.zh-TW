---
title: 開始使用零售業 Teams 範本
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
description: 了解如何使用 Teams 範本，透過提供預先定義的設定、頻道和預先安裝的應用程式，以建立專為零售商需求設計的團隊結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424633"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="56619-103">開始使用零售業 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="56619-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="56619-104">Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="56619-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="56619-105">Teams 範本具有專為零售商需求設計的團隊結構預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="56619-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="56619-106">您可以使用 Teams 範本快速建立適合零售商的團隊類型，並在整個組織中部署。</span><span class="sxs-lookup"><span data-stu-id="56619-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="56619-107">您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。</span><span class="sxs-lookup"><span data-stu-id="56619-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="56619-108">本文將介紹各個 Teams 範本，並建議如何使用範本。</span><span class="sxs-lookup"><span data-stu-id="56619-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="56619-109">如果您負責規劃、部署和管理整個零售組織的多個團隊，本文適合您。</span><span class="sxs-lookup"><span data-stu-id="56619-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="56619-110">您已在組織中部署 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="56619-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="56619-111">如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="56619-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="56619-112">如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="56619-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="56619-113">商店範本</span><span class="sxs-lookup"><span data-stu-id="56619-113">Store template</span></span>

<span data-ttu-id="56619-114">商店範本很適合用來建立團隊，以代表個體零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="56619-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="56619-115">使用商店範本，您可以為組織的每個零售商店位置建立團隊。</span><span class="sxs-lookup"><span data-stu-id="56619-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="56619-116">基礎範本類型</span><span class="sxs-lookup"><span data-stu-id="56619-116">Base template type</span></span> | <span data-ttu-id="56619-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="56619-117">baseTemplateId</span></span> | <span data-ttu-id="56619-118">此基礎範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="56619-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="56619-119">零售業 -</span><span class="sxs-lookup"><span data-stu-id="56619-119">Retail -</span></span> <br><span data-ttu-id="56619-120">商店</span><span class="sxs-lookup"><span data-stu-id="56619-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="56619-121">頻道</span><span class="sxs-lookup"><span data-stu-id="56619-121">Channels</span></span> <ul><li><span data-ttu-id="56619-122">班次交班\*</span><span class="sxs-lookup"><span data-stu-id="56619-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="56619-123">學習\*</span><span class="sxs-lookup"><span data-stu-id="56619-123">Learning\*</span></span></li></ul><span data-ttu-id="56619-124">\*自動將頻道加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="56619-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="56619-125">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="56619-125">Team properties</span></span> <ul><li><span data-ttu-id="56619-126">團隊可見度設定為公開</span><span class="sxs-lookup"><span data-stu-id="56619-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="56619-127">成員權限</span><span class="sxs-lookup"><span data-stu-id="56619-127">Member permissions</span></span> <ul><li><span data-ttu-id="56619-128">無法建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="56619-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="56619-129">無法新增/移除應用程式</span><span class="sxs-lookup"><span data-stu-id="56619-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="56619-130">無法建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="56619-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="56619-131">無法建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="56619-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="56619-132">為貴組織自訂商店範本的建議方法：</span><span class="sxs-lookup"><span data-stu-id="56619-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="56619-133">如果貴組織在每個商店中都有部門，請為每個部門新增頻道。</span><span class="sxs-lookup"><span data-stu-id="56619-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="56619-134">新增頻道有助於在部門內進行通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="56619-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="56619-135">如果貴組織有任何內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="56619-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="56619-136">請參閱 [Teams 範本入門](get-started-with-teams-templates.md) 以取得指示。</span><span class="sxs-lookup"><span data-stu-id="56619-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="56619-137">主管共同作業範本</span><span class="sxs-lookup"><span data-stu-id="56619-137">Manager Collaboration template</span></span>

<span data-ttu-id="56619-138">主管共同作業範本是專為零售商需求設計的另一個 Teams 範本。</span><span class="sxs-lookup"><span data-stu-id="56619-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="56619-139">主管共同作業範本很適合建立團隊，讓一組主管跨商店/地區共同作業等等。</span><span class="sxs-lookup"><span data-stu-id="56619-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="56619-140">例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。</span><span class="sxs-lookup"><span data-stu-id="56619-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="56619-141">基礎範本類型</span><span class="sxs-lookup"><span data-stu-id="56619-141">Base template type</span></span> | <span data-ttu-id="56619-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="56619-142">baseTemplateId</span></span> | <span data-ttu-id="56619-143">此基礎範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="56619-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="56619-144">零售業 -</span><span class="sxs-lookup"><span data-stu-id="56619-144">Retail -</span></span> <br><span data-ttu-id="56619-145">商店</span><span class="sxs-lookup"><span data-stu-id="56619-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="56619-146">頻道</span><span class="sxs-lookup"><span data-stu-id="56619-146">Channels</span></span> <ul><li><span data-ttu-id="56619-147">作業\*</span><span class="sxs-lookup"><span data-stu-id="56619-147">Operations\*</span></span></li><li><span data-ttu-id="56619-148">學習\*</span><span class="sxs-lookup"><span data-stu-id="56619-148">Learning\*</span></span></li></ul><span data-ttu-id="56619-149">\*自動將頻道加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="56619-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="56619-150">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="56619-150">Team properties</span></span> <ul><li><span data-ttu-id="56619-151">團隊可見度設定為私人</span><span class="sxs-lookup"><span data-stu-id="56619-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="56619-152">成員權限</span><span class="sxs-lookup"><span data-stu-id="56619-152">Member permissions</span></span> <ul><li><span data-ttu-id="56619-153">可以建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="56619-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="56619-154">可以新增/移除應用程式</span><span class="sxs-lookup"><span data-stu-id="56619-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="56619-155">可以建立/更新/移除定位字元</span><span class="sxs-lookup"><span data-stu-id="56619-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="56619-156">可以建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="56619-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="56619-157">為貴組織自訂主管共同作業範本的建議方法：</span><span class="sxs-lookup"><span data-stu-id="56619-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="56619-158">如果貴組織有任何與主管相關的內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="56619-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="56619-159">您可以查看 [Microsoft Teams 範本文件](get-started-with-teams-templates.md)的指示。</span><span class="sxs-lookup"><span data-stu-id="56619-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="56619-160">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="56619-160">How to use first party templates</span></span>

<span data-ttu-id="56619-161">若要使用這些範本，請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateDs。</span><span class="sxs-lookup"><span data-stu-id="56619-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="56619-162">若要了解如何部署 Teams 範本，請參閱 Microsoft Graph 文章，以了解如何[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="56619-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="56619-163">範本中的頻道會自動在 [一般] 索引標籤下建立。</span><span class="sxs-lookup"><span data-stu-id="56619-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="56619-164">範例：商店範本延伸模組指令碼</span><span class="sxs-lookup"><span data-stu-id="56619-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="56619-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="56619-165">Relate topic</span></span>

[<span data-ttu-id="56619-166">在系統管理中心中開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="56619-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
