---
title: 規劃 Microsoft 團隊服務管理
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 規劃運營角色並指派品質擁護者來提供和維護高品質的部署。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1268a87e5e5ae48547e1f2489641ac13cd3bae64
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862713"
---
# <a name="plan-my-service-management"></a><span data-ttu-id="7e273-103">規劃我的服務管理</span><span class="sxs-lookup"><span data-stu-id="7e273-103">Plan my service management</span></span>

<span data-ttu-id="7e273-104">本文概述傳送和維護高品質 Microsoft 團隊部署所需的需求。</span><span class="sxs-lookup"><span data-stu-id="7e273-104">This article gives an overview of the requirements that are necessary to deliver and maintain a high-quality Microsoft Teams deployment.</span></span> <span data-ttu-id="7e273-105">您可以在進行第一次試驗或生產部署前，在構想階段規劃服務管理和品質，以協助確保順利進行部署。</span><span class="sxs-lookup"><span data-stu-id="7e273-105">You can help ensure a successful deployment by planning for service management and quality during the Envision phase, before your first pilot or production deployment.</span></span>

## <a name="service-management-for-teams"></a><span data-ttu-id="7e273-106">團隊的服務管理</span><span class="sxs-lookup"><span data-stu-id="7e273-106">Service management for Teams</span></span>

<span data-ttu-id="7e273-107">服務管理是一個廣泛的主題，涵蓋在部署並為使用者啟用 Microsoft 團隊服務之後的日常作業。</span><span class="sxs-lookup"><span data-stu-id="7e273-107">Service management is a broad topic that covers day-to-day operations of the Microsoft Teams service after it has been deployed and enabled for users.</span></span> <span data-ttu-id="7e273-108">[團隊服務] 包含 Microsoft Office 365 和部署于內部部署的基礎結構元件（例如 [網路]）。</span><span class="sxs-lookup"><span data-stu-id="7e273-108">The Teams service encompasses Microsoft Office 365 and the infrastructure components that are deployed on-premises (for example, networking).</span></span>

<span data-ttu-id="7e273-109">服務管理的概念很可能不是大多陣列織的新概念。</span><span class="sxs-lookup"><span data-stu-id="7e273-109">The notion of service management is most likely not a new concept for most organizations.</span></span> <span data-ttu-id="7e273-110">您可能已經實現與現有服務相關聯的進程和工作。</span><span class="sxs-lookup"><span data-stu-id="7e273-110">You probably have already implemented processes and tasks that are associated with existing services.</span></span> <span data-ttu-id="7e273-111">如此一來，您可能會在規劃服務管理時補充所需的內容，以備日後支援 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="7e273-111">That said, you can probably augment what you have in place when you plan for service management today to support Microsoft Teams in the future.</span></span>

<span data-ttu-id="7e273-112">服務管理包括管理 Microsoft 團隊端到端的所有活動與程式。</span><span class="sxs-lookup"><span data-stu-id="7e273-112">Service management encompasses all the activities and processes involved in managing Microsoft Teams end to end.</span></span> <span data-ttu-id="7e273-113">服務管理的部分元件（由 Office 365 服務本身所組成的基礎結構元件）是 Microsoft 的責任，而客戶對其使用者負責管理團隊、網路和的各個方面。其提供的端點。</span><span class="sxs-lookup"><span data-stu-id="7e273-113">Some components of service management—the infrastructure components that the Office 365 service itself comprises—are Microsoft’s responsibility, whereas the customer is accountable to its users to manage the various aspects of Teams, the network, and endpoints they provide.</span></span>
<span data-ttu-id="7e273-114">如需團隊服務管理的客戶責任以及其與 underpin 使用者體驗品質的關鍵元件的完整討論，請參閱[規劃服務管理和品質](https://docs.microsoft.com/MicrosoftTeams/prepare-network)。</span><span class="sxs-lookup"><span data-stu-id="7e273-114">For a complete discussion of the customer responsibility for Teams service management and how it relates to the key components that underpin the quality of the user experience, see [Plan for service management and quality](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>

<span data-ttu-id="7e273-115">![三個品質元件的圖表](media/plan-my-service-management-image1.png "這三個元件的 [品質]--[Office 365 服務]、[網路] 和 [端點] 的圖表，以及服務管理如何與這三個元件重迭。")</span><span class="sxs-lookup"><span data-stu-id="7e273-115">![Diagram of the three components of quality](media/plan-my-service-management-image1.png "Diagram of the three components of quality--Office 365 service, network, and endpoints--and how service management overlaps all three.")</span></span>

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a><span data-ttu-id="7e273-116">操作指南簡介</span><span class="sxs-lookup"><span data-stu-id="7e273-116">Introduction to the Operations Guide</span></span> 

<span data-ttu-id="7e273-117">**何謂**、**誰**，以及**如何**在服務管理方面需要解答的三個重要問題。</span><span class="sxs-lookup"><span data-stu-id="7e273-117">**What**, **Who**, and **How** are three important questions that need to be answered when it comes to service management.</span></span>

<span data-ttu-id="7e273-118">您可以使用 [[操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)] 協助您解決這三個問題。</span><span class="sxs-lookup"><span data-stu-id="7e273-118">You can use the [Operations Guide](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) to help you address all three of these questions.</span></span> <span data-ttu-id="7e273-119">本指南提供每日、每週、每月以及視需要執行的活動清單。</span><span class="sxs-lookup"><span data-stu-id="7e273-119">The guide provides a list of activities to be performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="7e273-120">這些活動和工作對於維護高品質的小組部署而言是至關重要的。</span><span class="sxs-lookup"><span data-stu-id="7e273-120">These activities and tasks are critical for maintaining a high-quality Teams deployment.</span></span> <span data-ttu-id="7e273-121">決定要在服務管理中執行特定活動的人員，是規劃的一個重要層面，您需要儘早在 Envision 階段進行，以確保順利進行部署。</span><span class="sxs-lookup"><span data-stu-id="7e273-121">Determining who will be responsible for performing specific activities in service management is a critical aspect of your planning that you need to do early in the Envision phase to ensure a successful deployment.</span></span> <span data-ttu-id="7e273-122">在您發現任務和活動之後，必須先瞭解這些工作和活動，然後再按您指派給他們的群組或人員。</span><span class="sxs-lookup"><span data-stu-id="7e273-122">After you’ve figured out the tasks and activities, they need to be understood and followed by the groups or individuals that you assign to them.</span></span> <span data-ttu-id="7e273-123">本操作指南針對如何執行每項工作以及/或外部內容的參考，提供相關知識與指導方針。</span><span class="sxs-lookup"><span data-stu-id="7e273-123">The Operations Guide provides knowledge and guidance for how to perform each of the tasks, and/or references to outside content.</span></span>

## <a name="plan-for-operational-role-mapping"></a><span data-ttu-id="7e273-124">規劃操作角色對應</span><span class="sxs-lookup"><span data-stu-id="7e273-124">Plan for operational role mapping</span></span>

<span data-ttu-id="7e273-125">儘早規劃服務管理是一個重要的里程碑，因為「操作階段」是在第一個試驗使用者啟用時開始。</span><span class="sxs-lookup"><span data-stu-id="7e273-125">Planning for service management early is a critical milestone, because the operations phase begins when the first pilot users are enabled.</span></span> <span data-ttu-id="7e273-126">專案小組必須審查並同意所需的工作與活動，找出負責每個作業任務的小組，然後從各個小組取得承諾並登出。</span><span class="sxs-lookup"><span data-stu-id="7e273-126">The project team must review and agree on the tasks and activities required, identify the team that’s responsible for each operational task, and then get a commitment and sign-off from each respective team.</span></span>

<span data-ttu-id="7e273-127">登出完成後，負責的小組必須開始 operationalizing 這些角色和職責。</span><span class="sxs-lookup"><span data-stu-id="7e273-127">After sign-off is complete, the responsible team must then start operationalizing these roles and responsibilities.</span></span> <span data-ttu-id="7e273-128">這可能包括訓練與準備、更新人力資源模型，或確保外部合作夥伴已準備好交付。</span><span class="sxs-lookup"><span data-stu-id="7e273-128">This might include training and readiness, updating the staffing model, or ensuring that external partners are ready to deliver.</span></span>

<span data-ttu-id="7e273-129">在 Envision 階段的初期對應運營角色，可讓所有團隊在試驗和加速作業期間開始其運作工作，並確保部署開始之後一切都已準備好。</span><span class="sxs-lookup"><span data-stu-id="7e273-129">Mapping operational roles early in the Envision phase enables all teams to start their operational tasks during the pilot and ramp up operations and make sure that everything is ready after the deployment starts.</span></span>

<span data-ttu-id="7e273-130">本操作指南提供對應至一般角色的一般工作清單，這些工作應該在大多數情況下都有效。</span><span class="sxs-lookup"><span data-stu-id="7e273-130">The Operations Guide provides a list of common tasks mapped to typical roles that should be valid in most scenarios.</span></span> <span data-ttu-id="7e273-131">您必須自訂這些職責，才能為您的組織作業。</span><span class="sxs-lookup"><span data-stu-id="7e273-131">You need to customize these responsibilities to work for your organization.</span></span>

>[!TIP]
><span data-ttu-id="7e273-132">下列是一個範本範例，可將您執行以支援此專案的操作角色對應練習的結果進行記錄。</span><span class="sxs-lookup"><span data-stu-id="7e273-132">The following is an example of a template to document the result of operational roles mapping exercise that you performed to support this project.</span></span>


|<span data-ttu-id="7e273-133">操作角色</span><span class="sxs-lookup"><span data-stu-id="7e273-133">Operational Role</span></span> |<span data-ttu-id="7e273-134">描述</span><span class="sxs-lookup"><span data-stu-id="7e273-134">Description</span></span> |<span data-ttu-id="7e273-135">團隊</span><span class="sxs-lookup"><span data-stu-id="7e273-135">Team</span></span> |<span data-ttu-id="7e273-136">連絡人詳細資料</span><span class="sxs-lookup"><span data-stu-id="7e273-136">Contact Details</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="7e273-137">服務擁有者</span><span class="sxs-lookup"><span data-stu-id="7e273-137">Service Owner</span></span>|<span data-ttu-id="7e273-138">服務擁有者、公司分部介面、戰略</span><span class="sxs-lookup"><span data-stu-id="7e273-138">Service owner, interface to business divisions, strategy</span></span>|<span data-ttu-id="7e273-139">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-139">TBA</span></span>|<span data-ttu-id="7e273-140">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-140">TBA</span></span>|
|<span data-ttu-id="7e273-141">音訊會議作業</span><span class="sxs-lookup"><span data-stu-id="7e273-141">Audio Conferencing Operations</span></span>|<span data-ttu-id="7e273-142">每日作業、使用者和裝置帳戶移動/新增/變更、監控</span><span class="sxs-lookup"><span data-stu-id="7e273-142">Daily operations, user and device account move/add/change, monitoring</span></span>|<span data-ttu-id="7e273-143">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-143">TBA</span></span>| <span data-ttu-id="7e273-144">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-144">TBA</span></span>| 
|<span data-ttu-id="7e273-145">租使用者管理員</span><span class="sxs-lookup"><span data-stu-id="7e273-145">Tenant Admin</span></span>|<span data-ttu-id="7e273-146">變更整個租使用者的設定、啟用新功能</span><span class="sxs-lookup"><span data-stu-id="7e273-146">Change tenant-wide settings, enable new features</span></span>|<span data-ttu-id="7e273-147">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-147">TBA</span></span>|<span data-ttu-id="7e273-148">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-148">TBA</span></span>|
|<span data-ttu-id="7e273-149">技術支援中心</span><span class="sxs-lookup"><span data-stu-id="7e273-149">Help Desk</span></span>|<span data-ttu-id="7e273-150">使用者取得支援的介面</span><span class="sxs-lookup"><span data-stu-id="7e273-150">Interface for users to get support</span></span>|<span data-ttu-id="7e273-151">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-151">TBA</span></span>|<span data-ttu-id="7e273-152">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-152">TBA</span></span>|
|<span data-ttu-id="7e273-153">網路作業</span><span class="sxs-lookup"><span data-stu-id="7e273-153">Network Operations</span></span>|<span data-ttu-id="7e273-154">執行局域網、WAN、Wi-fi 和網際網路存取</span><span class="sxs-lookup"><span data-stu-id="7e273-154">Run LAN, WAN, Wi-Fi, and internet access</span></span>|<span data-ttu-id="7e273-155">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-155">TBA</span></span>|<span data-ttu-id="7e273-156">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-156">TBA</span></span>|
|<span data-ttu-id="7e273-157">用戶端 & 端點小組</span><span class="sxs-lookup"><span data-stu-id="7e273-157">Client & Endpoints Team</span></span>|<span data-ttu-id="7e273-158">管理桌面部署</span><span class="sxs-lookup"><span data-stu-id="7e273-158">Manage desktop deployments</span></span>|<span data-ttu-id="7e273-159">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-159">TBA</span></span>|<span data-ttu-id="7e273-160">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-160">TBA</span></span>|
|<span data-ttu-id="7e273-161">身分識別作業</span><span class="sxs-lookup"><span data-stu-id="7e273-161">Identity Operations</span></span>|<span data-ttu-id="7e273-162">管理身分識別結構（Active Directory、Active Directory Federation Services、Azure AD）</span><span class="sxs-lookup"><span data-stu-id="7e273-162">Manage identity infrastructure (Active Directory, Active Directory Federation Services, Azure AD)</span></span>|<span data-ttu-id="7e273-163">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-163">TBA</span></span>|<span data-ttu-id="7e273-164">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-164">TBA</span></span>|
|<span data-ttu-id="7e273-165">採納/變更管理</span><span class="sxs-lookup"><span data-stu-id="7e273-165">Adoption/Change Management</span></span>|<span data-ttu-id="7e273-166">管理解決方案的意識、訓練及採納</span><span class="sxs-lookup"><span data-stu-id="7e273-166">Manage awareness, training, and adoption for the solution</span></span>|<span data-ttu-id="7e273-167">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-167">TBA</span></span>|<span data-ttu-id="7e273-168">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-168">TBA</span></span>|
|<span data-ttu-id="7e273-169">Exchange 操作</span><span class="sxs-lookup"><span data-stu-id="7e273-169">Exchange Operations</span></span>|<span data-ttu-id="7e273-170">管理 Exchange 環境</span><span class="sxs-lookup"><span data-stu-id="7e273-170">Manage the Exchange environment</span></span>|<span data-ttu-id="7e273-171">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-171">TBA</span></span>|<span data-ttu-id="7e273-172">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-172">TBA</span></span>|
|<span data-ttu-id="7e273-173">電話作業</span><span class="sxs-lookup"><span data-stu-id="7e273-173">Telephony Operations</span></span>|<span data-ttu-id="7e273-174">管理 SBC 和電話號碼</span><span class="sxs-lookup"><span data-stu-id="7e273-174">Manage the SBC's and the phone numbers</span></span>|<span data-ttu-id="7e273-175">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-175">TBA</span></span>|<span data-ttu-id="7e273-176">TBA</span><span class="sxs-lookup"><span data-stu-id="7e273-176">TBA</span></span>|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a><span data-ttu-id="7e273-177">品質擁護者角色</span><span class="sxs-lookup"><span data-stu-id="7e273-177">The Quality Champion role</span></span>

<span data-ttu-id="7e273-178">群組或個人需要負責所有組織中的品質。</span><span class="sxs-lookup"><span data-stu-id="7e273-178">A group or individual needs to be accountable for quality in all organizations.</span></span>
<span data-ttu-id="7e273-179">這是服務管理中最重要的角色。</span><span class="sxs-lookup"><span data-stu-id="7e273-179">This is the most important role in service management.</span></span> <span data-ttu-id="7e273-180">品質擁護者是指派給人員或群組的客戶角色，他們會熱情他們的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="7e273-180">The quality champion is a customer role that's assigned to a person or group who is passionate about their users' experience.</span></span> <span data-ttu-id="7e273-181">這個角色需要技能來識別環境中的趨勢，以及與其他團隊合作來促進修正的贊助。</span><span class="sxs-lookup"><span data-stu-id="7e273-181">This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation.</span></span>
<span data-ttu-id="7e273-182">品質擁護者的最佳候選方案通常是客戶服務擁有者，他們可以根據組織的大小與複雜性而定，誰是熱情使用者體驗的人員或群組。</span><span class="sxs-lookup"><span data-stu-id="7e273-182">The best candidate for the quality champion is typically the customer service owner, who—depending on the organization’s size and complexity—could be any person or group who is passionate about user experience.</span></span>

<span data-ttu-id="7e273-183">[品質擁護者] 利用現有的工具與已記錄的程式，例如 [通話品質儀表板] （CQD）和 [品質體驗檢查指南]，以監控使用者體驗、識別品質趨勢，以及在必要時進行磁片磁碟機修正。</span><span class="sxs-lookup"><span data-stu-id="7e273-183">The quality champion leverages existing tools and documented processes, such as the Call Quality Dashboard (CQD) and the Quality Experience Review Guide, to monitor user experience, identify quality trends, and drive remediation where needed.</span></span> <span data-ttu-id="7e273-184">品質擁護者與各個小組合作，以促進修正動作，向指導委員會報告其進度和開啟的問題。</span><span class="sxs-lookup"><span data-stu-id="7e273-184">The quality champion works with the respective teams to drive remediation actions, reporting to a steering committee on their progress and open issues.</span></span>

<span data-ttu-id="7e273-185">[作業指南] 中記錄了與角色相關聯的工作和活動。</span><span class="sxs-lookup"><span data-stu-id="7e273-185">The tasks and activities associated with the role are documented in the Operations Guide.</span></span> <span data-ttu-id="7e273-186">這個角色應該在構想階段中儘早指派。</span><span class="sxs-lookup"><span data-stu-id="7e273-186">This role should be assigned early in the Envision phase.</span></span> <span data-ttu-id="7e273-187">Operationalizing 品質擁護者角色的主要步驟是取得該角色所需的知識，並確保準備好要提供該工作所需的預備作業。</span><span class="sxs-lookup"><span data-stu-id="7e273-187">A key step in operationalizing the role of Quality Champion is gaining the knowledge required for the role and ensuring the prerequisites are in place to deliver on the tasks.</span></span> <span data-ttu-id="7e273-188">此角色的主要工作是執行定期品質體驗審查。</span><span class="sxs-lookup"><span data-stu-id="7e273-188">A key task for this role is running a regular Quality Experience Review.</span></span>

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a><span data-ttu-id="7e273-189">[品質體驗回顧指南] 簡介</span><span class="sxs-lookup"><span data-stu-id="7e273-189">Introduction to the Quality Experience Review Guide</span></span>

<span data-ttu-id="7e273-190">[品質體驗檢查指南] 中有一組活動，可針對改善使用者體驗的主要區域評估並提供修正指導方針，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="7e273-190">The Quality Experience Review Guide has a set of activities that assess and provide remediation guidance in key areas that have the greatest impact for improving user experience, as shown in the figure below.</span></span>

<span data-ttu-id="7e273-191">![在品質體驗檢查期間檢查的主要區域圖例](media/plan-my-service-management-image2.png "在品質體驗檢查期間要檢查的主要區域：音訊、可靠性及使用者問卷結果。")</span><span class="sxs-lookup"><span data-stu-id="7e273-191">![Illustration of key areas to examine during quality experience review](media/plan-my-service-management-image2.png "The key areas to examine during a quality experience review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="7e273-192">透過不斷評估與修正本檔中所述的區域，您可以減少對使用者經驗造成負面影響的可能性。</span><span class="sxs-lookup"><span data-stu-id="7e273-192">By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="7e273-193">在部署中遇到的大多數使用者體驗問題，都可以分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="7e273-193">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="7e273-194">防火牆或 proxy 配置不完整</span><span class="sxs-lookup"><span data-stu-id="7e273-194">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="7e273-195">低 wi-fi 覆蓋範圍</span><span class="sxs-lookup"><span data-stu-id="7e273-195">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="7e273-196">頻寬不足</span><span class="sxs-lookup"><span data-stu-id="7e273-196">Insufficient bandwidth</span></span>

-   <span data-ttu-id="7e273-197">點對點</span><span class="sxs-lookup"><span data-stu-id="7e273-197">VPN</span></span>

-   <span data-ttu-id="7e273-198">使用未優化或內建的音訊裝置</span><span class="sxs-lookup"><span data-stu-id="7e273-198">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="7e273-199">有問題的子網或網路裝置</span><span class="sxs-lookup"><span data-stu-id="7e273-199">Problematic subnets or network devices</span></span>

<span data-ttu-id="7e273-200">[品質體驗回顧指南] 中所提供的指導方針主要是使用 [通話品質儀表板（CQD）] 作為主要工具來報告和調查所述的每個區域，並將焦點放在音訊上以最大化採納與影響。</span><span class="sxs-lookup"><span data-stu-id="7e273-200">The guidance provided in the Quality Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="7e273-201">針對網路所做的任何優化，以改善音訊體驗，也會直接翻譯成影片和桌面共用的改良功能。</span><span class="sxs-lookup"><span data-stu-id="7e273-201">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="7e273-202">我們強烈建議您提前提名品質擁護者。</span><span class="sxs-lookup"><span data-stu-id="7e273-202">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="7e273-203">命名之後，他們應該開始熟悉[品質體驗回顧指南](https://aka.ms/qerguide)中的內容。</span><span class="sxs-lookup"><span data-stu-id="7e273-203">After being nominated, they should start to familiarize themselves with the content in the [Quality Experience Review Guide](https://aka.ms/qerguide).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7e273-204">決策點</span><span class="sxs-lookup"><span data-stu-id="7e273-204">Decision points</span></span></td><td><ul><li><span data-ttu-id="7e273-205">決定誰負責貴組織中的雲端語音作業。</span><span class="sxs-lookup"><span data-stu-id="7e273-205">Decide who is accountable for cloud voice operations in your organization.</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7e273-206">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7e273-206">Next steps</span></span></td><td><ul><li><span data-ttu-id="7e273-207">下載 [服務管理的規劃] 完整指南。</span><span class="sxs-lookup"><span data-stu-id="7e273-207">Download the Planning for Service Management full guide.</span></span></li><li><span data-ttu-id="7e273-208">下載 [品質體驗回顧指南]。</span><span class="sxs-lookup"><span data-stu-id="7e273-208">Download the Quality Experience Review guide.</span></span></li><li><span data-ttu-id="7e273-209">完整回顧 [操作指南]。</span><span class="sxs-lookup"><span data-stu-id="7e273-209">Review the Operations Guide in full.</span></span></li><li><span data-ttu-id="7e273-210">將所有指南提供給每個作業小組成員，以進行審查並熟悉作業需求。</span><span class="sxs-lookup"><span data-stu-id="7e273-210">Provide all guides to every operations team members to review and be familiar with operations requirements.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->