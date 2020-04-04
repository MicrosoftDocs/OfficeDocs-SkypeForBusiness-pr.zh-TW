---
title: Microsoft 365 政府-GCC 部署
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 適用于 IT 專業人員的指導方針，可在處理受美國政府法規制約之資料的實體中，驅動 Office 365 部署
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
ms.openlocfilehash: 3ab398d4d76eb0c1ae6bac37b7c9c198ebc82d86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137804"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="cc3f1-103">規劃 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="cc3f1-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="cc3f1-104">本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署，或其他處理受限於政府法規與需求之資料的其他實體，而您可以使用 Microsoft 365 政府-GCC 來符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="cc3f1-105">新的2020年3月26日：請不要錯過我們可下載[的適用于 GCC 的快速入門手冊](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc3f1-106">Microsoft 團隊在進行線上通話和音訊/視訊會議時，會因為 coronavirus （COVID-19） pandemic 而遭遇大量的高峰。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="cc3f1-107">為了應對通話中的空前增加，並確保連續性和可用性，Microsoft 允許 Microsoft 團隊擁有音訊/視訊伺服器來利用商業資料中心中的處理能力，以及在我們的政府資料中心中。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="cc3f1-108">這些音訊/視訊伺服器位於 Microsoft Azure FedRAMP 在美國的高資格鑒定邊界伺服器內，且不會儲存任何客戶內容。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="cc3f1-109">不過，這些伺服器正在處理通話與會議的音訊和視頻，且在這段期間內是在我們的商業員工中運作。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="cc3f1-110">經確認，已遮罩的人員會透過審查這些伺服器的任何互動式登入，來監視這些伺服器以取得客戶資料的潛在存取權。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="cc3f1-111">合格的人員符合您存取客戶內容的 GCC 需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="cc3f1-112">如需有關篩選需求的詳細資訊，請參閱[GCC 服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="cc3f1-113">感謝您的支援人員，因為我們採取步驟來確保我們的服務在這些特別時間內保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="cc3f1-114">如果您的組織已符合 Microsoft 365 政府版 GCC 資格要求，且適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="cc3f1-115">步驟1。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-115">Step 1.</span></span> <span data-ttu-id="cc3f1-116">判斷貴組織是否需要 Microsoft 365 政府-GCC 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="cc3f1-117">Microsoft 365 政府版-GCC 環境提供對雲端服務（包括 FedRAMP 適中版，以及刑事審判與聯邦稅務資訊系統的需求（CJI 與 FTI 資料類型）的美國政府需求的規範。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="cc3f1-118">除了享受 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府-GCC 所特有的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="cc3f1-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="cc3f1-119">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="cc3f1-120">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="cc3f1-121">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="cc3f1-122">Microsoft 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="cc3f1-123">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中，找到適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="cc3f1-124">[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點，這些好處是圍繞在美國的會議規範需求中心。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="cc3f1-125">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="cc3f1-126">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="cc3f1-128">決策點</span><span class="sxs-lookup"><span data-stu-id="cc3f1-128">Decision points</span></span>|<ul><li><span data-ttu-id="cc3f1-129">決定 Microsoft 365 政府版-GCC 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="cc3f1-130">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="cc3f1-131">Microsoft 365 政府版-GCC 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="cc3f1-132">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="cc3f1-133">步驟2。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-133">Step 2.</span></span> <span data-ttu-id="cc3f1-134">適用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="cc3f1-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="cc3f1-135">如果決定此服務適合您的組織，請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="cc3f1-136">步驟3。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-136">Step 3.</span></span> <span data-ttu-id="cc3f1-137">瞭解 Microsoft 365 政府-GCC 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="cc3f1-138">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="cc3f1-140">決策點</span><span class="sxs-lookup"><span data-stu-id="cc3f1-140">Decision point</span></span>|<ul><li><span data-ttu-id="cc3f1-141">決定是否要修改任何預設的 Microsoft 365 政府版-GCC 安全設定，並解決以首先瞭解您所做的任何變更對您造成的影響。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="cc3f1-142">步驟4。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-142">Step 4.</span></span> <span data-ttu-id="cc3f1-143">瞭解哪些功能目前無法使用或預設為停用。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="cc3f1-144">為了滿足政府雲端客戶的需求，Microsoft 365 政府版與企業版方案之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="cc3f1-145">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="cc3f1-146">Microsoft 團隊服務描述</span><span class="sxs-lookup"><span data-stu-id="cc3f1-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="cc3f1-147">當所有其他工作負載在 GCC 雲端中都是完整的，當所有其他的整合作業完成後，就能在小組中使用它們。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="cc3f1-149">決策點</span><span class="sxs-lookup"><span data-stu-id="cc3f1-149">Decision point</span></span>|<ul><li><span data-ttu-id="cc3f1-150">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="cc3f1-151">步驟5。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-151">Step 5.</span></span> <span data-ttu-id="cc3f1-152">規劃管理</span><span class="sxs-lookup"><span data-stu-id="cc3f1-152">Plan for governance</span></span>

<span data-ttu-id="cc3f1-153">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="cc3f1-154">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="cc3f1-156">決策點</span><span class="sxs-lookup"><span data-stu-id="cc3f1-156">Decision point</span></span>|<ul><li><span data-ttu-id="cc3f1-157">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="cc3f1-158">步驟6。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-158">Step 6.</span></span> <span data-ttu-id="cc3f1-159">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="cc3f1-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="cc3f1-160">在您 onboarded 至 Microsoft 365 政府– GCC 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="cc3f1-161">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="cc3f1-162">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="cc3f1-163">步驟7。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-163">Step 7.</span></span> <span data-ttu-id="cc3f1-164">為會議和語音部署團隊</span><span class="sxs-lookup"><span data-stu-id="cc3f1-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="cc3f1-165">這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。</span><span class="sxs-lookup"><span data-stu-id="cc3f1-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

