---
title: 針對虛擬走訪的小組
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 使用 Microsoft 團隊設定您的虛擬走訪系統
ms.openlocfilehash: 3d5d68e7c4ba3cc203df33604a7210e67b402938
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778886"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="0fb7c-103">與團隊整合的虛擬走訪融入 EHR</span><span class="sxs-lookup"><span data-stu-id="0fb7c-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="0fb7c-104">Microsoft 團隊電子健康情況記錄 (EHR) 連接器可讓臨床醫師輕鬆地從 EHR 系統開始與其他團隊中的另一個提供者進行虛擬患者造訪或諮詢。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="0fb7c-105">Microsoft 團隊是以 Microsoft 365 雲端為基礎，在單一中樞中使用聊天、影片、語音和醫療保健工具來實現簡單、安全的共同作業及通訊，這些功能可支援與 HIPAA、高科技認證等的相容性。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="0fb7c-106">團隊的通訊與共同作業平臺可讓臨床醫師更容易地透過大量零散的系統來剪下，讓他們花時間提供最佳的功能。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="0fb7c-107">Microsoft 團隊電子健康情況記錄 (EHR) 連接器可以：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="0fb7c-108">啟動團隊從提供者和患者入口網站進行虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="0fb7c-109">在 connect 和中斷線上活動上寫回到 EHR 中繼資料，以啟用自動審核並保留記錄。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="0fb7c-110">整合現有的 clinician 和患者工作流程，同時允許他們使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="0fb7c-111">觀看影片，瞭解如何從 EHR 入口網站管理虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="0fb7c-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="0fb7c-112">Before you begin</span></span>

<span data-ttu-id="0fb7c-113">您必須先確認您具備下列先決條件，才能整合 EHR 連接器：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="0fb7c-114">適用于 Microsoft 雲端保健或訂閱 Microsoft 團隊 EHR 連接器獨立優惠的有效訂閱。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="0fb7c-115">使用者必須具備適當的 Microsoft 365 或 Office 365 授權，包括 Microsoft 團隊會議。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="0fb7c-116">您應該在組織內部採用並使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="0fb7c-117">組織必須具有長篇故事版本2018年11月或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="0fb7c-118">您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="0fb7c-119">您也需要來自貴組織中下列人員的資訊：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="0fb7c-120">Microsoft 365 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0fb7c-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="0fb7c-121">長篇故事系統管理員</span><span class="sxs-lookup"><span data-stu-id="0fb7c-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="0fb7c-122">要求長篇故事管理員提供長篇 marketplace 中提供的 Epic-Microsoft 團隊 Telehealth 整合指南。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="0fb7c-123">連接器設定</span><span class="sxs-lookup"><span data-stu-id="0fb7c-123">Connector setup</span></span>

<span data-ttu-id="0fb7c-124">連接器設定要求您：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="0fb7c-125">啟動 EHR 連接器配置入口網站</span><span class="sxs-lookup"><span data-stu-id="0fb7c-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="0fb7c-126">設定提供者組織資訊</span><span class="sxs-lookup"><span data-stu-id="0fb7c-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="0fb7c-127">驗證及核准設定</span><span class="sxs-lookup"><span data-stu-id="0fb7c-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="0fb7c-128">審查並完成設定</span><span class="sxs-lookup"><span data-stu-id="0fb7c-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="0fb7c-129">啟動 EHR 連接器配置入口網站</span><span class="sxs-lookup"><span data-stu-id="0fb7c-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="0fb7c-130">您可以透過啟動 EHR 連接器設定入口網站，將您的保健組織設定為使用 Microsoft 團隊啟動虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="0fb7c-131">使用測試 URL 來設定長篇測試環境的連接器。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="0fb7c-132">當您準備好要啟用長篇生產環境時，請使用生產 URL。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="0fb7c-133">測試環境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0fb7c-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="0fb7c-134">生產環境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0fb7c-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="0fb7c-135">貴組織的 Microsoft 365 系統管理員和長篇電腦系統管理員必須完成配置入口網站中的資訊與整合步驟。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="0fb7c-136">針對長篇配置步驟，請與分派給您組織的長篇資源。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="0fb7c-137">設定提供者組織資訊</span><span class="sxs-lookup"><span data-stu-id="0fb7c-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="0fb7c-138">此步驟將由 Microsoft 365 管理員完成。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="0fb7c-139">Microsoft 365 管理員必須啟動連接器配置入口網站，並以 Microsoft 認證登入，才能開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="0fb7c-140">若要完成此步驟，Microsoft 365 管理員必須從您的 Microsoft 365 系統管理員 () FHIR 基本 URL，以及將核准設定的長篇故事管理員的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="0fb7c-141">Microsoft 365 管理員必須啟動連接器設定頁面，並以 Microsoft 認證登入，以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="0fb7c-142">FHIR 基底 URL 是與您的伺服器 FHIR API 端點相對應的靜態位址。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="0fb7c-143">範例 URL 是 [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) 。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-143">An example URL is [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST).</span></span>

- <span data-ttu-id="0fb7c-144">[設定核准者名稱] 是將負責核准設定的長篇故事系統管理員名稱。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![設定核准者的名稱是從 EHR 連接器的清單中選取。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="0fb7c-146">驗證及核准設定</span><span class="sxs-lookup"><span data-stu-id="0fb7c-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="0fb7c-147">以核准者身分新增之醫療保健組織的長篇故事管理員必須立即使用相同的 EHR 連接器 URL，才能使用其 Microsoft 365 認證登入。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="0fb7c-148">成功驗證之後，系統會要求核准者使用其長篇認證登入，以驗證長篇組織。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="0fb7c-149">貴組織中的 Microsoft 365 管理員和長篇故事系統管理員可以是相同的人員。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="0fb7c-150">在這種情況下，請在第一個步驟中新增您自己的使用者名稱作為核准者。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="0fb7c-151">您仍需登入長篇故事來驗證您的存取權。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="0fb7c-152">長篇故事只能用來驗證您的 FHIR 基本 URL。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="0fb7c-153">Microsoft 不會使用此登入來儲存認證或存取 EHR 資料。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![驗證及核准認證設定。](../../media/ehc-provider-2.png)

<span data-ttu-id="0fb7c-155">成功長篇故事登入時，長篇故事管理員 **必須** 核准設定。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="0fb7c-156">如果設定不正確，Microsoft 365 系統管理員就能再次登入 Microsoft EHR 連接器入口網站來修改原始設定。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![確認已設定 EHR 連接器，並選擇變更配置。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="0fb7c-158">審查並完成設定</span><span class="sxs-lookup"><span data-stu-id="0fb7c-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="0fb7c-159">當長篇管理員核准配置資訊時，您會看到患者與提供者啟動的整合記錄。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="0fb7c-160">需要這些記錄，才能在長篇故事中完成虛擬就診設定。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="0fb7c-161">如需詳細資訊，請參閱 Epic-Microsoft 團隊 Telehealth 整合指南。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="0fb7c-162">在任何時候，Microsoft 365 或長篇故事管理員都可以登入配置入口網站，以查看整合記錄及修改組織設定（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![隨即會顯示整合資訊。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="0fb7c-164">啟動團隊虛擬走訪</span><span class="sxs-lookup"><span data-stu-id="0fb7c-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="0fb7c-165">完成 EHR 連接器步驟和長篇設定之後，您的組織就已準備好支援與 Microsoft 團隊進行的影片走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="0fb7c-166">虛擬造訪先決條件</span><span class="sxs-lookup"><span data-stu-id="0fb7c-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="0fb7c-167">您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="0fb7c-168">醫療保健組織必須已完成長篇組織與 Microsoft 365 組織之間的設定。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="0fb7c-169">提供者體驗</span><span class="sxs-lookup"><span data-stu-id="0fb7c-169">Provider experience</span></span>

<span data-ttu-id="0fb7c-170">貴組織的醫療保健提供者也可以將虛擬造訪從其長篇故事提供者的應用程式 (超空間、Haiku、Canto) 。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="0fb7c-171">[ **開始虛擬造訪** ] 按鈕會內嵌在提供者流程中。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="0fb7c-172">提供者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="0fb7c-173">提供者可以使用支援的瀏覽器或 Microsoft 團隊應用程式加入虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="0fb7c-174">當您第一次加入虛擬就診時，提供者必須進行一次登入其 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="0fb7c-175">一次登入後，提供者會直接取得 Microsoft 團隊中的虛擬約會。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="0fb7c-176"> (提供者必須登入 Microsoft 團隊) 。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="0fb7c-177">提供者可以查看特定約會的參與者連線和中斷連線更新。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="0fb7c-178">提供者可以查看患者連線至虛擬造訪的時間。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![使用患者的虛擬造訪提供者體驗](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="0fb7c-180">患者體驗</span><span class="sxs-lookup"><span data-stu-id="0fb7c-180">Patient experience</span></span>

<span data-ttu-id="0fb7c-181">連接器支援患者透過 MyChart 網頁和行動裝置加入虛擬走訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="0fb7c-182">在約會時，患者可以使用「 **開始虛擬造訪** 」按鈕，從 MyChart 進行虛擬造訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="0fb7c-183">患者體驗的主要功能：</span><span class="sxs-lookup"><span data-stu-id="0fb7c-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="0fb7c-184">患者可以在桌面和行動裝置上從新式網頁瀏覽器加入虛擬造訪，而不需安裝 app。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="0fb7c-185">患者只要按一下就能加入虛擬走訪，且不需要其他帳戶或登入。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="0fb7c-186">您不需要患者即可建立 Microsoft 帳戶或登入以啟動虛擬造訪。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="0fb7c-187">患者將放在大廳，直到醫療保健提供者加入約會並允許給虛擬造訪為止。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="0fb7c-188">您可以在加入虛擬造訪前，在大廳中測試影片和麥克風。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![[虛擬造訪] 的患者體驗](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="0fb7c-190">長篇故事、MyChart、Haiku 和 Canto 是長篇系統公司的商標。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="0fb7c-191">資料的隱私權和位置</span><span class="sxs-lookup"><span data-stu-id="0fb7c-191">Privacy and location of data</span></span>

<span data-ttu-id="0fb7c-192">整合在 EHR 系統中的團隊可優化整合和虛擬就診流程期間要使用及儲存的資料量。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="0fb7c-193">本方案遵循團隊隱私權中的整體小組隱私權與資料管理原則及指導方針。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="0fb7c-194">Microsoft 團隊 EHR 連接器不會在 EHR 系統中儲存或轉移任何可識別的個人資料，或患者或醫療保健提供者的任何健康記錄。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="0fb7c-195">EHR 連接器所儲存的唯一資料是 EHR 使用者的唯一識別碼，可在小組會議設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="0fb7c-196">EHR 使用者的唯一識別碼會儲存在 [Microsoft 365 客戶資料儲存在其中](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 的三個地理區域之一。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="0fb7c-197">會議參與者會根據現有的儲存原則來儲存所有聊天、錄製及其他透過會議參與者輸入至團隊的資料。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="0fb7c-198">如果您想要深入瞭解 Microsoft 團隊中的資料位置，請造訪 [團隊中的資料](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)位置。</span><span class="sxs-lookup"><span data-stu-id="0fb7c-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
