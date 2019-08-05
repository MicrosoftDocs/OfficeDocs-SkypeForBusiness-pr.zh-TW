---
title: 在零售中開始使用團隊範本
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用團隊範本來建立專為零售商需求而設計的小組結構。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181641"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="e2390-103">在零售中開始使用團隊範本</span><span class="sxs-lookup"><span data-stu-id="e2390-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="e2390-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本, 快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="e2390-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e2390-105">團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="e2390-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="e2390-106">您可以使用團隊範本快速建立適用于零售商的團隊類型, 並在整個組織中進行部署。</span><span class="sxs-lookup"><span data-stu-id="e2390-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="e2390-107">您也可以延伸團隊範本, 建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="e2390-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="e2390-108">在本文中, 我們將介紹每個團隊範本, 以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="e2390-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="e2390-109">如果您負責規劃、部署及管理多個零售組織中的多個小組, 本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="e2390-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span>

<span data-ttu-id="e2390-110">若要深入瞭解小組範本的整體資訊, 請參閱[開始使用團隊範本](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="e2390-110">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="e2390-111">商店範本</span><span class="sxs-lookup"><span data-stu-id="e2390-111">Store template</span></span>

<span data-ttu-id="e2390-112">商店範本非常適合用來建立小組代表個別的零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="e2390-112">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="e2390-113">您可以使用 [商店範本], 為貴組織中的每個零售商店位置建立小組。</span><span class="sxs-lookup"><span data-stu-id="e2390-113">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="e2390-114">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="e2390-114">Base template type</span></span> | <span data-ttu-id="e2390-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e2390-115">baseTemplateId</span></span> | <span data-ttu-id="e2390-116">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="e2390-116">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="e2390-117">面向</span><span class="sxs-lookup"><span data-stu-id="e2390-117">Retail -</span></span> <br><span data-ttu-id="e2390-118">存放</span><span class="sxs-lookup"><span data-stu-id="e2390-118">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="e2390-119">管道</span><span class="sxs-lookup"><span data-stu-id="e2390-119">Channels</span></span> <ul><li><span data-ttu-id="e2390-120">倒班切換\*</span><span class="sxs-lookup"><span data-stu-id="e2390-120">Shifts handoff\*</span></span></li><li><span data-ttu-id="e2390-121">教學\*</span><span class="sxs-lookup"><span data-stu-id="e2390-121">Learning\*</span></span></li></ul><span data-ttu-id="e2390-122">\*自動將通道</span><span class="sxs-lookup"><span data-stu-id="e2390-122">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="e2390-123">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="e2390-123">Team properties</span></span> <ul><li><span data-ttu-id="e2390-124">將團隊可見度設定為 Public</span><span class="sxs-lookup"><span data-stu-id="e2390-124">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="e2390-125">成員許可權</span><span class="sxs-lookup"><span data-stu-id="e2390-125">Member permissions</span></span> <ul><li><span data-ttu-id="e2390-126">無法建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="e2390-126">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="e2390-127">無法新增/移除 app</span><span class="sxs-lookup"><span data-stu-id="e2390-127">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="e2390-128">無法建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="e2390-128">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="e2390-129">無法建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="e2390-129">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="e2390-130">為您的組織自訂商店範本的建議方式:</span><span class="sxs-lookup"><span data-stu-id="e2390-130">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="e2390-131">如果您的組織在每個商店中都有部門, 請為每個部門新增頻道。</span><span class="sxs-lookup"><span data-stu-id="e2390-131">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="e2390-132">這將有利於在部門內進行通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="e2390-132">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="e2390-133">如果您的組織有任何內部網站 (例如, SharePoint 網站), 請考慮將其固定為相關團隊頻道中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e2390-133">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="e2390-134">請參閱[開始使用團隊範本](get-started-with-teams-templates.md)取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="e2390-134">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="e2390-135">Manager 共同工作範本</span><span class="sxs-lookup"><span data-stu-id="e2390-135">Manager Collaboration template</span></span>

<span data-ttu-id="e2390-136">Manager 共同工作範本是根據零售商的需求而設計的另一個團隊範本。</span><span class="sxs-lookup"><span data-stu-id="e2390-136">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="e2390-137">Manager 共同工作範本適用于為一組主管建立小組, 以便在商店/地區等共同作業。例如, 如果您的組織有地區, 您可以為加利福尼亞地區建立經理共同作業小組, 並包含該地區的所有書店管理員, 以及該地區的地區經理。</span><span class="sxs-lookup"><span data-stu-id="e2390-137">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="e2390-138">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="e2390-138">Base template type</span></span> | <span data-ttu-id="e2390-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e2390-139">baseTemplateId</span></span> | <span data-ttu-id="e2390-140">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="e2390-140">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="e2390-141">面向</span><span class="sxs-lookup"><span data-stu-id="e2390-141">Retail -</span></span> <br><span data-ttu-id="e2390-142">存放</span><span class="sxs-lookup"><span data-stu-id="e2390-142">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="e2390-143">管道</span><span class="sxs-lookup"><span data-stu-id="e2390-143">Channels</span></span> <ul><li><span data-ttu-id="e2390-144">作業\*</span><span class="sxs-lookup"><span data-stu-id="e2390-144">Operations\*</span></span></li><li><span data-ttu-id="e2390-145">教學\*</span><span class="sxs-lookup"><span data-stu-id="e2390-145">Learning\*</span></span></li></ul><span data-ttu-id="e2390-146">\*自動將通道</span><span class="sxs-lookup"><span data-stu-id="e2390-146">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="e2390-147">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="e2390-147">Team properties</span></span> <ul><li><span data-ttu-id="e2390-148">[團隊可見度] 設定為 [私人]</span><span class="sxs-lookup"><span data-stu-id="e2390-148">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="e2390-149">成員許可權</span><span class="sxs-lookup"><span data-stu-id="e2390-149">Member permissions</span></span> <ul><li><span data-ttu-id="e2390-150">可以建立/更新/刪除頻道</span><span class="sxs-lookup"><span data-stu-id="e2390-150">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="e2390-151">可以新增/移除 app</span><span class="sxs-lookup"><span data-stu-id="e2390-151">Can add/remove apps</span></span> </li><li><span data-ttu-id="e2390-152">可以建立/更新/移除索引標籤</span><span class="sxs-lookup"><span data-stu-id="e2390-152">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="e2390-153">可以建立/更新/移除連接器</span><span class="sxs-lookup"><span data-stu-id="e2390-153">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="e2390-154">為您的組織自訂管理員共同工作範本的建議方式:</span><span class="sxs-lookup"><span data-stu-id="e2390-154">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="e2390-155">如果您的組織擁有與主管相關的任何內部網站 (例如, SharePoint 網站), 請考慮將其固定為相關小組頻道中的索引標籤 (請參閱[這裡](get-started-with-teams-templates.md)的檔以取得指示)。</span><span class="sxs-lookup"><span data-stu-id="e2390-155">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>