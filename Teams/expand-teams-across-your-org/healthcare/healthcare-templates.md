---
title: 開始使用適用于醫療保健組織的團隊範本
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 開始使用適用于醫療保健組織的團隊範本
ms.openlocfilehash: 437a645a0ab32024e81f3c73ba0db09b08267b3d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232247"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="2a4bf-103">開始使用適用于醫療保健組織的團隊範本</span><span class="sxs-lookup"><span data-stu-id="2a4bf-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="2a4bf-104">Microsoft 團隊範本可讓您透過提供預先定義的設定、頻道及預先安裝應用程式範本, 快速且輕鬆地建立小組。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2a4bf-105">針對醫療保健組織而言, 範本特別實用, 因為它們為使用者提供結構, 以瞭解如何有效地利用團隊。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="2a4bf-106">範本也可讓系統管理員在組織中部署一致的團隊。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="2a4bf-107">本文適用于您負責規劃、部署及管理整個醫療保健組織中的多個小組。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="2a4bf-108">我們目前提供兩個您可以在各種情況下利用的第一方醫療保健範本。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="2a4bf-109">若要深入瞭解小組範本的整體資訊, 請參閱[開始使用團隊範本](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="2a4bf-110">Ward 範本</span><span class="sxs-lookup"><span data-stu-id="2a4bf-110">Ward template</span></span>

<span data-ttu-id="2a4bf-111">Ward 範本適用于 ward、pod 或部門中的通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="2a4bf-112">範本可用於協助患者管理, 以及 ward 的運作需求。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="2a4bf-113">例如, 您可以在*宣告*頻道中張貼 ward 宣告, 並在*人員*集中管理班次。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="2a4bf-114">如果您想要簡化您的 ward 作業, 這個範本適合您。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="2a4bf-115">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="2a4bf-115">Base Template Type</span></span> |<span data-ttu-id="2a4bf-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2a4bf-116">baseTemplateId</span></span> |<span data-ttu-id="2a4bf-117">比較基準範本頻道</span><span class="sxs-lookup"><span data-stu-id="2a4bf-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2a4bf-118">醫療保健-Ward</span><span class="sxs-lookup"><span data-stu-id="2a4bf-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="2a4bf-119">公告\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-119">Announcements\*</span></span> <br> <span data-ttu-id="2a4bf-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-120">Huddles\*</span></span> <br> <span data-ttu-id="2a4bf-121">輪\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-121">Rounds\*</span></span> <br> <span data-ttu-id="2a4bf-122">人員\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-122">Staffing\*</span></span> <br> <span data-ttu-id="2a4bf-123">訓練\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="2a4bf-124">\*自動將</span><span class="sxs-lookup"><span data-stu-id="2a4bf-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="2a4bf-125">醫院範本</span><span class="sxs-lookup"><span data-stu-id="2a4bf-125">Hospital template</span></span>

<span data-ttu-id="2a4bf-126">醫院範本適用于醫院中的多個 wards、箱與部門之間進行通訊與共同作業。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="2a4bf-127">此範本中包含幾個作業通道, 包括*宣告*、 *Custodial*和*藥房*, 但我們也提供下列腳本, 此腳本會以不同的其他部門擴充範本, 或以專業為中心的頻道, 您可以根據自己的喜好來新增、刪除或編輯。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="2a4bf-128">例如, 如果您有*Endocrinology*部門, 但不需要*Ophthalmology*的頻道, 則可以調整腳本以納入*Endocrinology*通道並移除*Ophthalmology*通道。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="2a4bf-129">我們建議您不要將這些專業或 ward 模型的通道自動將, 以免出現通知的飽和情況。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="2a4bf-130">使用者通常會最愛他們找到的任何頻道。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="2a4bf-131">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="2a4bf-131">Base Template Type</span></span> |<span data-ttu-id="2a4bf-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2a4bf-132">baseTemplateId</span></span> |<span data-ttu-id="2a4bf-133">比較基準範本頻道</span><span class="sxs-lookup"><span data-stu-id="2a4bf-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2a4bf-134">醫療保健-醫院</span><span class="sxs-lookup"><span data-stu-id="2a4bf-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="2a4bf-135">公告\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-135">Announcements\*</span></span> <br> <span data-ttu-id="2a4bf-136">從屬\*</span><span class="sxs-lookup"><span data-stu-id="2a4bf-136">Compliance\*</span></span> <br> <span data-ttu-id="2a4bf-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="2a4bf-137">Custodial</span></span> <br> <span data-ttu-id="2a4bf-138">人力資源</span><span class="sxs-lookup"><span data-stu-id="2a4bf-138">Human Resources</span></span> <br> <span data-ttu-id="2a4bf-139">藥房</span><span class="sxs-lookup"><span data-stu-id="2a4bf-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="2a4bf-140">\*自動將</span><span class="sxs-lookup"><span data-stu-id="2a4bf-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="2a4bf-141">如何使用第一方範本</span><span class="sxs-lookup"><span data-stu-id="2a4bf-141">How to use first party templates</span></span>

<span data-ttu-id="2a4bf-142">若要使用這些範本, 只要將申請主體中的 ' template@odata.bind」屬性從「標準」變更為上述 TemplateIDs。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="2a4bf-143">如需如何部署團隊範本的詳細資訊, 請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-143">For more information on how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="2a4bf-144">範本中的頻道會自動建立在 [一般] 索引標籤底下。</span><span class="sxs-lookup"><span data-stu-id="2a4bf-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="2a4bf-145">範例: 醫院範本延伸腳本</span><span class="sxs-lookup"><span data-stu-id="2a4bf-145">Example: Hospital template extension script</span></span>

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
              "displayName": "Women’s Health",
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

## <a name="related-topics"></a><span data-ttu-id="2a4bf-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a4bf-146">Related topics</span></span>

[<span data-ttu-id="2a4bf-147">團隊範本快速入門</span><span class="sxs-lookup"><span data-stu-id="2a4bf-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="2a4bf-148">開始使用適用于醫療保健組織的團隊</span><span class="sxs-lookup"><span data-stu-id="2a4bf-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
