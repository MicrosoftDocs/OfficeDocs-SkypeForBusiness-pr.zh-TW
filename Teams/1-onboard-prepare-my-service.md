---
title: 準備部署雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用上Microsoft 365檢查Office 365準備Teams，Teams核心功能、網路和雲端語音工作負載。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103969"
---
# <a name="prepare-my-service"></a><span data-ttu-id="45b90-103">準備我的服務</span><span class="sxs-lookup"><span data-stu-id="45b90-103">Prepare my service</span></span>

<span data-ttu-id="45b90-104">本文概述為貴組織準備雲端語音服務的需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="45b90-105">通過妥善準備，您可以確定已準備好為貴組織提供雲端語音功能。</span><span class="sxs-lookup"><span data-stu-id="45b90-105">By preparing properly, you can be sure you're ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="45b90-106">針對語音工作負載Microsoft Teams檢查清單</span><span class="sxs-lookup"><span data-stu-id="45b90-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="45b90-107">下列檢查清單會引導您完成在 Microsoft Teams 中執行音訊會議、電話系統 通話方案 (「通話方案」) 和 電話系統 直接路由 (「直接路由」) 功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="45b90-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans ("Calling Plans"), and Phone System Direct Routing ("Direct Routing") capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="45b90-108">準備Microsoft 365或Office 365 Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-108">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="45b90-109">設定Teams核心功能</span><span class="sxs-lookup"><span data-stu-id="45b90-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="45b90-110">準備您的網路</span><span class="sxs-lookup"><span data-stu-id="45b90-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="45b90-111">在用戶端中設定Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="45b90-112">在中設定直接路由Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="45b90-113">這些檢查清單的工作和活動是核心的「工作」專案，可適用于每一個雲端語音功能部署，Teams。</span><span class="sxs-lookup"><span data-stu-id="45b90-113">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="45b90-114">您可以自訂檢查清單，以包含您自己的行程中特有的活動Teams工作。</span><span class="sxs-lookup"><span data-stu-id="45b90-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="45b90-115">本指南僅著重于通話方案、音訊會議和直接路由。</span><span class="sxs-lookup"><span data-stu-id="45b90-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="45b90-116">如果您第一次Teams，[請Microsoft Teams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="45b90-116">If you're new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="45b90-117">有關規劃您的部署Teams一般指南，請從部署聊天、[團隊](deploy-chat-teams-channels-microsoft-teams-landing-page.md)、頻道和應用程式開始在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="45b90-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="45b90-118">使用提供的檢查清單來追蹤每個個別活動和工作的狀態，並確保您未略過任何重要步驟。</span><span class="sxs-lookup"><span data-stu-id="45b90-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="45b90-119">每個活動包含所需動作的詳細描述，以及可用於完成該活動之額外資訊的參照。</span><span class="sxs-lookup"><span data-stu-id="45b90-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="45b90-120">雖然我們建議您依序遵循檢查清單，但確切的順序會視您的部署範圍，以及您環境的組組和複雜度而決定。</span><span class="sxs-lookup"><span data-stu-id="45b90-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="45b90-121">這些部署會組織成支援「greenfield」Teams部署 (之前沒有 商務用 Skype Online 目前狀態) 或從 商務用 Skype Online 移Teams。</span><span class="sxs-lookup"><span data-stu-id="45b90-121">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="45b90-122">如果您是從線上商務用 Skype，您可能已經完成其中一些活動，現在可以忽略這些活動。</span><span class="sxs-lookup"><span data-stu-id="45b90-122">If you're migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="45b90-123">當您以每個網站為基礎啟動使用者時，強烈建議您使用 Voice [ (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)) 網站啟用 Playbook) 做為這些檢查清單的補充指南。</span><span class="sxs-lookup"><span data-stu-id="45b90-123">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="45b90-124">大部分的設定設定在 Teams 和 商務用 Skype 之間商務用 Skype常見。</span><span class="sxs-lookup"><span data-stu-id="45b90-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="45b90-125">您可以使用系統管理Microsoft 365系統管理中心Microsoft Teams系統管理中心來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="45b90-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="45b90-126">決策點</span><span class="sxs-lookup"><span data-stu-id="45b90-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="45b90-127">神秘將負責監督上機檢查清單的完成情況？</span><span class="sxs-lookup"><span data-stu-id="45b90-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="45b90-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="45b90-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="45b90-129">下載上機檢查清單。</span><span class="sxs-lookup"><span data-stu-id="45b90-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="45b90-130">依照貴組織的部署計畫，逐步完成上載檢查清單專案。</span><span class="sxs-lookup"><span data-stu-id="45b90-130">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="45b90-131">繼續上機</span><span class="sxs-lookup"><span data-stu-id="45b90-131">Continue onboarding</span></span>

<span data-ttu-id="45b90-132">完成這些檢查清單之後，您已成功新增語音功能至您的Teams部署。</span><span class="sxs-lookup"><span data-stu-id="45b90-132">After you complete these checklists, you'll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="45b90-133">下一個步驟是使用 Voice (Playbook) 網站啟用 [Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每個網站上上手，並有助於確保您規劃並執行重要的網站特定活動。</span><span class="sxs-lookup"><span data-stu-id="45b90-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="45b90-134">已準備就緒的網站按網站推出計畫</span><span class="sxs-lookup"><span data-stu-id="45b90-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="45b90-135">建立服務管理程式</span><span class="sxs-lookup"><span data-stu-id="45b90-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="45b90-136">執行測試和補救</span><span class="sxs-lookup"><span data-stu-id="45b90-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="45b90-137">測試雲端語音工作負載Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="45b90-138">在您將 Teams 雲端語音業務成功及技術實現計畫定義為構想階段，並著手在系統管理中心進行您想要的設定之後，下一個步驟就是驗證貴組織的預期和需求是否透過功能、功能和可用性符合。</span><span class="sxs-lookup"><span data-stu-id="45b90-138">After you've defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization's expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="45b90-139">在生產環境中部署試驗或最終部署之前，您應該先執行此驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="45b90-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="45b90-140">您可以利用在構想階段期間定義的商務成功計畫，做為判斷活動、預期、功能/功能測試案例，以及測試階段期間要評估的整體範圍的基礎。</span><span class="sxs-lookup"><span data-stu-id="45b90-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="45b90-141">定義您的測試方法</span><span class="sxs-lookup"><span data-stu-id="45b90-141">Define your testing approach</span></span>

<span data-ttu-id="45b90-142">測試方法最簡單的形式是以檢閱音訊會議、通話方案或直接路由服務的功能為基礎，並開發測試計劃，以驗證您的功能需求是否符合範圍中的使用者。</span><span class="sxs-lookup"><span data-stu-id="45b90-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="45b90-143">以下是音訊會議實施之板載階段範例測試計劃。</span><span class="sxs-lookup"><span data-stu-id="45b90-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="45b90-144">要測試的音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="45b90-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="45b90-145">結果摘要</span><span class="sxs-lookup"><span data-stu-id="45b90-145">Results summary</span></span> | <span data-ttu-id="45b90-146">其他筆記</span><span class="sxs-lookup"><span data-stu-id="45b90-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="45b90-147">排程包含音訊Teams撥入資訊的臨時會議</span><span class="sxs-lookup"><span data-stu-id="45b90-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="45b90-148">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-148">Pass/Fail</span></span>   | <span data-ttu-id="45b90-149">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-149">TBD</span></span> |
| <span data-ttu-id="45b90-150">使用電話使用會議音訊，從 PSTN 撥入會議，並包含提供的撥入資訊</span><span class="sxs-lookup"><span data-stu-id="45b90-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="45b90-151">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-151">Pass/Fail</span></span> | <span data-ttu-id="45b90-152">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-152">TBD</span></span> |
| <span data-ttu-id="45b90-153">透過 PSTN 撥出電話，讓其他人加入現有的會議</span><span class="sxs-lookup"><span data-stu-id="45b90-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="45b90-154">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-154">Pass/Fail</span></span> | <span data-ttu-id="45b90-155">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-155">TBD</span></span> |



| <span data-ttu-id="45b90-156">要測試的通話方案或直接路由功能</span><span class="sxs-lookup"><span data-stu-id="45b90-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="45b90-157">結果摘要</span><span class="sxs-lookup"><span data-stu-id="45b90-157">Results summary</span></span> | <span data-ttu-id="45b90-158">其他筆記</span><span class="sxs-lookup"><span data-stu-id="45b90-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="45b90-159">撥打 PSTN 號碼進行 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="45b90-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="45b90-160">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-160">Pass/Fail</span></span>       | <span data-ttu-id="45b90-161">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-161">TBD</span></span> |
| <span data-ttu-id="45b90-162">從行動電話、有線電話或有線電話 (撥打 PSTN 號碼) </span><span class="sxs-lookup"><span data-stu-id="45b90-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="45b90-163">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-163">Pass/Fail</span></span> | <span data-ttu-id="45b90-164">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-164">TBD</span></span>|
| <span data-ttu-id="45b90-165">將 PSTN 通話從一位Teams轉接到另一個使用者</span><span class="sxs-lookup"><span data-stu-id="45b90-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="45b90-166">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="45b90-166">Pass/Fail</span></span> | <span data-ttu-id="45b90-167">待定</span><span class="sxs-lookup"><span data-stu-id="45b90-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="45b90-168">若要協助建立測試案例做為起點，請參閱會議與[Teams提供的使用者指南清單](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。</span><span class="sxs-lookup"><span data-stu-id="45b90-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="45b90-169">設定雲端語音工作負載Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="45b90-170">現在，您定義測試方法後，下一個步驟是針對雲端語音功能來Teams服務環境和使用者。</span><span class="sxs-lookup"><span data-stu-id="45b90-170">Now that you've defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="45b90-171">有關其他資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="45b90-171">For additional information, see:</span></span>

- [<span data-ttu-id="45b90-172">音訊會議的技術規劃</span><span class="sxs-lookup"><span data-stu-id="45b90-172">Technical Planning for Audio Conferencing</span></span>](./cloud-voice-landing-page.md)

- [<span data-ttu-id="45b90-173">設定 Microsoft Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="45b90-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="45b90-174">使用通話方案電話系統方案的技術規劃</span><span class="sxs-lookup"><span data-stu-id="45b90-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="45b90-175">設定通話和通話商務用 Skype Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45b90-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="45b90-176">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="45b90-176">Plan Direct Routing</span></span>](./direct-routing-plan.md)

- [<span data-ttu-id="45b90-177">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="45b90-177">Configure Direct Routing</span></span>](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a><span data-ttu-id="45b90-178">執行測試計劃</span><span class="sxs-lookup"><span data-stu-id="45b90-178">Execute the test plan</span></span>

[//]: # (編輯正常嗎？「使用者」對我來說似乎有點模糊。)
<span data-ttu-id="45b90-180">在使用者環境和服務完成配置之後，測試的最後一個步驟包括測試計劃執行，並著重于功能驗證。</span><span class="sxs-lookup"><span data-stu-id="45b90-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="45b90-181">**音訊會議測試使用者和網站在範圍中的先決條件和假設：**</span><span class="sxs-lookup"><span data-stu-id="45b90-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="45b90-182">音訊會議服務的企業使用案例定義已經完成。</span><span class="sxs-lookup"><span data-stu-id="45b90-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="45b90-183">音訊會議所需的授權可供使用，而且已指派。</span><span class="sxs-lookup"><span data-stu-id="45b90-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="45b90-184">已識別組織網站和使用者群組清單。</span><span class="sxs-lookup"><span data-stu-id="45b90-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="45b90-185">已識別並設定具有語言喜好設定之專用和共用音訊會議電話撥入號碼的清單。</span><span class="sxs-lookup"><span data-stu-id="45b90-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="45b90-186">[已](what-are-communications-credits.md) 針對 (設定) 通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="45b90-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="45b90-187">音訊會議橋接器設定已識別並設定為 (PIN 長度、進入/離開通知、啟用通知喜好設定) 。</span><span class="sxs-lookup"><span data-stu-id="45b90-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="45b90-188">已識別、設定及應用支援音訊會議撥出案例的租使用者會議原則及撥號方案設定。</span><span class="sxs-lookup"><span data-stu-id="45b90-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="45b90-189">已識別並配置音訊會議合規性需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="45b90-190">**通話方案測試使用者和網站在範圍中的先決條件和假設：**</span><span class="sxs-lookup"><span data-stu-id="45b90-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="45b90-191">已完成通話方案服務的企業使用案例定義。</span><span class="sxs-lookup"><span data-stu-id="45b90-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="45b90-192">通話方案所需的授權是可用的，而且已指派。</span><span class="sxs-lookup"><span data-stu-id="45b90-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="45b90-193">已識別組織網站和使用者群組清單。</span><span class="sxs-lookup"><span data-stu-id="45b90-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="45b90-194">電話指派給使用者的號碼已經取得或移植到 Microsoft，且可在租使用者入口網站取得。</span><span class="sxs-lookup"><span data-stu-id="45b90-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="45b90-195">[已](what-are-communications-credits.md) 針對 (設定) 通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="45b90-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="45b90-196">已識別、設定及應用支援通話方案案例的租使用者使用者原則與撥號方案設定。</span><span class="sxs-lookup"><span data-stu-id="45b90-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="45b90-197">已識別並配置通話方案合規性需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="45b90-198">**使用者和網站在範圍中的直接路由測試先決條件和假設：**</span><span class="sxs-lookup"><span data-stu-id="45b90-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="45b90-199">直接路由服務的企業使用案例定義已經完成。</span><span class="sxs-lookup"><span data-stu-id="45b90-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="45b90-200">直接路由所需的授權是可用的，而且已指派。</span><span class="sxs-lookup"><span data-stu-id="45b90-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="45b90-201">已識別組織網站和使用者群組清單。</span><span class="sxs-lookup"><span data-stu-id="45b90-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="45b90-202">已[部署、 (SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs)) 驗證會話邊界控制器，並搭配電話系統。</span><span class="sxs-lookup"><span data-stu-id="45b90-202">A [certified session border controller (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="45b90-203">Enterprise已啟用語音，且已指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45b90-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="45b90-204">已識別、配置及指派語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="45b90-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="45b90-205">Microsoft Teams範圍中使用者的首選通話用戶端。</span><span class="sxs-lookup"><span data-stu-id="45b90-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="45b90-206">已識別並配置直接路由合規性需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="45b90-207">決策點</span><span class="sxs-lookup"><span data-stu-id="45b90-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="45b90-208">決定將部署哪些音訊會議功能 (服務決策) 。</span><span class="sxs-lookup"><span data-stu-id="45b90-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="45b90-209">識別音訊會議的使用者功能需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="45b90-210">識別音訊會議的服務組組需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="45b90-211">決定是否要部署和配置直接路由或通話方案。</span><span class="sxs-lookup"><span data-stu-id="45b90-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="45b90-212">決定電話系統服務決策中 (哪些功能) 。</span><span class="sxs-lookup"><span data-stu-id="45b90-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="45b90-213">識別通話方案或直接路由的使用者功能需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="45b90-214">識別通話方案或直接路由的服務組組需求。</span><span class="sxs-lookup"><span data-stu-id="45b90-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="45b90-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="45b90-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="45b90-216">開發和記錄您的測試計劃方法。</span><span class="sxs-lookup"><span data-stu-id="45b90-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="45b90-217">在音訊會議功能範圍內準備您的服務環境和使用者。</span><span class="sxs-lookup"><span data-stu-id="45b90-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="45b90-218">在通話方案或直接路由功能範圍內準備您的服務環境和使用者。</span><span class="sxs-lookup"><span data-stu-id="45b90-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="45b90-219">針對您想要啟用的音訊會議功能執行測試驗證。</span><span class="sxs-lookup"><span data-stu-id="45b90-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="45b90-220">針對您想要啟用的通話方案或直接路由功能執行測試驗證。</span><span class="sxs-lookup"><span data-stu-id="45b90-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="45b90-221">針對任何測試失敗，請確認您的組組正確無誤、檢閱社群文章，並提出支援案例 ，如有必要。</span><span class="sxs-lookup"><span data-stu-id="45b90-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="45b90-222">若要進一步瞭解如何在 Teams 中執行音訊會議測試的詳細指南，請參閱音訊會議[的詳細測試指南](./deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="45b90-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](./deploy-audio-conferencing-teams-landing-page.md).</span></span>

<span data-ttu-id="45b90-223">有關如何在 Teams 中執行通話方案測試的其他詳細[電話系統。](./cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="45b90-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](./cloud-voice-landing-page.md).</span></span>

<!--ENDOFSECTION-->