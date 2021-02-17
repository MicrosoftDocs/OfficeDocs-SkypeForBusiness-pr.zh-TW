---
title: 醫療保健組織的範本
author: serdarsoysal
ms.author: serdars
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
description: 使用 Microsoft Teams 範本與 Microsoft Graph，提供預先定義的設定、頻道和應用程式範本，以快速且輕鬆地建立團隊。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260335"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="f13d9-103">開始使用醫療保健組織的 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="f13d9-104">Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式的範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="f13d9-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="f13d9-105">對醫療保健組織來說，範本特別強大，因為範本提供結構讓使用者熟悉如何有效地使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="f13d9-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="f13d9-106">範本也允許系統管理員在組織中部署一致的團隊。</span><span class="sxs-lookup"><span data-stu-id="f13d9-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="f13d9-107">如果您負責規劃、部署和管理整個醫療保健組織的多個團隊，本文適合您。</span><span class="sxs-lookup"><span data-stu-id="f13d9-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="f13d9-108">我們目前提供兩種可用於各種情況的第一方醫療保健範本。</span><span class="sxs-lookup"><span data-stu-id="f13d9-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="f13d9-109">若要深入瞭解團隊範本，請參閱 Teams 範本 [入門](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="f13d9-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="f13d9-110">範本範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-110">Ward template</span></span>

<span data-ttu-id="f13d9-111">此範本適用于在小公司、容器或部門內進行通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="f13d9-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="f13d9-112">此範本可用來協助病患管理，以及風險管理的運作需求。</span><span class="sxs-lookup"><span data-stu-id="f13d9-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="f13d9-113">例如，公告公告可以張貼在公告頻道中，而班次可以在 *Staffing 中管理*。</span><span class="sxs-lookup"><span data-stu-id="f13d9-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="f13d9-114">如果您想要簡化您的服務運作方式，則此範本適合您。</span><span class="sxs-lookup"><span data-stu-id="f13d9-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="f13d9-115">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="f13d9-115">Base Template Type</span></span> |<span data-ttu-id="f13d9-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f13d9-116">baseTemplateId</span></span> |<span data-ttu-id="f13d9-117">比較基準範本通道</span><span class="sxs-lookup"><span data-stu-id="f13d9-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="f13d9-118">醫療保健 - 小品</span><span class="sxs-lookup"><span data-stu-id="f13d9-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="f13d9-119">公告\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-119">Announcements\*</span></span> <br> <span data-ttu-id="f13d9-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-120">Huddles\*</span></span> <br> <span data-ttu-id="f13d9-121">輪\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-121">Rounds\*</span></span> <br> <span data-ttu-id="f13d9-122">人手\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-122">Staffing\*</span></span> <br> <span data-ttu-id="f13d9-123">訓練\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="f13d9-124">\* 自動將我的最愛</span><span class="sxs-lookup"><span data-stu-id="f13d9-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="f13d9-125">醫院範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-125">Hospital template</span></span>

<span data-ttu-id="f13d9-126">該醫院範本適用于醫院內多個醫院、容器和部門之間的通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="f13d9-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="f13d9-127">此範本包含數個營運頻道，包括公告、小通和行銷，但我們也會在下方提供腳本，以各種額外的部門或以特殊為主的頻道延伸範本，您可以新增、刪除或編輯您喜歡的頻道。 </span><span class="sxs-lookup"><span data-stu-id="f13d9-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="f13d9-128">例如，如果您有一個內鏈系，但不需要一個 *Ophthalmoph* 的頻道，則腳本可以調整為包含一個內文 *學* 通道，並移除 *Ophthalmoph 通道*。</span><span class="sxs-lookup"><span data-stu-id="f13d9-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="f13d9-129">建議您不要自動將這些特殊或以小動物模型模式使用的頻道做為我的最愛，以避免通知飽和度。</span><span class="sxs-lookup"><span data-stu-id="f13d9-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="f13d9-130">使用者通常會將任何他們覺得相關的頻道最愛。</span><span class="sxs-lookup"><span data-stu-id="f13d9-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="f13d9-131">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="f13d9-131">Base Template Type</span></span> |<span data-ttu-id="f13d9-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f13d9-132">baseTemplateId</span></span> |<span data-ttu-id="f13d9-133">比較基準範本通道</span><span class="sxs-lookup"><span data-stu-id="f13d9-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="f13d9-134">醫療保健 - 醫院</span><span class="sxs-lookup"><span data-stu-id="f13d9-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="f13d9-135">公告\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-135">Announcements\*</span></span> <br> <span data-ttu-id="f13d9-136">合規性\*</span><span class="sxs-lookup"><span data-stu-id="f13d9-136">Compliance\*</span></span> <br> <span data-ttu-id="f13d9-137">保管</span><span class="sxs-lookup"><span data-stu-id="f13d9-137">Custodial</span></span> <br> <span data-ttu-id="f13d9-138">人力資源</span><span class="sxs-lookup"><span data-stu-id="f13d9-138">Human Resources</span></span> <br> <span data-ttu-id="f13d9-139">藥學</span><span class="sxs-lookup"><span data-stu-id="f13d9-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="f13d9-140">\* 自動將我的最愛</span><span class="sxs-lookup"><span data-stu-id="f13d9-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="f13d9-141">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-141">How to use first-party templates</span></span>

<span data-ttu-id="f13d9-142">若要使用這些範本，只要將要求內文中的 template@odata.bind' 屬性從 "standard" 變更為上述 TemplateIDs。</span><span class="sxs-lookup"><span data-stu-id="f13d9-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="f13d9-143">如何部署 Teams 範本，請參閱如何建立團隊的 Microsoft Graph [文章](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="f13d9-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="f13d9-144">範本中的頻道會自動在一般 Tab 下建立。</span><span class="sxs-lookup"><span data-stu-id="f13d9-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="f13d9-145">範例：醫院範本擴充功能腳本</span><span class="sxs-lookup"><span data-stu-id="f13d9-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="f13d9-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="f13d9-146">Related topics</span></span>

[<span data-ttu-id="f13d9-147">開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="f13d9-148">開始使用適用於醫療保健組織的 Teams</span><span class="sxs-lookup"><span data-stu-id="f13d9-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="f13d9-149">在系統管理主控台中開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="f13d9-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
