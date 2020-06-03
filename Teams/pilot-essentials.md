---
title: 使用商務用 Skype 試用 Microsoft 團隊 |部署、採納實現
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 啟動 Microsoft 團隊試點專案的指導方針，以探索所有團隊都能在您繼續使用商務用 Skype 時提供您的組織。
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
ms.openlocfilehash: 0849c2aae273953e7cb67b95f32cf30f4e17297f
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522686"
---
# <a name="conduct-a-user-pilot"></a><span data-ttu-id="72082-103">舉辦使用者試驗</span><span class="sxs-lookup"><span data-stu-id="72082-103">Conduct a user pilot</span></span>

<span data-ttu-id="72082-104">![升級歷程圖表，醒目提示部署與實現](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="72082-104">![Upgrade journey diagram, highlighting Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="72082-105">本文是您升級歷程的部署與實施階段的一部分，並分享深入的執行試驗。</span><span class="sxs-lookup"><span data-stu-id="72082-105">This article is part of Deployment and Implementation stage of your upgrade journey, and shares insights for running an effective pilot.</span></span> <span data-ttu-id="72082-106">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="72082-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="72082-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="72082-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="72082-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="72082-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="72082-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="72082-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="72082-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="72082-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="72082-111">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="72082-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="72082-112">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="72082-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="72082-113">透過部署新技術，您的組織可以實現成本節約、安全性合規性、員工滿意度及運作效率等業務價值，但也會影響使用者的生產力與組織基礎結構（您的網路）。</span><span class="sxs-lookup"><span data-stu-id="72082-113">By deploying new technologies, your organization can realize business value such as cost savings, security compliance, employee satisfaction, and operational efficiencies, but it can also affect your users' productivity and organizational infrastructure (your network).</span></span> <span data-ttu-id="72082-114">在您的整個組織啟用新技術之前，請先執行正式的使用者試驗。</span><span class="sxs-lookup"><span data-stu-id="72082-114">Before enabling new technology across your organization, conduct a formal user pilot.</span></span> <span data-ttu-id="72082-115">就像您在繪製整個聊天室前，在牆上繪製小的色彩片一樣，您可以執行試驗來驗證技術與使用者的準備情況、找出並減少問題，並協助確保整個組織範圍的實施順利完成。</span><span class="sxs-lookup"><span data-stu-id="72082-115">Just like you'd paint a small patch of color on a wall before painting the whole room, you'd test a broad rollout on a smaller scale by conducting a pilot to validate technical and user readiness, identify and mitigate issues, and help ensure a successful organization-wide implementation.</span></span>

<span data-ttu-id="72082-116">若要達到最實際的結果，試驗應涉及實際的使用者、模仿其溝通與共同作業的方式，以及驗證技術與使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="72082-116">To achieve the most realistic results, the pilot should involve actual users, mimic how they communicate and collaborate, and verify both technical and user experiences.</span></span> <span data-ttu-id="72082-117">無論您的組織是考慮並排執行商務用 Skype 和團隊、日後升級至小組，或是部署通話或會議等新功能，試驗都能協助您為貴組織找出正確的路徑。</span><span class="sxs-lookup"><span data-stu-id="72082-117">Whether your organization is considering running Skype for Business and Teams side by side, upgrading to Teams in the future, or deploying new functionality such a calling or conferencing, a pilot can help identify the right path forward for your organization.</span></span> <span data-ttu-id="72082-118">您有時會考慮推出的階段1，理想的試驗會利用您已開始的準備，並以目標使用者群組來實現您定義的方案。</span><span class="sxs-lookup"><span data-stu-id="72082-118">Sometimes considered Phase 1 of a rollout, the ideal pilot leverages the preparation you've already started and implements your defined plan with a targeted group of users.</span></span>

| | |
|---|---|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="72082-120">決策點</span><span class="sxs-lookup"><span data-stu-id="72082-120">Decision point</span></span>|<ul><li><span data-ttu-id="72082-121">您要如何使用試驗來通知專案方向？</span><span class="sxs-lookup"><span data-stu-id="72082-121">How will you use a pilot to inform project direction?</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="72082-123">後續步驟</span><span class="sxs-lookup"><span data-stu-id="72082-123">Next step</span></span>|<ul><li><span data-ttu-id="72082-124">請使用以下指導方針來設計及執行您的正式試點。</span><span class="sxs-lookup"><span data-stu-id="72082-124">Use the guidance below to design and execute your formal pilot.</span></span></li></ul>|

> [!Tip]
> <span data-ttu-id="72082-125">使用範例[試驗資源](https://aka.ms/UpgradeSuccessKit)，協助您設計通訊、測試計劃及意見反應問卷。</span><span class="sxs-lookup"><span data-stu-id="72082-125">Use the sample [pilot resources](https://aka.ms/UpgradeSuccessKit) to help design your communications, test plan, and feedback survey.</span></span>

## <a name="1-outline-pilot-logistics"></a><span data-ttu-id="72082-126">1. 大綱試驗物流</span><span class="sxs-lookup"><span data-stu-id="72082-126">1. Outline pilot logistics</span></span>

<span data-ttu-id="72082-127">成功的試驗已定義開始和結束日期，以及[明確定義](upgrade-define-project-scope.md#project-goals)的評估成功目標。</span><span class="sxs-lookup"><span data-stu-id="72082-127">A successful pilot has defined start and end dates, and [clearly defined goals](upgrade-define-project-scope.md#project-goals) for measuring success.</span></span> <span data-ttu-id="72082-128">這些目標應該與您更多專案的範圍相符，就像您在[定義專案範圍](upgrade-define-project-scope.md)時所記錄的一樣，並將用來在您的試驗結束後通知您的路徑。</span><span class="sxs-lookup"><span data-stu-id="72082-128">These goals should align with the scope of your broader project, as you documented when you [defined your project scope](upgrade-define-project-scope.md), and will be used to inform your path forward after your pilot is over.</span></span> <span data-ttu-id="72082-129">您也應該確定您已在專案工期中包含正確的專案關係人。</span><span class="sxs-lookup"><span data-stu-id="72082-129">You should also ensure that you've included the right stakeholders for the duration of the project.</span></span> <span data-ttu-id="72082-130">您可能會想要允許足夠的時間執行試驗並評估其影響：我們建議您至少30天。</span><span class="sxs-lookup"><span data-stu-id="72082-130">You'll want to be sure to allow enough time to run the pilot and assess its impact: we recommend a minimum of 30 days.</span></span>

<span data-ttu-id="72082-131">開始小型，並視需要新增至您的試驗（無論是加入工作負載或功能或其他使用者），讓您在進行反覆運算時評估結果並調整您的試執行時間。</span><span class="sxs-lookup"><span data-stu-id="72082-131">Start small, and add to your pilot as appropriate—whether by adding workloads or features, or additional users—making time to assess results and adjust your pilot as you iterate.</span></span> <span data-ttu-id="72082-132">您甚至可以選擇執行後續的試點，因為我們會在每個藍圖中發佈新的團隊功能。</span><span class="sxs-lookup"><span data-stu-id="72082-132">You might even opt to run subsequent pilots as new Teams features are released per the roadmap.</span></span>

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a><span data-ttu-id="72082-133">2. 選取您的試點參與者和測試案例</span><span class="sxs-lookup"><span data-stu-id="72082-133">2. Select your pilot participants and test scenarios</span></span>

<span data-ttu-id="72082-134">最重要的試驗規劃工作之一是精心的參與者選擇。</span><span class="sxs-lookup"><span data-stu-id="72082-134">One of the most important tasks of pilot planning is thoughtful participant selection.</span></span> <span data-ttu-id="72082-135">請記住，小組已針對團隊合作進行優化，因此請務必自行根據角色或角色選取試驗參與者，但也要根據其專案和小組工作來進行。</span><span class="sxs-lookup"><span data-stu-id="72082-135">Remember that Teams is optimized for teamwork, so be sure to select pilot participants not solely based on roles or personas but also based on their project and cross-team work.</span></span> <span data-ttu-id="72082-136">最適合開始的地方是向您的風險承擔者和部門經理要求您可以在小組中驗證的真實專案。</span><span class="sxs-lookup"><span data-stu-id="72082-136">A great place to start is asking your stakeholders and department managers for real projects that you can validate in Teams.</span></span> <span data-ttu-id="72082-137">角色式專案的範例可能是將團隊與您的銷售組織搭配使用，以確保欄位代表能輕鬆存取他們所需的資源，並與其他欄位成員共用見解。</span><span class="sxs-lookup"><span data-stu-id="72082-137">An example of a role-based project might be to use Teams with your sales organization to ensure that field reps can easily access the resources they need and share insights with other field members.</span></span> <span data-ttu-id="72082-138">以專案為基礎的工作範例，就是將產品啟動活動與行銷、訓練、公用關係及活動規劃小組協調。</span><span class="sxs-lookup"><span data-stu-id="72082-138">An example of project-based work might be coordinating a product launch event with the marketing, training, public relations, and event planning teams.</span></span> <span data-ttu-id="72082-139">無論您所選的是哪一種情況，試驗都應該延伸至 IT 中的主要人員、訓練及您的支援人員，讓您可以在充分優化專案管理資源的同時，全面驗證方案。</span><span class="sxs-lookup"><span data-stu-id="72082-139">Whichever scenarios you select, the pilot should extend to key people in IT, training, and your helpdesk, so you can thoroughly validate the solution while fully optimizing project management resources.</span></span>

> [!Tip]
> <span data-ttu-id="72082-140">選取您的小組試點群組參與者時，請務必包含商務用 Skype 的最上層使用者。</span><span class="sxs-lookup"><span data-stu-id="72082-140">When selecting your Teams pilot group participants, be sure to include top users of Skype for Business.</span></span> <span data-ttu-id="72082-141">請諮詢這些使用者，瞭解他們目前如何使用商務用 Skype，然後組建一個測試方案，以確認團隊能滿足其目前的需求。</span><span class="sxs-lookup"><span data-stu-id="72082-141">Check with those users to understand how they use Skype for Business today, then build out a test plan to verify that Teams can meet their current needs.</span></span>

## <a name="3-design-your-test-plan-and-feedback-survey"></a><span data-ttu-id="72082-142">3. 設計您的測試方案與意見反應問卷</span><span class="sxs-lookup"><span data-stu-id="72082-142">3. Design your test plan and feedback survey</span></span>

<span data-ttu-id="72082-143">若要取得成功的試驗體驗，請為參與者提供明確定義的工作，並將其與他們分享意見反應的方式共同作業。</span><span class="sxs-lookup"><span data-stu-id="72082-143">For a successful pilot experience, give your participants clearly defined tasks to complete along with a way for them to share their feedback.</span></span> <span data-ttu-id="72082-144">將任務組成群組，為您的使用者提供真實世界的案例，示範其日常活動的關聯性。</span><span class="sxs-lookup"><span data-stu-id="72082-144">Group tasks together to offer real-world scenarios to your users, demonstrating relevancy to their daily activities.</span></span> <span data-ttu-id="72082-145">讓您在[評估組織變更準備](https://aka.ms/OrgReadiness)指南中定義的使用案例，瞭解您的測試方案。</span><span class="sxs-lookup"><span data-stu-id="72082-145">Let the use cases you defined in [Assess organizational change readiness](https://aka.ms/OrgReadiness) guide your test plan.</span></span>

<span data-ttu-id="72082-146">貴組織可以選擇一次試驗所有功能，或使用逐步式方法，例如，先進行先導共同作業，然後再進行聊天與通話。</span><span class="sxs-lookup"><span data-stu-id="72082-146">Your organization might choose to pilot all functionality at once, or use a gradual approach—for example, pilot collaboration first, then meetings, then chat and calling.</span></span> <span data-ttu-id="72082-147">確定您有已開啟的意見反應頻道，以追蹤進度及測量結果。</span><span class="sxs-lookup"><span data-stu-id="72082-147">Ensure that you have an open feedback channel to track progress and measure outcomes.</span></span> <span data-ttu-id="72082-148">使用預先定義的問卷來輕鬆捕獲和評估試點結果;問卷設計應根據測試方案中的案例和功能而定。</span><span class="sxs-lookup"><span data-stu-id="72082-148">Use a predefined survey as an easy way to capture and assess pilot results; the survey design should be based on the scenarios and features in your test plan.</span></span>

## <a name="4-create-your-communications-plan"></a><span data-ttu-id="72082-149">4. 建立通訊方案</span><span class="sxs-lookup"><span data-stu-id="72082-149">4. Create your communications plan</span></span>

<span data-ttu-id="72082-150">您對試驗的成功至關重要，那就是您可以讓試點參與者掌握所發生的問題、時間和原因，以及它們的預期。</span><span class="sxs-lookup"><span data-stu-id="72082-150">It's crucial to the success of your pilot that you educate pilot participants on what's happening, when, and why, and what's expected of them.</span></span> <span data-ttu-id="72082-151">若要推動感興趣和最大的參與，請務必包含使用者價值訊息，以及使用者在逐步完成試驗時可取得其他資訊的訓練與支援的連結。</span><span class="sxs-lookup"><span data-stu-id="72082-151">To drive excitement and maximum participation, be sure to include user value messaging in addition to links to training and support where users can get additional information as they progress through the pilot.</span></span> <span data-ttu-id="72082-152">以下是一些可讓您開始使用試驗通訊方案的範例資源：</span><span class="sxs-lookup"><span data-stu-id="72082-152">Here are a few sample resources to get you started with your pilot communications plan:</span></span>

- <span data-ttu-id="72082-153">[試驗資源](https://aka.ms/UpgradeSuccessKit)，包括電子郵件範本和樣本意見問卷調查問題</span><span class="sxs-lookup"><span data-stu-id="72082-153">[Pilot resources](https://aka.ms/UpgradeSuccessKit), including email templates and sample feedback survey questions</span></span>
- <span data-ttu-id="72082-154">[從商務用 Skype 切換至 [小組](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)]，這是一種快速入門手冊，可協助商務用 skype 使用者開始使用團隊</span><span class="sxs-lookup"><span data-stu-id="72082-154">[Switch to Teams from Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), a quick-start guide designed to help Skype for Business users get started with Teams</span></span>

## <a name="5-conduct-your-pilot"></a><span data-ttu-id="72082-155">5. 進行試驗</span><span class="sxs-lookup"><span data-stu-id="72082-155">5. Conduct your pilot</span></span>

<span data-ttu-id="72082-156">完成所有物流之後，您就可以開始進行試驗了。</span><span class="sxs-lookup"><span data-stu-id="72082-156">With all the logistics in place, you're now ready to begin your pilot.</span></span> <span data-ttu-id="72082-157">您的試驗包括與您的使用者進行通訊、監控您的網路與使用狀況，以確保您的網路效能和通話品質保持正常、收集參與者的意見反應，以及回顧與團隊相關的問題。</span><span class="sxs-lookup"><span data-stu-id="72082-157">Conducting your pilot includes communicating with your users, monitoring your network and usage to ensure your network performance and call quality remain healthy, gathering feedback from participants, and reviewing helpdesk tickets for questions related to Teams.</span></span>

### <a name="tips-for-pilot-success"></a><span data-ttu-id="72082-158">試驗成功的秘訣</span><span class="sxs-lookup"><span data-stu-id="72082-158">Tips for pilot success</span></span>

<span data-ttu-id="72082-159">下列秘訣可協助確保您的試驗成功：</span><span class="sxs-lookup"><span data-stu-id="72082-159">The following tips can help ensure the success of your pilot:</span></span>

- <span data-ttu-id="72082-160">開始試用之前，請確認所有試點參與者都已啟用適當的 [共存模式]</span><span class="sxs-lookup"><span data-stu-id="72082-160">Before beginning your pilot, confirm that all pilot participants are enabled for the appropriate [coexistence mode]</span></span>
- <span data-ttu-id="72082-161">（ https://aka.ms/SkypeToTeams-SetCoexistence) 您想要驗證。</span><span class="sxs-lookup"><span data-stu-id="72082-161">(https://aka.ms/SkypeToTeams-SetCoexistence) you want to validate.</span></span>
- <span data-ttu-id="72082-162">每週，在整個試驗期間，與您的專案干係人見面，以查看使用者的意見反應、使用方式資料、網路資料和技術支援人員，以確保您的試點程式順暢運作。</span><span class="sxs-lookup"><span data-stu-id="72082-162">Weekly, throughout your pilot, meet with your project stakeholders to review user feedback, usage data, network data, and helpdesk tickets to ensure your pilot is running smoothly.</span></span> <span data-ttu-id="72082-163">視需要進行調整。</span><span class="sxs-lookup"><span data-stu-id="72082-163">Make any adjustments as needed.</span></span>

### <a name="suggested-timeline"></a><span data-ttu-id="72082-164">建議的時程表</span><span class="sxs-lookup"><span data-stu-id="72082-164">Suggested timeline</span></span>

<span data-ttu-id="72082-165">以下是30天試用版的建議時程表：</span><span class="sxs-lookup"><span data-stu-id="72082-165">Here's a suggested timeline for a 30-day pilot:</span></span>

- <span data-ttu-id="72082-166">試生產動員前的一周：傳送初始通訊至試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="72082-166">One week before the pilot kickoff: Send initial communication to pilot users.</span></span>
- <span data-ttu-id="72082-167">第1天：將動員會通訊傳送給試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="72082-167">Day 1: Send kickoff communication to pilot users.</span></span>
- <span data-ttu-id="72082-168">第7天：保留第一周的專案小組檢查點會議。</span><span class="sxs-lookup"><span data-stu-id="72082-168">Day 7: Hold the first weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="72082-169">第14天：傳送中間點溝通給您的試驗使用者，請按住每週專案小組檢查點會議。</span><span class="sxs-lookup"><span data-stu-id="72082-169">Day 14: Send mid-point communication to your pilot users, hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="72082-170">第21天：保留每週專案小組檢查點會議。</span><span class="sxs-lookup"><span data-stu-id="72082-170">Day 21: Hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="72082-171">第30天：傳送最終的通訊給您的試驗使用者。</span><span class="sxs-lookup"><span data-stu-id="72082-171">Day 30: Send final communication to your pilot users.</span></span>
- <span data-ttu-id="72082-172">Days 31 至45：評估試運行結果，並規劃後續步驟。</span><span class="sxs-lookup"><span data-stu-id="72082-172">Days 31–45: Assess pilot results, and plan for next steps.</span></span>

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a><span data-ttu-id="72082-173">6. 評估學習專案並評估您的轉寄方案</span><span class="sxs-lookup"><span data-stu-id="72082-173">6. Assess learnings and evaluate your go-forward plan</span></span>

<span data-ttu-id="72082-174">完成試驗之後，就可以收集所有意見反應問卷、最終的網路統計資料，以及針對您的目標進行分析的支援入場券，判斷是否要實施您的轉寄方案。</span><span class="sxs-lookup"><span data-stu-id="72082-174">After your pilot is complete, it's time to gather all feedback surveys, final network stats, and support tickets for analysis against your goals and determine whether you'll implement your go-forward plan.</span></span> <span data-ttu-id="72082-175">您可能會發現貴組織已準備好進行廣泛的部署，或者您想要將您的試驗延伸到更多使用者，或者您想要在您發現的任何問題遭到緩解之後，日後再重新查看試用版。</span><span class="sxs-lookup"><span data-stu-id="72082-175">You might find that your organization is ready for a broad deployment, or you want to extend your pilot to more users, or you want to revisit the pilot at a later date after any concerns you've identified have been mitigated.</span></span> <span data-ttu-id="72082-176">請記住，您的試驗是在_可控_環境中預測技術與使用者結果的絕佳方式。小心地提前跳躍了。</span><span class="sxs-lookup"><span data-stu-id="72082-176">Remember that your pilot is a great way to predict technical and user outcomes in a _controlled_ environment; be thoughtful about jumping ahead too quickly.</span></span>

<span data-ttu-id="72082-177">如果您的結果指出：</span><span class="sxs-lookup"><span data-stu-id="72082-177">If your results indicate:</span></span>

- <span data-ttu-id="72082-178">**您的試驗目標（例如，使用者滿意度和網路品質）** 已經完成，您應該準備好繼續進行下一階段的推出。</span><span class="sxs-lookup"><span data-stu-id="72082-178">**Your pilot goals (for example, user satisfaction and network quality) have been achieved**, you should be ready to proceed with the next phase of your rollout.</span></span> <span data-ttu-id="72082-179">根據專案的目標，這可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="72082-179">Depending on the goals of your project, this could be one of the following:</span></span>
  - <span data-ttu-id="72082-180">將試生產延伸至其他參與者</span><span class="sxs-lookup"><span data-stu-id="72082-180">Extending the pilot to additional participants</span></span>
  - [<span data-ttu-id="72082-181">針對部分或所有組織啟用團隊與商務用 Skype （**孤島**模式）</span><span class="sxs-lookup"><span data-stu-id="72082-181">Enabling Teams alongside Skype for Business (**Islands** mode) for some or all of your organization</span></span>](https://aka.ms/SkypeToTeams-SetCoexistence)
  - [<span data-ttu-id="72082-182">從商務用 Skype 將使用者升級至小組（**僅限團隊**模式），適用于部分或所有組織</span><span class="sxs-lookup"><span data-stu-id="72082-182">Upgrading users from Skype for Business to Teams (**Teams only** mode) for some or all of your organization</span></span>](https://aka.ms/SkypeToTeams-SetCoexistence)
- <span data-ttu-id="72082-183">**您的試用版並未達到您想要的結果（例如，使用者滿意度和網路品質）**，請花一些時間來調整方案的適當調整，並重新取得您的試用版。</span><span class="sxs-lookup"><span data-stu-id="72082-183">**Your pilot didn't achieve the outcomes you wanted (for example, user satisfaction and network quality)**, take time to make the appropriate adjustments to your plan and revisit your pilot.</span></span>

> [!Tip]
> <span data-ttu-id="72082-184">登記您的試點參與者作為對等擁護者，協助 evangelize 及將新使用者新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="72082-184">Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams.</span></span> <span data-ttu-id="72082-185">對等擁護者可以輕鬆與其他使用者、共用自己的體驗與學習專案，以及為其同事提供支援與指導方針。</span><span class="sxs-lookup"><span data-stu-id="72082-185">Peer champions can easily relate to other users, sharing their own experiences and learnings, and offering support and guidance to their colleagues.</span></span> <span data-ttu-id="72082-186">深入瞭解[擁護](https://go.microsoft.com/fwlink/?linkid=859068)程式，以及如何在您自己的推出中使用它們。</span><span class="sxs-lookup"><span data-stu-id="72082-186">Learn more about [champions](https://go.microsoft.com/fwlink/?linkid=859068) and how you might use them within your own rollout.</span></span>
