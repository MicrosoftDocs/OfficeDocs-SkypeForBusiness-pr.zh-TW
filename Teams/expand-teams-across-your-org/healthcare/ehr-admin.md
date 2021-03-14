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
ms.reviewer: ''
description: 使用 Microsoft Teams 設定您的虛擬就診系統
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125776"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="a1b62-103">使用 Teams 虛擬就診 - 整合至 EHR</span><span class="sxs-lookup"><span data-stu-id="a1b62-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="a1b62-104">Microsoft Teams 電子健康記錄 (EHR) 連接器讓臨床醫生可以直接從 EHR 系統，在 Teams 中啟動虛擬病患就診或諮詢。</span><span class="sxs-lookup"><span data-stu-id="a1b62-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="a1b62-105">Microsoft Teams 建立在 Microsoft 365 雲端上，可在支援符合 HIPAA、HITECH 認證等法規的單一中樞中，使用聊天、影片、語音和醫療保健工具進行簡單、安全的共同作業和通訊。</span><span class="sxs-lookup"><span data-stu-id="a1b62-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="a1b62-106">Teams 的通訊和共同作業平台讓臨床醫生能輕鬆消除零碎系統的雜亂，可以將時間花費在提供最佳的照護上。</span><span class="sxs-lookup"><span data-stu-id="a1b62-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="a1b62-107">Microsoft Teams 電子健康記錄 (EHR) 連接器可以：</span><span class="sxs-lookup"><span data-stu-id="a1b62-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="a1b62-108">從提供者和病患入口網站啟動 Teams 虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="a1b62-109">在連線和中斷連線事件時寫回 EHR 中繼資料，以啟用自動稽核和記錄保留。</span><span class="sxs-lookup"><span data-stu-id="a1b62-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="a1b62-110">整合至現有的臨床醫生和病患工作流程，同時允許他們使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a1b62-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="a1b62-111">觀看如何從 EHR 入口網站管理虛擬就診的影片。</span><span class="sxs-lookup"><span data-stu-id="a1b62-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="a1b62-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="a1b62-112">Before you begin</span></span>

<span data-ttu-id="a1b62-113">您需要確定您具有下列先決條件，才能整合 EHR 連接器：</span><span class="sxs-lookup"><span data-stu-id="a1b62-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="a1b62-114">在 [Epic 的 App Orchard 市集](https://apporchard.epic.com/Gallery?id=6153)中存取以使用 Microsoft Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a1b62-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="a1b62-115">適用於醫療保健的 Microsoft Cloud 作用中訂閱或 Microsoft Teams EHR 連接器獨立供應項目訂閱 (僅在生產測試期間強制執行)。</span><span class="sxs-lookup"><span data-stu-id="a1b62-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="a1b62-116">使用者必須擁有包含 Microsoft Teams 會議的適當 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="a1b62-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="a1b62-117">Microsoft Teams 應該採用並用於組織內部。</span><span class="sxs-lookup"><span data-stu-id="a1b62-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="a1b62-118">組織必須有 Epic 2018 年 11 月版本或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a1b62-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="a1b62-119">您的系統必須符合所有[軟體與瀏覽器必要條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="a1b62-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="a1b62-120">您也需要貴組織中下列人員的資訊：</span><span class="sxs-lookup"><span data-stu-id="a1b62-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="a1b62-121">Microsoft 365 系統管理員</span><span class="sxs-lookup"><span data-stu-id="a1b62-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="a1b62-122">Epic 客戶分析師</span><span class="sxs-lookup"><span data-stu-id="a1b62-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="a1b62-123">請您的 Epic 技術專家提供 Epic-Microsoft Teams 遠距健康整合指南，以在 Epic 市集提供。</span><span class="sxs-lookup"><span data-stu-id="a1b62-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="a1b62-124">連接器設定</span><span class="sxs-lookup"><span data-stu-id="a1b62-124">Connector setup</span></span>

<span data-ttu-id="a1b62-125">連接器設定需要您：</span><span class="sxs-lookup"><span data-stu-id="a1b62-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="a1b62-126">啟動 EHR 連接器組態入口網站</span><span class="sxs-lookup"><span data-stu-id="a1b62-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="a1b62-127">組態資訊</span><span class="sxs-lookup"><span data-stu-id="a1b62-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="a1b62-128">核准或檢視組態</span><span class="sxs-lookup"><span data-stu-id="a1b62-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="a1b62-129">檢閱並完成組態</span><span class="sxs-lookup"><span data-stu-id="a1b62-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="a1b62-130">啟動 EHR 連接器組態入口網站</span><span class="sxs-lookup"><span data-stu-id="a1b62-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="a1b62-131">若要設定您的醫療保健組織使用 Microsoft Teams 來啟動虛擬就診，請從啟動 EHR 連接器組態入口網站開始。</span><span class="sxs-lookup"><span data-stu-id="a1b62-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="a1b62-132">您可以設定單一或多個組織來測試整合。</span><span class="sxs-lookup"><span data-stu-id="a1b62-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="a1b62-133">在組態入口網站中設定測試與生產 URL。</span><span class="sxs-lookup"><span data-stu-id="a1b62-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="a1b62-134">在移至生產環境之前，先從 Epic 的測試環境測試整合。</span><span class="sxs-lookup"><span data-stu-id="a1b62-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="a1b62-135">EHR 連接器組態 URL：[https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a1b62-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="a1b62-136">貴組織的 Microsoft 365 系統管理員和 Epic 客戶分析師必須完成組態入口網站的資訊和整合步驟。</span><span class="sxs-lookup"><span data-stu-id="a1b62-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="a1b62-137">如需 Epic 組態步驟，請連絡指派給貴組織的 Epic 技術專家資源。</span><span class="sxs-lookup"><span data-stu-id="a1b62-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="a1b62-138">組態資訊</span><span class="sxs-lookup"><span data-stu-id="a1b62-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="a1b62-139">此步驟由 **Microsoft 365 系統管理員** 完成。</span><span class="sxs-lookup"><span data-stu-id="a1b62-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="a1b62-140">Microsoft 365 系統管理員必須啟動連接器組態入口網站，並且使用 Microsoft 認證來登入，才能開始組態程序。</span><span class="sxs-lookup"><span data-stu-id="a1b62-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="a1b62-141">若要完成此步驟，Microsoft 365 系統管理員必須收到 Epic 技術專家的有效快速健康照護互通資源 (FHIR) 基底 URL，以及將核准組態的 Epic 客戶分析師使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="a1b62-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="a1b62-142">Microsoft 365 系統管理員必須啟動連接器組態頁面，並且使用 Microsoft 認證來登入，才能開始組態程序。</span><span class="sxs-lookup"><span data-stu-id="a1b62-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="a1b62-143">FHIR 基底 URL 是一個靜態位址，對應到您的伺服器 FHIR API 端點。</span><span class="sxs-lookup"><span data-stu-id="a1b62-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="a1b62-144">範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。</span><span class="sxs-lookup"><span data-stu-id="a1b62-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="a1b62-145">組態核准者名稱是 Epic 客戶分析師的名稱，負責在下一個步驟中核准組態。</span><span class="sxs-lookup"><span data-stu-id="a1b62-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="a1b62-146">Epic 客戶分析師是貴組織中具有 Epic 登入存取權的人員。</span><span class="sxs-lookup"><span data-stu-id="a1b62-146">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![從 EHR 連接器中的清單選取組態核准者的名稱。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="a1b62-148">核准或檢視組態</span><span class="sxs-lookup"><span data-stu-id="a1b62-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="a1b62-149">您的醫療保健組織的 Epic 客戶分析師已新增為核准者，現在必須使用上一個步驟中的相同 EHR 連接器 URL，才能使用其 Microsoft 365 認證來登入。</span><span class="sxs-lookup"><span data-stu-id="a1b62-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="a1b62-150">成功驗證之後，系統會要求核准者使用他們的 Epic 認證來驗證 Epic 組織。</span><span class="sxs-lookup"><span data-stu-id="a1b62-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="a1b62-151">貴組織的 Microsoft 365 系統管理員和 Epic 客戶分析師可以是相同的人員。</span><span class="sxs-lookup"><span data-stu-id="a1b62-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="a1b62-152">在這種情況下，將您自己的使用者名稱新增為核准者。</span><span class="sxs-lookup"><span data-stu-id="a1b62-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="a1b62-153">您仍然需要登入 Epic 以驗證您的存取權。</span><span class="sxs-lookup"><span data-stu-id="a1b62-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="a1b62-154">Epic 登入僅用於驗證您的 FHIR 基底 URL。</span><span class="sxs-lookup"><span data-stu-id="a1b62-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="a1b62-155">Microsoft 不會透過這個登入來儲存認證或存取 EHR 資料。</span><span class="sxs-lookup"><span data-stu-id="a1b62-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![驗證並核准認證組態。](../../media/approve-view-configuration.png)

<span data-ttu-id="a1b62-157">成功進行 Epic 登入之後，Epic 客戶分析師 **必須** 核准組態。</span><span class="sxs-lookup"><span data-stu-id="a1b62-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="a1b62-158">如果組態不正確，Microsoft 365 系統管理員可以再次登入 Microsoft EHR 連接器入口網站來修改原始組態。</span><span class="sxs-lookup"><span data-stu-id="a1b62-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![確認已設定 EHR 連接器，並且可以選擇變更組態。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="a1b62-160">檢閱並完成組態</span><span class="sxs-lookup"><span data-stu-id="a1b62-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="a1b62-161">當 Epic 系統管理員核准組態資訊時，將會顯示病患和提供者啟動的整合記錄。</span><span class="sxs-lookup"><span data-stu-id="a1b62-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="a1b62-162">這些記錄是完成 Epic 中虛擬就診組態的必要項目。</span><span class="sxs-lookup"><span data-stu-id="a1b62-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="a1b62-163">請參閱 Epic-Microsoft Teams 遠距健康整合指南以了解更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a1b62-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="a1b62-164">Microsoft 365 或 Epic 客戶分析師隨時都可以登入組態入口網站，視需要檢視整合記錄並修改組織組態。</span><span class="sxs-lookup"><span data-stu-id="a1b62-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![系統會顯示整合資訊。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="a1b62-166">Epic 客戶分析師必須針對 Microsoft 系統管理員之前所設定的每一個 FHIR URL 完成核准程序。</span><span class="sxs-lookup"><span data-stu-id="a1b62-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![組態資訊已核准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="a1b62-168">啟動 Teams 虛擬就診</span><span class="sxs-lookup"><span data-stu-id="a1b62-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="a1b62-169">完成 EHR 連接器步驟和 Epic 組態之後，您的組織已準備好支援使用 Microsoft Teams 進行視訊就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="a1b62-170">虛擬就診必要條件</span><span class="sxs-lookup"><span data-stu-id="a1b62-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="a1b62-171">您的系統必須符合所有[軟體與瀏覽器必要條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="a1b62-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="a1b62-172">醫療保健組織必須已完成 Epic 組織與 Microsoft 365 組織之間的設定。</span><span class="sxs-lookup"><span data-stu-id="a1b62-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="a1b62-173">提供者體驗</span><span class="sxs-lookup"><span data-stu-id="a1b62-173">Provider experience</span></span>

<span data-ttu-id="a1b62-174">貴組織的醫療保健提供者也可以從他們的 Epic 提供者應用程式 (Hyperspace、Haiku、Canto) 加入使用 Microsoft Teams 的虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="a1b62-175">**[開始虛擬就診]** 按鈕內嵌在提供者流程中。</span><span class="sxs-lookup"><span data-stu-id="a1b62-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="a1b62-176">提供者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="a1b62-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="a1b62-177">提供者可以使用支援的瀏覽器或 Microsoft Teams 應用程式加入虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="a1b62-178">提供者第一次加入虛擬就診時，必須使用其 Microsoft 365 帳戶進行一次性登入。</span><span class="sxs-lookup"><span data-stu-id="a1b62-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="a1b62-179">一次性登入之後，提供者將直接進入 Microsoft Teams 中的虛擬約會。</span><span class="sxs-lookup"><span data-stu-id="a1b62-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="a1b62-180">(提供者必須已登入 Microsoft Teams)。</span><span class="sxs-lookup"><span data-stu-id="a1b62-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="a1b62-181">提供者可以看到指定約會的參與者連線和中斷連線即時更新。</span><span class="sxs-lookup"><span data-stu-id="a1b62-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="a1b62-182">提供者可以看到病患何時連線到虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![與病患進行虛擬就診的提供者體驗](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="a1b62-184">病患體驗</span><span class="sxs-lookup"><span data-stu-id="a1b62-184">Patient experience</span></span>

<span data-ttu-id="a1b62-185">連接器可支援透過 MyChart Web 與行動版加入虛擬就診的病患。</span><span class="sxs-lookup"><span data-stu-id="a1b62-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="a1b62-186">在預約時，病患可以使用 **[開始虛擬就診]** 按鈕，從 MyChart 開始虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="a1b62-187">病患體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="a1b62-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="a1b62-188">病患可以從桌上型電腦與行動裝置上的新式網頁瀏覽器加入虛擬就診，而不需要安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="a1b62-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="a1b62-189">病患只需要按一下即可加入虛擬就診，不需要其他帳戶或登入。</span><span class="sxs-lookup"><span data-stu-id="a1b62-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="a1b62-190">病患不需要建立 Microsoft 帳戶或登入就可以啟動虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="a1b62-191">病患將進入大廳，直到醫療保健提供者加入約會並准許他們進行虛擬就診。</span><span class="sxs-lookup"><span data-stu-id="a1b62-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="a1b62-192">在加入虛擬就診之前，可以在大廳測試視訊和麥克風是否可用。</span><span class="sxs-lookup"><span data-stu-id="a1b62-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![虛擬就診的病患體驗](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="a1b62-194">Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商標。</span><span class="sxs-lookup"><span data-stu-id="a1b62-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="a1b62-195">資料隱私權和位置</span><span class="sxs-lookup"><span data-stu-id="a1b62-195">Privacy and location of data</span></span>

<span data-ttu-id="a1b62-196">Teams 與 EHR 系統的整合，可最佳化整合和虛擬就診流程期間所使用和儲存的資料量。</span><span class="sxs-lookup"><span data-stu-id="a1b62-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="a1b62-197">解決方案遵循 Teams 隱私權中概述的整體 Teams 隱私權和資料管理原則和指導方針。</span><span class="sxs-lookup"><span data-stu-id="a1b62-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="a1b62-198">Microsoft Teams EHR 連接器不會儲存或傳輸任何可識別個人資料，也不會從 EHR 系統傳輸任何病患或醫療保健提供者的健康記錄。</span><span class="sxs-lookup"><span data-stu-id="a1b62-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="a1b62-199">EHR 連接器儲存的唯一資料是 EHR 使用者的唯一識別碼，在 Teams 會議設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="a1b62-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="a1b62-200">EHR 使用者的唯一識別碼儲存在 [Microsoft 365 客戶資料儲存位置](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)的三個地理區域其中之一。</span><span class="sxs-lookup"><span data-stu-id="a1b62-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="a1b62-201">會議參與者在 Teams 中輸入的所有聊天、錄音及其他資料，都是根據現有的儲存原則來儲存。</span><span class="sxs-lookup"><span data-stu-id="a1b62-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="a1b62-202">如果您想要深入了解 Microsoft Teams 中資料的位置，請參閱 [Teams 中資料的位置](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="a1b62-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
