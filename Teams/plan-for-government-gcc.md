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
ms.openlocfilehash: a1b97e82edd97079c1e4615e5bb7fcf4a1eb2fea
ms.sourcegitcommit: b6eb22e96be5fb18984f1dd05e4eb8f2cfc032f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42968658"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="60871-103">規劃 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="60871-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="60871-104">本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署，或其他處理受限於政府法規與需求之資料的其他實體，這些專業人員使用 Microsoft365政府-GCC 適用于符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="60871-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60871-105">Microsoft 團隊在進行線上通話和音訊/視訊會議時，會因為 coronavirus （COVID-19） pandemic 而遭遇大量的高峰。</span><span class="sxs-lookup"><span data-stu-id="60871-105">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="60871-106">為了應對通話中的空前增加，並確保連續性和可用性，Microsoft 允許 Microsoft 團隊擁有音訊/視訊伺服器來利用商業資料中心中的處理能力，以及在我們的政府資料中心中。</span><span class="sxs-lookup"><span data-stu-id="60871-106">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="60871-107">這些音訊/視訊伺服器位於 Microsoft Azure FedRAMP 在美國的高資格鑒定邊界伺服器內，且不會儲存任何客戶內容。</span><span class="sxs-lookup"><span data-stu-id="60871-107">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="60871-108">不過，這些伺服器正在處理通話與會議的音訊和視頻，且在這段期間內是在我們的商業員工中運作。</span><span class="sxs-lookup"><span data-stu-id="60871-108">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="60871-109">經確認，已遮罩的人員會透過審查這些伺服器的任何互動式登入，來監視這些伺服器以取得客戶資料的潛在存取權。</span><span class="sxs-lookup"><span data-stu-id="60871-109">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="60871-110">合格的人員符合您存取客戶內容的 GCC 需求。</span><span class="sxs-lookup"><span data-stu-id="60871-110">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="60871-111">如需有關篩選需求的詳細資訊，請參閱[GCC 服務描述](Office365-ServiceDescriptions\office-365-platform-service-description\office-365-us-government\gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="60871-111">For details about screening requirements, see the [GCC service description](Office365-ServiceDescriptions\office-365-platform-service-description\office-365-us-government\gcc.md).</span></span><br/>
> 
><span data-ttu-id="60871-112">感謝您的支援人員，因為我們採取步驟來確保我們的服務在這些特別時間內保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="60871-112">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="60871-113">如果您的組織已符合 Microsoft 365 政府版 GCC 資格要求，且適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="60871-113">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="60871-114">步驟1。</span><span class="sxs-lookup"><span data-stu-id="60871-114">Step 1.</span></span> <span data-ttu-id="60871-115">判斷貴組織是否需要 Microsoft 365 政府-GCC 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="60871-115">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="60871-116">Microsoft 365 政府版-GCC 環境提供對雲端服務（包括 FedRAMP 適中版，以及刑事審判與聯邦稅務資訊系統的需求（CJI 與 FTI 資料類型）的美國政府需求的規範。</span><span class="sxs-lookup"><span data-stu-id="60871-116">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="60871-117">除了享受 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府-GCC 所特有的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="60871-117">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="60871-118">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="60871-118">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="60871-119">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="60871-119">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="60871-120">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="60871-120">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="60871-121">Microsoft 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="60871-121">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="60871-122">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中，找到適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="60871-122">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="60871-123">[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點，這些好處是圍繞在美國的會議規範需求中心。</span><span class="sxs-lookup"><span data-stu-id="60871-123">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="60871-124">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="60871-124">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="60871-125">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="60871-125">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60871-127">決策點</span><span class="sxs-lookup"><span data-stu-id="60871-127">Decision points</span></span>|<ul><li><span data-ttu-id="60871-128">決定 Microsoft 365 政府版-GCC 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="60871-128">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="60871-129">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="60871-129">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="60871-130">Microsoft 365 政府版-GCC 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="60871-130">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="60871-131">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="60871-131">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="60871-132">步驟2。</span><span class="sxs-lookup"><span data-stu-id="60871-132">Step 2.</span></span> <span data-ttu-id="60871-133">適用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="60871-133">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="60871-134">如果決定此服務適合您的組織，請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="60871-134">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="60871-135">步驟3。</span><span class="sxs-lookup"><span data-stu-id="60871-135">Step 3.</span></span> <span data-ttu-id="60871-136">瞭解 Microsoft 365 政府-GCC 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="60871-136">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="60871-137">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="60871-137">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60871-139">決策點</span><span class="sxs-lookup"><span data-stu-id="60871-139">Decision point</span></span>|<ul><li><span data-ttu-id="60871-140">決定是否要修改任何預設的 Microsoft 365 政府版-GCC 安全設定，並解決以首先瞭解您所做的任何變更對您造成的影響。</span><span class="sxs-lookup"><span data-stu-id="60871-140">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="60871-141">步驟4。</span><span class="sxs-lookup"><span data-stu-id="60871-141">Step 4.</span></span> <span data-ttu-id="60871-142">瞭解哪些功能目前無法使用或預設為停用。</span><span class="sxs-lookup"><span data-stu-id="60871-142">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="60871-143">為了滿足政府雲端客戶的需求，Microsoft 365 政府版與企業版方案之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="60871-143">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="60871-144">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="60871-144">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="60871-145">功能</span><span class="sxs-lookup"><span data-stu-id="60871-145">Feature</span></span>                     | <span data-ttu-id="60871-146">GCC</span><span class="sxs-lookup"><span data-stu-id="60871-146">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="60871-147">基本</span><span class="sxs-lookup"><span data-stu-id="60871-147">Base</span></span> | <span data-ttu-id="60871-148">Id</span><span class="sxs-lookup"><span data-stu-id="60871-148">Login</span></span> | <span data-ttu-id="60871-149">可用</span><span class="sxs-lookup"><span data-stu-id="60871-149">Available</span></span> |
| | <span data-ttu-id="60871-150">目前狀態</span><span class="sxs-lookup"><span data-stu-id="60871-150">Presence</span></span> | <span data-ttu-id="60871-151">可用</span><span class="sxs-lookup"><span data-stu-id="60871-151">Available</span></span> |
| | <span data-ttu-id="60871-152">整合的目前狀態（商務用 Skype 和小組已統一）</span><span class="sxs-lookup"><span data-stu-id="60871-152">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="60871-153">可用</span><span class="sxs-lookup"><span data-stu-id="60871-153">Available</span></span> |
| <span data-ttu-id="60871-154">操作</span><span class="sxs-lookup"><span data-stu-id="60871-154">Activity</span></span> | <span data-ttu-id="60871-155">複製</span><span class="sxs-lookup"><span data-stu-id="60871-155">Feed</span></span> | <span data-ttu-id="60871-156">可用</span><span class="sxs-lookup"><span data-stu-id="60871-156">Available</span></span> |
|  | <span data-ttu-id="60871-157">我的活動</span><span class="sxs-lookup"><span data-stu-id="60871-157">My Activity</span></span> | <span data-ttu-id="60871-158">可用</span><span class="sxs-lookup"><span data-stu-id="60871-158">Available</span></span> |
| <span data-ttu-id="60871-159">聊天</span><span class="sxs-lookup"><span data-stu-id="60871-159">Chat</span></span> | <span data-ttu-id="60871-160">交談</span><span class="sxs-lookup"><span data-stu-id="60871-160">Conversation</span></span> | <span data-ttu-id="60871-161">可用</span><span class="sxs-lookup"><span data-stu-id="60871-161">Available</span></span> |
| | <span data-ttu-id="60871-162">檔案</span><span class="sxs-lookup"><span data-stu-id="60871-162">Files</span></span> | <span data-ttu-id="60871-163">可用</span><span class="sxs-lookup"><span data-stu-id="60871-163">Available</span></span> |
| | <span data-ttu-id="60871-164">組織結構</span><span class="sxs-lookup"><span data-stu-id="60871-164">Org chart</span></span> | <span data-ttu-id="60871-165">可用</span><span class="sxs-lookup"><span data-stu-id="60871-165">Available</span></span> |
| | <span data-ttu-id="60871-166">操作</span><span class="sxs-lookup"><span data-stu-id="60871-166">Activity</span></span> | <span data-ttu-id="60871-167">可用</span><span class="sxs-lookup"><span data-stu-id="60871-167">Available</span></span> |
| | <span data-ttu-id="60871-168">互通性（1:1 團隊-商務用 Skype 聊天）</span><span class="sxs-lookup"><span data-stu-id="60871-168">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="60871-169">可用</span><span class="sxs-lookup"><span data-stu-id="60871-169">Available</span></span> |
| <span data-ttu-id="60871-170">Teams</span><span class="sxs-lookup"><span data-stu-id="60871-170">Teams</span></span> | <span data-ttu-id="60871-171">頻道訊息</span><span class="sxs-lookup"><span data-stu-id="60871-171">Channel message</span></span> | <span data-ttu-id="60871-172">可用</span><span class="sxs-lookup"><span data-stu-id="60871-172">Available</span></span> |
| | <span data-ttu-id="60871-173">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="60871-173">Channel files</span></span> | <span data-ttu-id="60871-174">可用</span><span class="sxs-lookup"><span data-stu-id="60871-174">Available</span></span> |
| | <span data-ttu-id="60871-175">[OneNote] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="60871-175">OneNote tab</span></span> | <span data-ttu-id="60871-176">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="60871-176">On the Government backlog</span></span> |
| | <span data-ttu-id="60871-177">透過電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="60871-177">Email a channel</span></span> | <span data-ttu-id="60871-178">無法使用</span><span class="sxs-lookup"><span data-stu-id="60871-178">Not available</span></span> |
| | <span data-ttu-id="60871-179">新增成員</span><span class="sxs-lookup"><span data-stu-id="60871-179">Add member</span></span> | <span data-ttu-id="60871-180">可用</span><span class="sxs-lookup"><span data-stu-id="60871-180">Available</span></span> |
| | <span data-ttu-id="60871-181">來賓存取</span><span class="sxs-lookup"><span data-stu-id="60871-181">Guest access</span></span> | <span data-ttu-id="60871-182">可用</span><span class="sxs-lookup"><span data-stu-id="60871-182">Available</span></span> |
| <span data-ttu-id="60871-183">會議</span><span class="sxs-lookup"><span data-stu-id="60871-183">Meetings</span></span> | <span data-ttu-id="60871-184">排程會議</span><span class="sxs-lookup"><span data-stu-id="60871-184">Schedule meeting</span></span> | <span data-ttu-id="60871-185">可用</span><span class="sxs-lookup"><span data-stu-id="60871-185">Available</span></span> |
| | <span data-ttu-id="60871-186">加入會議</span><span class="sxs-lookup"><span data-stu-id="60871-186">Join meeting</span></span> | <span data-ttu-id="60871-187">可用</span><span class="sxs-lookup"><span data-stu-id="60871-187">Available</span></span> |
| | <span data-ttu-id="60871-188">VoIP 會議</span><span class="sxs-lookup"><span data-stu-id="60871-188">VoIP meeting</span></span> | <span data-ttu-id="60871-189">可用</span><span class="sxs-lookup"><span data-stu-id="60871-189">Available</span></span> |
| | <span data-ttu-id="60871-190">桌面共用</span><span class="sxs-lookup"><span data-stu-id="60871-190">Desktop sharing</span></span> | <span data-ttu-id="60871-191">可用</span><span class="sxs-lookup"><span data-stu-id="60871-191">Available</span></span> |
| | <span data-ttu-id="60871-192">在共用中提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="60871-192">Give and take control in sharing</span></span> | <span data-ttu-id="60871-193">可用</span><span class="sxs-lookup"><span data-stu-id="60871-193">Available</span></span> |
| | <span data-ttu-id="60871-194">從會議室連接</span><span class="sxs-lookup"><span data-stu-id="60871-194">Connect from a conference room</span></span> | <span data-ttu-id="60871-195">可用</span><span class="sxs-lookup"><span data-stu-id="60871-195">Available</span></span> |
| | <span data-ttu-id="60871-196">匿名加入</span><span class="sxs-lookup"><span data-stu-id="60871-196">Anonymous join</span></span> | <span data-ttu-id="60871-197">可用</span><span class="sxs-lookup"><span data-stu-id="60871-197">Available</span></span> |
| | <span data-ttu-id="60871-198">雲端錄製</span><span class="sxs-lookup"><span data-stu-id="60871-198">Cloud recording</span></span> | <span data-ttu-id="60871-199">可用</span><span class="sxs-lookup"><span data-stu-id="60871-199">Available</span></span> |
| | <span data-ttu-id="60871-200">會議記事</span><span class="sxs-lookup"><span data-stu-id="60871-200">Meeting notes</span></span> | <span data-ttu-id="60871-201">可用</span><span class="sxs-lookup"><span data-stu-id="60871-201">Available</span></span> |
| | <span data-ttu-id="60871-202">即時事件</span><span class="sxs-lookup"><span data-stu-id="60871-202">Live Events</span></span> | <span data-ttu-id="60871-203">可用</span><span class="sxs-lookup"><span data-stu-id="60871-203">Available</span></span> |
| | <span data-ttu-id="60871-204">同盟會議</span><span class="sxs-lookup"><span data-stu-id="60871-204">Federated meetings</span></span> | <span data-ttu-id="60871-205">可用</span><span class="sxs-lookup"><span data-stu-id="60871-205">Available</span></span> |
| | <span data-ttu-id="60871-206">Surface Hub 支援</span><span class="sxs-lookup"><span data-stu-id="60871-206">Surface Hub support</span></span> | <span data-ttu-id="60871-207">可用</span><span class="sxs-lookup"><span data-stu-id="60871-207">Available</span></span> |
| <span data-ttu-id="60871-208">撥</span><span class="sxs-lookup"><span data-stu-id="60871-208">Calls</span></span> | <span data-ttu-id="60871-209">連絡人</span><span class="sxs-lookup"><span data-stu-id="60871-209">Contacts</span></span> | <span data-ttu-id="60871-210">可用</span><span class="sxs-lookup"><span data-stu-id="60871-210">Available</span></span> |
| | <span data-ttu-id="60871-211">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="60871-211">History</span></span> | <span data-ttu-id="60871-212">可用</span><span class="sxs-lookup"><span data-stu-id="60871-212">Available</span></span> |
| | <span data-ttu-id="60871-213">語音信箱</span><span class="sxs-lookup"><span data-stu-id="60871-213">Voicemail</span></span> | <span data-ttu-id="60871-214">可用</span><span class="sxs-lookup"><span data-stu-id="60871-214">Available</span></span> |
| | <span data-ttu-id="60871-215">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="60871-215">VoIP call</span></span> | <span data-ttu-id="60871-216">可用</span><span class="sxs-lookup"><span data-stu-id="60871-216">Available</span></span> |
| | <span data-ttu-id="60871-217">商務用 Skype-小組通話</span><span class="sxs-lookup"><span data-stu-id="60871-217">Skype for Business - Teams calling</span></span> | <span data-ttu-id="60871-218">可用</span><span class="sxs-lookup"><span data-stu-id="60871-218">Available</span></span> |
| | <span data-ttu-id="60871-219">通話方案</span><span class="sxs-lookup"><span data-stu-id="60871-219">Calling Plans</span></span> | <span data-ttu-id="60871-220">可用</span><span class="sxs-lookup"><span data-stu-id="60871-220">Available</span></span> |
| | <span data-ttu-id="60871-221">音訊會議（透過允許會議參與者透過 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="60871-221">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="60871-222">可用</span><span class="sxs-lookup"><span data-stu-id="60871-222">Available</span></span> |
| | <span data-ttu-id="60871-223">Microsoft Phone 系統直向路由</span><span class="sxs-lookup"><span data-stu-id="60871-223">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="60871-224">可用</span><span class="sxs-lookup"><span data-stu-id="60871-224">Available</span></span> |
| | <span data-ttu-id="60871-225">PSTN 呼叫者的大廳</span><span class="sxs-lookup"><span data-stu-id="60871-225">Lobby for PSTN callers</span></span> | <span data-ttu-id="60871-226">可用</span><span class="sxs-lookup"><span data-stu-id="60871-226">Available</span></span> |
| | <span data-ttu-id="60871-227">通話佇列</span><span class="sxs-lookup"><span data-stu-id="60871-227">Call queue</span></span> | <span data-ttu-id="60871-228">可用</span><span class="sxs-lookup"><span data-stu-id="60871-228">Available</span></span> |
| | <span data-ttu-id="60871-229">老闆及代理人支援</span><span class="sxs-lookup"><span data-stu-id="60871-229">Boss and delegate support</span></span> | <span data-ttu-id="60871-230">可用</span><span class="sxs-lookup"><span data-stu-id="60871-230">Available</span></span> |
| | <span data-ttu-id="60871-231">顧問式與安全轉接</span><span class="sxs-lookup"><span data-stu-id="60871-231">Consultative and safe transfer</span></span> | <span data-ttu-id="60871-232">可用</span><span class="sxs-lookup"><span data-stu-id="60871-232">Available</span></span> |
| | <span data-ttu-id="60871-233">請勿打擾突破</span><span class="sxs-lookup"><span data-stu-id="60871-233">Do not disturb breakthrough</span></span> | <span data-ttu-id="60871-234">可用</span><span class="sxs-lookup"><span data-stu-id="60871-234">Available</span></span> |
| | <span data-ttu-id="60871-235">區別性鈴聲</span><span class="sxs-lookup"><span data-stu-id="60871-235">Distinctive ring</span></span> | <span data-ttu-id="60871-236">可用</span><span class="sxs-lookup"><span data-stu-id="60871-236">Available</span></span> |
| | <span data-ttu-id="60871-237">1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級</span><span class="sxs-lookup"><span data-stu-id="60871-237">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="60871-238">可用</span><span class="sxs-lookup"><span data-stu-id="60871-238">Available</span></span> |
| | <span data-ttu-id="60871-239">[轉寄至] 群組</span><span class="sxs-lookup"><span data-stu-id="60871-239">Forward to group</span></span> | <span data-ttu-id="60871-240">可用</span><span class="sxs-lookup"><span data-stu-id="60871-240">Available</span></span> |
| | <span data-ttu-id="60871-241">轉接至 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="60871-241">Transfer to PSTN call</span></span> | <span data-ttu-id="60871-242">可用</span><span class="sxs-lookup"><span data-stu-id="60871-242">Available</span></span> |
| | <span data-ttu-id="60871-243">緊急電話撥打電話方案</span><span class="sxs-lookup"><span data-stu-id="60871-243">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="60871-244">可用</span><span class="sxs-lookup"><span data-stu-id="60871-244">Available</span></span> |
| | <span data-ttu-id="60871-245">現有的認證 SIP 手機支援</span><span class="sxs-lookup"><span data-stu-id="60871-245">Support for existing certified SIP phones</span></span> | <span data-ttu-id="60871-246">可用</span><span class="sxs-lookup"><span data-stu-id="60871-246">Available</span></span> |
| | <span data-ttu-id="60871-247">USB HID</span><span class="sxs-lookup"><span data-stu-id="60871-247">USB HID</span></span> | <span data-ttu-id="60871-248">可用</span><span class="sxs-lookup"><span data-stu-id="60871-248">Available</span></span> |
| | <span data-ttu-id="60871-249">通話和會議的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="60871-249">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="60871-250">可用</span><span class="sxs-lookup"><span data-stu-id="60871-250">Available</span></span> |
| | <span data-ttu-id="60871-251">組織自動語音應答</span><span class="sxs-lookup"><span data-stu-id="60871-251">Organization auto attendant</span></span> | <span data-ttu-id="60871-252">可用</span><span class="sxs-lookup"><span data-stu-id="60871-252">Available</span></span> |
| | <span data-ttu-id="60871-253">Skype 消費者-小組通話支援</span><span class="sxs-lookup"><span data-stu-id="60871-253">Skype consumer - Teams call support</span></span> | <span data-ttu-id="60871-254">可用</span><span class="sxs-lookup"><span data-stu-id="60871-254">Available</span></span> |
| <span data-ttu-id="60871-255">檔案</span><span class="sxs-lookup"><span data-stu-id="60871-255">Files</span></span> | <span data-ttu-id="60871-256">近</span><span class="sxs-lookup"><span data-stu-id="60871-256">Recent</span></span> | <span data-ttu-id="60871-257">可用</span><span class="sxs-lookup"><span data-stu-id="60871-257">Available</span></span> |
| | <span data-ttu-id="60871-258">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60871-258">Microsoft Teams</span></span> | <span data-ttu-id="60871-259">可用</span><span class="sxs-lookup"><span data-stu-id="60871-259">Available</span></span> |
| <span data-ttu-id="60871-260">商店</span><span class="sxs-lookup"><span data-stu-id="60871-260">Store</span></span> | <span data-ttu-id="60871-261">App Store</span><span class="sxs-lookup"><span data-stu-id="60871-261">App Store</span></span> | <span data-ttu-id="60871-262">可用</span><span class="sxs-lookup"><span data-stu-id="60871-262">Available</span></span> |
| <span data-ttu-id="60871-263">檢索</span><span class="sxs-lookup"><span data-stu-id="60871-263">Search</span></span> | <span data-ttu-id="60871-264">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="60871-264">Messages</span></span> | <span data-ttu-id="60871-265">可用</span><span class="sxs-lookup"><span data-stu-id="60871-265">Available</span></span> |
| | <span data-ttu-id="60871-266">人員</span><span class="sxs-lookup"><span data-stu-id="60871-266">People</span></span> | <span data-ttu-id="60871-267">可用</span><span class="sxs-lookup"><span data-stu-id="60871-267">Available</span></span> |
| | <span data-ttu-id="60871-268">檔案</span><span class="sxs-lookup"><span data-stu-id="60871-268">Files</span></span> | <span data-ttu-id="60871-269">可用</span><span class="sxs-lookup"><span data-stu-id="60871-269">Available</span></span> |
| | <span data-ttu-id="60871-270">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="60871-270">Slash commands</span></span> | <span data-ttu-id="60871-271">可用</span><span class="sxs-lookup"><span data-stu-id="60871-271">Available</span></span> |
| <span data-ttu-id="60871-272">從屬</span><span class="sxs-lookup"><span data-stu-id="60871-272">Compliance</span></span> | <span data-ttu-id="60871-273">合規性內容搜尋</span><span class="sxs-lookup"><span data-stu-id="60871-273">Compliance content search</span></span> | <span data-ttu-id="60871-274">可用</span><span class="sxs-lookup"><span data-stu-id="60871-274">Available</span></span> |
| | <span data-ttu-id="60871-275">留成</span><span class="sxs-lookup"><span data-stu-id="60871-275">Retention</span></span> | <span data-ttu-id="60871-276">可用</span><span class="sxs-lookup"><span data-stu-id="60871-276">Available</span></span> |
| | <span data-ttu-id="60871-277">審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="60871-277">Audit log search</span></span> | <span data-ttu-id="60871-278">可用</span><span class="sxs-lookup"><span data-stu-id="60871-278">Available</span></span> |
| | <span data-ttu-id="60871-279">法律封存</span><span class="sxs-lookup"><span data-stu-id="60871-279">Legal hold</span></span> | <span data-ttu-id="60871-280">可用</span><span class="sxs-lookup"><span data-stu-id="60871-280">Available</span></span> |
| | <span data-ttu-id="60871-281">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="60871-281">eDiscovery</span></span> | <span data-ttu-id="60871-282">可用</span><span class="sxs-lookup"><span data-stu-id="60871-282">Available</span></span> |

> [!Note]
> <span data-ttu-id="60871-283">當所有其他工作負載在 GCC 雲端中都是完整的，當所有其他的整合作業完成後，就能在小組中使用它們。</span><span class="sxs-lookup"><span data-stu-id="60871-283">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60871-285">決策點</span><span class="sxs-lookup"><span data-stu-id="60871-285">Decision point</span></span>|<ul><li><span data-ttu-id="60871-286">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="60871-286">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="60871-287">步驟5。</span><span class="sxs-lookup"><span data-stu-id="60871-287">Step 5.</span></span> <span data-ttu-id="60871-288">規劃管理</span><span class="sxs-lookup"><span data-stu-id="60871-288">Plan for governance</span></span>

<span data-ttu-id="60871-289">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="60871-289">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="60871-290">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="60871-290">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60871-292">決策點</span><span class="sxs-lookup"><span data-stu-id="60871-292">Decision point</span></span>|<ul><li><span data-ttu-id="60871-293">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="60871-293">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="60871-294">步驟6。</span><span class="sxs-lookup"><span data-stu-id="60871-294">Step 6.</span></span> <span data-ttu-id="60871-295">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="60871-295">Deploy Teams for collaboration</span></span>

<span data-ttu-id="60871-296">在您 onboarded 至 Microsoft 365 政府– GCC 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="60871-296">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="60871-297">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="60871-297">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="60871-298">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="60871-298">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="60871-299">步驟7。</span><span class="sxs-lookup"><span data-stu-id="60871-299">Step 7.</span></span> <span data-ttu-id="60871-300">為會議和語音部署團隊</span><span class="sxs-lookup"><span data-stu-id="60871-300">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="60871-301">這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。</span><span class="sxs-lookup"><span data-stu-id="60871-301">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

