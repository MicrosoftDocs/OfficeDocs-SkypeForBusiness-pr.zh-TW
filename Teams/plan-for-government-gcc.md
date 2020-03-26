---
title: 規劃 Microsoft 365 政府-GCC 部署-Microsoft 團隊
author: lolajacobsen
ms.author: lolaj
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f7987d450b5a7b1fc23c39ed1e96ee0f953ae9
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978505"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="b5089-103">規劃 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="b5089-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="b5089-104">本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署，或其他處理受限於政府法規與需求之資料的其他實體，這些專業人員使用 Microsoft365政府-GCC 適用于符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="b5089-105">新的2020年3月26日：請不要錯過我們可下載[的適用于 GCC 的快速入門手冊](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="b5089-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5089-106">Microsoft 團隊在進行線上通話和音訊/視訊會議時，會因為 coronavirus （COVID-19） pandemic 而遭遇大量的高峰。</span><span class="sxs-lookup"><span data-stu-id="b5089-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="b5089-107">為了應對通話中的空前增加，並確保連續性和可用性，Microsoft 允許 Microsoft 團隊擁有音訊/視訊伺服器來利用商業資料中心中的處理能力，以及在我們的政府資料中心中。</span><span class="sxs-lookup"><span data-stu-id="b5089-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="b5089-108">這些音訊/視訊伺服器位於 Microsoft Azure FedRAMP 在美國的高資格鑒定邊界伺服器內，且不會儲存任何客戶內容。</span><span class="sxs-lookup"><span data-stu-id="b5089-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="b5089-109">不過，這些伺服器正在處理通話與會議的音訊和視頻，且在這段期間內是在我們的商業員工中運作。</span><span class="sxs-lookup"><span data-stu-id="b5089-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="b5089-110">經確認，已遮罩的人員會透過審查這些伺服器的任何互動式登入，來監視這些伺服器以取得客戶資料的潛在存取權。</span><span class="sxs-lookup"><span data-stu-id="b5089-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="b5089-111">合格的人員符合您存取客戶內容的 GCC 需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="b5089-112">如需有關篩選需求的詳細資訊，請參閱[GCC 服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="b5089-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="b5089-113">感謝您的支援人員，因為我們採取步驟來確保我們的服務在這些特別時間內保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="b5089-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="b5089-114">如果您的組織已符合 Microsoft 365 政府版 GCC 資格要求，且適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="b5089-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="b5089-115">步驟1。</span><span class="sxs-lookup"><span data-stu-id="b5089-115">Step 1.</span></span> <span data-ttu-id="b5089-116">判斷貴組織是否需要 Microsoft 365 政府-GCC 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="b5089-117">Microsoft 365 政府版-GCC 環境提供對雲端服務（包括 FedRAMP 適中版，以及刑事審判與聯邦稅務資訊系統的需求（CJI 與 FTI 資料類型）的美國政府需求的規範。</span><span class="sxs-lookup"><span data-stu-id="b5089-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="b5089-118">除了享受 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府-GCC 所特有的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="b5089-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="b5089-119">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="b5089-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="b5089-120">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="b5089-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="b5089-121">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="b5089-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="b5089-122">Microsoft 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="b5089-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="b5089-123">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中，找到適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b5089-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="b5089-124">[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點，這些好處是圍繞在美國的會議規範需求中心。</span><span class="sxs-lookup"><span data-stu-id="b5089-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="b5089-125">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="b5089-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="b5089-126">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b5089-128">決策點</span><span class="sxs-lookup"><span data-stu-id="b5089-128">Decision points</span></span>|<ul><li><span data-ttu-id="b5089-129">決定 Microsoft 365 政府版-GCC 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="b5089-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="b5089-130">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="b5089-131">Microsoft 365 政府版-GCC 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="b5089-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="b5089-132">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="b5089-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="b5089-133">步驟2。</span><span class="sxs-lookup"><span data-stu-id="b5089-133">Step 2.</span></span> <span data-ttu-id="b5089-134">適用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="b5089-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="b5089-135">如果決定此服務適合您的組織，請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="b5089-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="b5089-136">步驟3。</span><span class="sxs-lookup"><span data-stu-id="b5089-136">Step 3.</span></span> <span data-ttu-id="b5089-137">瞭解 Microsoft 365 政府-GCC 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b5089-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="b5089-138">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b5089-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b5089-140">決策點</span><span class="sxs-lookup"><span data-stu-id="b5089-140">Decision point</span></span>|<ul><li><span data-ttu-id="b5089-141">決定是否要修改任何預設的 Microsoft 365 政府版-GCC 安全設定，並解決以首先瞭解您所做的任何變更對您造成的影響。</span><span class="sxs-lookup"><span data-stu-id="b5089-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="b5089-142">步驟4。</span><span class="sxs-lookup"><span data-stu-id="b5089-142">Step 4.</span></span> <span data-ttu-id="b5089-143">瞭解哪些功能目前無法使用或預設為停用。</span><span class="sxs-lookup"><span data-stu-id="b5089-143">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="b5089-144">為了滿足政府雲端客戶的需求，Microsoft 365 政府版與企業版方案之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="b5089-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="b5089-145">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="b5089-145">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="b5089-146">功能</span><span class="sxs-lookup"><span data-stu-id="b5089-146">Feature</span></span>                     | <span data-ttu-id="b5089-147">GCC</span><span class="sxs-lookup"><span data-stu-id="b5089-147">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="b5089-148">基本</span><span class="sxs-lookup"><span data-stu-id="b5089-148">Base</span></span> | <span data-ttu-id="b5089-149">Id</span><span class="sxs-lookup"><span data-stu-id="b5089-149">Login</span></span> | <span data-ttu-id="b5089-150">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-150">Available</span></span> |
| | <span data-ttu-id="b5089-151">目前狀態</span><span class="sxs-lookup"><span data-stu-id="b5089-151">Presence</span></span> | <span data-ttu-id="b5089-152">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-152">Available</span></span> |
| | <span data-ttu-id="b5089-153">整合的目前狀態（商務用 Skype 和小組已統一）</span><span class="sxs-lookup"><span data-stu-id="b5089-153">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="b5089-154">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-154">Available</span></span> |
| <span data-ttu-id="b5089-155">操作</span><span class="sxs-lookup"><span data-stu-id="b5089-155">Activity</span></span> | <span data-ttu-id="b5089-156">複製</span><span class="sxs-lookup"><span data-stu-id="b5089-156">Feed</span></span> | <span data-ttu-id="b5089-157">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-157">Available</span></span> |
|  | <span data-ttu-id="b5089-158">我的活動</span><span class="sxs-lookup"><span data-stu-id="b5089-158">My Activity</span></span> | <span data-ttu-id="b5089-159">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-159">Available</span></span> |
| <span data-ttu-id="b5089-160">聊天</span><span class="sxs-lookup"><span data-stu-id="b5089-160">Chat</span></span> | <span data-ttu-id="b5089-161">交談</span><span class="sxs-lookup"><span data-stu-id="b5089-161">Conversation</span></span> | <span data-ttu-id="b5089-162">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-162">Available</span></span> |
| | <span data-ttu-id="b5089-163">檔案</span><span class="sxs-lookup"><span data-stu-id="b5089-163">Files</span></span> | <span data-ttu-id="b5089-164">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-164">Available</span></span> |
| | <span data-ttu-id="b5089-165">組織結構</span><span class="sxs-lookup"><span data-stu-id="b5089-165">Org chart</span></span> | <span data-ttu-id="b5089-166">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-166">Available</span></span> |
| | <span data-ttu-id="b5089-167">操作</span><span class="sxs-lookup"><span data-stu-id="b5089-167">Activity</span></span> | <span data-ttu-id="b5089-168">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-168">Available</span></span> |
| | <span data-ttu-id="b5089-169">互通性（1:1 團隊-商務用 Skype 聊天）</span><span class="sxs-lookup"><span data-stu-id="b5089-169">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="b5089-170">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-170">Available</span></span> |
| <span data-ttu-id="b5089-171">Teams</span><span class="sxs-lookup"><span data-stu-id="b5089-171">Teams</span></span> | <span data-ttu-id="b5089-172">頻道訊息</span><span class="sxs-lookup"><span data-stu-id="b5089-172">Channel message</span></span> | <span data-ttu-id="b5089-173">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-173">Available</span></span> |
| | <span data-ttu-id="b5089-174">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="b5089-174">Channel files</span></span> | <span data-ttu-id="b5089-175">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-175">Available</span></span> |
| | <span data-ttu-id="b5089-176">[OneNote] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b5089-176">OneNote tab</span></span> | <span data-ttu-id="b5089-177">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="b5089-177">On the Government backlog</span></span> |
| | <span data-ttu-id="b5089-178">透過電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="b5089-178">Email a channel</span></span> | <span data-ttu-id="b5089-179">無法使用</span><span class="sxs-lookup"><span data-stu-id="b5089-179">Not available</span></span> |
| | <span data-ttu-id="b5089-180">新增成員</span><span class="sxs-lookup"><span data-stu-id="b5089-180">Add member</span></span> | <span data-ttu-id="b5089-181">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-181">Available</span></span> |
| | <span data-ttu-id="b5089-182">來賓存取</span><span class="sxs-lookup"><span data-stu-id="b5089-182">Guest access</span></span> | <span data-ttu-id="b5089-183">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-183">Available</span></span> |
| <span data-ttu-id="b5089-184">會議</span><span class="sxs-lookup"><span data-stu-id="b5089-184">Meetings</span></span> | <span data-ttu-id="b5089-185">排程會議</span><span class="sxs-lookup"><span data-stu-id="b5089-185">Schedule meeting</span></span> | <span data-ttu-id="b5089-186">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-186">Available</span></span> |
| | <span data-ttu-id="b5089-187">加入會議</span><span class="sxs-lookup"><span data-stu-id="b5089-187">Join meeting</span></span> | <span data-ttu-id="b5089-188">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-188">Available</span></span> |
| | <span data-ttu-id="b5089-189">VoIP 會議</span><span class="sxs-lookup"><span data-stu-id="b5089-189">VoIP meeting</span></span> | <span data-ttu-id="b5089-190">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-190">Available</span></span> |
| | <span data-ttu-id="b5089-191">桌面共用</span><span class="sxs-lookup"><span data-stu-id="b5089-191">Desktop sharing</span></span> | <span data-ttu-id="b5089-192">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-192">Available</span></span> |
| | <span data-ttu-id="b5089-193">在共用中提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="b5089-193">Give and take control in sharing</span></span> | <span data-ttu-id="b5089-194">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-194">Available</span></span> |
| | <span data-ttu-id="b5089-195">從會議室連接</span><span class="sxs-lookup"><span data-stu-id="b5089-195">Connect from a conference room</span></span> | <span data-ttu-id="b5089-196">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-196">Available</span></span> |
| | <span data-ttu-id="b5089-197">匿名加入</span><span class="sxs-lookup"><span data-stu-id="b5089-197">Anonymous join</span></span> | <span data-ttu-id="b5089-198">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-198">Available</span></span> |
| | <span data-ttu-id="b5089-199">雲端錄製</span><span class="sxs-lookup"><span data-stu-id="b5089-199">Cloud recording</span></span> | <span data-ttu-id="b5089-200">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-200">Available</span></span> |
| | <span data-ttu-id="b5089-201">會議記事</span><span class="sxs-lookup"><span data-stu-id="b5089-201">Meeting notes</span></span> | <span data-ttu-id="b5089-202">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-202">Available</span></span> |
| | <span data-ttu-id="b5089-203">即時事件</span><span class="sxs-lookup"><span data-stu-id="b5089-203">Live Events</span></span> | <span data-ttu-id="b5089-204">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-204">Available</span></span> |
| | <span data-ttu-id="b5089-205">同盟會議</span><span class="sxs-lookup"><span data-stu-id="b5089-205">Federated meetings</span></span> | <span data-ttu-id="b5089-206">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-206">Available</span></span> |
| | <span data-ttu-id="b5089-207">Surface Hub 支援</span><span class="sxs-lookup"><span data-stu-id="b5089-207">Surface Hub support</span></span> | <span data-ttu-id="b5089-208">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-208">Available</span></span> |
| <span data-ttu-id="b5089-209">撥</span><span class="sxs-lookup"><span data-stu-id="b5089-209">Calls</span></span> | <span data-ttu-id="b5089-210">連絡人</span><span class="sxs-lookup"><span data-stu-id="b5089-210">Contacts</span></span> | <span data-ttu-id="b5089-211">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-211">Available</span></span> |
| | <span data-ttu-id="b5089-212">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="b5089-212">History</span></span> | <span data-ttu-id="b5089-213">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-213">Available</span></span> |
| | <span data-ttu-id="b5089-214">語音信箱</span><span class="sxs-lookup"><span data-stu-id="b5089-214">Voicemail</span></span> | <span data-ttu-id="b5089-215">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-215">Available</span></span> |
| | <span data-ttu-id="b5089-216">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="b5089-216">VoIP call</span></span> | <span data-ttu-id="b5089-217">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-217">Available</span></span> |
| | <span data-ttu-id="b5089-218">商務用 Skype-小組通話</span><span class="sxs-lookup"><span data-stu-id="b5089-218">Skype for Business - Teams calling</span></span> | <span data-ttu-id="b5089-219">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-219">Available</span></span> |
| | <span data-ttu-id="b5089-220">通話方案</span><span class="sxs-lookup"><span data-stu-id="b5089-220">Calling Plans</span></span> | <span data-ttu-id="b5089-221">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-221">Available</span></span> |
| | <span data-ttu-id="b5089-222">音訊會議（透過允許會議參與者透過 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="b5089-222">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="b5089-223">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-223">Available</span></span> |
| | <span data-ttu-id="b5089-224">Microsoft Phone 系統直向路由</span><span class="sxs-lookup"><span data-stu-id="b5089-224">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="b5089-225">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-225">Available</span></span> |
| | <span data-ttu-id="b5089-226">PSTN 呼叫者的大廳</span><span class="sxs-lookup"><span data-stu-id="b5089-226">Lobby for PSTN callers</span></span> | <span data-ttu-id="b5089-227">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-227">Available</span></span> |
| | <span data-ttu-id="b5089-228">通話佇列</span><span class="sxs-lookup"><span data-stu-id="b5089-228">Call queue</span></span> | <span data-ttu-id="b5089-229">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-229">Available</span></span> |
| | <span data-ttu-id="b5089-230">老闆及代理人支援</span><span class="sxs-lookup"><span data-stu-id="b5089-230">Boss and delegate support</span></span> | <span data-ttu-id="b5089-231">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-231">Available</span></span> |
| | <span data-ttu-id="b5089-232">顧問式與安全轉接</span><span class="sxs-lookup"><span data-stu-id="b5089-232">Consultative and safe transfer</span></span> | <span data-ttu-id="b5089-233">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-233">Available</span></span> |
| | <span data-ttu-id="b5089-234">請勿打擾突破</span><span class="sxs-lookup"><span data-stu-id="b5089-234">Do not disturb breakthrough</span></span> | <span data-ttu-id="b5089-235">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-235">Available</span></span> |
| | <span data-ttu-id="b5089-236">區別性鈴聲</span><span class="sxs-lookup"><span data-stu-id="b5089-236">Distinctive ring</span></span> | <span data-ttu-id="b5089-237">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-237">Available</span></span> |
| | <span data-ttu-id="b5089-238">1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級</span><span class="sxs-lookup"><span data-stu-id="b5089-238">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="b5089-239">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-239">Available</span></span> |
| | <span data-ttu-id="b5089-240">[轉寄至] 群組</span><span class="sxs-lookup"><span data-stu-id="b5089-240">Forward to group</span></span> | <span data-ttu-id="b5089-241">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-241">Available</span></span> |
| | <span data-ttu-id="b5089-242">轉接至 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="b5089-242">Transfer to PSTN call</span></span> | <span data-ttu-id="b5089-243">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-243">Available</span></span> |
| | <span data-ttu-id="b5089-244">緊急電話撥打電話方案</span><span class="sxs-lookup"><span data-stu-id="b5089-244">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="b5089-245">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-245">Available</span></span> |
| | <span data-ttu-id="b5089-246">現有的認證 SIP 手機支援</span><span class="sxs-lookup"><span data-stu-id="b5089-246">Support for existing certified SIP phones</span></span> | <span data-ttu-id="b5089-247">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-247">Available</span></span> |
| | <span data-ttu-id="b5089-248">USB HID</span><span class="sxs-lookup"><span data-stu-id="b5089-248">USB HID</span></span> | <span data-ttu-id="b5089-249">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-249">Available</span></span> |
| | <span data-ttu-id="b5089-250">通話和會議的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b5089-250">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="b5089-251">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-251">Available</span></span> |
| | <span data-ttu-id="b5089-252">組織自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b5089-252">Organization auto attendant</span></span> | <span data-ttu-id="b5089-253">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-253">Available</span></span> |
| | <span data-ttu-id="b5089-254">Skype 消費者-小組通話支援</span><span class="sxs-lookup"><span data-stu-id="b5089-254">Skype consumer - Teams call support</span></span> | <span data-ttu-id="b5089-255">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-255">Available</span></span> |
| <span data-ttu-id="b5089-256">檔案</span><span class="sxs-lookup"><span data-stu-id="b5089-256">Files</span></span> | <span data-ttu-id="b5089-257">近</span><span class="sxs-lookup"><span data-stu-id="b5089-257">Recent</span></span> | <span data-ttu-id="b5089-258">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-258">Available</span></span> |
| | <span data-ttu-id="b5089-259">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5089-259">Microsoft Teams</span></span> | <span data-ttu-id="b5089-260">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-260">Available</span></span> |
| <span data-ttu-id="b5089-261">商店</span><span class="sxs-lookup"><span data-stu-id="b5089-261">Store</span></span> | <span data-ttu-id="b5089-262">App Store</span><span class="sxs-lookup"><span data-stu-id="b5089-262">App Store</span></span> | <span data-ttu-id="b5089-263">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-263">Available</span></span> |
| <span data-ttu-id="b5089-264">檢索</span><span class="sxs-lookup"><span data-stu-id="b5089-264">Search</span></span> | <span data-ttu-id="b5089-265">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="b5089-265">Messages</span></span> | <span data-ttu-id="b5089-266">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-266">Available</span></span> |
| | <span data-ttu-id="b5089-267">人員</span><span class="sxs-lookup"><span data-stu-id="b5089-267">People</span></span> | <span data-ttu-id="b5089-268">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-268">Available</span></span> |
| | <span data-ttu-id="b5089-269">檔案</span><span class="sxs-lookup"><span data-stu-id="b5089-269">Files</span></span> | <span data-ttu-id="b5089-270">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-270">Available</span></span> |
| | <span data-ttu-id="b5089-271">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="b5089-271">Slash commands</span></span> | <span data-ttu-id="b5089-272">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-272">Available</span></span> |
| <span data-ttu-id="b5089-273">從屬</span><span class="sxs-lookup"><span data-stu-id="b5089-273">Compliance</span></span> | <span data-ttu-id="b5089-274">合規性內容搜尋</span><span class="sxs-lookup"><span data-stu-id="b5089-274">Compliance content search</span></span> | <span data-ttu-id="b5089-275">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-275">Available</span></span> |
| | <span data-ttu-id="b5089-276">留成</span><span class="sxs-lookup"><span data-stu-id="b5089-276">Retention</span></span> | <span data-ttu-id="b5089-277">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-277">Available</span></span> |
| | <span data-ttu-id="b5089-278">審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="b5089-278">Audit log search</span></span> | <span data-ttu-id="b5089-279">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-279">Available</span></span> |
| | <span data-ttu-id="b5089-280">法律封存</span><span class="sxs-lookup"><span data-stu-id="b5089-280">Legal hold</span></span> | <span data-ttu-id="b5089-281">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-281">Available</span></span> |
| | <span data-ttu-id="b5089-282">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b5089-282">eDiscovery</span></span> | <span data-ttu-id="b5089-283">可用</span><span class="sxs-lookup"><span data-stu-id="b5089-283">Available</span></span> |

> [!Note]
> <span data-ttu-id="b5089-284">當所有其他工作負載在 GCC 雲端中都是完整的，當所有其他的整合作業完成後，就能在小組中使用它們。</span><span class="sxs-lookup"><span data-stu-id="b5089-284">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b5089-286">決策點</span><span class="sxs-lookup"><span data-stu-id="b5089-286">Decision point</span></span>|<ul><li><span data-ttu-id="b5089-287">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-287">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="b5089-288">步驟5。</span><span class="sxs-lookup"><span data-stu-id="b5089-288">Step 5.</span></span> <span data-ttu-id="b5089-289">規劃管理</span><span class="sxs-lookup"><span data-stu-id="b5089-289">Plan for governance</span></span>

<span data-ttu-id="b5089-290">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-290">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="b5089-291">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="b5089-291">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b5089-293">決策點</span><span class="sxs-lookup"><span data-stu-id="b5089-293">Decision point</span></span>|<ul><li><span data-ttu-id="b5089-294">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="b5089-294">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="b5089-295">步驟6。</span><span class="sxs-lookup"><span data-stu-id="b5089-295">Step 6.</span></span> <span data-ttu-id="b5089-296">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="b5089-296">Deploy Teams for collaboration</span></span>

<span data-ttu-id="b5089-297">在您 onboarded 至 Microsoft 365 政府– GCC 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="b5089-297">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="b5089-298">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="b5089-298">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="b5089-299">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="b5089-299">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="b5089-300">步驟7。</span><span class="sxs-lookup"><span data-stu-id="b5089-300">Step 7.</span></span> <span data-ttu-id="b5089-301">為會議和語音部署團隊</span><span class="sxs-lookup"><span data-stu-id="b5089-301">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="b5089-302">這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。</span><span class="sxs-lookup"><span data-stu-id="b5089-302">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

