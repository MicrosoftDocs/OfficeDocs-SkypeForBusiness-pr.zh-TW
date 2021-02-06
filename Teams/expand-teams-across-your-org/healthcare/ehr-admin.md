---
title: 針對虛擬走訪的小組
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
description: 使用 Microsoft 團隊設定您的虛擬走訪系統
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125776"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="cd401-103">與團隊整合的虛擬走訪融入 EHR</span><span class="sxs-lookup"><span data-stu-id="cd401-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="cd401-104">Microsoft 團隊電子健康情況記錄 (EHR) 連接器可讓臨床醫師輕鬆地從 EHR 系統開始與其他團隊中的另一個提供者進行虛擬患者造訪或諮詢。</span><span class="sxs-lookup"><span data-stu-id="cd401-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="cd401-105">Microsoft 團隊是以 Microsoft 365 雲端為基礎，在單一中樞中使用聊天、影片、語音和醫療保健工具來實現簡單、安全的共同作業及通訊，這些功能可支援與 HIPAA、高科技認證等的相容性。</span><span class="sxs-lookup"><span data-stu-id="cd401-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="cd401-106">團隊的通訊與共同作業平臺可讓臨床醫師更容易地透過大量零散的系統來剪下，讓他們花時間提供最佳的功能。</span><span class="sxs-lookup"><span data-stu-id="cd401-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="cd401-107">Microsoft 團隊電子健康情況記錄 (EHR) 連接器可以：</span><span class="sxs-lookup"><span data-stu-id="cd401-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="cd401-108">啟動團隊從提供者和患者入口網站進行虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="cd401-109">在 connect 和中斷線上活動上寫回到 EHR 中繼資料，以啟用自動審核並保留記錄。</span><span class="sxs-lookup"><span data-stu-id="cd401-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="cd401-110">整合現有的 clinician 和患者工作流程，同時允許他們使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="cd401-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="cd401-111">觀看影片，瞭解如何從 EHR 入口網站管理虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="cd401-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="cd401-112">Before you begin</span></span>

<span data-ttu-id="cd401-113">您必須先確認您具備下列先決條件，才能整合 EHR 連接器：</span><span class="sxs-lookup"><span data-stu-id="cd401-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="cd401-114">在 [長篇應用程式果園 marketplace](https://apporchard.epic.com/Gallery?id=6153)中使用 Microsoft 團隊 app 的存取權。</span><span class="sxs-lookup"><span data-stu-id="cd401-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="cd401-115">[適用于 Microsoft 雲端的 Microsoft 雲端訂閱] 或 [Microsoft 團隊訂閱] 的 [使用中訂閱]，只會在生產測試) 中強制執行 (。</span><span class="sxs-lookup"><span data-stu-id="cd401-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="cd401-116">使用者必須具備適當的 Microsoft 365 或 Office 365 授權，包括 Microsoft 團隊會議。</span><span class="sxs-lookup"><span data-stu-id="cd401-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="cd401-117">您應該在組織內部採用並使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="cd401-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="cd401-118">組織必須具有長篇故事版本2018年11月或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cd401-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="cd401-119">您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="cd401-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="cd401-120">您也需要來自貴組織中下列人員的資訊：</span><span class="sxs-lookup"><span data-stu-id="cd401-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="cd401-121">Microsoft 365 系統管理員</span><span class="sxs-lookup"><span data-stu-id="cd401-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="cd401-122">長篇故事客戶分析師</span><span class="sxs-lookup"><span data-stu-id="cd401-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="cd401-123">要求長篇故事技術專家提供長篇 marketplace 中提供的 Epic-Microsoft 團隊 Telehealth 整合指南。</span><span class="sxs-lookup"><span data-stu-id="cd401-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="cd401-124">連接器設定</span><span class="sxs-lookup"><span data-stu-id="cd401-124">Connector setup</span></span>

<span data-ttu-id="cd401-125">連接器設定要求您：</span><span class="sxs-lookup"><span data-stu-id="cd401-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="cd401-126">啟動 EHR 連接器配置入口網站</span><span class="sxs-lookup"><span data-stu-id="cd401-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="cd401-127">配置資訊</span><span class="sxs-lookup"><span data-stu-id="cd401-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="cd401-128">核准或查看設定</span><span class="sxs-lookup"><span data-stu-id="cd401-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="cd401-129">審查並完成設定</span><span class="sxs-lookup"><span data-stu-id="cd401-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="cd401-130">啟動 EHR 連接器配置入口網站</span><span class="sxs-lookup"><span data-stu-id="cd401-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="cd401-131">您可以透過啟動 EHR 連接器設定入口網站，將您的保健組織設定為使用 Microsoft 團隊啟動虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="cd401-132">您可以設定一或多個組織來測試整合。</span><span class="sxs-lookup"><span data-stu-id="cd401-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="cd401-133">在配置入口網站中設定測試與生產 URL。</span><span class="sxs-lookup"><span data-stu-id="cd401-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="cd401-134">在移至生產之前，請先測試長篇測試環境的整合。</span><span class="sxs-lookup"><span data-stu-id="cd401-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="cd401-135">EHR 連接器配置 URL： [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cd401-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="cd401-136">貴組織的 Microsoft 365 系統管理員和長篇客戶分析師必須完成配置入口網站中的資訊與整合步驟。</span><span class="sxs-lookup"><span data-stu-id="cd401-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="cd401-137">針對長篇配置步驟，請聯絡指派給您組織的長篇技術專家資源。</span><span class="sxs-lookup"><span data-stu-id="cd401-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="cd401-138">配置資訊</span><span class="sxs-lookup"><span data-stu-id="cd401-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="cd401-139">此步驟將由 **Microsoft 365 管理員** 完成。</span><span class="sxs-lookup"><span data-stu-id="cd401-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="cd401-140">Microsoft 365 管理員必須啟動連接器配置入口網站，並以 Microsoft 認證登入，才能開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="cd401-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="cd401-141">若要完成此步驟，Microsoft 365 管理員必須收到有效的快速健康情況互通性資源 () FHIR 您的長篇技術專家的基本 URL，以及要核准設定的長篇客戶分析員的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="cd401-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="cd401-142">Microsoft 365 管理員必須啟動連接器設定頁面，並以 Microsoft 認證登入，以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="cd401-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="cd401-143">FHIR 基底 URL 是與您的伺服器 FHIR API 端點相對應的靜態位址。</span><span class="sxs-lookup"><span data-stu-id="cd401-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="cd401-144">範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` 。</span><span class="sxs-lookup"><span data-stu-id="cd401-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="cd401-145">[設定核准者名稱] 是要在下一步中負責核准設定的長篇客戶分析員的名稱。</span><span class="sxs-lookup"><span data-stu-id="cd401-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="cd401-146">長篇故事客戶分析機構是您組織中的人員，且具有 [登入] 存取長篇故事。</span><span class="sxs-lookup"><span data-stu-id="cd401-146">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![設定核准者的名稱是從 EHR 連接器的清單中選取。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="cd401-148">核准或查看設定</span><span class="sxs-lookup"><span data-stu-id="cd401-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="cd401-149">以核准者身分新增之保健組織的長篇故事客戶分析員現在必須使用相同的 EHR 連接器 URL，才能使用其 Microsoft 365 認證登入。</span><span class="sxs-lookup"><span data-stu-id="cd401-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="cd401-150">成功驗證之後，系統會要求核准者使用其長篇認證登入，以驗證長篇組織。</span><span class="sxs-lookup"><span data-stu-id="cd401-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="cd401-151">貴組織中的 Microsoft 365 系統管理員與長篇客戶分析員可以是同一個人。</span><span class="sxs-lookup"><span data-stu-id="cd401-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="cd401-152">在這種情況下，請新增您自己的使用者名稱作為核准者。</span><span class="sxs-lookup"><span data-stu-id="cd401-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="cd401-153">您仍需登入長篇故事來驗證您的存取權。</span><span class="sxs-lookup"><span data-stu-id="cd401-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="cd401-154">長篇故事只能用來驗證您的 FHIR 基本 URL。</span><span class="sxs-lookup"><span data-stu-id="cd401-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="cd401-155">Microsoft 不會使用此登入來儲存認證或存取 EHR 資料。</span><span class="sxs-lookup"><span data-stu-id="cd401-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![驗證及核准認證設定。](../../media/approve-view-configuration.png)

<span data-ttu-id="cd401-157">成功長篇故事登入後，長篇故事客戶分析員 **必須** 核准設定。</span><span class="sxs-lookup"><span data-stu-id="cd401-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="cd401-158">如果設定不正確，Microsoft 365 系統管理員就能再次登入 Microsoft EHR 連接器入口網站來修改原始設定。</span><span class="sxs-lookup"><span data-stu-id="cd401-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![確認已設定 EHR 連接器，並選擇變更配置。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="cd401-160">審查並完成設定</span><span class="sxs-lookup"><span data-stu-id="cd401-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="cd401-161">當長篇管理員核准配置資訊時，您會看到患者與提供者啟動的整合記錄。</span><span class="sxs-lookup"><span data-stu-id="cd401-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="cd401-162">需要這些記錄，才能在長篇故事中完成虛擬就診設定。</span><span class="sxs-lookup"><span data-stu-id="cd401-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="cd401-163">如需詳細資訊，請參閱 Epic-Microsoft 團隊 Telehealth 整合指南。</span><span class="sxs-lookup"><span data-stu-id="cd401-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="cd401-164">在任何時候，Microsoft 365 或長篇故事客戶分析員都可以登入配置入口網站，以查看整合記錄及修改組織設定（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="cd401-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![隨即會顯示整合資訊。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="cd401-166">您必須先完成由 Microsoft 系統管理員設定的每個 FHIR URL 的長篇故事客戶分析員完成核准流程。</span><span class="sxs-lookup"><span data-stu-id="cd401-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![配置資訊已獲核准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="cd401-168">啟動團隊虛擬走訪</span><span class="sxs-lookup"><span data-stu-id="cd401-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="cd401-169">完成 EHR 連接器步驟和長篇設定之後，您的組織就已準備好支援與 Microsoft 團隊進行的影片走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="cd401-170">虛擬造訪先決條件</span><span class="sxs-lookup"><span data-stu-id="cd401-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="cd401-171">您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="cd401-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="cd401-172">醫療保健組織必須已完成長篇組織與 Microsoft 365 組織之間的設定。</span><span class="sxs-lookup"><span data-stu-id="cd401-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="cd401-173">提供者體驗</span><span class="sxs-lookup"><span data-stu-id="cd401-173">Provider experience</span></span>

<span data-ttu-id="cd401-174">貴組織的醫療保健提供者也可以將虛擬造訪從其長篇故事提供者的應用程式 (超空間、Haiku、Canto) 。</span><span class="sxs-lookup"><span data-stu-id="cd401-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="cd401-175">[ **開始虛擬造訪** ] 按鈕會內嵌在提供者流程中。</span><span class="sxs-lookup"><span data-stu-id="cd401-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="cd401-176">提供者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="cd401-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="cd401-177">提供者可以使用支援的瀏覽器或 Microsoft 團隊應用程式加入虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="cd401-178">第一次加入虛擬就診時，提供者必須使用 Microsoft 365 帳戶進行一次性登入。</span><span class="sxs-lookup"><span data-stu-id="cd401-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="cd401-179">一次登入之後，提供者會直接取得 Microsoft 團隊中的虛擬約會。</span><span class="sxs-lookup"><span data-stu-id="cd401-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="cd401-180"> (提供者必須登入 Microsoft 團隊) 。</span><span class="sxs-lookup"><span data-stu-id="cd401-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="cd401-181">提供者可以查看特定約會的參與者連線和中斷連線更新。</span><span class="sxs-lookup"><span data-stu-id="cd401-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="cd401-182">提供者可以查看患者連線至虛擬造訪的時間。</span><span class="sxs-lookup"><span data-stu-id="cd401-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![使用患者的虛擬造訪提供者體驗](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="cd401-184">患者體驗</span><span class="sxs-lookup"><span data-stu-id="cd401-184">Patient experience</span></span>

<span data-ttu-id="cd401-185">連接器支援患者透過 MyChart 網頁和行動裝置加入虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="cd401-186">在約會時，患者可以使用「 **開始虛擬造訪** 」按鈕，從 MyChart 進行虛擬造訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="cd401-187">患者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="cd401-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="cd401-188">患者可以在桌面和行動裝置上從新式網頁瀏覽器加入虛擬造訪，而不需安裝 app。</span><span class="sxs-lookup"><span data-stu-id="cd401-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="cd401-189">患者只要按一下就能加入虛擬走訪，且不需要其他帳戶或登入。</span><span class="sxs-lookup"><span data-stu-id="cd401-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="cd401-190">您不需要患者即可建立 Microsoft 帳戶或登入以啟動虛擬造訪。</span><span class="sxs-lookup"><span data-stu-id="cd401-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="cd401-191">患者將放在大廳，直到醫療保健提供者加入約會並允許給虛擬造訪為止。</span><span class="sxs-lookup"><span data-stu-id="cd401-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="cd401-192">您可以在加入虛擬造訪前，在大廳中測試影片和麥克風。</span><span class="sxs-lookup"><span data-stu-id="cd401-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![[虛擬造訪] 的患者體驗](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="cd401-194">長篇故事、MyChart、Haiku 和 Canto 是長篇系統公司的商標。</span><span class="sxs-lookup"><span data-stu-id="cd401-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="cd401-195">資料的隱私權和位置</span><span class="sxs-lookup"><span data-stu-id="cd401-195">Privacy and location of data</span></span>

<span data-ttu-id="cd401-196">整合在 EHR 系統中的團隊可優化整合和虛擬就診流程期間要使用及儲存的資料量。</span><span class="sxs-lookup"><span data-stu-id="cd401-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="cd401-197">本方案遵循團隊隱私權中的整體小組隱私權與資料管理原則及指導方針。</span><span class="sxs-lookup"><span data-stu-id="cd401-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="cd401-198">Microsoft 團隊 EHR 連接器不會在 EHR 系統中儲存或轉移任何可識別的個人資料，或患者或醫療保健提供者的任何健康記錄。</span><span class="sxs-lookup"><span data-stu-id="cd401-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="cd401-199">EHR 連接器所儲存的唯一資料是 EHR 使用者的唯一識別碼，可在小組會議設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="cd401-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="cd401-200">EHR 使用者的唯一識別碼會儲存在 [您的 Microsoft 365 客戶資料儲存位置](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)中所述的三個地理區域之一。</span><span class="sxs-lookup"><span data-stu-id="cd401-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="cd401-201">會議參與者會根據現有的儲存原則來儲存所有聊天、錄製及其他透過會議參與者輸入至團隊的資料。</span><span class="sxs-lookup"><span data-stu-id="cd401-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="cd401-202">如果您想要深入瞭解 Microsoft 團隊中的資料位置，請造訪 [團隊中的資料](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)位置。</span><span class="sxs-lookup"><span data-stu-id="cd401-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
