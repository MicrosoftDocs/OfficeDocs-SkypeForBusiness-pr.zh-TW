---
title: 虛擬就診的 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: 使用 Microsoft Teams 設定您的虛擬就診系統
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705247"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="4cced-103">使用 Teams 虛擬就診 - 整合至 EHR</span><span class="sxs-lookup"><span data-stu-id="4cced-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="4cced-104">Microsoft TeamsEHR (EHR) 連接器的電子健康記錄功能，讓臨床醫師可以直接從 EHR 系統啟動虛擬病患Teams或諮詢其他提供者。</span><span class="sxs-lookup"><span data-stu-id="4cced-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="4cced-105">Microsoft Teams 建立在 Microsoft 365 雲端上，可在支援符合 HIPAA、HITECH 認證等法規的單一中樞中，使用聊天、影片、語音和醫療保健工具進行簡單、安全的共同作業和通訊。</span><span class="sxs-lookup"><span data-stu-id="4cced-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="4cced-106">Teams 的通訊和共同作業平台讓臨床醫生能輕鬆消除零碎系統的雜亂，可以將時間花費在提供最佳的照護上。</span><span class="sxs-lookup"><span data-stu-id="4cced-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="4cced-107">Microsoft TeamsEHR (電子健康) 連接器可以：</span><span class="sxs-lookup"><span data-stu-id="4cced-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="4cced-108">從Teams EHR 系統，以整合的臨床工作流程啟動虛擬訪問。</span><span class="sxs-lookup"><span data-stu-id="4cced-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="4cced-109">讓病患從Teams入口網站加入虛擬訪問。</span><span class="sxs-lookup"><span data-stu-id="4cced-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="4cced-110">將中繼資料寫回 EHR 系統，Teams出席者連接和中斷連接時進行虛擬訪問記錄，並啟用自動稽核和記錄保留功能。</span><span class="sxs-lookup"><span data-stu-id="4cced-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="4cced-111">觀看如何從 EHR 入口網站管理虛擬就診的影片。</span><span class="sxs-lookup"><span data-stu-id="4cced-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="4cced-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="4cced-112">Before you begin</span></span>

<span data-ttu-id="4cced-113">您需要確定您具有下列先決條件，才能整合 EHR 連接器：</span><span class="sxs-lookup"><span data-stu-id="4cced-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="4cced-114">在 [Epic 的 App Orchard 市集](https://apporchard.epic.com/Gallery?id=6153)中存取以使用 Microsoft Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4cced-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="4cced-115">適用于醫療保健的 Microsoft Cloud 使用中訂閱或Microsoft Teams EHR 連接器獨立版方案 (僅在生產測試期間強制執行) 。</span><span class="sxs-lookup"><span data-stu-id="4cced-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="4cced-116">使用者必須擁有包含 Microsoft Teams 會議的適當 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="4cced-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="4cced-117">Microsoft Teams 應該採用並用於組織內部。</span><span class="sxs-lookup"><span data-stu-id="4cced-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="4cced-118">組織必須有 Epic 2018 年 11 月版本或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4cced-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="4cced-119">您的系統必須符合所有[軟體與瀏覽器必要條件](../../hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="4cced-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="4cced-120">您也需要貴組織中下列人員的資訊：</span><span class="sxs-lookup"><span data-stu-id="4cced-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="4cced-121">Microsoft 365 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4cced-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="4cced-122">Epic 客戶分析師</span><span class="sxs-lookup"><span data-stu-id="4cced-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="4cced-123">請與您的 Epic 技術專家檢視 [Epic-Microsoft Teams 遠距健康整合指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。</span><span class="sxs-lookup"><span data-stu-id="4cced-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="4cced-124">確定所有先決條件都已完成。</span><span class="sxs-lookup"><span data-stu-id="4cced-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="4cced-125">連接器設定</span><span class="sxs-lookup"><span data-stu-id="4cced-125">Connector setup</span></span>

<span data-ttu-id="4cced-126">連接器設定需要您：</span><span class="sxs-lookup"><span data-stu-id="4cced-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="4cced-127">啟動 EHR 連接器組式入口網站</span><span class="sxs-lookup"><span data-stu-id="4cced-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="4cced-128">組態資訊</span><span class="sxs-lookup"><span data-stu-id="4cced-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="4cced-129">核准或檢視組態</span><span class="sxs-lookup"><span data-stu-id="4cced-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="4cced-130">檢閱並完成組態</span><span class="sxs-lookup"><span data-stu-id="4cced-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="4cced-131">啟動 EHR 連接器組式入口網站</span><span class="sxs-lookup"><span data-stu-id="4cced-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="4cced-132">啟動 EHR 連接器組Microsoft Teams開始將醫療保健組織配置為使用虛擬Microsoft Teams啟動虛擬訪問。</span><span class="sxs-lookup"><span data-stu-id="4cced-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="4cced-133">您可以設定單一或多個組織來測試整合。</span><span class="sxs-lookup"><span data-stu-id="4cced-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="4cced-134">在組態入口網站中設定測試與生產 URL。</span><span class="sxs-lookup"><span data-stu-id="4cced-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="4cced-135">在移至生產環境之前，先從 Epic 的測試環境測試整合。</span><span class="sxs-lookup"><span data-stu-id="4cced-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="4cced-136">EHR 連接器組態 URL：[https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4cced-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="4cced-137">貴組織的 Microsoft 365 系統管理員和 Epic 客戶分析師必須完成組態入口網站的資訊和整合步驟。</span><span class="sxs-lookup"><span data-stu-id="4cced-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="4cced-138">如需 Epic 組態步驟，請連絡指派給貴組織的 Epic 技術專家資源。</span><span class="sxs-lookup"><span data-stu-id="4cced-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="4cced-139">組態資訊</span><span class="sxs-lookup"><span data-stu-id="4cced-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="4cced-140">此步驟由 **Microsoft 365 系統管理員** 完成。</span><span class="sxs-lookup"><span data-stu-id="4cced-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="4cced-141">Microsoft 365 系統管理員必須啟動連接器組態入口網站，並且使用 Microsoft 認證來登入，才能開始組態程序。</span><span class="sxs-lookup"><span data-stu-id="4cced-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="4cced-142">若要完成此步驟，Microsoft 365 系統管理員必須收到 Epic 技術專家的有效快速健康照護互通資源 (FHIR) 基底 URL，以及將核准組態的 Epic 客戶分析師使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="4cced-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="4cced-143">Microsoft 365 系統管理員必須啟動連接器組態頁面，並且使用 Microsoft 認證來登入，才能開始組態程序。</span><span class="sxs-lookup"><span data-stu-id="4cced-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="4cced-144">FHIR 基底 URL 是一個靜態位址，對應到您的伺服器 FHIR API 端點。</span><span class="sxs-lookup"><span data-stu-id="4cced-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="4cced-145">範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。</span><span class="sxs-lookup"><span data-stu-id="4cced-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="4cced-146">組態核准者名稱是 Epic 客戶分析師的名稱，負責在下一個步驟中核准組態。</span><span class="sxs-lookup"><span data-stu-id="4cced-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="4cced-147">Epic 客戶分析師是貴組織中具有 Epic 登入存取權的人員。</span><span class="sxs-lookup"><span data-stu-id="4cced-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![從 EHR 連接器中的清單選取組態核准者的名稱。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="4cced-149">核准或檢視組態</span><span class="sxs-lookup"><span data-stu-id="4cced-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="4cced-150">已新增為核准者之醫療保健組織的重要客戶分析師現在必須使用上一個步驟中的相同 EHR 連接器 URL，才能使用其 Microsoft 365 認證進行登錄。</span><span class="sxs-lookup"><span data-stu-id="4cced-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="4cced-151">成功驗證之後，系統會要求核准者使用他們的 Epic 認證來驗證 Epic 組織。</span><span class="sxs-lookup"><span data-stu-id="4cced-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="4cced-152">貴組織的 Microsoft 365 系統管理員和 Epic 客戶分析師可以是相同的人員。</span><span class="sxs-lookup"><span data-stu-id="4cced-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="4cced-153">在這種情況下，將您自己的使用者名稱新增為核准者。</span><span class="sxs-lookup"><span data-stu-id="4cced-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="4cced-154">您仍然需要登入 Epic 以驗證您的存取權。</span><span class="sxs-lookup"><span data-stu-id="4cced-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="4cced-155">Epic 登入僅用於驗證您的 FHIR 基底 URL。</span><span class="sxs-lookup"><span data-stu-id="4cced-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="4cced-156">Microsoft 不會透過這個登入來儲存認證或存取 EHR 資料。</span><span class="sxs-lookup"><span data-stu-id="4cced-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![驗證並核准認證組態。](../../media/approve-view-configuration.png)

<span data-ttu-id="4cced-158">成功進行 Epic 登入之後，Epic 客戶分析師 **必須** 核准組態。</span><span class="sxs-lookup"><span data-stu-id="4cced-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="4cced-159">如果組態不正確，Microsoft 365 系統管理員可以再次登入 Microsoft EHR 連接器入口網站來修改原始組態。</span><span class="sxs-lookup"><span data-stu-id="4cced-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![確認已設定 EHR 連接器，並且可以選擇變更組態。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="4cced-161">檢閱並完成組態</span><span class="sxs-lookup"><span data-stu-id="4cced-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="4cced-162">當 Epic 系統管理員核准組態資訊時，將會顯示病患和提供者啟動的整合記錄。</span><span class="sxs-lookup"><span data-stu-id="4cced-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="4cced-163">這些記錄是完成 Epic 中虛擬就診組態的必要項目。</span><span class="sxs-lookup"><span data-stu-id="4cced-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="4cced-164">請參閱 Epic-Microsoft Teams 遠距健康整合指南以了解更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4cced-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="4cced-165">Microsoft 365 或 Epic 客戶分析師隨時都可以登入組態入口網站，視需要檢視整合記錄並修改組織組態。</span><span class="sxs-lookup"><span data-stu-id="4cced-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![系統會顯示整合資訊。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="4cced-167">Epic 客戶分析師必須針對 Microsoft 系統管理員之前所設定的每一個 FHIR URL 完成核准程序。</span><span class="sxs-lookup"><span data-stu-id="4cced-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![組態資訊已核准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="4cced-169">啟動 Teams 虛擬就診</span><span class="sxs-lookup"><span data-stu-id="4cced-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="4cced-170">完成 EHR 連接器步驟和長篇大說之後，貴組織就可以使用 Microsoft Teams 支援視Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4cced-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="4cced-171">虛擬就診必要條件</span><span class="sxs-lookup"><span data-stu-id="4cced-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="4cced-172">您的系統必須符合所有[軟體與瀏覽器必要條件](../../hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="4cced-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="4cced-173">醫療保健組織必須已完成 Epic 組織與 Microsoft 365 組織之間的設定。</span><span class="sxs-lookup"><span data-stu-id="4cced-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="4cced-174">提供者體驗</span><span class="sxs-lookup"><span data-stu-id="4cced-174">Provider experience</span></span>

<span data-ttu-id="4cced-175">貴組織的醫療保健提供者也可以從他們的 Epic 提供者應用程式 (Hyperspace、Haiku、Canto) 加入使用 Microsoft Teams 的虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="4cced-176">**[開始虛擬就診]** 按鈕內嵌在提供者流程中。</span><span class="sxs-lookup"><span data-stu-id="4cced-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="4cced-177">提供者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="4cced-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="4cced-178">提供者可以使用支援的瀏覽器或 Microsoft Teams 應用程式加入虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="4cced-179">提供者第一次加入虛擬就診時，必須使用其 Microsoft 365 帳戶進行一次性登入。</span><span class="sxs-lookup"><span data-stu-id="4cced-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="4cced-p114">一次性登入之後，提供者將直接進入 Microsoft Teams 中的虛擬約會。(提供者必須已登入 Microsoft Teams)。</span><span class="sxs-lookup"><span data-stu-id="4cced-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="4cced-182">提供者可以看到指定約會的參與者連線和中斷連線即時更新。</span><span class="sxs-lookup"><span data-stu-id="4cced-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="4cced-183">提供者可以看到病患何時連線到虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![與病患進行虛擬就診的提供者體驗](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="4cced-185">病患體驗</span><span class="sxs-lookup"><span data-stu-id="4cced-185">Patient experience</span></span>

<span data-ttu-id="4cced-186">連接器可支援透過 MyChart Web 與行動版加入虛擬就診的病患。</span><span class="sxs-lookup"><span data-stu-id="4cced-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="4cced-187">在預約時，病患可以使用 **[開始虛擬就診]** 按鈕，從 MyChart 開始虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="4cced-188">病患體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="4cced-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="4cced-189">病患可以從桌上型電腦與行動裝置上的新式網頁瀏覽器加入虛擬就診，而不需要安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="4cced-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="4cced-190">病患只需要按一下即可加入虛擬就診，不需要其他帳戶或登入。</span><span class="sxs-lookup"><span data-stu-id="4cced-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="4cced-191">病患不需要建立 Microsoft 帳戶或登入就可以啟動虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="4cced-192">病患將進入大廳，直到醫療保健提供者加入約會並准許他們進行虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="4cced-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="4cced-193">在加入虛擬就診之前，可以在大廳測試視訊和麥克風是否可用。</span><span class="sxs-lookup"><span data-stu-id="4cced-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![虛擬就診的病患體驗](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="4cced-195">Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商標。</span><span class="sxs-lookup"><span data-stu-id="4cced-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="4cced-196">資料隱私權和位置</span><span class="sxs-lookup"><span data-stu-id="4cced-196">Privacy and location of data</span></span>

<span data-ttu-id="4cced-197">Teams 與 EHR 系統的整合，可最佳化整合和虛擬就診流程期間所使用和儲存的資料量。</span><span class="sxs-lookup"><span data-stu-id="4cced-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="4cced-198">解決方案遵循 Teams 隱私權中概述的整體 Teams 隱私權和資料管理原則和指導方針。</span><span class="sxs-lookup"><span data-stu-id="4cced-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="4cced-199">Microsoft Teams EHR 連接器不會儲存或傳輸任何可識別個人資料，也不會從 EHR 系統傳輸任何病患或醫療保健提供者的健康記錄。</span><span class="sxs-lookup"><span data-stu-id="4cced-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="4cced-200">EHR 連接器儲存的唯一資料是 EHR 使用者的唯一識別碼，在 Teams 會議設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="4cced-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="4cced-201">EHR 使用者的唯一識別碼儲存在 [Microsoft 365 客戶資料儲存位置](/microsoft-365/enterprise/o365-data-locations)的三個地理區域其中之一。</span><span class="sxs-lookup"><span data-stu-id="4cced-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="4cced-202">會議參與者在 Teams 中輸入的所有聊天、錄音及其他資料，都是根據現有的儲存原則來儲存。</span><span class="sxs-lookup"><span data-stu-id="4cced-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="4cced-203">如果您想要深入了解 Microsoft Teams 中資料的位置，請參閱 [Teams 中資料的位置](../../location-of-data-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4cced-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cced-204">相關主題</span><span class="sxs-lookup"><span data-stu-id="4cced-204">Related topics</span></span>

[<span data-ttu-id="4cced-205">Teams虛擬訪問</span><span class="sxs-lookup"><span data-stu-id="4cced-205">Teams virtual visits</span></span>](ehr-admin-reports.md)