---
title: 進行使用者試驗，評估並測試 Microsoft Teams 在貴組織中如何工作
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 啟動 Microsoft Teams 試驗指南，探索 Teams 提供貴組織的所有功能，同時您繼續使用商務用 Skype
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2d909722674f23e253d0ae937efddb14d96d7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108369"
---
# <a name="conduct-a-user-pilot"></a><span data-ttu-id="db3b0-103">舉辦使用者試驗</span><span class="sxs-lookup"><span data-stu-id="db3b0-103">Conduct a user pilot</span></span>

<span data-ttu-id="db3b0-104">![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="db3b0-104">![Upgrade journey diagram, highlighting Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="db3b0-105">本文是升級歷程的部署與執行階段的一部分，並分享執行有效試驗的深入見解。</span><span class="sxs-lookup"><span data-stu-id="db3b0-105">This article is part of Deployment and Implementation stage of your upgrade journey, and shares insights for running an effective pilot.</span></span> <span data-ttu-id="db3b0-106">繼續進行之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="db3b0-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="db3b0-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="db3b0-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="db3b0-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="db3b0-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="db3b0-109">瞭解商務用 Skype 和 Teams 的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="db3b0-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="db3b0-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="db3b0-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="db3b0-111">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="db3b0-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="db3b0-112">準備您的組織</span><span class="sxs-lookup"><span data-stu-id="db3b0-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

<span data-ttu-id="db3b0-113">部署新技術，貴組織可以發揮節省成本、安全性合規性、員工滿意度及營運效率等商業價值，但也會影響使用者的生產力和組織基礎結構 (網路) 。</span><span class="sxs-lookup"><span data-stu-id="db3b0-113">By deploying new technologies, your organization can realize business value such as cost savings, security compliance, employee satisfaction, and operational efficiencies, but it can also affect your users' productivity and organizational infrastructure (your network).</span></span> <span data-ttu-id="db3b0-114">在全組織啟用新技術之前，請進行正式的使用者試驗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-114">Before enabling new technology across your organization, conduct a formal user pilot.</span></span> <span data-ttu-id="db3b0-115">就像在繪製整個會議室之前，在牆面繪製一小片色彩一樣，您也得進行試驗，以驗證技術和使用者的整備狀態、找出並減輕問題，以及協助確保整個組織的成功實施，以在較小的範圍內測試廣泛推行。</span><span class="sxs-lookup"><span data-stu-id="db3b0-115">Just like you'd paint a small patch of color on a wall before painting the whole room, you'd test a broad rollout on a smaller scale by conducting a pilot to validate technical and user readiness, identify and mitigate issues, and help ensure a successful organization-wide implementation.</span></span>

<span data-ttu-id="db3b0-116">若要取得最實際的結果，試驗應讓實際使用者參與、模仿使用者溝通和共同合作的方式，以及驗證技術和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-116">To achieve the most realistic results, the pilot should involve actual users, mimic how they communicate and collaborate, and verify both technical and user experiences.</span></span> <span data-ttu-id="db3b0-117">無論貴組織正考慮並排進行商務用 Skype 和 Teams、日後升級至 Teams，或部署通話或會議等新功能，試驗都可以協助找出適合貴組織前進的路徑。</span><span class="sxs-lookup"><span data-stu-id="db3b0-117">Whether your organization is considering running Skype for Business and Teams side by side, upgrading to Teams in the future, or deploying new functionality such a calling or conferencing, a pilot can help identify the right path forward for your organization.</span></span> <span data-ttu-id="db3b0-118">有時被視為推出的第 1 階段，理想的試驗會運用您已開始的準備工作，並針對目標使用者群組來實施您定義的計畫。</span><span class="sxs-lookup"><span data-stu-id="db3b0-118">Sometimes considered Phase 1 of a rollout, the ideal pilot leverages the preparation you've already started and implements your defined plan with a targeted group of users.</span></span>

| | |
|---|---|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="db3b0-120">決策點</span><span class="sxs-lookup"><span data-stu-id="db3b0-120">Decision point</span></span>|<ul><li><span data-ttu-id="db3b0-121">您將如何使用試驗來告知專案方向？</span><span class="sxs-lookup"><span data-stu-id="db3b0-121">How will you use a pilot to inform project direction?</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="db3b0-123">後續步驟</span><span class="sxs-lookup"><span data-stu-id="db3b0-123">Next step</span></span>|<ul><li><span data-ttu-id="db3b0-124">請使用下列指南來設計並執行正式試驗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-124">Use the guidance below to design and execute your formal pilot.</span></span></li></ul>|

> [!Tip]
> <span data-ttu-id="db3b0-125">使用範例 [試驗資源](https://aka.ms/UpgradeSuccessKit) ，協助設計通訊、測試計劃及意見回饋問卷。</span><span class="sxs-lookup"><span data-stu-id="db3b0-125">Use the sample [pilot resources](https://aka.ms/UpgradeSuccessKit) to help design your communications, test plan, and feedback survey.</span></span>

## <a name="1-outline-pilot-logistics"></a><span data-ttu-id="db3b0-126">1. 大綱試驗物流</span><span class="sxs-lookup"><span data-stu-id="db3b0-126">1. Outline pilot logistics</span></span>

<span data-ttu-id="db3b0-127">成功的試驗已定義開始日期和結束日期，並明確 [定義衡量](upgrade-define-project-scope.md#project-goals) 成功的目標。</span><span class="sxs-lookup"><span data-stu-id="db3b0-127">A successful pilot has defined start and end dates, and [clearly defined goals](upgrade-define-project-scope.md#project-goals) for measuring success.</span></span> <span data-ttu-id="db3b0-128">如您定義專案範圍時所記載的，這些目標應該會與您更廣泛的專案範圍[](upgrade-define-project-scope.md)保持一致，並可用來在試驗結束後提供您前進的路徑。</span><span class="sxs-lookup"><span data-stu-id="db3b0-128">These goals should align with the scope of your broader project, as you documented when you [defined your project scope](upgrade-define-project-scope.md), and will be used to inform your path forward after your pilot is over.</span></span> <span data-ttu-id="db3b0-129">您也應該確保您在專案期間包含正確的專案關係人。</span><span class="sxs-lookup"><span data-stu-id="db3b0-129">You should also ensure that you've included the right stakeholders for the duration of the project.</span></span> <span data-ttu-id="db3b0-130">您務必要允許足夠的時間執行試驗並評估其影響：我們建議您至少 30 天。</span><span class="sxs-lookup"><span data-stu-id="db3b0-130">You'll want to be sure to allow enough time to run the pilot and assess its impact: we recommend a minimum of 30 days.</span></span>

<span data-ttu-id="db3b0-131">從小型開始，並在適當的時候加入您的試驗 ，無論是新增工作量或功能，還是新增其他使用者，都能夠花時間評估結果，並隨著您的試驗進行調整。</span><span class="sxs-lookup"><span data-stu-id="db3b0-131">Start small, and add to your pilot as appropriate—whether by adding workloads or features, or additional users—making time to assess results and adjust your pilot as you iterate.</span></span> <span data-ttu-id="db3b0-132">您甚至可以選擇執行後續試驗，因為新的 Teams 功能會根據藍圖發佈。</span><span class="sxs-lookup"><span data-stu-id="db3b0-132">You might even opt to run subsequent pilots as new Teams features are released per the roadmap.</span></span>

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a><span data-ttu-id="db3b0-133">2. 選取您的試驗參與者和測試案例</span><span class="sxs-lookup"><span data-stu-id="db3b0-133">2. Select your pilot participants and test scenarios</span></span>

<span data-ttu-id="db3b0-134">試驗規劃最重要的工作之一是周全的參與者選擇。</span><span class="sxs-lookup"><span data-stu-id="db3b0-134">One of the most important tasks of pilot planning is thoughtful participant selection.</span></span> <span data-ttu-id="db3b0-135">請記住，Teams 已針對團隊合作優化，因此請務必根據角色或角色，也根據他們的專案和跨小組工作來選取試驗參與者。</span><span class="sxs-lookup"><span data-stu-id="db3b0-135">Remember that Teams is optimized for teamwork, so be sure to select pilot participants not solely based on roles or personas but also based on their project and cross-team work.</span></span> <span data-ttu-id="db3b0-136">首先，請詢問專案關係人及部門主管，瞭解您可以在 Teams 中驗證的實際專案。</span><span class="sxs-lookup"><span data-stu-id="db3b0-136">A great place to start is asking your stakeholders and department managers for real projects that you can validate in Teams.</span></span> <span data-ttu-id="db3b0-137">角色型專案的範例可能是使用 Teams 與銷售組織，以確保現場代表可以輕鬆存取所需的資源，並與其他欄位成員共用深入見解。</span><span class="sxs-lookup"><span data-stu-id="db3b0-137">An example of a role-based project might be to use Teams with your sales organization to ensure that field reps can easily access the resources they need and share insights with other field members.</span></span> <span data-ttu-id="db3b0-138">專案型工作的範例可能是將產品啟動活動與行銷、訓練、公關及活動規劃小組協調。</span><span class="sxs-lookup"><span data-stu-id="db3b0-138">An example of project-based work might be coordinating a product launch event with the marketing, training, public relations, and event planning teams.</span></span> <span data-ttu-id="db3b0-139">無論您選取哪一種案例，試驗應該會延伸至 IT、訓練和技術支援中心的重要人員，因此您可以徹底驗證解決方案，同時充分優化專案管理資源。</span><span class="sxs-lookup"><span data-stu-id="db3b0-139">Whichever scenarios you select, the pilot should extend to key people in IT, training, and your helpdesk, so you can thoroughly validate the solution while fully optimizing project management resources.</span></span>

> [!Tip]
> <span data-ttu-id="db3b0-140">選取 Teams 試驗群組參與者時，請務必包含商務用 Skype 的熱門使用者。</span><span class="sxs-lookup"><span data-stu-id="db3b0-140">When selecting your Teams pilot group participants, be sure to include top users of Skype for Business.</span></span> <span data-ttu-id="db3b0-141">請與這些使用者確認他們目前如何使用商務用 Skype，然後建立測試計劃，確認 Teams 可以符合他們目前的需求。</span><span class="sxs-lookup"><span data-stu-id="db3b0-141">Check with those users to understand how they use Skype for Business today, then build out a test plan to verify that Teams can meet their current needs.</span></span>

## <a name="3-design-your-test-plan-and-feedback-survey"></a><span data-ttu-id="db3b0-142">3. 設計您的測試計劃與意見回饋問卷</span><span class="sxs-lookup"><span data-stu-id="db3b0-142">3. Design your test plan and feedback survey</span></span>

<span data-ttu-id="db3b0-143">若要獲得成功的試驗體驗，請給予參與者明確定義的工作來完成，並讓他們分享他們的意見。</span><span class="sxs-lookup"><span data-stu-id="db3b0-143">For a successful pilot experience, give your participants clearly defined tasks to complete along with a way for them to share their feedback.</span></span> <span data-ttu-id="db3b0-144">將工作分組在一起，提供實際案例給使用者，顯示其每日活動的相關性。</span><span class="sxs-lookup"><span data-stu-id="db3b0-144">Group tasks together to offer real-world scenarios to your users, demonstrating relevancy to their daily activities.</span></span> <span data-ttu-id="db3b0-145">讓您在評估組織變更準備狀況中定義的使用 [案例](./upgrade-org-change-readiness.md) 引導您的測試計劃。</span><span class="sxs-lookup"><span data-stu-id="db3b0-145">Let the use cases you defined in [Assess organizational change readiness](./upgrade-org-change-readiness.md) guide your test plan.</span></span>

<span data-ttu-id="db3b0-146">貴組織可能會選擇一次試驗所有功能，或使用漸進式方法，例如先試驗共同合作，然後再試驗會議，然後進行聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="db3b0-146">Your organization might choose to pilot all functionality at once, or use a gradual approach—for example, pilot collaboration first, then meetings, then chat and calling.</span></span> <span data-ttu-id="db3b0-147">請確保您擁有開放式的意見回饋通道，以追蹤進度並衡量結果。</span><span class="sxs-lookup"><span data-stu-id="db3b0-147">Ensure that you have an open feedback channel to track progress and measure outcomes.</span></span> <span data-ttu-id="db3b0-148">使用預先定義的問卷，輕鬆取得及評估試驗結果;問卷設計應該以測試方案中的情境和功能為基礎。</span><span class="sxs-lookup"><span data-stu-id="db3b0-148">Use a predefined survey as an easy way to capture and assess pilot results; the survey design should be based on the scenarios and features in your test plan.</span></span>

## <a name="4-create-your-communications-plan"></a><span data-ttu-id="db3b0-149">4. 建立通訊計畫</span><span class="sxs-lookup"><span data-stu-id="db3b0-149">4. Create your communications plan</span></span>

<span data-ttu-id="db3b0-150">您必須教育試驗參與者瞭解進行中的專案、時間、原因，以及預期目標，這是試驗成功的關鍵。</span><span class="sxs-lookup"><span data-stu-id="db3b0-150">It's crucial to the success of your pilot that you educate pilot participants on what's happening, when, and why, and what's expected of them.</span></span> <span data-ttu-id="db3b0-151">若要提高興奮感和最大參與度，請務必加入使用者價值訊息，以及訓練與支援的連結，讓使用者在試驗進行時取得其他資訊。</span><span class="sxs-lookup"><span data-stu-id="db3b0-151">To drive excitement and maximum participation, be sure to include user value messaging in addition to links to training and support where users can get additional information as they progress through the pilot.</span></span> <span data-ttu-id="db3b0-152">以下是一些範例資源，可引導您開始使用試驗通訊計畫：</span><span class="sxs-lookup"><span data-stu-id="db3b0-152">Here are a few sample resources to get you started with your pilot communications plan:</span></span>

- <span data-ttu-id="db3b0-153">[試驗資源](https://aka.ms/UpgradeSuccessKit)，包括電子郵件範本和範例意見回饋問卷問題</span><span class="sxs-lookup"><span data-stu-id="db3b0-153">[Pilot resources](https://aka.ms/UpgradeSuccessKit), including email templates and sample feedback survey questions</span></span>
- <span data-ttu-id="db3b0-154">[從商務用 Skype 切換到 Teams，](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)這是專為協助商務用 Skype 使用者開始使用 Teams 設計的快速入門手冊</span><span class="sxs-lookup"><span data-stu-id="db3b0-154">[Switch to Teams from Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), a quick-start guide designed to help Skype for Business users get started with Teams</span></span>

## <a name="5-conduct-your-pilot"></a><span data-ttu-id="db3b0-155">5. 進行您的試驗</span><span class="sxs-lookup"><span data-stu-id="db3b0-155">5. Conduct your pilot</span></span>

<span data-ttu-id="db3b0-156">所有物流就緒後，就可以開始試驗了。</span><span class="sxs-lookup"><span data-stu-id="db3b0-156">With all the logistics in place, you're now ready to begin your pilot.</span></span> <span data-ttu-id="db3b0-157">進行試驗包括與使用者通訊、監控您的網路和使用狀況，以確保您的網路績效和通話品質維持健康、收集參與者的意見，以及檢閱 Teams 相關問題的服務台票證。</span><span class="sxs-lookup"><span data-stu-id="db3b0-157">Conducting your pilot includes communicating with your users, monitoring your network and usage to ensure your network performance and call quality remain healthy, gathering feedback from participants, and reviewing helpdesk tickets for questions related to Teams.</span></span>

### <a name="tips-for-pilot-success"></a><span data-ttu-id="db3b0-158">試驗成功的秘訣</span><span class="sxs-lookup"><span data-stu-id="db3b0-158">Tips for pilot success</span></span>

<span data-ttu-id="db3b0-159">下列秘訣可協助確保試驗成功：</span><span class="sxs-lookup"><span data-stu-id="db3b0-159">The following tips can help ensure the success of your pilot:</span></span>

- <span data-ttu-id="db3b0-160">開始試驗之前，請確認所有試驗參與者都已啟用適當的 [共存模式]</span><span class="sxs-lookup"><span data-stu-id="db3b0-160">Before beginning your pilot, confirm that all pilot participants are enabled for the appropriate [coexistence mode]</span></span>
- <span data-ttu-id="db3b0-161"> (https://aka.ms/SkypeToTeams-SetCoexistence) 驗證。</span><span class="sxs-lookup"><span data-stu-id="db3b0-161">(https://aka.ms/SkypeToTeams-SetCoexistence) you want to validate.</span></span>
- <span data-ttu-id="db3b0-162">每週在試驗期間與專案關係人開會，以審查使用者的意見回饋、使用方式資料、網路資料和服務台票證，以確保您的試驗順利進行。</span><span class="sxs-lookup"><span data-stu-id="db3b0-162">Weekly, throughout your pilot, meet with your project stakeholders to review user feedback, usage data, network data, and helpdesk tickets to ensure your pilot is running smoothly.</span></span> <span data-ttu-id="db3b0-163">根據需要進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="db3b0-163">Make any adjustments as needed.</span></span>

### <a name="suggested-timeline"></a><span data-ttu-id="db3b0-164">建議的時程表</span><span class="sxs-lookup"><span data-stu-id="db3b0-164">Suggested timeline</span></span>

<span data-ttu-id="db3b0-165">以下是為期 30 天的試驗建議時程表：</span><span class="sxs-lookup"><span data-stu-id="db3b0-165">Here's a suggested timeline for a 30-day pilot:</span></span>

- <span data-ttu-id="db3b0-166">試驗啟動前一周：傳送初始通訊給試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="db3b0-166">One week before the pilot kickoff: Send initial communication to pilot users.</span></span>
- <span data-ttu-id="db3b0-167">第 1 天：傳送啟動通訊給試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="db3b0-167">Day 1: Send kickoff communication to pilot users.</span></span>
- <span data-ttu-id="db3b0-168">第 7 天：召開第一次每週專案小組檢查會議。</span><span class="sxs-lookup"><span data-stu-id="db3b0-168">Day 7: Hold the first weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="db3b0-169">第 14 天：傳送中間點通訊給試驗使用者，召開每週的專案小組檢查會議。</span><span class="sxs-lookup"><span data-stu-id="db3b0-169">Day 14: Send mid-point communication to your pilot users, hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="db3b0-170">第 21 天：每週召開一次專案小組檢查檢查會議。</span><span class="sxs-lookup"><span data-stu-id="db3b0-170">Day 21: Hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="db3b0-171">第 30 天：傳送最終通訊給試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="db3b0-171">Day 30: Send final communication to your pilot users.</span></span>
- <span data-ttu-id="db3b0-172">第 31 天至第 45 天：評估試驗結果，並規劃下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="db3b0-172">Days 31–45: Assess pilot results, and plan for next steps.</span></span>

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a><span data-ttu-id="db3b0-173">6. 評估學習並評估您的進一步計畫</span><span class="sxs-lookup"><span data-stu-id="db3b0-173">6. Assess learnings and evaluate your go-forward plan</span></span>

<span data-ttu-id="db3b0-174">試驗完成後，該是收集所有意見回饋問卷、最終網路統計資料，以及針對目標進行分析的支援票證，然後決定是否要執行您的進一步計畫。</span><span class="sxs-lookup"><span data-stu-id="db3b0-174">After your pilot is complete, it's time to gather all feedback surveys, final network stats, and support tickets for analysis against your goals and determine whether you'll implement your go-forward plan.</span></span> <span data-ttu-id="db3b0-175">您可能會發現貴組織已準備好進行廣泛部署，或您想要將試驗範圍擴大到更多使用者，或是在已減輕您發現的任何疑慮之後，于日後重新檢查試驗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-175">You might find that your organization is ready for a broad deployment, or you want to extend your pilot to more users, or you want to revisit the pilot at a later date after any concerns you've identified have been mitigated.</span></span> <span data-ttu-id="db3b0-176">請記住，您的試驗是預測受控制環境中技術和使用者結果 _的很好_ 方法;考慮一下跳得太快。</span><span class="sxs-lookup"><span data-stu-id="db3b0-176">Remember that your pilot is a great way to predict technical and user outcomes in a _controlled_ environment; be thoughtful about jumping ahead too quickly.</span></span>

<span data-ttu-id="db3b0-177">如果結果顯示：</span><span class="sxs-lookup"><span data-stu-id="db3b0-177">If your results indicate:</span></span>

- <span data-ttu-id="db3b0-178">**您的試驗 (** 例如使用者滿意度和網路品質) 已經達成，您應該準備好繼續進行下一階段的推出。</span><span class="sxs-lookup"><span data-stu-id="db3b0-178">**Your pilot goals (for example, user satisfaction and network quality) have been achieved**, you should be ready to proceed with the next phase of your rollout.</span></span> <span data-ttu-id="db3b0-179">根據您的專案目標，這可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="db3b0-179">Depending on the goals of your project, this could be one of the following:</span></span>
  - <span data-ttu-id="db3b0-180">將試驗延伸到其他參與者</span><span class="sxs-lookup"><span data-stu-id="db3b0-180">Extending the pilot to additional participants</span></span>
  - [<span data-ttu-id="db3b0-181">啟用 Teams 與商務用 Skype (**群島** 模式) 部分或所有組織啟用</span><span class="sxs-lookup"><span data-stu-id="db3b0-181">Enabling Teams alongside Skype for Business (**Islands** mode) for some or all of your organization</span></span>](./setting-your-coexistence-and-upgrade-settings.md)
  - [<span data-ttu-id="db3b0-182">將商務用 Skype 使用者升級 (**Teams**) 部分或所有組織使用 Teams 模式</span><span class="sxs-lookup"><span data-stu-id="db3b0-182">Upgrading users from Skype for Business to Teams (**Teams only** mode) for some or all of your organization</span></span>](./setting-your-coexistence-and-upgrade-settings.md)
- <span data-ttu-id="db3b0-183">**您的試驗沒有** 取得想要的結果，例如 (使用者滿意度和網路品質) 花一些時間調整您的計畫，然後重新檢查您的試驗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-183">**Your pilot didn't achieve the outcomes you wanted (for example, user satisfaction and network quality)**, take time to make the appropriate adjustments to your plan and revisit your pilot.</span></span>

> [!Tip]
> <span data-ttu-id="db3b0-184">將試驗參與者招募為同儕支援者，協助宣傳新使用者並加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="db3b0-184">Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams.</span></span> <span data-ttu-id="db3b0-185">同儕支援者可以輕鬆地與其他使用者聯繫、分享自己的體驗和學習，以及提供支援和指引給同事。</span><span class="sxs-lookup"><span data-stu-id="db3b0-185">Peer champions can easily relate to other users, sharing their own experiences and learnings, and offering support and guidance to their colleagues.</span></span> <span data-ttu-id="db3b0-186">深入瞭解冠軍 [，](https://go.microsoft.com/fwlink/?linkid=859068) 以及如何在您自己的推出中使用它們。</span><span class="sxs-lookup"><span data-stu-id="db3b0-186">Learn more about [champions](https://go.microsoft.com/fwlink/?linkid=859068) and how you might use them within your own rollout.</span></span>