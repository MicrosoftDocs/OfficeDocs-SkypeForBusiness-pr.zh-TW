---
title: 部署 Microsoft 團隊雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下載網站啟用行動手冊以規劃您的團隊推出, 並加速及優化使用者採納、品質與滿意度。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17b73629aa874232a449605b45f97ea10e445204
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233027"
---
# <a name="deploy-my-service"></a><span data-ttu-id="f0ea4-103">部署我的服務</span><span class="sxs-lookup"><span data-stu-id="f0ea4-103">Deploy my service</span></span>

<span data-ttu-id="f0ea4-104">本文將提供正確部署雲端語音服務的需求概覽。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="f0ea4-105">透過遵循部署雲端語音服務的規範性指導方針, 您可以確定您已成功地考慮所有需求, 並提供可重複的結果。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="f0ea4-106">Microsoft 團隊語音工作負載的 [網站啟用] 行動手冊</span><span class="sxs-lookup"><span data-stu-id="f0ea4-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="f0ea4-107">使用這項行動手冊, 協助您的組織以網站為基礎, 順利規劃並執行 Microsoft 團隊語音功能。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="f0ea4-108">包括所有必要的活動、建議的時程表, 以及每個活動的相關指南的連結, 此行動手冊會涵蓋端對端指導方針, 以協助確保針對特定網站成功的小組語音部署, 並將重點放在重要因素上給使用者。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="f0ea4-109">透過完成本行動手冊中的活動, 您的組織可以:</span><span class="sxs-lookup"><span data-stu-id="f0ea4-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="f0ea4-110">有效規劃並排程您的團隊推出。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="f0ea4-111">加速並優化使用者採用。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="f0ea4-112">減少支援需求並提高使用者滿意度。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ea4-113">本文和相關的行動手冊並不是用來描述服務啟用所需的每個技術設定步驟, 或提供撥號音給特定網站。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="f0ea4-114">相反地, 他們會將重點放在快速的使用者的活動和工作上, 並讓他們透過快速且流暢的過渡來開始使用團隊語音作業, 同時將支援需求降至最低。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="f0ea4-115">如需如何針對團隊語音設定您的環境的最佳技術指導方針, 請參閱設定[小組語音工作負載](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)的 [[直接佈線](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)]、[團隊[核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)]、[[網路]針對團隊](onboarding-checklist-configure-networking.md), 並[啟用 Office 365](onboarding-checklist-enable-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="f0ea4-116">行動手冊焦點區域</span><span class="sxs-lookup"><span data-stu-id="f0ea4-116">Playbook focus areas</span></span>

<span data-ttu-id="f0ea4-117">行動手冊的重點是解決影響使用者對小組語音部署所感覺的因素。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="f0ea4-118">活動和工作會分為下列焦點區域:</span><span class="sxs-lookup"><span data-stu-id="f0ea4-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="f0ea4-119">驗證服務準備</span><span class="sxs-lookup"><span data-stu-id="f0ea4-119">Validation of service readiness</span></span>
    - <span data-ttu-id="f0ea4-120">音訊會議</span><span class="sxs-lookup"><span data-stu-id="f0ea4-120">Audio Conferencing</span></span>
    - <span data-ttu-id="f0ea4-121">通話方案</span><span class="sxs-lookup"><span data-stu-id="f0ea4-121">Calling Plans</span></span>
    - <span data-ttu-id="f0ea4-122">直接路由</span><span class="sxs-lookup"><span data-stu-id="f0ea4-122">Direct Routing</span></span>

-   <span data-ttu-id="f0ea4-123">使用者啟用</span><span class="sxs-lookup"><span data-stu-id="f0ea4-123">User enablement</span></span>

-   <span data-ttu-id="f0ea4-124">端點</span><span class="sxs-lookup"><span data-stu-id="f0ea4-124">Endpoints</span></span>

-   <span data-ttu-id="f0ea4-125">使用量與品質</span><span class="sxs-lookup"><span data-stu-id="f0ea4-125">Usage and quality</span></span>

-   <span data-ttu-id="f0ea4-126">促進</span><span class="sxs-lookup"><span data-stu-id="f0ea4-126">Adoption</span></span>

<span data-ttu-id="f0ea4-127">[[網站啟用行動手冊] 語音 (行動手冊)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 活頁簿。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="f0ea4-128">這五個焦點區域中的每一個都是活頁簿中的個別工作表, 而每個部署工作和活動都會群組到其中一個工作表上。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="f0ea4-129">![[網站啟用行動手冊] 的螢幕擷取畫面](media/deploy-my-service-image1.png "行動手冊的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="f0ea4-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="f0ea4-130">您將針對團隊推出的範圍內的每個網站, 建立一個單獨的行動手冊實例。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="f0ea4-131">如何使用行動手冊</span><span class="sxs-lookup"><span data-stu-id="f0ea4-131">How to use the playbook</span></span>

<span data-ttu-id="f0ea4-132">無論位置為何大小和複雜度, 都能讓每個網站都能儘早規劃您的工作和活動, 並在實際的服務推出期間和之後以最佳循序執行這些作業。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="f0ea4-133">我們建議您在規劃並執行自己的 Microsoft 團隊語音時, 按照這些步驟進行。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="f0ea4-134">下載 [[網站啟用] 行動手冊 (適用于 Microsoft 團隊語音的語音 (行動手冊)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="f0ea4-135">針對每個網站分別建立 [行動手冊] 複本。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="f0ea4-136">在名為 [**行動手冊] {SiteName-code}** 的工作表索引標籤上, 將 **{sitename 程式碼}** 取代為相關的網站名稱和/或網站程式碼。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="f0ea4-137">輸入**網站名稱、網站程式碼**及**規劃的啟動日期**, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="f0ea4-138">這是一個重要的步驟, 因為它會針對行動手冊中的每個活動調整建議的截止時間。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="f0ea4-139">![包含網站名稱、網站程式碼及規劃啟動日期的範例](media/deploy-my-service-image2.png "含紐約網站名稱、網站程式碼 NY01 及規劃啟動日期為20年3月18日的範例")</span><span class="sxs-lookup"><span data-stu-id="f0ea4-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="f0ea4-140">查看每個活動、執行必要的動作, 並在您逐步完成時程表時更新狀態。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="f0ea4-141">狀態以圖形表示, 如下所述:</span><span class="sxs-lookup"><span data-stu-id="f0ea4-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="f0ea4-142">![綠色核取記號](media/deploy-my-service-image3.png)為 **[是] 或 [不適用 (綠色)]** 的圖例: 活動已完成, 或不適用於此網站, 因此不需要進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="f0ea4-143">![黃色驚嘆號](media/deploy-my-service-image4.png)的圖例<strong>該活動尚未完成 (黃色):</strong>此活動尚未完成, 且必須在排程上更新為 [是] 或 [否]。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="f0ea4-144">![紅色 X 的圖例, 代表 [](media/deploy-my-service-image5.png)否] <strong>(紅色):</strong>由於問題而無法完成活動, 且必須傳送給專案狀態會議。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="f0ea4-145">狀態是在每個區段中累計, 而節標題則是以其中一個狀態指標來設定格式。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="f0ea4-146">[**每週] 狀態**也會自動更新。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="f0ea4-147">[![行動手冊] 中每週狀態匯總的螢幕擷取畫面][(media/deploy-my-service-image6.png "行動手冊] 中每週狀態匯總的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="f0ea4-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="f0ea4-148">針對您所有的位置, 重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0ea4-149">某些步驟可能不適用於所有位置與網站。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="f0ea4-150">如果特定活動與網站無關, 您必須選取 [**不適**用於此活動]。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="f0ea4-151">**請勿刪除**[行動手冊] 中的任何資料列;如果您這樣做, 狀態匯總公式將無法運作。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="f0ea4-152">請注意, 可能會花費比您計畫更多時間的活動 (例如, 數位移植與採購活動)。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="f0ea4-153">這些活動可能會對網站部署時程表造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="f0ea4-154">請務必查看並更新活動清單及相關聯的時程表, 並在[指導委員會會議](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)中展示, 以確保專案關係人知道每個網站的狀態, 以及部署排程的任何可能的偏差。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="f0ea4-155">決策點</span><span class="sxs-lookup"><span data-stu-id="f0ea4-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="f0ea4-156">決定您的部署是否需要網站啟用行動手冊。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="f0ea4-157">針對您要部署的每個網站, 決定誰將負責為 Microsoft 團隊自訂 [網站啟用] 行動手冊。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="f0ea4-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f0ea4-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="f0ea4-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下載網站啟用行動手冊</a>。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="f0ea4-160">針對您的第一個網站自訂 [網站啟用] 行動手冊。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="f0ea4-161">視需要重複其他網站的步驟。</span><span class="sxs-lookup"><span data-stu-id="f0ea4-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->