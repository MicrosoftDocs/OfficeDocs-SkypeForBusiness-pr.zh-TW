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
ms.openlocfilehash: 51afc464b5f6d0fa698250d1255315535e383bf8
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374320"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="b91af-103">規劃 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="b91af-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="b91af-104">本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署，或其他處理受限於政府法規與需求之資料的其他實體，這些專業人員使用 Microsoft365政府-GCC 適用于符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="b91af-105">如果您的組織已符合 Microsoft 365 政府版 GCC 資格要求，且適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="b91af-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="b91af-106">步驟1。</span><span class="sxs-lookup"><span data-stu-id="b91af-106">Step 1.</span></span> <span data-ttu-id="b91af-107">判斷貴組織是否需要 Microsoft 365 政府-GCC 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="b91af-108">Microsoft 365 政府版-GCC 環境提供對雲端服務（包括 FedRAMP 適中版，以及刑事審判與聯邦稅務資訊系統的需求（CJI 與 FTI 資料類型）的美國政府需求的規範。</span><span class="sxs-lookup"><span data-stu-id="b91af-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="b91af-109">除了享受 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府-GCC 所特有的下列功能帶來的好處：</span><span class="sxs-lookup"><span data-stu-id="b91af-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="b91af-110">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="b91af-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="b91af-111">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="b91af-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="b91af-112">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="b91af-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="b91af-113">Microsoft 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="b91af-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="b91af-114">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中，找到適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b91af-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="b91af-115">[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點，這些好處是圍繞在美國的會議規範需求中心。</span><span class="sxs-lookup"><span data-stu-id="b91af-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="b91af-116">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="b91af-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="b91af-117">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b91af-119">決策點</span><span class="sxs-lookup"><span data-stu-id="b91af-119">Decision points</span></span>|<ul><li><span data-ttu-id="b91af-120">決定 Microsoft 365 政府版-GCC 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="b91af-120">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="b91af-121">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="b91af-122">Microsoft 365 政府版-GCC 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="b91af-122">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="b91af-123">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="b91af-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="b91af-124">步驟2。</span><span class="sxs-lookup"><span data-stu-id="b91af-124">Step 2.</span></span> <span data-ttu-id="b91af-125">適用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="b91af-125">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="b91af-126">如果決定此服務適合您的組織，請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="b91af-126">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="b91af-127">步驟3。</span><span class="sxs-lookup"><span data-stu-id="b91af-127">Step 3.</span></span> <span data-ttu-id="b91af-128">瞭解 Microsoft 365 政府-GCC 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b91af-128">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="b91af-129">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b91af-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b91af-131">決策點</span><span class="sxs-lookup"><span data-stu-id="b91af-131">Decision point</span></span>|<ul><li><span data-ttu-id="b91af-132">決定是否要修改任何預設的 Microsoft 365 政府版-GCC 安全設定，並解決以首先瞭解您所做的任何變更對您造成的影響。</span><span class="sxs-lookup"><span data-stu-id="b91af-132">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="b91af-133">步驟4。</span><span class="sxs-lookup"><span data-stu-id="b91af-133">Step 4.</span></span> <span data-ttu-id="b91af-134">瞭解哪些功能目前無法使用或預設為停用。</span><span class="sxs-lookup"><span data-stu-id="b91af-134">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="b91af-135">為了滿足政府雲端客戶的需求，Microsoft 365 政府版與企業版方案之間有一些差異。</span><span class="sxs-lookup"><span data-stu-id="b91af-135">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="b91af-136">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="b91af-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="b91af-137">功能</span><span class="sxs-lookup"><span data-stu-id="b91af-137">Feature</span></span>                     | <span data-ttu-id="b91af-138">GCC</span><span class="sxs-lookup"><span data-stu-id="b91af-138">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="b91af-139">基本</span><span class="sxs-lookup"><span data-stu-id="b91af-139">Base</span></span> | <span data-ttu-id="b91af-140">Id</span><span class="sxs-lookup"><span data-stu-id="b91af-140">Login</span></span> | <span data-ttu-id="b91af-141">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-141">Available</span></span> |
| | <span data-ttu-id="b91af-142">目前狀態</span><span class="sxs-lookup"><span data-stu-id="b91af-142">Presence</span></span> | <span data-ttu-id="b91af-143">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-143">Available</span></span> |
| | <span data-ttu-id="b91af-144">整合的目前狀態（商務用 Skype 和小組已統一）</span><span class="sxs-lookup"><span data-stu-id="b91af-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="b91af-145">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-145">Available</span></span> |
| <span data-ttu-id="b91af-146">操作</span><span class="sxs-lookup"><span data-stu-id="b91af-146">Activity</span></span> | <span data-ttu-id="b91af-147">複製</span><span class="sxs-lookup"><span data-stu-id="b91af-147">Feed</span></span> | <span data-ttu-id="b91af-148">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-148">Available</span></span> |
|  | <span data-ttu-id="b91af-149">我的活動</span><span class="sxs-lookup"><span data-stu-id="b91af-149">My Activity</span></span> | <span data-ttu-id="b91af-150">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-150">Available</span></span> |
| <span data-ttu-id="b91af-151">聊天</span><span class="sxs-lookup"><span data-stu-id="b91af-151">Chat</span></span> | <span data-ttu-id="b91af-152">交談</span><span class="sxs-lookup"><span data-stu-id="b91af-152">Conversation</span></span> | <span data-ttu-id="b91af-153">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-153">Available</span></span> |
| | <span data-ttu-id="b91af-154">檔案</span><span class="sxs-lookup"><span data-stu-id="b91af-154">Files</span></span> | <span data-ttu-id="b91af-155">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-155">Available</span></span> |
| | <span data-ttu-id="b91af-156">組織結構</span><span class="sxs-lookup"><span data-stu-id="b91af-156">Org chart</span></span> | <span data-ttu-id="b91af-157">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-157">Available</span></span> |
| | <span data-ttu-id="b91af-158">操作</span><span class="sxs-lookup"><span data-stu-id="b91af-158">Activity</span></span> | <span data-ttu-id="b91af-159">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-159">Available</span></span> |
| | <span data-ttu-id="b91af-160">互通性（1:1 團隊-商務用 Skype 聊天）</span><span class="sxs-lookup"><span data-stu-id="b91af-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="b91af-161">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-161">Available</span></span> |
| <span data-ttu-id="b91af-162">Teams</span><span class="sxs-lookup"><span data-stu-id="b91af-162">Teams</span></span> | <span data-ttu-id="b91af-163">頻道訊息</span><span class="sxs-lookup"><span data-stu-id="b91af-163">Channel message</span></span> | <span data-ttu-id="b91af-164">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-164">Available</span></span> |
| | <span data-ttu-id="b91af-165">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="b91af-165">Channel files</span></span> | <span data-ttu-id="b91af-166">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-166">Available</span></span> |
| | <span data-ttu-id="b91af-167">[OneNote] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b91af-167">OneNote tab</span></span> | <span data-ttu-id="b91af-168">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="b91af-168">On the Government backlog</span></span> |
| | <span data-ttu-id="b91af-169">透過電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="b91af-169">Email a channel</span></span> | <span data-ttu-id="b91af-170">無法使用</span><span class="sxs-lookup"><span data-stu-id="b91af-170">Not available</span></span> |
| | <span data-ttu-id="b91af-171">新增成員</span><span class="sxs-lookup"><span data-stu-id="b91af-171">Add member</span></span> | <span data-ttu-id="b91af-172">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-172">Available</span></span> |
| | <span data-ttu-id="b91af-173">來賓存取</span><span class="sxs-lookup"><span data-stu-id="b91af-173">Guest access</span></span> | <span data-ttu-id="b91af-174">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-174">Available</span></span> |
| <span data-ttu-id="b91af-175">會議</span><span class="sxs-lookup"><span data-stu-id="b91af-175">Meetings</span></span> | <span data-ttu-id="b91af-176">排程會議</span><span class="sxs-lookup"><span data-stu-id="b91af-176">Schedule meeting</span></span> | <span data-ttu-id="b91af-177">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-177">Available</span></span> |
| | <span data-ttu-id="b91af-178">加入會議</span><span class="sxs-lookup"><span data-stu-id="b91af-178">Join meeting</span></span> | <span data-ttu-id="b91af-179">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-179">Available</span></span> |
| | <span data-ttu-id="b91af-180">VoIP 會議</span><span class="sxs-lookup"><span data-stu-id="b91af-180">VoIP meeting</span></span> | <span data-ttu-id="b91af-181">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-181">Available</span></span> |
| | <span data-ttu-id="b91af-182">桌面共用</span><span class="sxs-lookup"><span data-stu-id="b91af-182">Desktop sharing</span></span> | <span data-ttu-id="b91af-183">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-183">Available</span></span> |
| | <span data-ttu-id="b91af-184">在共用中提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="b91af-184">Give and take control in sharing</span></span> | <span data-ttu-id="b91af-185">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-185">Available</span></span> |
| | <span data-ttu-id="b91af-186">從會議室連接</span><span class="sxs-lookup"><span data-stu-id="b91af-186">Connect from a conference room</span></span> | <span data-ttu-id="b91af-187">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-187">Available</span></span> |
| | <span data-ttu-id="b91af-188">匿名加入</span><span class="sxs-lookup"><span data-stu-id="b91af-188">Anonymous join</span></span> | <span data-ttu-id="b91af-189">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-189">Available</span></span> |
| | <span data-ttu-id="b91af-190">雲端錄製</span><span class="sxs-lookup"><span data-stu-id="b91af-190">Cloud recording</span></span> | <span data-ttu-id="b91af-191">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-191">Available</span></span> |
| | <span data-ttu-id="b91af-192">會議記事</span><span class="sxs-lookup"><span data-stu-id="b91af-192">Meeting notes</span></span> | <span data-ttu-id="b91af-193">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-193">Available</span></span> |
| | <span data-ttu-id="b91af-194">即時事件</span><span class="sxs-lookup"><span data-stu-id="b91af-194">Live Events</span></span> | <span data-ttu-id="b91af-195">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-195">Available</span></span> |
| | <span data-ttu-id="b91af-196">同盟會議</span><span class="sxs-lookup"><span data-stu-id="b91af-196">Federated meetings</span></span> | <span data-ttu-id="b91af-197">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-197">Available</span></span> |
| | <span data-ttu-id="b91af-198">Surface Hub 支援</span><span class="sxs-lookup"><span data-stu-id="b91af-198">Surface Hub support</span></span> | <span data-ttu-id="b91af-199">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-199">Available</span></span> |
| <span data-ttu-id="b91af-200">撥</span><span class="sxs-lookup"><span data-stu-id="b91af-200">Calls</span></span> | <span data-ttu-id="b91af-201">連絡人</span><span class="sxs-lookup"><span data-stu-id="b91af-201">Contacts</span></span> | <span data-ttu-id="b91af-202">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-202">Available</span></span> |
| | <span data-ttu-id="b91af-203">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="b91af-203">History</span></span> | <span data-ttu-id="b91af-204">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-204">Available</span></span> |
| | <span data-ttu-id="b91af-205">語音信箱</span><span class="sxs-lookup"><span data-stu-id="b91af-205">Voicemail</span></span> | <span data-ttu-id="b91af-206">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-206">Available</span></span> |
| | <span data-ttu-id="b91af-207">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="b91af-207">VoIP call</span></span> | <span data-ttu-id="b91af-208">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-208">Available</span></span> |
| | <span data-ttu-id="b91af-209">商務用 Skype-小組通話</span><span class="sxs-lookup"><span data-stu-id="b91af-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="b91af-210">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-210">Available</span></span> |
| | <span data-ttu-id="b91af-211">通話方案</span><span class="sxs-lookup"><span data-stu-id="b91af-211">Calling Plans</span></span> | <span data-ttu-id="b91af-212">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-212">Available</span></span> |
| | <span data-ttu-id="b91af-213">音訊會議（透過允許會議參與者透過 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="b91af-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="b91af-214">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-214">Available</span></span> |
| | <span data-ttu-id="b91af-215">Microsoft Phone 系統直向路由</span><span class="sxs-lookup"><span data-stu-id="b91af-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="b91af-216">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-216">Available</span></span> |
| | <span data-ttu-id="b91af-217">PSTN 呼叫者的大廳</span><span class="sxs-lookup"><span data-stu-id="b91af-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="b91af-218">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-218">Available</span></span> |
| | <span data-ttu-id="b91af-219">通話佇列</span><span class="sxs-lookup"><span data-stu-id="b91af-219">Call queue</span></span> | <span data-ttu-id="b91af-220">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-220">Available</span></span> |
| | <span data-ttu-id="b91af-221">老闆及代理人支援</span><span class="sxs-lookup"><span data-stu-id="b91af-221">Boss and delegate support</span></span> | <span data-ttu-id="b91af-222">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-222">Available</span></span> |
| | <span data-ttu-id="b91af-223">顧問式與安全轉接</span><span class="sxs-lookup"><span data-stu-id="b91af-223">Consultative and safe transfer</span></span> | <span data-ttu-id="b91af-224">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-224">Available</span></span> |
| | <span data-ttu-id="b91af-225">請勿打擾突破</span><span class="sxs-lookup"><span data-stu-id="b91af-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="b91af-226">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-226">Available</span></span> |
| | <span data-ttu-id="b91af-227">區別性鈴聲</span><span class="sxs-lookup"><span data-stu-id="b91af-227">Distinctive ring</span></span> | <span data-ttu-id="b91af-228">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-228">Available</span></span> |
| | <span data-ttu-id="b91af-229">1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級</span><span class="sxs-lookup"><span data-stu-id="b91af-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="b91af-230">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-230">Available</span></span> |
| | <span data-ttu-id="b91af-231">[轉寄至] 群組</span><span class="sxs-lookup"><span data-stu-id="b91af-231">Forward to group</span></span> | <span data-ttu-id="b91af-232">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-232">Available</span></span> |
| | <span data-ttu-id="b91af-233">轉接至 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="b91af-233">Transfer to PSTN call</span></span> | <span data-ttu-id="b91af-234">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-234">Available</span></span> |
| | <span data-ttu-id="b91af-235">緊急電話撥打電話方案</span><span class="sxs-lookup"><span data-stu-id="b91af-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="b91af-236">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-236">Available</span></span> |
| | <span data-ttu-id="b91af-237">現有的認證 SIP 手機支援</span><span class="sxs-lookup"><span data-stu-id="b91af-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="b91af-238">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-238">Available</span></span> |
| | <span data-ttu-id="b91af-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="b91af-239">USB HID</span></span> | <span data-ttu-id="b91af-240">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-240">Available</span></span> |
| | <span data-ttu-id="b91af-241">通話和會議的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b91af-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="b91af-242">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-242">Available</span></span> |
| | <span data-ttu-id="b91af-243">組織自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b91af-243">Organization auto attendant</span></span> | <span data-ttu-id="b91af-244">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-244">Available</span></span> |
| | <span data-ttu-id="b91af-245">Skype 消費者-小組通話支援</span><span class="sxs-lookup"><span data-stu-id="b91af-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="b91af-246">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-246">Available</span></span> |
| <span data-ttu-id="b91af-247">檔案</span><span class="sxs-lookup"><span data-stu-id="b91af-247">Files</span></span> | <span data-ttu-id="b91af-248">近</span><span class="sxs-lookup"><span data-stu-id="b91af-248">Recent</span></span> | <span data-ttu-id="b91af-249">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-249">Available</span></span> |
| | <span data-ttu-id="b91af-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b91af-250">Microsoft Teams</span></span> | <span data-ttu-id="b91af-251">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-251">Available</span></span> |
| <span data-ttu-id="b91af-252">存放</span><span class="sxs-lookup"><span data-stu-id="b91af-252">Store</span></span> | <span data-ttu-id="b91af-253">App Store</span><span class="sxs-lookup"><span data-stu-id="b91af-253">App Store</span></span> | <span data-ttu-id="b91af-254">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-254">Available</span></span> |
| <span data-ttu-id="b91af-255">檢索</span><span class="sxs-lookup"><span data-stu-id="b91af-255">Search</span></span> | <span data-ttu-id="b91af-256">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="b91af-256">Messages</span></span> | <span data-ttu-id="b91af-257">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-257">Available</span></span> |
| | <span data-ttu-id="b91af-258">人員</span><span class="sxs-lookup"><span data-stu-id="b91af-258">People</span></span> | <span data-ttu-id="b91af-259">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-259">Available</span></span> |
| | <span data-ttu-id="b91af-260">檔案</span><span class="sxs-lookup"><span data-stu-id="b91af-260">Files</span></span> | <span data-ttu-id="b91af-261">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-261">Available</span></span> |
| | <span data-ttu-id="b91af-262">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="b91af-262">Slash commands</span></span> | <span data-ttu-id="b91af-263">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-263">Available</span></span> |
| <span data-ttu-id="b91af-264">從屬</span><span class="sxs-lookup"><span data-stu-id="b91af-264">Compliance</span></span> | <span data-ttu-id="b91af-265">合規性內容搜尋</span><span class="sxs-lookup"><span data-stu-id="b91af-265">Compliance content search</span></span> | <span data-ttu-id="b91af-266">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-266">Available</span></span> |
| | <span data-ttu-id="b91af-267">留成</span><span class="sxs-lookup"><span data-stu-id="b91af-267">Retention</span></span> | <span data-ttu-id="b91af-268">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-268">Available</span></span> |
| | <span data-ttu-id="b91af-269">審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="b91af-269">Audit log search</span></span> | <span data-ttu-id="b91af-270">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-270">Available</span></span> |
| | <span data-ttu-id="b91af-271">法律封存</span><span class="sxs-lookup"><span data-stu-id="b91af-271">Legal hold</span></span> | <span data-ttu-id="b91af-272">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-272">Available</span></span> |
| | <span data-ttu-id="b91af-273">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b91af-273">eDiscovery</span></span> | <span data-ttu-id="b91af-274">離線</span><span class="sxs-lookup"><span data-stu-id="b91af-274">Available</span></span> |

> [!Note]
> <span data-ttu-id="b91af-275">當所有其他工作負載在 GCC 雲端中都是完整的，當所有其他的整合作業完成後，就能在小組中使用它們。</span><span class="sxs-lookup"><span data-stu-id="b91af-275">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b91af-277">決策點</span><span class="sxs-lookup"><span data-stu-id="b91af-277">Decision point</span></span>|<ul><li><span data-ttu-id="b91af-278">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-278">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="b91af-279">步驟5。</span><span class="sxs-lookup"><span data-stu-id="b91af-279">Step 5.</span></span> <span data-ttu-id="b91af-280">規劃管理</span><span class="sxs-lookup"><span data-stu-id="b91af-280">Plan for governance</span></span>

<span data-ttu-id="b91af-281">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-281">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="b91af-282">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="b91af-282">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b91af-284">決策點</span><span class="sxs-lookup"><span data-stu-id="b91af-284">Decision point</span></span>|<ul><li><span data-ttu-id="b91af-285">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="b91af-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="b91af-286">步驟6。</span><span class="sxs-lookup"><span data-stu-id="b91af-286">Step 6.</span></span> <span data-ttu-id="b91af-287">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="b91af-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="b91af-288">在您 onboarded 至 Microsoft 365 政府– GCC 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="b91af-288">After you’ve been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="b91af-289">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="b91af-289">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="b91af-290">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="b91af-290">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="b91af-291">步驟7。</span><span class="sxs-lookup"><span data-stu-id="b91af-291">Step 7.</span></span> <span data-ttu-id="b91af-292">為會議和語音部署團隊</span><span class="sxs-lookup"><span data-stu-id="b91af-292">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="b91af-293">這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。</span><span class="sxs-lookup"><span data-stu-id="b91af-293">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

