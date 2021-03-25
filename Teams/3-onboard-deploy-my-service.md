---
title: 部署 Microsoft Teams 雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下載網站啟用手冊以規劃 Teams 的推出，並加速及優化使用者採用、品質感知和滿意度。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112629"
---
# <a name="deploy-my-service"></a><span data-ttu-id="3383c-103">部署我的服務</span><span class="sxs-lookup"><span data-stu-id="3383c-103">Deploy my service</span></span>

<span data-ttu-id="3383c-104">本文概述正確部署雲端語音服務的需求。</span><span class="sxs-lookup"><span data-stu-id="3383c-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="3383c-105">遵循部署雲端語音服務的規範性指引，您可以確定您已成功考慮到所有需求，並交付可重複的結果。</span><span class="sxs-lookup"><span data-stu-id="3383c-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="3383c-106">Microsoft Teams 語音工作負載的網站啟用手冊</span><span class="sxs-lookup"><span data-stu-id="3383c-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="3383c-107">使用此手冊可協助貴組織成功規劃並執行 Microsoft Teams 語音功能的部署，並依據網站進行。</span><span class="sxs-lookup"><span data-stu-id="3383c-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="3383c-108">包含所有必要的活動、建議的時程表，以及每個活動對應指南的連結，本手冊涵蓋端對端指南，可協助確保為給定網站成功部署 Teams 語音，並著重于使用者重要的因素。</span><span class="sxs-lookup"><span data-stu-id="3383c-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="3383c-109">貴組織可以完成此遊戲手冊中的活動：</span><span class="sxs-lookup"><span data-stu-id="3383c-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="3383c-110">有效規劃並排程 Teams 推出。</span><span class="sxs-lookup"><span data-stu-id="3383c-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="3383c-111">加速並優化使用者採用。</span><span class="sxs-lookup"><span data-stu-id="3383c-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="3383c-112">減少支援需求，提高使用者滿意度。</span><span class="sxs-lookup"><span data-stu-id="3383c-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="3383c-113">本文和相關遊戲手冊並非用來描述服務啟用或提供撥號音至特定網站所需的每一個技術組組步驟。</span><span class="sxs-lookup"><span data-stu-id="3383c-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="3383c-114">相反地，他們會專注于建議使用者輕鬆上電的活動和工作，讓他們能透過快速且順暢的轉換，以高採用率開始耗用 Teams 語音工作負載，同時將支援需求最小化。</span><span class="sxs-lookup"><span data-stu-id="3383c-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="3383c-115">請參閱設定 Teams 語音工作負載的上線檢查清單、在[Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)中設定直接路由[](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)[、Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)核心功能、Teams 網路，以及啟用[Microsoft 365 或 Office 365](onboarding-checklist-enable-office-365.md)的技術指南。 [](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="3383c-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="3383c-116">Playbook 焦點區域</span><span class="sxs-lookup"><span data-stu-id="3383c-116">Playbook focus areas</span></span>

<span data-ttu-id="3383c-117">遊戲手冊的焦點是解決影響使用者對於 Teams 語音部署感知的因素。</span><span class="sxs-lookup"><span data-stu-id="3383c-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="3383c-118">活動和工作會分組到下列焦點區域：</span><span class="sxs-lookup"><span data-stu-id="3383c-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="3383c-119">服務就緒性驗證</span><span class="sxs-lookup"><span data-stu-id="3383c-119">Validation of service readiness</span></span>
    - <span data-ttu-id="3383c-120">音訊會議</span><span class="sxs-lookup"><span data-stu-id="3383c-120">Audio Conferencing</span></span>
    - <span data-ttu-id="3383c-121">通話方案</span><span class="sxs-lookup"><span data-stu-id="3383c-121">Calling Plans</span></span>
    - <span data-ttu-id="3383c-122">直接路由</span><span class="sxs-lookup"><span data-stu-id="3383c-122">Direct Routing</span></span>

-   <span data-ttu-id="3383c-123">使用者啟用</span><span class="sxs-lookup"><span data-stu-id="3383c-123">User enablement</span></span>

-   <span data-ttu-id="3383c-124">端點</span><span class="sxs-lookup"><span data-stu-id="3383c-124">Endpoints</span></span>

-   <span data-ttu-id="3383c-125">使用和品質</span><span class="sxs-lookup"><span data-stu-id="3383c-125">Usage and quality</span></span>

-   <span data-ttu-id="3383c-126">採用</span><span class="sxs-lookup"><span data-stu-id="3383c-126">Adoption</span></span>

<span data-ttu-id="3383c-127">Voice [和 Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) (Playbook) 是 Microsoft Excel 活頁簿。</span><span class="sxs-lookup"><span data-stu-id="3383c-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="3383c-128">這五個焦點區域都是活頁簿中的個別工作表，且每個部署任務和活動會分組到其中一個工作表上。</span><span class="sxs-lookup"><span data-stu-id="3383c-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="3383c-129">![網站啟用手冊的螢幕擷取畫面](media/deploy-my-service-image1.png "遊戲手冊的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3383c-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="3383c-130">您將針對 Teams 推出範圍中的每個網站，建立另一個遊戲手冊實例。</span><span class="sxs-lookup"><span data-stu-id="3383c-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="3383c-131">如何使用遊戲手冊</span><span class="sxs-lookup"><span data-stu-id="3383c-131">How to use the playbook</span></span>

<span data-ttu-id="3383c-132">無論位置大小與複雜度如何，啟用每個網站都需要您及早規劃工作與活動，並在實際服務推出之前、期間及之後以最佳循序執行。</span><span class="sxs-lookup"><span data-stu-id="3383c-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="3383c-133">我們建議您在規劃並執行自己的 Microsoft Teams 語音歷程時，遵循這些步驟。</span><span class="sxs-lookup"><span data-stu-id="3383c-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="3383c-134">下載 Microsoft Teams Voice ([Playbook) 啟用 Playbook。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3383c-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="3383c-135">為每個網站建立另一份遊戲手冊。</span><span class="sxs-lookup"><span data-stu-id="3383c-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="3383c-136">在 **{SiteName-Code}** 的名為 Playbook 的工作表的 Tab 上，將 **{SiteName-Code}** 取代為相關的網站名稱和/或網站代碼。</span><span class="sxs-lookup"><span data-stu-id="3383c-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="3383c-137">輸入 **網站名稱、網站代碼** 和 **計畫啟動日期**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3383c-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="3383c-138">這是一個至關重要的步驟，因為它會調整手冊中每個活動的建議期限。</span><span class="sxs-lookup"><span data-stu-id="3383c-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="3383c-139">![包含網站名稱、網站代碼和計畫啟動日期的範例](media/deploy-my-service-image2.png "包含紐約網站名稱、網站代碼 NY01 和 20-Mar-18 的計畫啟動日期的範例")</span><span class="sxs-lookup"><span data-stu-id="3383c-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="3383c-140">在流覽時程表時，檢查每個活動、採取必要動作並更新狀態。</span><span class="sxs-lookup"><span data-stu-id="3383c-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="3383c-141">狀態以圖形表示，如下所述：</span><span class="sxs-lookup"><span data-stu-id="3383c-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="3383c-142">![綠色核取方塊的圖例是或不適用 (綠色 ](media/deploy-my-service-image3.png) **) ：** 活動已經完成，或不適用於此網站，因此不需要執行其他動作。</span><span class="sxs-lookup"><span data-stu-id="3383c-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="3383c-143">![黃色驚嘆號圖例 活動尚未完成 (黃色 ](media/deploy-my-service-image4.png) <strong>) ：</strong> 活動尚未完成，且必須在排程上更新為是或否。</span><span class="sxs-lookup"><span data-stu-id="3383c-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="3383c-144">![紅色 X 的圖例， (紅色) ：活動因問題無法完成，必須帶至專案 ](media/deploy-my-service-image5.png) <strong></strong>狀態會議。</span><span class="sxs-lookup"><span data-stu-id="3383c-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="3383c-145">狀態會在每個區段內匯總，且節標題的格式會以其中一個狀態指示器的格式。</span><span class="sxs-lookup"><span data-stu-id="3383c-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="3383c-146">**每週狀態** 也會自動更新。</span><span class="sxs-lookup"><span data-stu-id="3383c-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="3383c-147">![劇本中每週狀態匯總的螢幕擷取畫面](media/deploy-my-service-image6.png "劇本中每週狀態匯總的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3383c-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="3383c-148">針對您擁有的所有位置重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="3383c-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3383c-149">某些步驟可能不適用於所有位置和網站。</span><span class="sxs-lookup"><span data-stu-id="3383c-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="3383c-150">如果特定活動與網站不相關，您必須選取 **不適用** 此活動。</span><span class="sxs-lookup"><span data-stu-id="3383c-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="3383c-151">**請勿刪除** 遊戲手冊中的任何列;如果您這麼做，狀態匯總公式將無法工作。</span><span class="sxs-lookup"><span data-stu-id="3383c-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="3383c-152">請注意可能需要超過您計畫時間的活動，例如數位移植和採購活動。</span><span class="sxs-lookup"><span data-stu-id="3383c-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="3383c-153">這些活動可能會對網站部署時程表造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="3383c-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="3383c-154">請務必每週檢查並更新活動清單和相關時程表，並出席指導性委員會會議，以確保專案關係[](./envision-steering-committee-complete-guide.md)人瞭解每個網站的狀態，以及任何可能的部署排程偏差。</span><span class="sxs-lookup"><span data-stu-id="3383c-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3383c-155">決策點</span><span class="sxs-lookup"><span data-stu-id="3383c-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="3383c-156">決定是否需要網站啟用 Playbook 才能進行部署。</span><span class="sxs-lookup"><span data-stu-id="3383c-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="3383c-157">決定誰將負責為您部署的每一個網站自訂 Microsoft Teams 的網站啟用手冊。</span><span class="sxs-lookup"><span data-stu-id="3383c-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3383c-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3383c-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="3383c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下載網站啟用手冊</a>。</span><span class="sxs-lookup"><span data-stu-id="3383c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="3383c-160">自訂第一個網站的網站啟用手冊。</span><span class="sxs-lookup"><span data-stu-id="3383c-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="3383c-161">如果需要，請針對其他網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="3383c-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->