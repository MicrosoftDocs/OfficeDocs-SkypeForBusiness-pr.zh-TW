---
title: 使用 Microsoft Graph 建立的中小型企業團隊範本
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
description: 使用 microsoft Graph 中建的預先定義範本，快速且輕鬆地為中小型企業建立小組。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9807e7f3694731af398abd83189698420ec36b8a
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506146"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="0af95-103">專為中小型企業的 Microsoft Graph 所建的團隊範本</span><span class="sxs-lookup"><span data-stu-id="0af95-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="0af95-104">Microsoft 團隊範本可讓您透過提供預先定義的設定、頻道及預先安裝應用程式範本，快速且輕鬆地建立小組。</span><span class="sxs-lookup"><span data-stu-id="0af95-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="0af95-105">在中小型企業中，範本特別強大，因為它們可協助管理員快速地在組織中部署團隊。</span><span class="sxs-lookup"><span data-stu-id="0af95-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="0af95-106">範本也可協助使用者，並快速開始使用團隊。</span><span class="sxs-lookup"><span data-stu-id="0af95-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="0af95-107">如果您負責規劃、部署及管理整個組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="0af95-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="0af95-108">我們目前提供三個第一方的 SMB 範本，您可以在各種情況下利用這些範本。</span><span class="sxs-lookup"><span data-stu-id="0af95-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="0af95-109">所有範本都會建立*私人*團隊。</span><span class="sxs-lookup"><span data-stu-id="0af95-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="0af95-110">在您建立好團隊並準備好要向您的組織中推出後，您就可以視需要將隱私權設定為「*組織內*」或「*公開*」。</span><span class="sxs-lookup"><span data-stu-id="0af95-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="0af95-111">若要深入瞭解小組範本的整體資訊，請參閱[開始使用團隊範本](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="0af95-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="0af95-112">整個公司的範本</span><span class="sxs-lookup"><span data-stu-id="0af95-112">Company-Wide template</span></span>
<span data-ttu-id="0af95-113">公司範圍的範本適用于與整個公司相關的溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="0af95-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="0af95-114">您可以在全公司的宣告、行業新聞或主管文章中使用 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="0af95-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="0af95-115">人力資源通道是合併所有 HR 相關活動（例如作業文章、新員工加入、訓練及開發）的絕佳位置。</span><span class="sxs-lookup"><span data-stu-id="0af95-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="0af95-116">[有趣的內容] 頻道可為所有的隨機及趣味文章提供社交平臺。</span><span class="sxs-lookup"><span data-stu-id="0af95-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="0af95-117">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="0af95-117">Base template type</span></span>  | <span data-ttu-id="0af95-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0af95-118">baseTemplateId</span></span> | <span data-ttu-id="0af95-119">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="0af95-120">SMB</span><span class="sxs-lookup"><span data-stu-id="0af95-120">SMB -</span></span> <br><span data-ttu-id="0af95-121">整個公司</span><span class="sxs-lookup"><span data-stu-id="0af95-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="0af95-122">頻道</span><span class="sxs-lookup"><span data-stu-id="0af95-122">Channels</span></span> <ul><li><span data-ttu-id="0af95-123">一般\*</span><span class="sxs-lookup"><span data-stu-id="0af95-123">General\*</span></span></li><li><span data-ttu-id="0af95-124">人力資源\*</span><span class="sxs-lookup"><span data-stu-id="0af95-124">Human Resources\*</span></span></li><li><span data-ttu-id="0af95-125">有趣的內容\*</span><span class="sxs-lookup"><span data-stu-id="0af95-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="0af95-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="0af95-126">Apps</span></span><ul><li><span data-ttu-id="0af95-127">公司入口網站（已固定至**人力資源**頻道的網站）</span><span class="sxs-lookup"><span data-stu-id="0af95-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="0af95-128">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-128">Team properties</span></span> <ul><li><span data-ttu-id="0af95-129">[團隊可見度] 設定為 [私人]</span><span class="sxs-lookup"><span data-stu-id="0af95-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="0af95-130">\* 自動將通道</span><span class="sxs-lookup"><span data-stu-id="0af95-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="0af95-131">若要從預先定義的範本中取得預設值來建立公司範圍的小組，請在要求內提供小組物件的 JSON 表示。</span><span class="sxs-lookup"><span data-stu-id="0af95-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="0af95-132">若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。</span><span class="sxs-lookup"><span data-stu-id="0af95-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="0af95-133">徵求</span><span class="sxs-lookup"><span data-stu-id="0af95-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="0af95-134">總經理小組範本</span><span class="sxs-lookup"><span data-stu-id="0af95-134">Executive Team template</span></span>

<span data-ttu-id="0af95-135">總經理小組範本適用于建立公司主管的小組，以便在年度優先順序、會計預算、戰略計畫、主要用戶端等公司方案中進行溝通與共同作業。此範本隨附*私人*頻道，以邀請選取使用者取得特定主題。</span><span class="sxs-lookup"><span data-stu-id="0af95-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="0af95-136">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="0af95-136">Base template type</span></span>  | <span data-ttu-id="0af95-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0af95-137">baseTemplateId</span></span> | <span data-ttu-id="0af95-138">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="0af95-139">SMB</span><span class="sxs-lookup"><span data-stu-id="0af95-139">SMB -</span></span> <br><span data-ttu-id="0af95-140">主管小組</span><span class="sxs-lookup"><span data-stu-id="0af95-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="0af95-141">頻道</span><span class="sxs-lookup"><span data-stu-id="0af95-141">Channels</span></span> <ul><li><span data-ttu-id="0af95-142">一般\*</span><span class="sxs-lookup"><span data-stu-id="0af95-142">General\*</span></span></li><li><span data-ttu-id="0af95-143">私有\*</span><span class="sxs-lookup"><span data-stu-id="0af95-143">Private \*</span></span></li></ul> <span data-ttu-id="0af95-144">應用程式</span><span class="sxs-lookup"><span data-stu-id="0af95-144">Apps</span></span><ul><li><span data-ttu-id="0af95-145">OneNote （已釘選到**私人**頻道）</span><span class="sxs-lookup"><span data-stu-id="0af95-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="0af95-146">Planner （釘選到**私人**頻道）</span><span class="sxs-lookup"><span data-stu-id="0af95-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="0af95-147">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-147">Team properties</span></span> <ul><li><span data-ttu-id="0af95-148">[團隊可見度] 設定為 [私人]</span><span class="sxs-lookup"><span data-stu-id="0af95-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="0af95-149">\* 自動將通道</span><span class="sxs-lookup"><span data-stu-id="0af95-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="0af95-150">若要從預先定義的範本中取得預設值來建立主管小組，請在要求內提供小組物件的 JSON 表示。</span><span class="sxs-lookup"><span data-stu-id="0af95-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="0af95-151">若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。</span><span class="sxs-lookup"><span data-stu-id="0af95-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="0af95-152">徵求</span><span class="sxs-lookup"><span data-stu-id="0af95-152">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="0af95-153">部門小組範本</span><span class="sxs-lookup"><span data-stu-id="0af95-153">Departmental Team template</span></span>

<span data-ttu-id="0af95-154">部門小組範本可用於為個別部門或專案建立小組。</span><span class="sxs-lookup"><span data-stu-id="0af95-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="0af95-155">[財務小組] 範本適用于財務小組成員中的所有文章、宣告及每日共同作業和通訊，以及適當的管理小組成員。</span><span class="sxs-lookup"><span data-stu-id="0af95-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="0af95-156">範本隨附*私人*頻道，以邀請選取使用者提供特定主題。</span><span class="sxs-lookup"><span data-stu-id="0af95-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="0af95-157">我們也提供下列適用于財務小組的腳本，透過新增、刪除或編輯您的喜好，就能將範本延伸到其他部門或特定專案。</span><span class="sxs-lookup"><span data-stu-id="0af95-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="0af95-158">例如，如果您有*行銷*部門，您可以將團隊從*財務*版重新命名為 [*行銷*]，以建立新的行銷團隊，以調整腳本的改編方式。</span><span class="sxs-lookup"><span data-stu-id="0af95-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="0af95-159">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="0af95-159">Base template type</span></span> | <span data-ttu-id="0af95-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0af95-160">baseTemplateId</span></span> | <span data-ttu-id="0af95-161">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="0af95-162">SMB</span><span class="sxs-lookup"><span data-stu-id="0af95-162">SMB -</span></span> <br><span data-ttu-id="0af95-163">財務</span><span class="sxs-lookup"><span data-stu-id="0af95-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="0af95-164">頻道</span><span class="sxs-lookup"><span data-stu-id="0af95-164">Channels</span></span> <ul><li><span data-ttu-id="0af95-165">一般\*</span><span class="sxs-lookup"><span data-stu-id="0af95-165">General\*</span></span></li><li><span data-ttu-id="0af95-166">私有\*</span><span class="sxs-lookup"><span data-stu-id="0af95-166">Private \*</span></span></li></ul><br> <span data-ttu-id="0af95-167">應用程式</span><span class="sxs-lookup"><span data-stu-id="0af95-167">Apps</span></span><ul><li><span data-ttu-id="0af95-168">OneNote （已釘選到**私人**頻道）</span><span class="sxs-lookup"><span data-stu-id="0af95-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="0af95-169">Planner （釘選到**私人**頻道）</span><span class="sxs-lookup"><span data-stu-id="0af95-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="0af95-170">團隊屬性</span><span class="sxs-lookup"><span data-stu-id="0af95-170">Team properties</span></span> <ul><li><span data-ttu-id="0af95-171">[團隊可見度] 設定為 [私人]</span><span class="sxs-lookup"><span data-stu-id="0af95-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="0af95-172">\* 自動將通道</span><span class="sxs-lookup"><span data-stu-id="0af95-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="0af95-173">若要從預先定義的範本提取預設值來建立財務小組，請在要求內提供小組物件的 JSON 表示。</span><span class="sxs-lookup"><span data-stu-id="0af95-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="0af95-174">若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。</span><span class="sxs-lookup"><span data-stu-id="0af95-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="0af95-175">徵求</span><span class="sxs-lookup"><span data-stu-id="0af95-175">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="0af95-176">範例：財務小組範本延伸腳本</span><span class="sxs-lookup"><span data-stu-id="0af95-176">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="0af95-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="0af95-177">Related topics</span></span>

- [<span data-ttu-id="0af95-178">開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="0af95-178">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="0af95-179">[建立小組](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在預覽中）</span><span class="sxs-lookup"><span data-stu-id="0af95-179">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

