---
title: 準備部署 Microsoft 團隊雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用 [加入檢查清單] 來為小組準備 Office 365, 並設定小組核心功能、網路和雲端語音工作負載。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63b507237cbc9a1d32dc891b99eaf6425528b559
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236566"
---
# <a name="prepare-my-service"></a><span data-ttu-id="c71f2-103">準備我的服務</span><span class="sxs-lookup"><span data-stu-id="c71f2-103">Prepare my service</span></span>

<span data-ttu-id="c71f2-104">本文概述為貴組織準備雲端語音服務的需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="c71f2-105">透過正確地準備, 您可以確定您已準備好將雲端語音功能提供給您的組織。</span><span class="sxs-lookup"><span data-stu-id="c71f2-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="c71f2-106">Microsoft 團隊語音工作負載的加入檢查清單</span><span class="sxs-lookup"><span data-stu-id="c71f2-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="c71f2-107">下列檢查清單會逐步引導您完成在 Microsoft 團隊中實現音訊會議、電話系統與通話方案 (「通話方案」), 以及手機系統 Direct 路由 ("直接路由") 功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="c71f2-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="c71f2-108">為團隊準備 Office 365</span><span class="sxs-lookup"><span data-stu-id="c71f2-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="c71f2-109">設定團隊核心功能</span><span class="sxs-lookup"><span data-stu-id="c71f2-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="c71f2-110">設定網路</span><span class="sxs-lookup"><span data-stu-id="c71f2-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="c71f2-111">在團隊中設定雲端語音工作負載</span><span class="sxs-lookup"><span data-stu-id="c71f2-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="c71f2-112">在團隊中設定直接路由</span><span class="sxs-lookup"><span data-stu-id="c71f2-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="c71f2-113">這些檢查清單中的工作與活動是「待辦事項」專案, 可套用至團隊的每個雲端語音功能部署。</span><span class="sxs-lookup"><span data-stu-id="c71f2-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="c71f2-114">您可以自訂檢查清單, 以包含您自己團隊歷程所特有的活動和工作。</span><span class="sxs-lookup"><span data-stu-id="c71f2-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="c71f2-115">本指南專門說明通話方案、音訊會議及直接路由。</span><span class="sxs-lookup"><span data-stu-id="c71f2-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="c71f2-116">如果您是團隊新手, 請參閱[Microsoft 團隊的概覽](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="c71f2-117">如需規劃團隊部署的一般指導方針, 請先[在 Microsoft 團隊中開始部署聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="c71f2-118">使用提供的檢查清單來追蹤每個個別活動和工作的狀態, 並確認您未略過任何重要步驟。</span><span class="sxs-lookup"><span data-stu-id="c71f2-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="c71f2-119">每個活動都包含所需動作的詳細描述, 以及您可以用來完成該活動的其他資訊參考。</span><span class="sxs-lookup"><span data-stu-id="c71f2-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="c71f2-120">雖然我們建議您依照檢查清單的順序, 但確切的順序取決於您的部署範圍, 以及環境的設定和複雜性。</span><span class="sxs-lookup"><span data-stu-id="c71f2-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="c71f2-121">其組織結構是支援「嶄新」團隊部署 (沒有先前的商務用 skype Online 目前狀態), 或從商務用 Skype Online 遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="c71f2-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="c71f2-122">如果您是從商務用 Skype Online 進行遷移, 您可能已經完成這些活動, 而且現在可以略過它們。</span><span class="sxs-lookup"><span data-stu-id="c71f2-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="c71f2-123">如果您是以每個網站為基礎加入使用者, 我們強烈建議您使用 [[網站啟用嚮導] (行動手冊))](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)作為這些檢查清單的輔助指南。</span><span class="sxs-lookup"><span data-stu-id="c71f2-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="c71f2-124">在團隊與商務用 Skype Online 之間, 大部分的設定都是常見的配置。</span><span class="sxs-lookup"><span data-stu-id="c71f2-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="c71f2-125">您使用 Microsoft 365 系統管理中心及 Microsoft 團隊系統管理中心來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="c71f2-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="c71f2-126">決策點</span><span class="sxs-lookup"><span data-stu-id="c71f2-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="c71f2-127">誰將負責監視加入核對檢查的完成情況？</span><span class="sxs-lookup"><span data-stu-id="c71f2-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="c71f2-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c71f2-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="c71f2-129">下載加入檢查清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="c71f2-130">依照貴組織的部署方案逐步逐步完成 [加入檢查清單專案]。</span><span class="sxs-lookup"><span data-stu-id="c71f2-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="c71f2-131">繼續加入</span><span class="sxs-lookup"><span data-stu-id="c71f2-131">Continue onboarding</span></span>

<span data-ttu-id="c71f2-132">完成這些檢查清單後, 您就可以成功地在小組部署中新增語音功能了。</span><span class="sxs-lookup"><span data-stu-id="c71f2-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="c71f2-133">在下一個步驟中, 使用 [[網站啟用行動手冊-語音 (行動手冊)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ] 協助您在每個網站上為您的使用者進行設計, 並協助確保您規劃並執行重要的網站特定活動。</span><span class="sxs-lookup"><span data-stu-id="c71f2-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="c71f2-134">[由網站推出方案準備就緒] 網站</span><span class="sxs-lookup"><span data-stu-id="c71f2-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="c71f2-135">建立服務管理流程</span><span class="sxs-lookup"><span data-stu-id="c71f2-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="c71f2-136">執行測試與修正</span><span class="sxs-lookup"><span data-stu-id="c71f2-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="c71f2-137">在團隊中測試雲端語音工作負載</span><span class="sxs-lookup"><span data-stu-id="c71f2-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="c71f2-138">在構想階段中定義並記錄您的小組雲端企業成功和技術實現方案之後, 且在系統管理中心進行您想要的設定後, 下一步就是驗證貴組織的您可以透過功能、功能和可用性來滿足預期和需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="c71f2-139">您應該先執行此驗證步驟, 才能在您的生產環境中部署試驗或最終部署。</span><span class="sxs-lookup"><span data-stu-id="c71f2-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="c71f2-140">您可以利用在您的構想階段所定義的商業成功方案, 作為判斷活動、預期、功能/功能測試案例的基礎, 以及在測試階段評估的整體範圍。</span><span class="sxs-lookup"><span data-stu-id="c71f2-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="c71f2-141">定義您的測試方法</span><span class="sxs-lookup"><span data-stu-id="c71f2-141">Define your testing approach</span></span>

<span data-ttu-id="c71f2-142">在其最簡單的形式中, 您的測試方法是以您的語音會議、呼叫方案或直接路由服務的功能功能為基礎, 並開發測試方案, 以驗證範圍中的使用者是否符合您的功能需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="c71f2-143">下列是音訊會議實現的板載階段範例測試方案。</span><span class="sxs-lookup"><span data-stu-id="c71f2-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="c71f2-144">要測試的音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="c71f2-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="c71f2-145">結果摘要</span><span class="sxs-lookup"><span data-stu-id="c71f2-145">Results summary</span></span> | <span data-ttu-id="c71f2-146">其他筆記</span><span class="sxs-lookup"><span data-stu-id="c71f2-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="c71f2-147">安排包含音訊會議撥入資訊的即席小組會議</span><span class="sxs-lookup"><span data-stu-id="c71f2-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="c71f2-148">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-148">Pass/Fail</span></span>   | <span data-ttu-id="c71f2-149">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-149">TBD</span></span> |
| <span data-ttu-id="c71f2-150">使用電話從 PSTN 撥入會議音訊, 並提供隨附的撥入資訊</span><span class="sxs-lookup"><span data-stu-id="c71f2-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="c71f2-151">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-151">Pass/Fail</span></span> | <span data-ttu-id="c71f2-152">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-152">TBD</span></span> |
| <span data-ttu-id="c71f2-153">透過 PSTN 撥出, 將其他人加入現有的會議</span><span class="sxs-lookup"><span data-stu-id="c71f2-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="c71f2-154">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-154">Pass/Fail</span></span> | <span data-ttu-id="c71f2-155">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-155">TBD</span></span> |



| <span data-ttu-id="c71f2-156">通話方案或直接路由功能以進行測試</span><span class="sxs-lookup"><span data-stu-id="c71f2-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="c71f2-157">結果摘要</span><span class="sxs-lookup"><span data-stu-id="c71f2-157">Results summary</span></span> | <span data-ttu-id="c71f2-158">其他筆記</span><span class="sxs-lookup"><span data-stu-id="c71f2-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="c71f2-159">透過撥 PSTN 號碼撥打 PSTN 電話</span><span class="sxs-lookup"><span data-stu-id="c71f2-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="c71f2-160">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-160">Pass/Fail</span></span>       | <span data-ttu-id="c71f2-161">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-161">TBD</span></span> |
| <span data-ttu-id="c71f2-162">從外部線路撥打 PSTN 號碼 (行動裝置、有線電話), 接聽 PSTN 電話</span><span class="sxs-lookup"><span data-stu-id="c71f2-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="c71f2-163">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-163">Pass/Fail</span></span> | <span data-ttu-id="c71f2-164">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-164">TBD</span></span>|
| <span data-ttu-id="c71f2-165">將 PSTN 呼叫從一個團隊使用者轉接到另一個。</span><span class="sxs-lookup"><span data-stu-id="c71f2-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="c71f2-166">通過/失敗</span><span class="sxs-lookup"><span data-stu-id="c71f2-166">Pass/Fail</span></span> | <span data-ttu-id="c71f2-167">TBD</span><span class="sxs-lookup"><span data-stu-id="c71f2-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="c71f2-168">若要協助將測試案例建立作為起點, 請參閱[小組會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中提供的使用者指南清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="c71f2-169">為團隊設定雲端語音工作負載</span><span class="sxs-lookup"><span data-stu-id="c71f2-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="c71f2-170">現在您已定義測試方法, 下一個步驟是在團隊雲端語音功能的範圍內設定您的服務環境和使用者。</span><span class="sxs-lookup"><span data-stu-id="c71f2-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="c71f2-171">如需其他資訊, 請參閱:</span><span class="sxs-lookup"><span data-stu-id="c71f2-171">For additional information, see:</span></span>

- [<span data-ttu-id="c71f2-172">音訊會議的技術規劃</span><span class="sxs-lookup"><span data-stu-id="c71f2-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="c71f2-173">為 Microsoft 團隊設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="c71f2-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="c71f2-174">使用通話方案的電話系統技術規劃</span><span class="sxs-lookup"><span data-stu-id="c71f2-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="c71f2-175">設定商務用 Skype 和 Microsoft 團隊的通話方案</span><span class="sxs-lookup"><span data-stu-id="c71f2-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="c71f2-176">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="c71f2-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="c71f2-177">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="c71f2-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="c71f2-178">執行測試方案</span><span class="sxs-lookup"><span data-stu-id="c71f2-178">Execute the test plan</span></span>

[//]: # (編輯好嗎？「使用者」似乎對我而言有點不明確。)
<span data-ttu-id="c71f2-180">在使用者環境和服務設定之後, 測試的最後一個步驟, 包括將焦點放在功能和功能驗證的測試方案執行。</span><span class="sxs-lookup"><span data-stu-id="c71f2-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="c71f2-181">**音訊會議: 針對範圍中的使用者和網站, 測試先決條件及假設:**</span><span class="sxs-lookup"><span data-stu-id="c71f2-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c71f2-182">已完成音訊會議服務的商務使用案例定義。</span><span class="sxs-lookup"><span data-stu-id="c71f2-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="c71f2-183">提供音訊會議所需的授權, 且已指派。</span><span class="sxs-lookup"><span data-stu-id="c71f2-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="c71f2-184">已識別組織網站和使用者群組的清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c71f2-185">已識別並設定具有語言喜好設定的專用和共用音訊會議撥入號碼的清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="c71f2-186">[通訊點數](what-are-communications-credits.md)(視需要) 已針對您的組織進行設定。</span><span class="sxs-lookup"><span data-stu-id="c71f2-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c71f2-187">已識別並設定音訊會議的 [會議橋接] 設定 (PIN 長度、進入/結束通知、啟用通知喜好設定)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="c71f2-188">已識別、設定及套用支援音訊會議撥出案例的租使用者會議原則和撥號方案設定。</span><span class="sxs-lookup"><span data-stu-id="c71f2-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c71f2-189">已確認並設定音訊會議規範需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c71f2-190">**針對範圍中的使用者和網站, 呼叫方案測試先決條件與假設:**</span><span class="sxs-lookup"><span data-stu-id="c71f2-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c71f2-191">已完成通話方案服務的商務使用案例定義。</span><span class="sxs-lookup"><span data-stu-id="c71f2-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="c71f2-192">提供通話方案所需的授權, 且已指派。</span><span class="sxs-lookup"><span data-stu-id="c71f2-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="c71f2-193">已識別組織網站和使用者群組的清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c71f2-194">要指派給使用者的電話號碼已取得或移植至 Microsoft, 且可在租使用者入口網站使用。</span><span class="sxs-lookup"><span data-stu-id="c71f2-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="c71f2-195">[通訊點數](what-are-communications-credits.md)(視需要) 已針對您的組織進行設定。</span><span class="sxs-lookup"><span data-stu-id="c71f2-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c71f2-196">已識別、設定及套用支援通話方案案例的租使用者原則和撥號方案設定。</span><span class="sxs-lookup"><span data-stu-id="c71f2-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c71f2-197">已確認及設定通話方案規範需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c71f2-198">**在範圍中針對使用者和網站的直接路由測試先決條件及假設:**</span><span class="sxs-lookup"><span data-stu-id="c71f2-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c71f2-199">已完成直傳送服務的商務使用案例定義。</span><span class="sxs-lookup"><span data-stu-id="c71f2-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="c71f2-200">直接路由所需的授權可供使用且已指派。</span><span class="sxs-lookup"><span data-stu-id="c71f2-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="c71f2-201">已識別組織網站和使用者群組的清單。</span><span class="sxs-lookup"><span data-stu-id="c71f2-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c71f2-202">已[驗證的會話邊界控制器 (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、設定並與電話系統配對。</span><span class="sxs-lookup"><span data-stu-id="c71f2-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="c71f2-203">已啟用企業語音, 且已指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c71f2-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="c71f2-204">已確認、設定並指派語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="c71f2-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="c71f2-205">Microsoft 團隊已設定為 [作用中的使用者] 的首選呼叫用戶端。</span><span class="sxs-lookup"><span data-stu-id="c71f2-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="c71f2-206">已確認並設定直接路由合規性需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="c71f2-207">決策點</span><span class="sxs-lookup"><span data-stu-id="c71f2-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="c71f2-208">決定將部署哪些音訊會議功能功能 (服務決策)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c71f2-209">識別音訊會議的使用者功能需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="c71f2-210">識別音訊會議的服務設定需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="c71f2-211">決定是否要部署及設定直接路由或通話方案。</span><span class="sxs-lookup"><span data-stu-id="c71f2-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="c71f2-212">決定要部署哪些電話系統功能功能 (服務決策)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c71f2-213">識別通話方案或直接路由的使用者功能需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="c71f2-214">識別通話方案或直接路由的服務設定需求。</span><span class="sxs-lookup"><span data-stu-id="c71f2-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="c71f2-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c71f2-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="c71f2-216">開發並記錄您的測試方案方法。</span><span class="sxs-lookup"><span data-stu-id="c71f2-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="c71f2-217">為您的服務環境和使用者準備作用中的音訊會議功能。</span><span class="sxs-lookup"><span data-stu-id="c71f2-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="c71f2-218">針對通話方案或直接路由功能, 在範圍中準備您的服務環境和使用者。</span><span class="sxs-lookup"><span data-stu-id="c71f2-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="c71f2-219">針對您想要啟用的音訊會議功能執行測試驗證。</span><span class="sxs-lookup"><span data-stu-id="c71f2-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="c71f2-220">針對您想要啟用的通話方案或直接路由功能執行測試驗證。</span><span class="sxs-lookup"><span data-stu-id="c71f2-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="c71f2-221">針對任何測試失敗, 請確認您的設定正確無誤、查看社區文章, 並視需要 (如果需要的話) 引發支援案例。</span><span class="sxs-lookup"><span data-stu-id="c71f2-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="c71f2-222">如需如何在團隊中執行音訊會議測試的其他詳細指導方針, 請參閱[音訊會議的詳細測試指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="c71f2-223">如需如何在團隊中針對通話方案進行測試的其他詳細指導方針, 請參閱[電話系統的詳細測試指南](onboarding-test-plan-for-enterprises-Phone-System.md)。</span><span class="sxs-lookup"><span data-stu-id="c71f2-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
