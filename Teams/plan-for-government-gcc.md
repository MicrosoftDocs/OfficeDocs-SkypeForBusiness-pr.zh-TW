---
title: Microsoft 365 政府版 - GCC 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT 專業人員在處理受美國政府法規規範之資料的實體中推動 Microsoft 365 部署指南
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117831"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="ef3db-103">規劃 Microsoft 365 政府版 - GCC 部署</span><span class="sxs-lookup"><span data-stu-id="ef3db-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="ef3db-104">本指南適用于在美國聯邦、州、地方、部落或地區政府機構中推動 Microsoft 365 部署的 IT 專業人員，或是處理受政府法規和需求所規範之資料的其他實體，而 Microsoft 365 政府 - GCC 適合用於符合這些要求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="ef3db-105">2020 年 3 月 26 日新版：請勿錯過我們可下載的 [GCC 快速入門手冊](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef3db-106">由於冠狀病毒性冠狀病毒 (COVID-19，Microsoft Teams 的線上通話和音訊/視訊會議) 高峰。</span><span class="sxs-lookup"><span data-stu-id="ef3db-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="ef3db-107">為了因應通話的前所未有的增加，並確保持續性和可用性，Microsoft 允許 Microsoft Teams GCC 音訊/視像伺服器在我們的商業資料中心以及政府資料中心運用處理容量。</span><span class="sxs-lookup"><span data-stu-id="ef3db-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="ef3db-108">這些音訊/視像伺服器位於美國的 Microsoft Azure FedRAMP 高認證邊界伺服器中，不會儲存任何客戶內容。</span><span class="sxs-lookup"><span data-stu-id="ef3db-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="ef3db-109">不過，這些伺服器正在處理通話和會議的音訊和視音訊，並在此期間由我們的商業人員操作。</span><span class="sxs-lookup"><span data-stu-id="ef3db-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="ef3db-110">合格、經篩選的人員會檢查這些伺服器，以檢查這些伺服器的任何互動式登入，以監控客戶資料的潛在存取權。</span><span class="sxs-lookup"><span data-stu-id="ef3db-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="ef3db-111">合格人員符合 GCC 要求，以存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="ef3db-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="ef3db-112">有關篩選需求的詳細資訊，請參閱 [GCC 服務描述](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="ef3db-113">感謝您的支援，我們採取一些步驟，確保我們的服務在非同尋常時期保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="ef3db-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="ef3db-114">如果貴組織已經符合 Microsoft 365 政府 - GCC 資格要求，並申請並已被計畫接受，您可以略過步驟 1 和 2，直接前往步驟 3。</span><span class="sxs-lookup"><span data-stu-id="ef3db-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="ef3db-115">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="ef3db-115">Step 1.</span></span> <span data-ttu-id="ef3db-116">判斷貴組織是否需要 Microsoft 365 政府 - GCC 並符合資格要求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="ef3db-117">Microsoft 365 政府 - GCC 環境符合美國政府對雲端服務的需求，包括 FedRAMP 中度，以及犯罪審判和聯邦稅務資訊系統 (CJI 和 FTI 資料類型) 。</span><span class="sxs-lookup"><span data-stu-id="ef3db-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="ef3db-118">除了享受 Microsoft 365 的功能之外，組織還受益于 Microsoft 365 政府 - GCC 特有的下列功能：</span><span class="sxs-lookup"><span data-stu-id="ef3db-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="ef3db-119">貴組織的客戶內容在邏輯上與 Microsoft 商業 Microsoft 365 服務中的客戶內容分隔。</span><span class="sxs-lookup"><span data-stu-id="ef3db-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="ef3db-120">貴組織的客戶內容會儲存在美國境內。</span><span class="sxs-lookup"><span data-stu-id="ef3db-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="ef3db-121">您組織客戶內容的存取權僅限於已篩選的 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="ef3db-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="ef3db-122">Microsoft 365 政府 - GCC 遵守美國公共部門客戶所需的認證和認證。</span><span class="sxs-lookup"><span data-stu-id="ef3db-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="ef3db-123">您可以在 Microsoft 365 政府版方案找到適用于美國政府客戶的 [Microsoft 365](https://products.office.com/government/compare-office-365-government-plans)政府 - GCC 產品詳細資訊，包括 [資格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="ef3db-124">[Microsoft 365 美國政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)版服務描述說明平臺的好處，其核心是符合美國國內的合規性需求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="ef3db-125">您可能會想要將服務描述中的資訊表傳輸至 Excel 活頁簿，並新增兩欄：與組織 **Y/N** 相關，以及符合組織 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="ef3db-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="ef3db-126">然後，您可以與同事一起查看這份清單，確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ef3db-128">決策點</span><span class="sxs-lookup"><span data-stu-id="ef3db-128">Decision points</span></span>|<ul><li><span data-ttu-id="ef3db-129">決定 Microsoft 365 政府版 - GCC 是否適合貴組織。</span><span class="sxs-lookup"><span data-stu-id="ef3db-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="ef3db-130">確認貴組織符合資格要求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="ef3db-131">Microsoft 365 政府版 - GCC 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="ef3db-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="ef3db-132">非美國政府客戶可以從許多 [Microsoft 365 政府版方案中選擇](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="ef3db-133">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="ef3db-133">Step 2.</span></span> <span data-ttu-id="ef3db-134">申請 Microsoft 365 政府版 - GCC</span><span class="sxs-lookup"><span data-stu-id="ef3db-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="ef3db-135">決定這項服務適合貴組織後，請在這裡開始申請[這項服務。](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="ef3db-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="ef3db-136">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="ef3db-136">Step 3.</span></span> <span data-ttu-id="ef3db-137">瞭解 Microsoft 365 政府版 - GCC 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="ef3db-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="ef3db-138">我們建議您在修改管理員和安全性設定之前，先花[](enable-features-office-365.md)一些時間仔細查看，並考慮對合規性的影響，然後再對預設安全性設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="ef3db-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ef3db-140">決策點</span><span class="sxs-lookup"><span data-stu-id="ef3db-140">Decision point</span></span>|<ul><li><span data-ttu-id="ef3db-141">決定是否要修改任何預設的 Microsoft 365 政府 - GCC 安全性設定，解決以先瞭解您可能進行的任何變更的影響。</span><span class="sxs-lookup"><span data-stu-id="ef3db-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="ef3db-142">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="ef3db-142">Step 4.</span></span> <span data-ttu-id="ef3db-143">瞭解預設目前無法使用或停用的功能。</span><span class="sxs-lookup"><span data-stu-id="ef3db-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="ef3db-144">為了配合我們政府雲端客戶的需求，Microsoft 365 政府 - GCC 和企業版方案之間有些差異。</span><span class="sxs-lookup"><span data-stu-id="ef3db-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="ef3db-145">請參閱下表，瞭解哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="ef3db-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="ef3db-146">Microsoft Teams 服務描述</span><span class="sxs-lookup"><span data-stu-id="ef3db-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="ef3db-147">其他工作負載在 GCC 雲端中完全可用後，當所有其他整合工作完成時，這些工作負載就會在 Teams 中可用。</span><span class="sxs-lookup"><span data-stu-id="ef3db-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ef3db-149">決策點</span><span class="sxs-lookup"><span data-stu-id="ef3db-149">Decision point</span></span>|<ul><li><span data-ttu-id="ef3db-150">決定 Teams 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="ef3db-151">步驟 5。</span><span class="sxs-lookup"><span data-stu-id="ef3db-151">Step 5.</span></span> <span data-ttu-id="ef3db-152">管理計畫</span><span class="sxs-lookup"><span data-stu-id="ef3db-152">Plan for governance</span></span>

<span data-ttu-id="ef3db-153">判斷您的監管需求，以及如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="ef3db-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="ef3db-154">請前往 [Teams 中的管理規劃](plan-teams-governance.md) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ef3db-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ef3db-156">決策點</span><span class="sxs-lookup"><span data-stu-id="ef3db-156">Decision point</span></span>|<ul><li><span data-ttu-id="ef3db-157">請遵循 Teams 中管理計畫中的指導方針，決定並記錄 [您的管理需求](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="ef3db-158">步驟 6.</span><span class="sxs-lookup"><span data-stu-id="ef3db-158">Step 6.</span></span> <span data-ttu-id="ef3db-159">部署 Teams 以共同合作</span><span class="sxs-lookup"><span data-stu-id="ef3db-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="ef3db-160">在您加入 Microsoft 365 政府 - GCC 之後，請遵循如何推出 Microsoft Teams 中概述的建議 [部署路徑](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="ef3db-161">請務必與採用與變更管理團隊和 Teams 領獎人互動。</span><span class="sxs-lookup"><span data-stu-id="ef3db-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="ef3db-162">您也可以與 [FastTrack](https://www.microsoft.com/fasttrack) 或您選擇的合作夥伴合作，以開始服務。</span><span class="sxs-lookup"><span data-stu-id="ef3db-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="ef3db-163">步驟 7.</span><span class="sxs-lookup"><span data-stu-id="ef3db-163">Step 7.</span></span> <span data-ttu-id="ef3db-164">部署會議與語音的 Teams</span><span class="sxs-lookup"><span data-stu-id="ef3db-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="ef3db-165">這也是將 Teams 與更廣泛的專案關係人群組一起使用，開始規劃推出會議和 [雲端語音功能的時候](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3db-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>