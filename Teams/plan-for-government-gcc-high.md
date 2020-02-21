---
title: 規劃 Microsoft 365 政府版-GCC 高部署版-Microsoft 團隊
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 適用于 IT 專業人員的指導方針，可在處理受美國政府法規制約之資料的實體中，驅動 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3c44867b14a4b3bf83a45cf1dbbb37151c648a8
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161588"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="930ee-103">規劃 Microsoft 365 政府-GCC 高部署</span><span class="sxs-lookup"><span data-stu-id="930ee-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="930ee-104">本指導方針適用于在美國聯邦政府機構中部署 Office 365 的 IT 專業人員，或其他處理受限於政府法規與需求之資料的實體，且適合使用 Microsoft 365 政府版-GCC 高以符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="930ee-105">如果您的組織已符合 Microsoft 365 政府版-GCC 優質資格要求，且已適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="930ee-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="930ee-106">步驟1。</span><span class="sxs-lookup"><span data-stu-id="930ee-106">Step 1.</span></span> <span data-ttu-id="930ee-107">判斷貴組織是否需要 Microsoft 365 政府-GCC 高並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="930ee-108">Microsoft 365 政府版-GCC 高環境提供與美國雲端服務政府需求相符的規範。</span><span class="sxs-lookup"><span data-stu-id="930ee-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="930ee-109">除了享有 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府專用的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="930ee-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="930ee-110">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="930ee-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="930ee-111">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="930ee-111">Your organization’s customer content is stored within the United States.</span></span>
- <span data-ttu-id="930ee-112">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="930ee-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="930ee-113">Microsoft 365 政府版-GCC 高 = accreditations 我們公用事業部門客戶所需的認證與。</span><span class="sxs-lookup"><span data-stu-id="930ee-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="930ee-114">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有關適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="930ee-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="930ee-115">[ [Office 365 美國政府服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)] 描述的是平臺的優點，這些好處是在美國內滿足合規性需求的中心。</span><span class="sxs-lookup"><span data-stu-id="930ee-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform’s benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="930ee-116">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="930ee-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="930ee-117">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="930ee-119">決策點</span><span class="sxs-lookup"><span data-stu-id="930ee-119">Decision points</span></span>|<ul><li><span data-ttu-id="930ee-120">決定 Microsoft 365 政府版-GCC 高是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="930ee-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="930ee-121">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="930ee-122">Microsoft 365 政府-GCC 高版僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="930ee-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="930ee-123">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="930ee-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="930ee-124">步驟2。</span><span class="sxs-lookup"><span data-stu-id="930ee-124">Step 2.</span></span> <span data-ttu-id="930ee-125">適用于 Microsoft 365 政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="930ee-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="930ee-126">如果您認為此服務適合您的組織，請開始[申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="930ee-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="930ee-127">步驟3。</span><span class="sxs-lookup"><span data-stu-id="930ee-127">Step 3.</span></span> <span data-ttu-id="930ee-128">瞭解 Microsoft 365 政府-GCC 高預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="930ee-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="930ee-129">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="930ee-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="930ee-131">決策點</span><span class="sxs-lookup"><span data-stu-id="930ee-131">Decision point</span></span>|<ul><li><span data-ttu-id="930ee-132">判斷您是否需要修改任何預設的 Microsoft 365 政府版-GCC 高安全性設定，並解決以先瞭解您所做的任何變更對您所做的影響。</span><span class="sxs-lookup"><span data-stu-id="930ee-132">Decide whether you’ll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="930ee-133">步驟4。</span><span class="sxs-lookup"><span data-stu-id="930ee-133">Step 4.</span></span> <span data-ttu-id="930ee-134">瞭解 Microsoft 365 政府-GCC 高版中目前提供哪些團隊功能</span><span class="sxs-lookup"><span data-stu-id="930ee-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="930ee-135">為了符合政府雲端客戶的需求，Microsoft 365 政府版中的小組與企業方案中的團隊之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="930ee-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="930ee-136">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="930ee-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="930ee-137">功能</span><span class="sxs-lookup"><span data-stu-id="930ee-137">Feature</span></span>                     | <span data-ttu-id="930ee-138">GCC 高</span><span class="sxs-lookup"><span data-stu-id="930ee-138">GCC High</span></span>       |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="930ee-139">基本</span><span class="sxs-lookup"><span data-stu-id="930ee-139">Base</span></span> | <span data-ttu-id="930ee-140">Id</span><span class="sxs-lookup"><span data-stu-id="930ee-140">Login</span></span> | <span data-ttu-id="930ee-141">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-141">Available</span></span> |
| | <span data-ttu-id="930ee-142">目前狀態</span><span class="sxs-lookup"><span data-stu-id="930ee-142">Presence</span></span> | <span data-ttu-id="930ee-143">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-143">Available</span></span> |
| | <span data-ttu-id="930ee-144">整合的目前狀態（商務用 Skype 和小組已統一）</span><span class="sxs-lookup"><span data-stu-id="930ee-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="930ee-145">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-145">Available</span></span> |
| | <span data-ttu-id="930ee-146">Linux 用戶端</span><span class="sxs-lookup"><span data-stu-id="930ee-146">Linux client</span></span> | <span data-ttu-id="930ee-147">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-147">On the Government backlog</span></span> |
| <span data-ttu-id="930ee-148">操作</span><span class="sxs-lookup"><span data-stu-id="930ee-148">Activity</span></span> | <span data-ttu-id="930ee-149">複製</span><span class="sxs-lookup"><span data-stu-id="930ee-149">Feed</span></span> | <span data-ttu-id="930ee-150">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-150">Available</span></span> |
|  | <span data-ttu-id="930ee-151">我的活動</span><span class="sxs-lookup"><span data-stu-id="930ee-151">My Activity</span></span> | <span data-ttu-id="930ee-152">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-152">Available</span></span> |
| <span data-ttu-id="930ee-153">聊天</span><span class="sxs-lookup"><span data-stu-id="930ee-153">Chat</span></span> | <span data-ttu-id="930ee-154">交談</span><span class="sxs-lookup"><span data-stu-id="930ee-154">Conversation</span></span> | <span data-ttu-id="930ee-155">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-155">Available</span></span> |
| | <span data-ttu-id="930ee-156">檔案</span><span class="sxs-lookup"><span data-stu-id="930ee-156">Files</span></span> | <span data-ttu-id="930ee-157">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-157">Available</span></span> |
| | <span data-ttu-id="930ee-158">組織結構</span><span class="sxs-lookup"><span data-stu-id="930ee-158">Org chart</span></span> | <span data-ttu-id="930ee-159">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-159">Available</span></span> |
| | <span data-ttu-id="930ee-160">操作</span><span class="sxs-lookup"><span data-stu-id="930ee-160">Activity</span></span> | <span data-ttu-id="930ee-161">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-161">Available</span></span> |
| | <span data-ttu-id="930ee-162">互通性（1:1 團隊-商務用 Skype 聊天）</span><span class="sxs-lookup"><span data-stu-id="930ee-162">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="930ee-163">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-163">Available</span></span> |
| <span data-ttu-id="930ee-164">Teams</span><span class="sxs-lookup"><span data-stu-id="930ee-164">Teams</span></span> | <span data-ttu-id="930ee-165">頻道訊息</span><span class="sxs-lookup"><span data-stu-id="930ee-165">Channel message</span></span> | <span data-ttu-id="930ee-166">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-166">Available</span></span> |
| | <span data-ttu-id="930ee-167">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="930ee-167">Channel files</span></span> | <span data-ttu-id="930ee-168">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-168">Available</span></span> |
| | <span data-ttu-id="930ee-169">[OneNote] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="930ee-169">OneNote tab</span></span> | <span data-ttu-id="930ee-170">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-170">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-171">透過電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="930ee-171">Email a channel</span></span> | <span data-ttu-id="930ee-172">無法使用</span><span class="sxs-lookup"><span data-stu-id="930ee-172">Not available</span></span> |
| | <span data-ttu-id="930ee-173">新增成員</span><span class="sxs-lookup"><span data-stu-id="930ee-173">Add member</span></span> | <span data-ttu-id="930ee-174">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-174">Available</span></span> |
| | <span data-ttu-id="930ee-175">來賓存取</span><span class="sxs-lookup"><span data-stu-id="930ee-175">Guest access</span></span> | <span data-ttu-id="930ee-176">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-176">On the Government backlog</span></span> |
| <span data-ttu-id="930ee-177">會議</span><span class="sxs-lookup"><span data-stu-id="930ee-177">Meetings</span></span> | <span data-ttu-id="930ee-178">排程會議</span><span class="sxs-lookup"><span data-stu-id="930ee-178">Schedule meeting</span></span> | <span data-ttu-id="930ee-179">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-179">Available</span></span> |
| | <span data-ttu-id="930ee-180">加入會議</span><span class="sxs-lookup"><span data-stu-id="930ee-180">Join meeting</span></span> | <span data-ttu-id="930ee-181">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-181">Available</span></span> |
| | <span data-ttu-id="930ee-182">VoIP 會議</span><span class="sxs-lookup"><span data-stu-id="930ee-182">VoIP meeting</span></span> | <span data-ttu-id="930ee-183">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-183">Available</span></span> |
| | <span data-ttu-id="930ee-184">桌面共用</span><span class="sxs-lookup"><span data-stu-id="930ee-184">Desktop sharing</span></span> | <span data-ttu-id="930ee-185">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-185">Available</span></span> |
| | <span data-ttu-id="930ee-186">在共用中提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="930ee-186">Give and take control in sharing</span></span> | <span data-ttu-id="930ee-187">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-187">Available</span></span> |
| | <span data-ttu-id="930ee-188">從會議室連接</span><span class="sxs-lookup"><span data-stu-id="930ee-188">Connect from a conference room</span></span> | <span data-ttu-id="930ee-189">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-189">Available</span></span> |
| | <span data-ttu-id="930ee-190">匿名加入</span><span class="sxs-lookup"><span data-stu-id="930ee-190">Anonymous join</span></span> | <span data-ttu-id="930ee-191">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-191">Available</span></span> |
| | <span data-ttu-id="930ee-192">雲端錄製</span><span class="sxs-lookup"><span data-stu-id="930ee-192">Cloud recording</span></span> | <span data-ttu-id="930ee-193">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-193">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-194">會議記事</span><span class="sxs-lookup"><span data-stu-id="930ee-194">Meeting notes</span></span> | <span data-ttu-id="930ee-195">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-195">Available</span></span> |
| | <span data-ttu-id="930ee-196">廣播會議</span><span class="sxs-lookup"><span data-stu-id="930ee-196">Broadcast meetings</span></span> | <span data-ttu-id="930ee-197">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-197">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-198">雲端（GCCH 至 GCCH）同盟會議</span><span class="sxs-lookup"><span data-stu-id="930ee-198">Intra-cloud (GCCH to GCCH) Federated meetings</span></span> | <span data-ttu-id="930ee-199">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-199">Available</span></span> |
| | <span data-ttu-id="930ee-200">Surface Hub 支援</span><span class="sxs-lookup"><span data-stu-id="930ee-200">Surface Hub support</span></span> | <span data-ttu-id="930ee-201">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-201">On the Government backlog</span></span> |
| <span data-ttu-id="930ee-202">撥</span><span class="sxs-lookup"><span data-stu-id="930ee-202">Calls</span></span> | <span data-ttu-id="930ee-203">連絡人</span><span class="sxs-lookup"><span data-stu-id="930ee-203">Contacts</span></span> | <span data-ttu-id="930ee-204">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-204">Available</span></span> |
| | <span data-ttu-id="930ee-205">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="930ee-205">History</span></span> | <span data-ttu-id="930ee-206">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-206">Available</span></span> |
| | <span data-ttu-id="930ee-207">語音信箱</span><span class="sxs-lookup"><span data-stu-id="930ee-207">Voicemail</span></span> | <span data-ttu-id="930ee-208">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-208">Available</span></span> |
| | <span data-ttu-id="930ee-209">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="930ee-209">VoIP call</span></span> | <span data-ttu-id="930ee-210">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-210">Available</span></span> |
| | <span data-ttu-id="930ee-211">商務用 Skype-小組通話</span><span class="sxs-lookup"><span data-stu-id="930ee-211">Skype for Business - Teams calling</span></span> | <span data-ttu-id="930ee-212">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-212">Available</span></span> |
| | <span data-ttu-id="930ee-213">通話方案</span><span class="sxs-lookup"><span data-stu-id="930ee-213">Calling Plans</span></span> | <span data-ttu-id="930ee-214">無法使用</span><span class="sxs-lookup"><span data-stu-id="930ee-214">Not Available</span></span> |
| | <span data-ttu-id="930ee-215">音訊會議（透過允許會議參與者透過 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="930ee-215">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="930ee-216">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-216">Available</span></span> |
| | <span data-ttu-id="930ee-217">Microsoft Phone 系統直向路由</span><span class="sxs-lookup"><span data-stu-id="930ee-217">Microsoft Phone System Direct Routing</span></span> | <span data-ttu-id="930ee-218">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-218">Available</span></span> |
| | <span data-ttu-id="930ee-219">PSTN 呼叫者的大廳</span><span class="sxs-lookup"><span data-stu-id="930ee-219">Lobby for PSTN callers</span></span> | <span data-ttu-id="930ee-220">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-220">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-221">通話佇列</span><span class="sxs-lookup"><span data-stu-id="930ee-221">Call queue</span></span> | <span data-ttu-id="930ee-222">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-222">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-223">老闆及代理人支援</span><span class="sxs-lookup"><span data-stu-id="930ee-223">Boss and delegate support</span></span> | <span data-ttu-id="930ee-224">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-224">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-225">顧問式與安全轉接</span><span class="sxs-lookup"><span data-stu-id="930ee-225">Consultative and safe transfer</span></span> | <span data-ttu-id="930ee-226">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-226">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-227">請勿打擾突破</span><span class="sxs-lookup"><span data-stu-id="930ee-227">Do not disturb breakthrough</span></span> | <span data-ttu-id="930ee-228">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-228">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-229">區別性鈴聲</span><span class="sxs-lookup"><span data-stu-id="930ee-229">Distinctive ring</span></span> | <span data-ttu-id="930ee-230">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-230">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-231">1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級</span><span class="sxs-lookup"><span data-stu-id="930ee-231">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="930ee-232">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-232">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-233">[轉寄至] 群組</span><span class="sxs-lookup"><span data-stu-id="930ee-233">Forward to group</span></span> | <span data-ttu-id="930ee-234">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-234">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-235">轉接至 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="930ee-235">Transfer to PSTN call</span></span> | <span data-ttu-id="930ee-236">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-236">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-237">緊急電話撥打電話方案</span><span class="sxs-lookup"><span data-stu-id="930ee-237">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="930ee-238">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-238">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-239">現有的認證 SIP 手機支援</span><span class="sxs-lookup"><span data-stu-id="930ee-239">Support for existing certified SIP phones</span></span> | <span data-ttu-id="930ee-240">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-240">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-241">USB HID</span><span class="sxs-lookup"><span data-stu-id="930ee-241">USB HID</span></span> | <span data-ttu-id="930ee-242">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-242">Available</span></span> |
| | <span data-ttu-id="930ee-243">通話和會議的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="930ee-243">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="930ee-244">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-244">Available</span></span> |
| | <span data-ttu-id="930ee-245">組織自動語音應答</span><span class="sxs-lookup"><span data-stu-id="930ee-245">Organization auto attendant</span></span> | <span data-ttu-id="930ee-246">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="930ee-246">On the Government backlog</span></span> |
| | <span data-ttu-id="930ee-247">Skype 消費者-小組通話支援</span><span class="sxs-lookup"><span data-stu-id="930ee-247">Skype consumer - Teams call support</span></span> | <span data-ttu-id="930ee-248">無法使用</span><span class="sxs-lookup"><span data-stu-id="930ee-248">Not available</span></span> |
| <span data-ttu-id="930ee-249">檔案</span><span class="sxs-lookup"><span data-stu-id="930ee-249">Files</span></span> | <span data-ttu-id="930ee-250">近</span><span class="sxs-lookup"><span data-stu-id="930ee-250">Recent</span></span> | <span data-ttu-id="930ee-251">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-251">Available</span></span> |
| | <span data-ttu-id="930ee-252">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="930ee-252">Microsoft Teams</span></span> | <span data-ttu-id="930ee-253">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-253">Available</span></span> |
| <span data-ttu-id="930ee-254">存放</span><span class="sxs-lookup"><span data-stu-id="930ee-254">Store</span></span> | <span data-ttu-id="930ee-255">App Store</span><span class="sxs-lookup"><span data-stu-id="930ee-255">App Store</span></span> | <span data-ttu-id="930ee-256">無法使用</span><span class="sxs-lookup"><span data-stu-id="930ee-256">Not available</span></span> |
| <span data-ttu-id="930ee-257">檢索</span><span class="sxs-lookup"><span data-stu-id="930ee-257">Search</span></span> | <span data-ttu-id="930ee-258">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="930ee-258">Messages</span></span> | <span data-ttu-id="930ee-259">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-259">Available</span></span> |
| | <span data-ttu-id="930ee-260">人員</span><span class="sxs-lookup"><span data-stu-id="930ee-260">People</span></span> | <span data-ttu-id="930ee-261">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-261">Available</span></span> |
| | <span data-ttu-id="930ee-262">檔案</span><span class="sxs-lookup"><span data-stu-id="930ee-262">Files</span></span> | <span data-ttu-id="930ee-263">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-263">Available</span></span> |
| | <span data-ttu-id="930ee-264">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="930ee-264">Slash commands</span></span> | <span data-ttu-id="930ee-265">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-265">Available</span></span> |
| <span data-ttu-id="930ee-266">從屬</span><span class="sxs-lookup"><span data-stu-id="930ee-266">Compliance</span></span> | <span data-ttu-id="930ee-267">合規性內容搜尋</span><span class="sxs-lookup"><span data-stu-id="930ee-267">Compliance content search</span></span> | <span data-ttu-id="930ee-268">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-268">Available</span></span> |
| | <span data-ttu-id="930ee-269">留成</span><span class="sxs-lookup"><span data-stu-id="930ee-269">Retention</span></span> | <span data-ttu-id="930ee-270">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-270">Available</span></span> |
| | <span data-ttu-id="930ee-271">審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="930ee-271">Audit log search</span></span> | <span data-ttu-id="930ee-272">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-272">Available</span></span> |
| | <span data-ttu-id="930ee-273">法律封存</span><span class="sxs-lookup"><span data-stu-id="930ee-273">Legal hold</span></span> | <span data-ttu-id="930ee-274">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-274">Available</span></span> |
| | <span data-ttu-id="930ee-275">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="930ee-275">eDiscovery</span></span> | <span data-ttu-id="930ee-276">離線</span><span class="sxs-lookup"><span data-stu-id="930ee-276">Available</span></span> |

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="930ee-278">決策點</span><span class="sxs-lookup"><span data-stu-id="930ee-278">Decision point</span></span>|<ul><li><span data-ttu-id="930ee-279">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-279">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="930ee-280">步驟5。</span><span class="sxs-lookup"><span data-stu-id="930ee-280">Step 5.</span></span> <span data-ttu-id="930ee-281">規劃管理</span><span class="sxs-lookup"><span data-stu-id="930ee-281">Plan for governance</span></span>

<span data-ttu-id="930ee-282">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-282">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="930ee-283">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="930ee-283">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="930ee-284">決策點</span><span class="sxs-lookup"><span data-stu-id="930ee-284">Decision point</span></span> |<ul><li><span data-ttu-id="930ee-285">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="930ee-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="930ee-286">步驟6。</span><span class="sxs-lookup"><span data-stu-id="930ee-286">Step 6.</span></span> <span data-ttu-id="930ee-287">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="930ee-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="930ee-288">在您 onboarded 至 Microsoft 365 政府-GCC 高版之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="930ee-288">After you’ve been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="930ee-289">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="930ee-289">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="930ee-290">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="930ee-290">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

