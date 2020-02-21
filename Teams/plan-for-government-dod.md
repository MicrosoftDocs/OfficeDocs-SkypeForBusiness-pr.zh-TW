---
title: 規劃 Microsoft 365 政府 DoD 部署-Microsoft 團隊
author: lolajacobsen
ms.author: lolaj
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12d9350437867b04a181e62e8b23bb6ed78d8fbc
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161734"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="8afe1-103">規劃 Microsoft 365 政府 DoD 部署</span><span class="sxs-lookup"><span data-stu-id="8afe1-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="8afe1-104">本指導方針適用于在美國聯邦政府機構中部署 Office 365 的 IT 專業人員，或其他處理受限於政府法規與需求之資料的實體，而在這些實體中使用 Microsoft 365 政府版-DoD 適用于符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="8afe1-105">如果您的組織已符合 Microsoft 365 政府-DoD 資格要求，且已在計畫中套用並接受，您可以跳過步驟1和2，然後直接移至步驟3。</span><span class="sxs-lookup"><span data-stu-id="8afe1-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="8afe1-106">步驟1。</span><span class="sxs-lookup"><span data-stu-id="8afe1-106">Step 1.</span></span> <span data-ttu-id="8afe1-107">判斷貴組織是否需要 Microsoft 365 政府-DoD 並符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="8afe1-108">Microsoft 365 政府 DoD 環境提供與美國雲端服務政府需求相符的規範。</span><span class="sxs-lookup"><span data-stu-id="8afe1-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="8afe1-109">除了享受 Office 365 的功能和功能之外，組織還能利用 Microsoft 365 政府（DoD）獨有的下列功能。</span><span class="sxs-lookup"><span data-stu-id="8afe1-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="8afe1-110">貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。</span><span class="sxs-lookup"><span data-stu-id="8afe1-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="8afe1-111">貴組織的客戶內容會儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="8afe1-111">Your organization’s customer content is stored within the United States.</span></span>
- <span data-ttu-id="8afe1-112">您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。</span><span class="sxs-lookup"><span data-stu-id="8afe1-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="8afe1-113">Microsoft 365 政府-DoD 符合美國公有事業部門客戶所需的認證與 accreditations。</span><span class="sxs-lookup"><span data-stu-id="8afe1-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="8afe1-114">您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有關適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8afe1-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="8afe1-115">[ [Office 365 美國政府服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)] 描述的是平臺的優點，這些好處是在美國內滿足合規性需求的中心。</span><span class="sxs-lookup"><span data-stu-id="8afe1-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform’s benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="8afe1-116">您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。</span><span class="sxs-lookup"><span data-stu-id="8afe1-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="8afe1-117">然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8afe1-119">決策點</span><span class="sxs-lookup"><span data-stu-id="8afe1-119">Decision points</span></span>|<ul><li><span data-ttu-id="8afe1-120">決定 Microsoft 365 政府 DoD 是否適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="8afe1-120">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="8afe1-121">確認您的組織符合資格需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="8afe1-122">Microsoft 365 政府-DoD 僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="8afe1-122">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="8afe1-123">非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。</span><span class="sxs-lookup"><span data-stu-id="8afe1-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="8afe1-124">步驟2。</span><span class="sxs-lookup"><span data-stu-id="8afe1-124">Step 2.</span></span> <span data-ttu-id="8afe1-125">適用于 Microsoft 365 政府-DoD</span><span class="sxs-lookup"><span data-stu-id="8afe1-125">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="8afe1-126">如果您認為此服務適合您的組織，請開始[申請此服務](https://products.office.com/government/eligibility-validation)的程式。</span><span class="sxs-lookup"><span data-stu-id="8afe1-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="8afe1-127">步驟3。</span><span class="sxs-lookup"><span data-stu-id="8afe1-127">Step 3.</span></span> <span data-ttu-id="8afe1-128">瞭解 Microsoft 365 政府 DoD 預設安全性設定。</span><span class="sxs-lookup"><span data-stu-id="8afe1-128">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="8afe1-129">我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="8afe1-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8afe1-131">決策點</span><span class="sxs-lookup"><span data-stu-id="8afe1-131">Decision point</span></span>|<ul><li><span data-ttu-id="8afe1-132">判斷您是否需要修改任何預設的 Microsoft 365 政府 DoD 安全性設定，以解決您的任何變更對您可能造成的影響。</span><span class="sxs-lookup"><span data-stu-id="8afe1-132">Decide whether you’ll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="8afe1-133">步驟4。</span><span class="sxs-lookup"><span data-stu-id="8afe1-133">Step 4.</span></span> <span data-ttu-id="8afe1-134">瞭解 Microsoft 365 政府-DoD 目前提供哪些團隊功能</span><span class="sxs-lookup"><span data-stu-id="8afe1-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="8afe1-135">為了符合政府雲端客戶的需求，Microsoft 365 政府-DoD 和團隊在企業方案中有一些差異。</span><span class="sxs-lookup"><span data-stu-id="8afe1-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="8afe1-136">請參閱下表，查看有哪些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="8afe1-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="8afe1-137">功能</span><span class="sxs-lookup"><span data-stu-id="8afe1-137">Feature</span></span>                     | <span data-ttu-id="8afe1-138">DoD</span><span class="sxs-lookup"><span data-stu-id="8afe1-138">DoD</span></span>       |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="8afe1-139">基本</span><span class="sxs-lookup"><span data-stu-id="8afe1-139">Base</span></span> | <span data-ttu-id="8afe1-140">Id</span><span class="sxs-lookup"><span data-stu-id="8afe1-140">Login</span></span> | <span data-ttu-id="8afe1-141">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-141">Available</span></span> |
| | <span data-ttu-id="8afe1-142">目前狀態</span><span class="sxs-lookup"><span data-stu-id="8afe1-142">Presence</span></span> | <span data-ttu-id="8afe1-143">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-143">Available</span></span> |
| | <span data-ttu-id="8afe1-144">整合的目前狀態（商務用 Skype 和小組已統一）</span><span class="sxs-lookup"><span data-stu-id="8afe1-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="8afe1-145">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-145">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-146">Linux 用戶端</span><span class="sxs-lookup"><span data-stu-id="8afe1-146">Linux client</span></span> | <span data-ttu-id="8afe1-147">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-147">On the Government backlog</span></span> |
| <span data-ttu-id="8afe1-148">操作</span><span class="sxs-lookup"><span data-stu-id="8afe1-148">Activity</span></span> | <span data-ttu-id="8afe1-149">複製</span><span class="sxs-lookup"><span data-stu-id="8afe1-149">Feed</span></span> | <span data-ttu-id="8afe1-150">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-150">Available</span></span> |
|  | <span data-ttu-id="8afe1-151">我的活動</span><span class="sxs-lookup"><span data-stu-id="8afe1-151">My Activity</span></span> | <span data-ttu-id="8afe1-152">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-152">Available</span></span> |
| <span data-ttu-id="8afe1-153">聊天</span><span class="sxs-lookup"><span data-stu-id="8afe1-153">Chat</span></span> | <span data-ttu-id="8afe1-154">交談</span><span class="sxs-lookup"><span data-stu-id="8afe1-154">Conversation</span></span> | <span data-ttu-id="8afe1-155">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-155">Available</span></span> |
| | <span data-ttu-id="8afe1-156">檔案</span><span class="sxs-lookup"><span data-stu-id="8afe1-156">Files</span></span> | <span data-ttu-id="8afe1-157">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-157">Available</span></span> |
| | <span data-ttu-id="8afe1-158">組織結構</span><span class="sxs-lookup"><span data-stu-id="8afe1-158">Org chart</span></span> | <span data-ttu-id="8afe1-159">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-159">Available</span></span> |
| | <span data-ttu-id="8afe1-160">操作</span><span class="sxs-lookup"><span data-stu-id="8afe1-160">Activity</span></span> | <span data-ttu-id="8afe1-161">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-161">Available</span></span> |
| | <span data-ttu-id="8afe1-162">互通性（1:1 團隊-商務用 Skype 聊天）</span><span class="sxs-lookup"><span data-stu-id="8afe1-162">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="8afe1-163">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-163">On the Government backlog</span></span> |
| <span data-ttu-id="8afe1-164">Teams</span><span class="sxs-lookup"><span data-stu-id="8afe1-164">Teams</span></span> | <span data-ttu-id="8afe1-165">頻道訊息</span><span class="sxs-lookup"><span data-stu-id="8afe1-165">Channel message</span></span> | <span data-ttu-id="8afe1-166">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-166">Available</span></span> |
| | <span data-ttu-id="8afe1-167">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="8afe1-167">Channel files</span></span> | <span data-ttu-id="8afe1-168">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-168">Available</span></span> |
| | <span data-ttu-id="8afe1-169">[OneNote] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="8afe1-169">OneNote tab</span></span> | <span data-ttu-id="8afe1-170">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-170">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-171">透過電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="8afe1-171">Email a channel</span></span> | <span data-ttu-id="8afe1-172">無法使用</span><span class="sxs-lookup"><span data-stu-id="8afe1-172">Not available</span></span> |
| | <span data-ttu-id="8afe1-173">新增成員</span><span class="sxs-lookup"><span data-stu-id="8afe1-173">Add member</span></span> | <span data-ttu-id="8afe1-174">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-174">Available</span></span> |
| | <span data-ttu-id="8afe1-175">來賓存取</span><span class="sxs-lookup"><span data-stu-id="8afe1-175">Guest access</span></span> | <span data-ttu-id="8afe1-176">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-176">On the Government backlog</span></span> |
| <span data-ttu-id="8afe1-177">會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-177">Meetings</span></span> | <span data-ttu-id="8afe1-178">排程會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-178">Schedule meeting</span></span> | <span data-ttu-id="8afe1-179">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-179">Available</span></span> |
| | <span data-ttu-id="8afe1-180">加入會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-180">Join meeting</span></span> | <span data-ttu-id="8afe1-181">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-181">Available</span></span> |
| | <span data-ttu-id="8afe1-182">VoIP 會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-182">VoIP meeting</span></span> | <span data-ttu-id="8afe1-183">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-183">Available</span></span> |
| | <span data-ttu-id="8afe1-184">桌面共用</span><span class="sxs-lookup"><span data-stu-id="8afe1-184">Desktop sharing</span></span> | <span data-ttu-id="8afe1-185">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-185">Available</span></span> |
| | <span data-ttu-id="8afe1-186">在共用中提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="8afe1-186">Give and take control in sharing</span></span> | <span data-ttu-id="8afe1-187">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-187">Available</span></span> |
| | <span data-ttu-id="8afe1-188">從會議室連接</span><span class="sxs-lookup"><span data-stu-id="8afe1-188">Connect from a conference room</span></span> | <span data-ttu-id="8afe1-189">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-189">Available</span></span> |
| | <span data-ttu-id="8afe1-190">雲端錄製</span><span class="sxs-lookup"><span data-stu-id="8afe1-190">Cloud recording</span></span> | <span data-ttu-id="8afe1-191">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-191">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-192">會議記事</span><span class="sxs-lookup"><span data-stu-id="8afe1-192">Meeting notes</span></span> | <span data-ttu-id="8afe1-193">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-193">Available</span></span> |
| | <span data-ttu-id="8afe1-194">廣播會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-194">Broadcast meetings</span></span> | <span data-ttu-id="8afe1-195">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-195">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-196">雲端（DoD 到 DoD）同盟會議</span><span class="sxs-lookup"><span data-stu-id="8afe1-196">Intra-cloud (DoD to DoD) Federated meetings</span></span> | <span data-ttu-id="8afe1-197">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-197">Available</span></span> |
| | <span data-ttu-id="8afe1-198">Surface Hub 支援</span><span class="sxs-lookup"><span data-stu-id="8afe1-198">Surface Hub support</span></span> | <span data-ttu-id="8afe1-199">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-199">On the Government backlog</span></span> |
| <span data-ttu-id="8afe1-200">撥</span><span class="sxs-lookup"><span data-stu-id="8afe1-200">Calls</span></span> | <span data-ttu-id="8afe1-201">連絡人</span><span class="sxs-lookup"><span data-stu-id="8afe1-201">Contacts</span></span> | <span data-ttu-id="8afe1-202">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-202">Available</span></span> |
| | <span data-ttu-id="8afe1-203">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="8afe1-203">History</span></span> | <span data-ttu-id="8afe1-204">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-204">Available</span></span> |
| | <span data-ttu-id="8afe1-205">語音信箱</span><span class="sxs-lookup"><span data-stu-id="8afe1-205">Voicemail</span></span> | <span data-ttu-id="8afe1-206">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-206">Available</span></span> |
| | <span data-ttu-id="8afe1-207">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="8afe1-207">VoIP call</span></span> | <span data-ttu-id="8afe1-208">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-208">Available</span></span> |
| | <span data-ttu-id="8afe1-209">商務用 Skype-小組通話</span><span class="sxs-lookup"><span data-stu-id="8afe1-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="8afe1-210">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-210">Available</span></span> |
| | <span data-ttu-id="8afe1-211">通話方案</span><span class="sxs-lookup"><span data-stu-id="8afe1-211">Calling Plans</span></span> | <span data-ttu-id="8afe1-212">無法使用</span><span class="sxs-lookup"><span data-stu-id="8afe1-212">Not Available</span></span> |
| | <span data-ttu-id="8afe1-213">音訊會議（透過允許會議參與者透過 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="8afe1-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="8afe1-214">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-214">Available</span></span> |
| | <span data-ttu-id="8afe1-215">Microsoft Phone 系統直向路由</span><span class="sxs-lookup"><span data-stu-id="8afe1-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="8afe1-216">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-216">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-217">PSTN 呼叫者的大廳</span><span class="sxs-lookup"><span data-stu-id="8afe1-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="8afe1-218">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-218">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-219">通話佇列</span><span class="sxs-lookup"><span data-stu-id="8afe1-219">Call queue</span></span> | <span data-ttu-id="8afe1-220">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-220">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-221">老闆及代理人支援</span><span class="sxs-lookup"><span data-stu-id="8afe1-221">Boss and delegate support</span></span> | <span data-ttu-id="8afe1-222">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-222">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-223">顧問式與安全轉接</span><span class="sxs-lookup"><span data-stu-id="8afe1-223">Consultative and safe transfer</span></span> | <span data-ttu-id="8afe1-224">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-224">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-225">請勿打擾突破</span><span class="sxs-lookup"><span data-stu-id="8afe1-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="8afe1-226">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-226">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-227">區別性鈴聲</span><span class="sxs-lookup"><span data-stu-id="8afe1-227">Distinctive ring</span></span> | <span data-ttu-id="8afe1-228">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-228">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-229">1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級</span><span class="sxs-lookup"><span data-stu-id="8afe1-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="8afe1-230">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-230">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-231">[轉寄至] 群組</span><span class="sxs-lookup"><span data-stu-id="8afe1-231">Forward to group</span></span> | <span data-ttu-id="8afe1-232">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-232">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-233">轉接至 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="8afe1-233">Transfer to PSTN call</span></span> | <span data-ttu-id="8afe1-234">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-234">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-235">緊急電話撥打電話方案</span><span class="sxs-lookup"><span data-stu-id="8afe1-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="8afe1-236">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-236">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-237">現有的認證 SIP 手機支援</span><span class="sxs-lookup"><span data-stu-id="8afe1-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="8afe1-238">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-238">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="8afe1-239">USB HID</span></span> | <span data-ttu-id="8afe1-240">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-240">Available</span></span> |
| | <span data-ttu-id="8afe1-241">通話和會議的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8afe1-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="8afe1-242">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-242">Available</span></span> |
| | <span data-ttu-id="8afe1-243">組織自動語音應答</span><span class="sxs-lookup"><span data-stu-id="8afe1-243">Organization auto attendant</span></span> | <span data-ttu-id="8afe1-244">在政府積壓工作</span><span class="sxs-lookup"><span data-stu-id="8afe1-244">On the Government backlog</span></span> |
| | <span data-ttu-id="8afe1-245">Skype 消費者-小組通話支援</span><span class="sxs-lookup"><span data-stu-id="8afe1-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="8afe1-246">無法使用</span><span class="sxs-lookup"><span data-stu-id="8afe1-246">Not available</span></span> |
| <span data-ttu-id="8afe1-247">檔案</span><span class="sxs-lookup"><span data-stu-id="8afe1-247">Files</span></span> | <span data-ttu-id="8afe1-248">近</span><span class="sxs-lookup"><span data-stu-id="8afe1-248">Recent</span></span> | <span data-ttu-id="8afe1-249">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-249">Available</span></span> |
| | <span data-ttu-id="8afe1-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8afe1-250">Microsoft Teams</span></span> | <span data-ttu-id="8afe1-251">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-251">Available</span></span> |
| <span data-ttu-id="8afe1-252">存放</span><span class="sxs-lookup"><span data-stu-id="8afe1-252">Store</span></span> | <span data-ttu-id="8afe1-253">App Store</span><span class="sxs-lookup"><span data-stu-id="8afe1-253">App Store</span></span> | <span data-ttu-id="8afe1-254">無法使用</span><span class="sxs-lookup"><span data-stu-id="8afe1-254">Not available</span></span> |
| <span data-ttu-id="8afe1-255">檢索</span><span class="sxs-lookup"><span data-stu-id="8afe1-255">Search</span></span> | <span data-ttu-id="8afe1-256">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="8afe1-256">Messages</span></span> | <span data-ttu-id="8afe1-257">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-257">Available</span></span> |
| | <span data-ttu-id="8afe1-258">人員</span><span class="sxs-lookup"><span data-stu-id="8afe1-258">People</span></span> | <span data-ttu-id="8afe1-259">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-259">Available</span></span> |
| | <span data-ttu-id="8afe1-260">檔案</span><span class="sxs-lookup"><span data-stu-id="8afe1-260">Files</span></span> | <span data-ttu-id="8afe1-261">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-261">Available</span></span> |
| | <span data-ttu-id="8afe1-262">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="8afe1-262">Slash commands</span></span> | <span data-ttu-id="8afe1-263">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-263">Available</span></span> |
| <span data-ttu-id="8afe1-264">從屬</span><span class="sxs-lookup"><span data-stu-id="8afe1-264">Compliance</span></span> | <span data-ttu-id="8afe1-265">合規性內容搜尋</span><span class="sxs-lookup"><span data-stu-id="8afe1-265">Compliance content search</span></span> | <span data-ttu-id="8afe1-266">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-266">Available</span></span> |
| | <span data-ttu-id="8afe1-267">留成</span><span class="sxs-lookup"><span data-stu-id="8afe1-267">Retention</span></span> | <span data-ttu-id="8afe1-268">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-268">Available</span></span> |
| | <span data-ttu-id="8afe1-269">審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="8afe1-269">Audit log search</span></span> | <span data-ttu-id="8afe1-270">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-270">Available</span></span> |
| | <span data-ttu-id="8afe1-271">法律封存</span><span class="sxs-lookup"><span data-stu-id="8afe1-271">Legal hold</span></span> | <span data-ttu-id="8afe1-272">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-272">Available</span></span> |
| | <span data-ttu-id="8afe1-273">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8afe1-273">eDiscovery</span></span> | <span data-ttu-id="8afe1-274">離線</span><span class="sxs-lookup"><span data-stu-id="8afe1-274">Available</span></span> |

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8afe1-276">決策點</span><span class="sxs-lookup"><span data-stu-id="8afe1-276">Decision point</span></span>|<ul><li><span data-ttu-id="8afe1-277">決定 [小組] 功能集是否符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-277">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="8afe1-278">步驟5。</span><span class="sxs-lookup"><span data-stu-id="8afe1-278">Step 5.</span></span> <span data-ttu-id="8afe1-279">規劃管理</span><span class="sxs-lookup"><span data-stu-id="8afe1-279">Plan for governance</span></span>

<span data-ttu-id="8afe1-280">決定您的管理需求，以及如何符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-280">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="8afe1-281">如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="8afe1-281">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="8afe1-282">決策點</span><span class="sxs-lookup"><span data-stu-id="8afe1-282">Decision point</span></span> |<ul><li><span data-ttu-id="8afe1-283">按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="8afe1-283">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="8afe1-284">步驟6。</span><span class="sxs-lookup"><span data-stu-id="8afe1-284">Step 6.</span></span> <span data-ttu-id="8afe1-285">部署團隊以進行共同作業</span><span class="sxs-lookup"><span data-stu-id="8afe1-285">Deploy Teams for collaboration</span></span>

<span data-ttu-id="8afe1-286">在您 onboarded 至 Microsoft 365 政府– DoD 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。</span><span class="sxs-lookup"><span data-stu-id="8afe1-286">After you’ve been onboarded to Microsoft 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="8afe1-287">請務必與您的採納及變更管理小組和小組擁護者接洽。</span><span class="sxs-lookup"><span data-stu-id="8afe1-287">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="8afe1-288">您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。</span><span class="sxs-lookup"><span data-stu-id="8afe1-288">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
