---
title: Office 365 政府-DoD 部署
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 適用于 IT 專業人員的指導方針，可在處理受美國政府 DoD 法規制約之資料的實體中，將 Office 365 部署驅動。
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
ms.openlocfilehash: e690016f16c261a97594e8b9f44d7937c655c1bb
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665875"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="81284-103">規劃 Office 365 政府 DoD 部署</span><span class="sxs-lookup"><span data-stu-id="81284-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="81284-104">本指導方針適用于在美國聯邦政府機構或其他處理受政府管理法規與需求之資料的實體中，或其他處理 Office 365 政府-DoD，且適合符合這些需求的 IT 專業365人員使用。</span><span class="sxs-lookup"><span data-stu-id="81284-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="81284-105">如果您的組織已符合 Office 365 政府-DoD 資格要求，且已在計畫中套用並接受，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="81284-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="81284-106">步驟1。</span><span class="sxs-lookup"><span data-stu-id="81284-106">Step 1.</span></span> <span data-ttu-id="81284-107">判斷貴組織是否需要 Office 365 政府-DoD 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="81284-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="81284-108">Office 365 政府 DoD 環境會針對雲端服務的美國政府需求提供合規性。</span><span class="sxs-lookup"><span data-stu-id="81284-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="81284-109">除了享有 Office 365 的功能和功能之外，組織還能利用 Office 365 政府版所特有的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="81284-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="81284-110">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="81284-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="81284-111">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="81284-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="81284-112">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="81284-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="81284-113">Office 365 政府-DoD 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="81284-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="81284-114">您可以在[office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有關美國政府客戶的 office 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="81284-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="81284-115">[ [Office 365 美國政府服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)] 描述的是平臺的優點，這些好處是在美國內滿足合規性需求的中心。</span><span class="sxs-lookup"><span data-stu-id="81284-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="81284-116">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="81284-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="81284-117">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="81284-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="81284-119">決策點</span><span class="sxs-lookup"><span data-stu-id="81284-119">Decision points</span></span>|<ul><li><span data-ttu-id="81284-120">決定 Office 365 政府 DoD 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="81284-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="81284-121">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="81284-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="81284-122">Office 365 政府-DoD 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="81284-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="81284-123">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="81284-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="81284-124">步驟2。</span><span class="sxs-lookup"><span data-stu-id="81284-124">Step 2.</span></span> <span data-ttu-id="81284-125">適用于 Office 365 政府-DoD</span><span class="sxs-lookup"><span data-stu-id="81284-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="81284-126">如果您認為此服務適合您的組織，請開始[申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="81284-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="81284-127">步驟3。</span><span class="sxs-lookup"><span data-stu-id="81284-127">Step 3.</span></span> <span data-ttu-id="81284-128">瞭解 Office 365 政府 DoD 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="81284-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="81284-129">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="81284-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="81284-131">決策點</span><span class="sxs-lookup"><span data-stu-id="81284-131">Decision point</span></span>|<ul><li><span data-ttu-id="81284-132">決定是否要修改任何預設的 Office 365 政府 DoD 安全性設定，以解決您的需求，以先瞭解您可能所做的任何變更的影響。</span><span class="sxs-lookup"><span data-stu-id="81284-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="81284-133">步驟4。</span><span class="sxs-lookup"><span data-stu-id="81284-133">Step 4.</span></span> <span data-ttu-id="81284-134">瞭解 Office 365 政府-DoD 目前提供哪些團隊功能</span><span class="sxs-lookup"><span data-stu-id="81284-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="81284-135">為了符合政府雲端客戶的需求，Office 365 政府-DoD 中的小組與企業方案中的小組之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="81284-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="81284-136">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="81284-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="81284-137">Microsoft 團隊服務描述</span><span class="sxs-lookup"><span data-stu-id="81284-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="81284-138">步驟5。</span><span class="sxs-lookup"><span data-stu-id="81284-138">Step 5.</span></span> <span data-ttu-id="81284-139">規劃管理</span><span class="sxs-lookup"><span data-stu-id="81284-139">Plan for governance</span></span>

<span data-ttu-id="81284-140">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="81284-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="81284-141">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="81284-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="81284-142">決策點</span><span class="sxs-lookup"><span data-stu-id="81284-142">Decision point</span></span> |<ul><li><span data-ttu-id="81284-143">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="81284-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="81284-144">步驟6。</span><span class="sxs-lookup"><span data-stu-id="81284-144">Step 6.</span></span> <span data-ttu-id="81284-145">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="81284-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="81284-146">在您 onboarded 至 Office 365 政府– DoD 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="81284-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="81284-147">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="81284-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="81284-148">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="81284-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
