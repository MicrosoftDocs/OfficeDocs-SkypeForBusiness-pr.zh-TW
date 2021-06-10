---
title: Microsoft 365政府 - GCC部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 適用于 IT 專業人員的指引，Office 365受美國政府法規規範之實體中的部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5f8df087ca7ad999a9756467925be68c60e96f
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718054"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="57b25-103">規劃 Office 365 政府版 - GCC部署</span><span class="sxs-lookup"><span data-stu-id="57b25-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="57b25-104">本指南適用于在美國聯邦政府機構中推動 Office 365 部署的 IT 專業人員，或是處理受政府法規和需求規範之資料的其他實體，而使用 Office 365 政府版 – GCC High 適合符合這些要求。</span><span class="sxs-lookup"><span data-stu-id="57b25-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="57b25-105">如果貴組織已經符合 Office 365 政府版 - GCC 高資格要求，且已申請且已接受計畫，您可以略過步驟 1 和 2，直接前往步驟 3。</span><span class="sxs-lookup"><span data-stu-id="57b25-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="57b25-106">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="57b25-106">Step 1.</span></span> <span data-ttu-id="57b25-107">判斷貴組織是否需要Office 365 政府版 - GCC並符合資格要求。</span><span class="sxs-lookup"><span data-stu-id="57b25-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="57b25-108">Office 365 政府版 - GCC高環境提供符合美國政府雲端服務需求的規範。</span><span class="sxs-lookup"><span data-stu-id="57b25-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="57b25-109">除了享受新功能和功能之外，Office 365還受益于下列功能，這些功能是 Office 365 政府版 - GCC高：</span><span class="sxs-lookup"><span data-stu-id="57b25-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="57b25-110">貴組織的客戶內容會從邏輯上與 Microsoft 商務服務中的Office 365內容分隔。</span><span class="sxs-lookup"><span data-stu-id="57b25-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="57b25-111">貴組織的客戶內容會儲存在美國境內。</span><span class="sxs-lookup"><span data-stu-id="57b25-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="57b25-112">您組織客戶內容的存取權僅限於已篩選的 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="57b25-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="57b25-113">Office 365 政府版 – GCC高符合美國公共部門客戶所需的認證和認證。</span><span class="sxs-lookup"><span data-stu-id="57b25-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="57b25-114">您可以針對美國政府客戶Office 365 政府版高GCC方案 ，包括資格要求Office 365 政府版更多[相關資訊。](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements) [](https://products.office.com/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="57b25-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="57b25-115">美國政府[Office 365服務](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)描述說明平臺的好處，其核心是符合美國國內的合規性需求。</span><span class="sxs-lookup"><span data-stu-id="57b25-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="57b25-116">您可能會想要將服務描述中的資訊表傳輸至 Excel 活頁簿，並新增兩欄：與組織 **Y/N** 相關，以及符合組織 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="57b25-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="57b25-117">然後，您可以與同事一起查看這份清單，確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="57b25-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="57b25-119">決策點</span><span class="sxs-lookup"><span data-stu-id="57b25-119">Decision points</span></span>|<ul><li><span data-ttu-id="57b25-120">決定 Office 365 政府版 - GCC高是否適合貴組織。</span><span class="sxs-lookup"><span data-stu-id="57b25-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="57b25-121">確認貴組織符合資格要求。</span><span class="sxs-lookup"><span data-stu-id="57b25-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="57b25-122">Office 365 政府版 - GCC高僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="57b25-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="57b25-123">非美國政府客戶可以從許多方案Office 365 政府版[選擇](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="57b25-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="57b25-124">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="57b25-124">Step 2.</span></span> <span data-ttu-id="57b25-125">申請Office 365 政府版 - GCC高</span><span class="sxs-lookup"><span data-stu-id="57b25-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="57b25-126">決定這項服務適合貴組織後，請開始申請 [這項服務程式](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="57b25-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="57b25-127">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="57b25-127">Step 3.</span></span> <span data-ttu-id="57b25-128">瞭解Office 365 政府版 - GCC高預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="57b25-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="57b25-129">建議您在修改管理員和安全性設定之前，先花[](enable-features-office-365.md)一些時間仔細查看，並考慮對合規性的影響，然後再對預設安全性設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="57b25-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="57b25-131">決策點</span><span class="sxs-lookup"><span data-stu-id="57b25-131">Decision point</span></span>|<ul><li><span data-ttu-id="57b25-132">決定是否需要修改任何預設Office 365 政府版 - GCC安全性設定，解決以先瞭解您可能進行的任何變更的影響。</span><span class="sxs-lookup"><span data-stu-id="57b25-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="57b25-133">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="57b25-133">Step 4.</span></span> <span data-ttu-id="57b25-134">瞭解Teams中目前提供哪些Office 365 政府版 - GCC功能</span><span class="sxs-lookup"><span data-stu-id="57b25-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="57b25-135">為了配合我們的政府雲端客戶的需求，Teams方案中的 Teams - Office 365 政府版 高GCC與 Teams Enterprise有一些差異。</span><span class="sxs-lookup"><span data-stu-id="57b25-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="57b25-136">請參閱下表，瞭解哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="57b25-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="57b25-137">Microsoft Teams服務描述</span><span class="sxs-lookup"><span data-stu-id="57b25-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="57b25-138">步驟 5。</span><span class="sxs-lookup"><span data-stu-id="57b25-138">Step 5.</span></span> <span data-ttu-id="57b25-139">管理計畫</span><span class="sxs-lookup"><span data-stu-id="57b25-139">Plan for governance</span></span>

<span data-ttu-id="57b25-140">判斷您的監管需求，以及如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="57b25-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="57b25-141">若要詳細資訊[，](plan-teams-governance.md)請前往 Teams 中規劃管理。</span><span class="sxs-lookup"><span data-stu-id="57b25-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="57b25-142">決策點</span><span class="sxs-lookup"><span data-stu-id="57b25-142">Decision point</span></span> |<ul><li><span data-ttu-id="57b25-143">請遵循管理計畫中的指導方針，在 Teams 中判斷[和記錄您的Teams。](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="57b25-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="57b25-144">步驟 6.</span><span class="sxs-lookup"><span data-stu-id="57b25-144">Step 6.</span></span> <span data-ttu-id="57b25-145">部署Teams共同合作</span><span class="sxs-lookup"><span data-stu-id="57b25-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="57b25-146">在您上機至 Office 365 政府版 - GCC之後，請遵循如何推出 Microsoft Teams 中[概述的建議部署Microsoft Teams。](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="57b25-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="57b25-147">請務必與採用與變更管理團隊互動，並Teams領軍者。</span><span class="sxs-lookup"><span data-stu-id="57b25-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="57b25-148">您也可以與 [FastTrack](https://www.microsoft.com/fasttrack) 或您選擇的合作夥伴合作，以開始服務。</span><span class="sxs-lookup"><span data-stu-id="57b25-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
