---
title: Teams Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 使用Microsoft Teams Microsoft Graph內建的預先定義範本，以快速且輕鬆地為中小型企業建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116991"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="fa637-103">Teams Microsoft Graph中小企業版中內建的範本</span><span class="sxs-lookup"><span data-stu-id="fa637-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="fa637-104">Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="fa637-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="fa637-105">對於中小型企業而言，範本可能特別強大，因為它們可協助系統管理員在Teams部署。</span><span class="sxs-lookup"><span data-stu-id="fa637-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="fa637-106">範本也可以協助引導使用者，並開始使用Teams功能。</span><span class="sxs-lookup"><span data-stu-id="fa637-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="fa637-107">如果您負責規劃、部署及管理整個組織的多個團隊，本文適合您閱讀。</span><span class="sxs-lookup"><span data-stu-id="fa637-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="fa637-108">我們目前提供三個第一方 SMB 範本，您可以針對各種情況使用。</span><span class="sxs-lookup"><span data-stu-id="fa637-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="fa637-109">所有範本都會建立 *私人* Teams。</span><span class="sxs-lookup"><span data-stu-id="fa637-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="fa637-110">一旦建立Teams準備好要推出至貴組織，您可以設定隱私權為 *組織* 範圍或公用 *，並* 在適當時設定。</span><span class="sxs-lookup"><span data-stu-id="fa637-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="fa637-111">如需深入了解一般小組範本，請參閱 [Teams 範本入門](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="fa637-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="fa637-112">Company-Wide範本</span><span class="sxs-lookup"><span data-stu-id="fa637-112">Company-Wide template</span></span>
<span data-ttu-id="fa637-113">Company-Wide範本適用于與整個公司相關的通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="fa637-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="fa637-114">您可以使用一般頻道來發佈全公司的公告、產業新聞或主管文章。</span><span class="sxs-lookup"><span data-stu-id="fa637-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="fa637-115">人力資源頻道是整合所有人力資源相關活動的地方，例如職位、新員工入職、訓練及發展。</span><span class="sxs-lookup"><span data-stu-id="fa637-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="fa637-116">Fun Stuff 頻道提供所有隨機且有趣的文章的社交平臺。</span><span class="sxs-lookup"><span data-stu-id="fa637-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="fa637-117">範本類型</span><span class="sxs-lookup"><span data-stu-id="fa637-117">Base template type</span></span>  | <span data-ttu-id="fa637-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fa637-118">baseTemplateId</span></span> | <span data-ttu-id="fa637-119">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="fa637-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="fa637-120">SMB -</span></span> <br><span data-ttu-id="fa637-121">全公司</span><span class="sxs-lookup"><span data-stu-id="fa637-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="fa637-122">頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-122">Channels</span></span> <ul><li><span data-ttu-id="fa637-123">一般\*</span><span class="sxs-lookup"><span data-stu-id="fa637-123">General\*</span></span></li><li><span data-ttu-id="fa637-124">人力資源\*</span><span class="sxs-lookup"><span data-stu-id="fa637-124">Human Resources\*</span></span></li><li><span data-ttu-id="fa637-125">有趣的專案\*</span><span class="sxs-lookup"><span data-stu-id="fa637-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="fa637-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="fa637-126">Apps</span></span><ul><li><span data-ttu-id="fa637-127">公司入口網站 (釘到人力資源頻道連結 **的網站)**</span><span class="sxs-lookup"><span data-stu-id="fa637-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="fa637-128">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-128">Team properties</span></span> <ul><li><span data-ttu-id="fa637-129">團隊可見度設定為私人</span><span class="sxs-lookup"><span data-stu-id="fa637-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="fa637-130">\*自動最愛的頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="fa637-131">若要從Company-Wide範本中採用預設值來建立團隊，請提供要求內文中小組物件的 JSON 標記法。</span><span class="sxs-lookup"><span data-stu-id="fa637-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="fa637-132">若要深入瞭解如何部署Teams範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="fa637-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="fa637-133">請求</span><span class="sxs-lookup"><span data-stu-id="fa637-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="fa637-134">主管小組範本</span><span class="sxs-lookup"><span data-stu-id="fa637-134">Executive Team template</span></span>

<span data-ttu-id="fa637-135">執行小組範本是建立一個團隊，讓公司高主管在年度優先順序、財務預算、策略計畫及頂級客戶等公司計畫上溝通及共同合作的理想範本。</span><span class="sxs-lookup"><span data-stu-id="fa637-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="fa637-136">此範本隨附私人 *頻道* ，可邀請特定主題的選取使用者。</span><span class="sxs-lookup"><span data-stu-id="fa637-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="fa637-137">範本類型</span><span class="sxs-lookup"><span data-stu-id="fa637-137">Base template type</span></span>  | <span data-ttu-id="fa637-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fa637-138">baseTemplateId</span></span> | <span data-ttu-id="fa637-139">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="fa637-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="fa637-140">SMB -</span></span> <br><span data-ttu-id="fa637-141">高主管小組</span><span class="sxs-lookup"><span data-stu-id="fa637-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="fa637-142">頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-142">Channels</span></span> <ul><li><span data-ttu-id="fa637-143">一般\*</span><span class="sxs-lookup"><span data-stu-id="fa637-143">General\*</span></span></li><li><span data-ttu-id="fa637-144">私人 \*</span><span class="sxs-lookup"><span data-stu-id="fa637-144">Private \*</span></span></li></ul> <span data-ttu-id="fa637-145">應用程式</span><span class="sxs-lookup"><span data-stu-id="fa637-145">Apps</span></span><ul><li><span data-ttu-id="fa637-146">OneNote (釘 **到私人頻道**) </span><span class="sxs-lookup"><span data-stu-id="fa637-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="fa637-147">Planner (釘到私人 **頻道**) </span><span class="sxs-lookup"><span data-stu-id="fa637-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="fa637-148">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-148">Team properties</span></span> <ul><li><span data-ttu-id="fa637-149">團隊可見度設定為私人</span><span class="sxs-lookup"><span data-stu-id="fa637-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="fa637-150">\*自動最愛的頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="fa637-151">若要從預先定義的範本中採用預設值來建立主管團隊，請提供要求內文中團隊物件的 JSON 標記法。</span><span class="sxs-lookup"><span data-stu-id="fa637-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="fa637-152">若要深入瞭解如何部署Teams範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="fa637-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="fa637-153">請求</span><span class="sxs-lookup"><span data-stu-id="fa637-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="fa637-154">部門小組範本</span><span class="sxs-lookup"><span data-stu-id="fa637-154">Departmental Team template</span></span>

<span data-ttu-id="fa637-155">部門小組範本可用於為個別部門或專案建立團隊。</span><span class="sxs-lookup"><span data-stu-id="fa637-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="fa637-156">財務小組範本適合適用于財務小組成員及執行小組成員內的所有文章、公告，以及每日共同合作及溝通。</span><span class="sxs-lookup"><span data-stu-id="fa637-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="fa637-157">範本隨附私人 *頻道* ，可邀請特定主題的選取使用者。</span><span class="sxs-lookup"><span data-stu-id="fa637-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="fa637-158">我們也提供以下腳本給財務小組，可用來將範本新增、刪除或編輯至您的喜好，以將範本延伸到其他部門或特定專案。</span><span class="sxs-lookup"><span data-stu-id="fa637-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="fa637-159">例如，如果您有行銷部門，可以將團隊從財務重新命名為行銷，以建立新的行銷小組，以調整腳本 \*\*</span><span class="sxs-lookup"><span data-stu-id="fa637-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="fa637-160">範本類型</span><span class="sxs-lookup"><span data-stu-id="fa637-160">Base template type</span></span> | <span data-ttu-id="fa637-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fa637-161">baseTemplateId</span></span> | <span data-ttu-id="fa637-162">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="fa637-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="fa637-163">SMB -</span></span> <br><span data-ttu-id="fa637-164">財務</span><span class="sxs-lookup"><span data-stu-id="fa637-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="fa637-165">頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-165">Channels</span></span> <ul><li><span data-ttu-id="fa637-166">一般\*</span><span class="sxs-lookup"><span data-stu-id="fa637-166">General\*</span></span></li><li><span data-ttu-id="fa637-167">私人 \*</span><span class="sxs-lookup"><span data-stu-id="fa637-167">Private \*</span></span></li></ul><br> <span data-ttu-id="fa637-168">應用程式</span><span class="sxs-lookup"><span data-stu-id="fa637-168">Apps</span></span><ul><li><span data-ttu-id="fa637-169">OneNote (釘 **到私人頻道**) </span><span class="sxs-lookup"><span data-stu-id="fa637-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="fa637-170">Planner (釘到私人 **頻道**) </span><span class="sxs-lookup"><span data-stu-id="fa637-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="fa637-171">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="fa637-171">Team properties</span></span> <ul><li><span data-ttu-id="fa637-172">團隊可見度設定為私人</span><span class="sxs-lookup"><span data-stu-id="fa637-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="fa637-173">\*自動最愛的頻道</span><span class="sxs-lookup"><span data-stu-id="fa637-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="fa637-174">若要從預先定義的範本中採用預設值來建立財務小組，請提供要求內文中小組物件的 JSON 標記法。</span><span class="sxs-lookup"><span data-stu-id="fa637-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="fa637-175">若要深入瞭解如何部署Teams範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="fa637-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="fa637-176">請求</span><span class="sxs-lookup"><span data-stu-id="fa637-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="fa637-177">範例：財務小組範本擴充腳本</span><span class="sxs-lookup"><span data-stu-id="fa637-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="fa637-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa637-178">Related topics</span></span>

- [<span data-ttu-id="fa637-179">在系統管理Teams中開始使用範本</span><span class="sxs-lookup"><span data-stu-id="fa637-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="fa637-180">開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="fa637-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="fa637-181">[在預覽 (](/graph/api/team-post?view=graph-rest-beta) 中建立) </span><span class="sxs-lookup"><span data-stu-id="fa637-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>