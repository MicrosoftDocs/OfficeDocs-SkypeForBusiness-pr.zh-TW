---
title: 開始使用適用于醫療保健組織的團隊
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 開始使用適用于醫療保健組織的團隊
ms.openlocfilehash: 380d9c75bc2f7eeb66bc6d0d0f5598d2a243a9da
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767152"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="8f238-103">開始使用適用于醫療保健組織的團隊</span><span class="sxs-lookup"><span data-stu-id="8f238-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="8f238-104">Microsoft 團隊提供許多適用于醫院和其他醫療保健組織的功能。</span><span class="sxs-lookup"><span data-stu-id="8f238-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="8f238-105">團隊功能正處於開發階段，可協助醫院進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="8f238-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="8f238-106">護理協調與共同作業</span><span class="sxs-lookup"><span data-stu-id="8f238-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="8f238-107">安全訊息</span><span class="sxs-lookup"><span data-stu-id="8f238-107">Secure Messaging</span></span>
- <span data-ttu-id="8f238-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="8f238-108">Telehealth</span></span>
- <span data-ttu-id="8f238-109">電子醫療保健記錄（EHR）整合</span><span class="sxs-lookup"><span data-stu-id="8f238-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="8f238-110">第一線員工 Worker 系統整合</span><span class="sxs-lookup"><span data-stu-id="8f238-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="8f238-111">本節內容是根據團隊的基本功能（例如會議、通話和訊息傳遞）來建立，並假設您已經部署在貴組織中部署的小組。</span><span class="sxs-lookup"><span data-stu-id="8f238-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams deployed in your organization.</span></span> <span data-ttu-id="8f238-112">如果您尚未推出小組，請先閱讀[瞭解如何推出 Microsoft 團隊](../../How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8f238-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="8f238-113">護理協調-Microsoft 團隊患者 app</span><span class="sxs-lookup"><span data-stu-id="8f238-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="8f238-114">Microsoft 團隊現在有一個專門針對醫療保健組織的護理協調解決方案，可協助他們提供最佳的患者治療。</span><span class="sxs-lookup"><span data-stu-id="8f238-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="8f238-115">Crux 的 [護理協調] 解決方案是「Microsoft 團隊患者 app」，它是第一個與電子醫療記錄（[EHR）系統](https://www.hl7.org/fhir/)整合的第一個參與方索引標籤 app，可讓您有價值地使用。在內容中將醫療資訊納入 Microsoft 小組，以實現臨床共同作業及通訊。</span><span class="sxs-lookup"><span data-stu-id="8f238-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="8f238-116">護理協調方案可以與主要獨立軟體廠商（Isv）進行介面，讓您可以使用現有的健康資料標準（例如 HL7v2 和 FHIR），將患者 app 連線至您的 EHR 系統。</span><span class="sxs-lookup"><span data-stu-id="8f238-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="8f238-117">具備下列業界領袖的 Microsoft 合作夥伴，可與團隊建立電子健康情況記錄整合：</span><span class="sxs-lookup"><span data-stu-id="8f238-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="8f238-118">Datica （透過其[CMI](https://datica.com/compliant-managed-integration/)產品）</span><span class="sxs-lookup"><span data-stu-id="8f238-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="8f238-119">Infor Cloverleaf （透過[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）</span><span class="sxs-lookup"><span data-stu-id="8f238-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="8f238-120">Redox （透過[R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/)）</span><span class="sxs-lookup"><span data-stu-id="8f238-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="8f238-121">Dapasoft （透過[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)）</span><span class="sxs-lookup"><span data-stu-id="8f238-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="8f238-122">嘗試針對醫療保健提供者組織實施 Microsoft 團隊的 EHR 整合與互通性合作夥伴，必須為患者 app 提供與醫療保健供應商組織 EHR 系統的安全且驗證的連線。</span><span class="sxs-lookup"><span data-stu-id="8f238-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="8f238-123">這可讓相關患者記錄的單向（唯讀）流程進入患者 app。</span><span class="sxs-lookup"><span data-stu-id="8f238-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="8f238-124">患者 app 可瞭解 FHIR 格式，因此合作夥伴也負責將匯總資料從各種其他格式（例如 HL7v2 等）轉換成 FHIR DSTU2 或 STU3。</span><span class="sxs-lookup"><span data-stu-id="8f238-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![圖示醒目提示護理協調與共同作業](../../media/ehr-1.png)

<br>

<span data-ttu-id="8f238-126">患者 app 整合了電子醫療記錄（EHR）系統，並可讓護理提供者在小組安全的平臺中即時溝通患者治療。</span><span class="sxs-lookup"><span data-stu-id="8f238-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="8f238-127">患者 app 是護理協調區域中的第一項主要投資，目的是解決下列難題：</span><span class="sxs-lookup"><span data-stu-id="8f238-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="8f238-128">在工作中保持不太高效，且透過患者體驗進行重要溝通</span><span class="sxs-lookup"><span data-stu-id="8f238-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="8f238-129">產生管理負擔的各自為政資訊</span><span class="sxs-lookup"><span data-stu-id="8f238-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="8f238-130">使用複雜及零散共同作業工具的臨床醫師中的不滿</span><span class="sxs-lookup"><span data-stu-id="8f238-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="8f238-131">低效率的人員間護理協調，可能會燒壞太昂貴的臨床時間</span><span class="sxs-lookup"><span data-stu-id="8f238-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="8f238-132">Microsoft 團隊可讓醫生、臨床醫師、護士及其他員工高效地進行共同作業：</span><span class="sxs-lookup"><span data-stu-id="8f238-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="8f238-133">成為可在 Office 檔上運作及共同合作的單一虛擬化小組的一部分</span><span class="sxs-lookup"><span data-stu-id="8f238-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="8f238-134">在其他患者需要注意的持續交談</span><span class="sxs-lookup"><span data-stu-id="8f238-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="8f238-135">使用頻道搭配索引標籤來組織其工作，並提供可讓他們釘選資訊來源之索引標籤的其他說明</span><span class="sxs-lookup"><span data-stu-id="8f238-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="8f238-136">將頻道會議與團隊的威力、影片、螢幕共用、錄製和工具功能配合使用，以管理每日會議</span><span class="sxs-lookup"><span data-stu-id="8f238-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="8f238-137">使用患者 app 來彙整必須監視的高風險患者清單，並從 EHR 系統中拉回其最新詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8f238-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="8f238-138">患者 app 本身會將下列功能新增至 Microsoft 團隊：</span><span class="sxs-lookup"><span data-stu-id="8f238-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="8f238-139">能夠在單一頻道中建立多個患者清單。</span><span class="sxs-lookup"><span data-stu-id="8f238-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="8f238-140">透過可設定的欄來查看和排序顯示的患者資訊的功能。</span><span class="sxs-lookup"><span data-stu-id="8f238-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="8f238-141">透過小組範本自動進行應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="8f238-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="8f238-142">可在 iOS 版和 Android 版的團隊 App 中使用，可在適用于 iOS 和 Android 的小組應用程式中，使用 Microsoft 團隊網頁與桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f238-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="8f238-143">透過分析一致性語句來支援 FHIR DSTU2 和 STU3 版本。</span><span class="sxs-lookup"><span data-stu-id="8f238-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="8f238-144">針對其使用者介面上的所有視圖和搜尋動作的審核記錄，以保護每個 HIPAA 指引中的 PHI。</span><span class="sxs-lookup"><span data-stu-id="8f238-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="8f238-145">患者 app 是在小組擴充性平臺上建立，並利用 [定位點架構] 在頻道中顯示豐富的患者內容。</span><span class="sxs-lookup"><span data-stu-id="8f238-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="8f238-146">若要深入瞭解其他團隊 app 和平臺本身，請參閱[Microsoft 團隊相關應用程式](/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="8f238-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="8f238-147">患者 app 是私人預覽，且 FHIR 介面在 Beta 版中。</span><span class="sxs-lookup"><span data-stu-id="8f238-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="8f238-148">已發行的版本不應該是向後相容的。</span><span class="sxs-lookup"><span data-stu-id="8f238-148">Released versions are not expected to be backward compatible.</span></span>

![桌面和行動裝置上患者 app 的螢幕擷取畫面](../../media/ehr-2.png)

<span data-ttu-id="8f238-150">如需詳細資訊，請參閱將[電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="8f238-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="8f238-151">模版</span><span class="sxs-lookup"><span data-stu-id="8f238-151">Templates</span></span>

<span data-ttu-id="8f238-152">我們已開發新的範本來建立小組，以套用至醫院設定。</span><span class="sxs-lookup"><span data-stu-id="8f238-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="8f238-153">如此一來，您就能更輕鬆地建立可讓醫療保健工人在不同部門或 wards 中與患者共同合作的小組。</span><span class="sxs-lookup"><span data-stu-id="8f238-153">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="8f238-154">請參閱[開始使用醫療保健組織的團隊範本](healthcare-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="8f238-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="8f238-155">團隊可以針對內部部門（例如心臟病科）或 [護理 wards] 或 [開發中的其他範本] 進行啟動。</span><span class="sxs-lookup"><span data-stu-id="8f238-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="8f238-156">安全訊息</span><span class="sxs-lookup"><span data-stu-id="8f238-156">Secure Messaging</span></span>

<span data-ttu-id="8f238-157">安全訊息支援在護理小組中共同作業，包括幾個新功能：</span><span class="sxs-lookup"><span data-stu-id="8f238-157">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="8f238-158">郵件寄件者可以為郵件設定特殊的優先順序，所以收件者會反復收到通知，直到他們閱讀郵件為止。</span><span class="sxs-lookup"><span data-stu-id="8f238-158">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="8f238-159">郵件寄件者可以要求讀信回條，當郵件收件者閱讀郵件時，就會收到通知。</span><span class="sxs-lookup"><span data-stu-id="8f238-159">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="8f238-160">總之，這些功能可讓您更快速地注意到緊急訊息，並確信郵件已被接收和讀取。</span><span class="sxs-lookup"><span data-stu-id="8f238-160">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="8f238-161">使用這些功能的新的護理團隊可以在每個患者上建立。</span><span class="sxs-lookup"><span data-stu-id="8f238-161">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="8f238-162">這些功能都是以原則為基礎，而且可以指派給個人或整個團隊。</span><span class="sxs-lookup"><span data-stu-id="8f238-162">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="8f238-163">如需進一步的詳細資料，請參閱[開始使用醫療保健組織的安全訊息原則](messaging-policies-hc.md)。</span><span class="sxs-lookup"><span data-stu-id="8f238-163">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="8f238-164">此外，與安全訊息相關的功能，也是由醫療保健組織聯盟的其他租使用者，允許更豐富的租使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="8f238-164">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="8f238-165">（請參閱[Microsoft 團隊中的 [管理外部存取（同盟）](../../manage-external-access.md)]）。</span><span class="sxs-lookup"><span data-stu-id="8f238-165">(see [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="8f238-166">第一線員工工作人員整合</span><span class="sxs-lookup"><span data-stu-id="8f238-166">Firstline Worker integration</span></span>

<span data-ttu-id="8f238-167">Microsoft 團隊會與第一線員工工作人員整合，這可以用來共同調整倒班人員的功能。</span><span class="sxs-lookup"><span data-stu-id="8f238-167">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="8f238-168">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="8f238-168">See the following articles:</span></span>

- [<span data-ttu-id="8f238-169">將 Microsoft StaffHub 小組移至 Microsoft 團隊中的倒班</span><span class="sxs-lookup"><span data-stu-id="8f238-169">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="8f238-170">在 Microsoft 團隊中為您的組織管理倒班應用程式</span><span class="sxs-lookup"><span data-stu-id="8f238-170">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
