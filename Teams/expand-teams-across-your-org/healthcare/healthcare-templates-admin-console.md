---
title: 使用 Teams 醫療保健範本建立團隊
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 在系統管理中心或 Microsoft Graph 使用 Microsoft Teams 範本，提供預先定義的設定、頻道和應用程式範本，以快速且輕鬆地建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260305"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="7ca0b-103">使用 Teams 醫療保健範本建立團隊</span><span class="sxs-lookup"><span data-stu-id="7ca0b-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="7ca0b-104">Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7ca0b-105">對醫療保健組織來說，範本特別強大，因為它們提供結構，讓使用者以如何有效地使用 Teams 為導向。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="7ca0b-106">範本也可讓系統管理員在組織中部署一致的小組。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="7ca0b-107">如果您負責規劃、部署和管理整個醫療保健組織的多個團隊，本文適合您。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="7ca0b-108">選擇使用 Teams 醫療保健範本建立團隊的方法：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="7ca0b-109">誰</span><span class="sxs-lookup"><span data-stu-id="7ca0b-109">Who</span></span> | <span data-ttu-id="7ca0b-110">使用方法：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="7ca0b-111">系統管理員和 IT 專業人員</span><span class="sxs-lookup"><span data-stu-id="7ca0b-111">Admins and IT Professionals</span></span> | <span data-ttu-id="7ca0b-112">[使用 Teams 系統管理中心](#use-the-teams-templates-in-the-teams-admin-center)根據醫療保健 Teams 範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="7ca0b-113">開發人員和系統整合者</span><span class="sxs-lookup"><span data-stu-id="7ca0b-113">Developers and systems integrators</span></span> | <span data-ttu-id="7ca0b-114">[使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 根據醫療保健 Teams 範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="7ca0b-115">使用 Teams 系統管理中心的 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="7ca0b-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="7ca0b-116">Microsoft Teams 系統管理員可以使用 Teams 系統管理中心，並透過 Teams 範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="7ca0b-117">我們目前提供兩種第一方醫療保健範本，可用於各種情況。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="7ca0b-118">若要深入了解一般小組範本，請參閱[管理中心網站中的 Teams 範本入門](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="7ca0b-119">在病患照護上共同作業</span><span class="sxs-lookup"><span data-stu-id="7ca0b-119">Collaborate on patient care</span></span>

 <span data-ttu-id="7ca0b-120">簡化病房、配藥處或部門內的醫療保健通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="7ca0b-121">範本可用來協助病患管理和醫院的操作需求。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="7ca0b-122">範本類型</span><span class="sxs-lookup"><span data-stu-id="7ca0b-122">Base template type</span></span> |<span data-ttu-id="7ca0b-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7ca0b-123">baseTemplateId</span></span>| <span data-ttu-id="7ca0b-124">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="7ca0b-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="7ca0b-125">在病患照護上共同作業</span><span class="sxs-lookup"><span data-stu-id="7ca0b-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="7ca0b-126">頻道：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-126">Channels:</span></span><ul><li><span data-ttu-id="7ca0b-127">一般</span><span class="sxs-lookup"><span data-stu-id="7ca0b-127">General</span></span></li><li><span data-ttu-id="7ca0b-128">公告</span><span class="sxs-lookup"><span data-stu-id="7ca0b-128">Announcements</span></span></li><li><span data-ttu-id="7ca0b-129">過程中討論</span><span class="sxs-lookup"><span data-stu-id="7ca0b-129">Huddles</span></span></li><li><span data-ttu-id="7ca0b-130">輪次</span><span class="sxs-lookup"><span data-stu-id="7ca0b-130">Rounds</span></span></li><li><span data-ttu-id="7ca0b-131">人員</span><span class="sxs-lookup"><span data-stu-id="7ca0b-131">Staffing</span></span></li><li><span data-ttu-id="7ca0b-132">訓練</span><span class="sxs-lookup"><span data-stu-id="7ca0b-132">Training</span></span></li></ul> <span data-ttu-id="7ca0b-133">應用程式：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-133">Apps:</span></span> <ul><li><span data-ttu-id="7ca0b-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="7ca0b-134">Wiki</span></span></li><li><span data-ttu-id="7ca0b-135">清單</span><span class="sxs-lookup"><span data-stu-id="7ca0b-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="7ca0b-136">醫院</span><span class="sxs-lookup"><span data-stu-id="7ca0b-136">Hospital</span></span>

<span data-ttu-id="7ca0b-137">簡化醫院內多個病房、配藥處或部門之間的通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="7ca0b-138">此範本包含一組用於醫院作業的基本頻道，且可自我擴充以包含專科、臨時特別項目等。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="7ca0b-139">範本類型</span><span class="sxs-lookup"><span data-stu-id="7ca0b-139">Base template type</span></span> |<span data-ttu-id="7ca0b-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7ca0b-140">baseTemplateId</span></span> | <span data-ttu-id="7ca0b-141">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="7ca0b-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="7ca0b-142">醫院</span><span class="sxs-lookup"><span data-stu-id="7ca0b-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="7ca0b-143">頻道：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-143">Channels:</span></span> <ul><li><span data-ttu-id="7ca0b-144">一般</span><span class="sxs-lookup"><span data-stu-id="7ca0b-144">General</span></span></li><li><span data-ttu-id="7ca0b-145">公告</span><span class="sxs-lookup"><span data-stu-id="7ca0b-145">Announcements</span></span></li><li><span data-ttu-id="7ca0b-146">合規性</span><span class="sxs-lookup"><span data-stu-id="7ca0b-146">Compliance</span></span></li><li><span data-ttu-id="7ca0b-147">監管</span><span class="sxs-lookup"><span data-stu-id="7ca0b-147">Custodial</span></span></li><li><span data-ttu-id="7ca0b-148">人力資源</span><span class="sxs-lookup"><span data-stu-id="7ca0b-148">Human resources</span></span></li><li><span data-ttu-id="7ca0b-149">藥品部</span><span class="sxs-lookup"><span data-stu-id="7ca0b-149">Pharmacy</span></span></li></ul> <span data-ttu-id="7ca0b-150">應用程式：</span><span class="sxs-lookup"><span data-stu-id="7ca0b-150">Apps:</span></span> <ul><li><span data-ttu-id="7ca0b-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="7ca0b-151">Wiki</span></span></li><li><span data-ttu-id="7ca0b-152">清單</span><span class="sxs-lookup"><span data-stu-id="7ca0b-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="7ca0b-153">使用 Teams 範本與 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="7ca0b-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="7ca0b-154">開發人員可以使用 Microsoft Graph 搭配 Teams 範本建立團隊。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="7ca0b-155">我們目前提供兩種第一方醫療保健範本，可用於各種情況。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="7ca0b-156">如需深入了解一般小組範本，請參閱 [Teams 範本入門](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="7ca0b-157">而有關 Teams 範本和 Microsoft Graph 的資訊，請參閱 [Microsoft Teams API 概觀](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 資源類型](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="7ca0b-158">Word 範本</span><span class="sxs-lookup"><span data-stu-id="7ca0b-158">Ward template</span></span>

<span data-ttu-id="7ca0b-159">病房範本適用於在病房、配藥處或部門內進行通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="7ca0b-160">範本可用來協助病患管理，以及病房的操作需求。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="7ca0b-161">例如，您可以在 *[公告]* 頻道中張貼病房公告，而班次可以在 *[人員]* 中管理。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="7ca0b-162">如果您想要簡化您的病房作業，則此範本適合您。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="7ca0b-163">範本類型</span><span class="sxs-lookup"><span data-stu-id="7ca0b-163">Base Template Type</span></span> |<span data-ttu-id="7ca0b-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7ca0b-164">baseTemplateId</span></span> |<span data-ttu-id="7ca0b-165">基準範本頻道</span><span class="sxs-lookup"><span data-stu-id="7ca0b-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="7ca0b-166">醫療保健 - 病房</span><span class="sxs-lookup"><span data-stu-id="7ca0b-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="7ca0b-167">公告\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-167">Announcements\*</span></span> <br> <span data-ttu-id="7ca0b-168">過程中討論\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-168">Huddles\*</span></span> <br> <span data-ttu-id="7ca0b-169">輪次\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-169">Rounds\*</span></span> <br> <span data-ttu-id="7ca0b-170">人員\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-170">Staffing\*</span></span> <br> <span data-ttu-id="7ca0b-171">訓練\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="7ca0b-172">\*自動加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="7ca0b-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="7ca0b-173">醫院範本</span><span class="sxs-lookup"><span data-stu-id="7ca0b-173">Hospital template</span></span>

<span data-ttu-id="7ca0b-174">醫院範本適用於醫院內多個病房、配藥處或部門的通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="7ca0b-175">此範本包含數個操作頻道，包括 *[公告]*、 *[監管]* 和 *[藥品部]*。我們還提供指令碼，可讓您以各種額外的部門或專科為主的頻道來延伸範本，且您可以新增、刪除或編輯您喜歡的頻道。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="7ca0b-176">例如，如果您有 *[內科]* 部門，但不需要 *[眼科]* 的頻道，則指令碼可以調整為包含 *[內科]* 頻道，並移除 *[眼科]* 頻道。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="7ca0b-177">建議您不要將這些專科或病房模型頻道自動加入我的最愛，以避免通知飽和。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="7ca0b-178">使用者通常會將任何他們覺得相關的頻道加入最愛。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="7ca0b-179">範本類型</span><span class="sxs-lookup"><span data-stu-id="7ca0b-179">Base Template Type</span></span> |<span data-ttu-id="7ca0b-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7ca0b-180">baseTemplateId</span></span> |<span data-ttu-id="7ca0b-181">基準範本頻道</span><span class="sxs-lookup"><span data-stu-id="7ca0b-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="7ca0b-182">醫療保健 - 醫院</span><span class="sxs-lookup"><span data-stu-id="7ca0b-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="7ca0b-183">公告\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-183">Announcements\*</span></span> <br> <span data-ttu-id="7ca0b-184">合規性\*</span><span class="sxs-lookup"><span data-stu-id="7ca0b-184">Compliance\*</span></span> <br> <span data-ttu-id="7ca0b-185">監管</span><span class="sxs-lookup"><span data-stu-id="7ca0b-185">Custodial</span></span> <br> <span data-ttu-id="7ca0b-186">人力資源</span><span class="sxs-lookup"><span data-stu-id="7ca0b-186">Human Resources</span></span> <br> <span data-ttu-id="7ca0b-187">藥品部</span><span class="sxs-lookup"><span data-stu-id="7ca0b-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="7ca0b-188">\*自動加入我的最愛</span><span class="sxs-lookup"><span data-stu-id="7ca0b-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="7ca0b-189">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="7ca0b-189">How to use first-party templates</span></span>

<span data-ttu-id="7ca0b-190">若要使用這些範本，只需將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateDs。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="7ca0b-191">如需了解如何部署 Teams 範本，請參閱 Microsoft Graph 文章，以了解如何[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="7ca0b-192">範本中的頻道會自動在 [一般] 索引標籤下建立。</span><span class="sxs-lookup"><span data-stu-id="7ca0b-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="7ca0b-193">範例：醫院範本延伸模組指令碼</span><span class="sxs-lookup"><span data-stu-id="7ca0b-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="7ca0b-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="7ca0b-194">Related topics</span></span>

[<span data-ttu-id="7ca0b-195">開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="7ca0b-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="7ca0b-196">開始使用適用於醫療保健組織的 Teams</span><span class="sxs-lookup"><span data-stu-id="7ca0b-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
