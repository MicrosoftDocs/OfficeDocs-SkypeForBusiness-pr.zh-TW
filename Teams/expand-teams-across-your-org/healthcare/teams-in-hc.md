---
title: 開始使用適用於醫療保健組織的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
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
description: 瞭解醫療保健的功能，包括護理協調、安全的訊息、telehealth、EHR 整合，以及第一線員工 worker 系統整合。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68954745bc1631e2031fce80ff1681056e9f4bdd
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361583"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="dabc4-103">開始使用適用於醫療保健組織的 Teams</span><span class="sxs-lookup"><span data-stu-id="dabc4-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="dabc4-104">Microsoft 團隊提供許多適用于醫院和其他醫療保健組織的功能。</span><span class="sxs-lookup"><span data-stu-id="dabc4-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="dabc4-105">團隊功能正處於開發階段，可協助醫院進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="dabc4-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="dabc4-106">護理協調與共同作業</span><span class="sxs-lookup"><span data-stu-id="dabc4-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="dabc4-107">安全訊息</span><span class="sxs-lookup"><span data-stu-id="dabc4-107">Secure Messaging</span></span>
- <span data-ttu-id="dabc4-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="dabc4-108">Telehealth</span></span>
- <span data-ttu-id="dabc4-109">電子醫療保健記錄 (EHR) 整合</span><span class="sxs-lookup"><span data-stu-id="dabc4-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="dabc4-110">第一線員工 Worker 系統整合</span><span class="sxs-lookup"><span data-stu-id="dabc4-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="dabc4-111">本節內容是以小組的基本功能為基礎，例如會議、通話和訊息，並假設您已在組織中部署團隊。</span><span class="sxs-lookup"><span data-stu-id="dabc4-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="dabc4-112">如果您尚未推出小組，請先閱讀 [瞭解如何推出 Microsoft 團隊](../../How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="dabc4-113">護理協調-Microsoft 團隊患者 app</span><span class="sxs-lookup"><span data-stu-id="dabc4-113">Care Coordination - Microsoft Teams Patients app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dabc4-114">**2020年10月15日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="dabc4-114">**Effective  October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="dabc4-115">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="dabc4-115">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="dabc4-116">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="dabc4-116">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="dabc4-117">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="dabc4-117">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="dabc4-118">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dabc4-118">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="dabc4-119">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="dabc4-119">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="dabc4-120">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-120">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="dabc4-121">Microsoft 團隊現在有一個專門針對醫療保健組織的護理協調解決方案，可協助他們提供最佳的患者治療。</span><span class="sxs-lookup"><span data-stu-id="dabc4-121">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="dabc4-122">Crux 的 [護理協調] 解決方案是「Microsoft 團隊患者 app」，它是一種與電子健康情況)  (記錄整合的第一個參與方索引標籤 app，可使用快速的醫療保健互通性資源 ([FHIR](https://www.hl7.org/fhir/)) 介面，讓 Microsoft 團隊在內容中進行臨床共同作業及通訊。</span><span class="sxs-lookup"><span data-stu-id="dabc4-122">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="dabc4-123">您可以使用 HL7v2 和 FHIR 等現有的健康資料標準，將患者 app 連線至您的 EHR 系統，以與主要獨立軟體廠商 (Isv) 連線，來與主流獨立軟體廠商進行介面。</span><span class="sxs-lookup"><span data-stu-id="dabc4-123">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="dabc4-124">具備下列業界領袖的 Microsoft 合作夥伴，可與團隊建立電子健康情況記錄整合：</span><span class="sxs-lookup"><span data-stu-id="dabc4-124">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="dabc4-125">透過其 [CMI](https://datica.com/compliant-managed-integration/) 提供的 Datica () </span><span class="sxs-lookup"><span data-stu-id="dabc4-125">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="dabc4-126">Infor Cloverleaf (透過 [INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) </span><span class="sxs-lookup"><span data-stu-id="dabc4-126">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="dabc4-127">透過 [R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/) Redox () </span><span class="sxs-lookup"><span data-stu-id="dabc4-127">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="dabc4-128">Dapasoft (到 [COROLAR FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) </span><span class="sxs-lookup"><span data-stu-id="dabc4-128">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="dabc4-129">嘗試針對醫療保健提供者組織實施 Microsoft 團隊的 EHR 整合與互通性合作夥伴，必須為患者 app 提供與醫療保健供應商組織 EHR 系統的安全且驗證的連線。</span><span class="sxs-lookup"><span data-stu-id="dabc4-129">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="dabc4-130">這可讓單向 (只會將相關患者記錄的) 流程讀入患者 app。</span><span class="sxs-lookup"><span data-stu-id="dabc4-130">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="dabc4-131">患者 app 可瞭解 FHIR 格式，因此合作夥伴也負責將匯總資料從各種其他格式（例如 HL7v2 等）轉換成 FHIR DSTU2 或 STU3。</span><span class="sxs-lookup"><span data-stu-id="dabc4-131">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![圖示醒目提示護理協調與共同作業](../../media/ehr-1.png)

<br>

<span data-ttu-id="dabc4-133">患者 app 整合了電子醫療記錄 (EHR) 系統，並能讓護理提供者在小組的安全平臺中即時與患者護理進行溝通。</span><span class="sxs-lookup"><span data-stu-id="dabc4-133">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams' secure platform.</span></span> <span data-ttu-id="dabc4-134">患者 app 是護理協調區域中的第一項主要投資，目的是解決下列難題：</span><span class="sxs-lookup"><span data-stu-id="dabc4-134">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="dabc4-135">在工作中保持不太高效，且透過患者體驗進行重要溝通</span><span class="sxs-lookup"><span data-stu-id="dabc4-135">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="dabc4-136">產生管理負擔的各自為政資訊</span><span class="sxs-lookup"><span data-stu-id="dabc4-136">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="dabc4-137">使用複雜及零散共同作業工具的臨床醫師中的不滿</span><span class="sxs-lookup"><span data-stu-id="dabc4-137">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="dabc4-138">低效率的人員間護理協調，可能會燒壞太昂貴的臨床時間</span><span class="sxs-lookup"><span data-stu-id="dabc4-138">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="dabc4-139">Microsoft 團隊可讓醫生、臨床醫師、護士及其他員工高效地進行共同作業：</span><span class="sxs-lookup"><span data-stu-id="dabc4-139">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="dabc4-140">成為可在 Office 檔上運作及共同合作的單一虛擬化小組的一部分</span><span class="sxs-lookup"><span data-stu-id="dabc4-140">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="dabc4-141">在其他患者需要注意的持續交談</span><span class="sxs-lookup"><span data-stu-id="dabc4-141">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="dabc4-142">使用頻道搭配索引標籤來組織其工作，並提供可讓他們釘選資訊來源之索引標籤的其他說明</span><span class="sxs-lookup"><span data-stu-id="dabc4-142">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="dabc4-143">將頻道會議與團隊的威力、影片、螢幕共用、錄製和工具功能配合使用，以管理每日會議</span><span class="sxs-lookup"><span data-stu-id="dabc4-143">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="dabc4-144">使用患者 app 來彙整必須監視的高風險患者清單，並從 EHR 系統中拉回其最新詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dabc4-144">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="dabc4-145">患者 app 本身會將下列功能新增至 Microsoft 團隊：</span><span class="sxs-lookup"><span data-stu-id="dabc4-145">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="dabc4-146">能夠在單一頻道中建立多個患者清單。</span><span class="sxs-lookup"><span data-stu-id="dabc4-146">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="dabc4-147">透過可設定的欄來查看和排序顯示的患者資訊的功能。</span><span class="sxs-lookup"><span data-stu-id="dabc4-147">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="dabc4-148">透過小組範本自動進行應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="dabc4-148">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="dabc4-149">可在 iOS 版和 Android 版的團隊 App 中使用，可在適用于 iOS 和 Android 的小組應用程式中，使用 Microsoft 團隊網頁與桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="dabc4-149">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="dabc4-150">透過分析一致性語句來支援 FHIR DSTU2 和 STU3 版本。</span><span class="sxs-lookup"><span data-stu-id="dabc4-150">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="dabc4-151">針對其使用者介面上的所有視圖和搜尋動作的審核記錄，以保護每個 HIPAA 指引中的 PHI。</span><span class="sxs-lookup"><span data-stu-id="dabc4-151">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="dabc4-152">患者 app 是在小組擴充性平臺上建立，並利用 [定位點架構] 在頻道中顯示豐富的患者內容。</span><span class="sxs-lookup"><span data-stu-id="dabc4-152">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="dabc4-153">若要深入瞭解其他團隊 app 和平臺本身，請參閱 [Microsoft 團隊相關應用程式](/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-153">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="dabc4-154">患者 app 是私人預覽，且 FHIR 介面在 Beta 版中。</span><span class="sxs-lookup"><span data-stu-id="dabc4-154">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="dabc4-155">已發行的版本不應該是向後相容的。</span><span class="sxs-lookup"><span data-stu-id="dabc4-155">Released versions are not expected to be backward compatible.</span></span>

![桌面和行動裝置上患者 app 的螢幕擷取畫面](../../media/ehr-2.png)

<span data-ttu-id="dabc4-157">如需詳細資訊，請參閱將 [電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md) 。</span><span class="sxs-lookup"><span data-stu-id="dabc4-157">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="teams-templates"></a><span data-ttu-id="dabc4-158">團隊範本</span><span class="sxs-lookup"><span data-stu-id="dabc4-158">Teams templates</span></span>

<span data-ttu-id="dabc4-159">我們已開發新的範本來建立小組，以套用至醫院設定。</span><span class="sxs-lookup"><span data-stu-id="dabc4-159">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="dabc4-160">如此一來，您就能更輕鬆地建立可讓醫療保健工人在不同部門或 wards 中與患者共同合作的小組。</span><span class="sxs-lookup"><span data-stu-id="dabc4-160">This makes it easier to create teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="dabc4-161">請參閱 [開始使用醫療保健組織的團隊範本](healthcare-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-161">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="dabc4-162">團隊可以針對內部部門（例如心臟病科）或 [護理 wards] 或 [開發中的其他範本] 進行啟動。</span><span class="sxs-lookup"><span data-stu-id="dabc4-162">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="lists-app"></a><span data-ttu-id="dabc4-163">清單應用程式</span><span class="sxs-lookup"><span data-stu-id="dabc4-163">Lists app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="dabc4-164">團隊中的 [清單] 應用程式可協助團隊追蹤資訊並組織工作。</span><span class="sxs-lookup"><span data-stu-id="dabc4-164">The Lists app in Teams helps teams track information and organize work.</span></span> <span data-ttu-id="dabc4-165">App 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dabc4-165">The app is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="dabc4-166">清單可以從預先定義的範本中從頭開始建立，或是將資料匯入 Excel。</span><span class="sxs-lookup"><span data-stu-id="dabc4-166">Lists can be created from scratch, from predefined templates, or by importing data to Excel.</span></span>

<span data-ttu-id="dabc4-167">護理小組可以使用患者範本來開始使用。</span><span class="sxs-lookup"><span data-stu-id="dabc4-167">Care teams can use the Patients template to get started.</span></span> <span data-ttu-id="dabc4-168">他們可以建立清單來追蹤患者的需求和狀態。</span><span class="sxs-lookup"><span data-stu-id="dabc4-168">They can create lists to track the needs and status of patients.</span></span> <span data-ttu-id="dabc4-169">您可以在 Excel 試算表中加入現有的患者資料，在小組中建立清單。</span><span class="sxs-lookup"><span data-stu-id="dabc4-169">Existing patient data on Excel spreadsheets can be brought in to create a list in Teams.</span></span> <span data-ttu-id="dabc4-170">這些清單可用來進行諸如舍入與患者監視等案例，以協助您共同處理護理。</span><span class="sxs-lookup"><span data-stu-id="dabc4-170">These lists can be used for scenarios such as rounds and patient monitoring to coordinate care.</span></span>

<span data-ttu-id="dabc4-171">例如，電荷護士在小組中建立一個患者清單，其中包含所有的護理小組成員。</span><span class="sxs-lookup"><span data-stu-id="dabc4-171">For example, a charge nurse creates a patient list in a team that includes all care team members.</span></span> <span data-ttu-id="dabc4-172">在舍入期間，護理小組會在行動裝置上存取小組，並更新清單中的患者資訊，讓小組中的每個人都可以查看，以保持同步處理。在您的舍入會話中，護理小組會收集以討論及評估重要健康情況效能指標，以確保患者位於正確的 glide 路徑上以進行放電，他們可以使用大型顯示畫面上的小組共用此資訊。</span><span class="sxs-lookup"><span data-stu-id="dabc4-172">During rounds, the care team access Teams on their mobile devices and update patient information in the list, which everyone on the team can view to stay in sync. At rounding sessions where the care team gathers to discuss and evaluate key health performance metrics to ensure a patient is on the right glide path to discharge, they can share this information using Teams on a large display screen.</span></span> <span data-ttu-id="dabc4-173">保護不在網站上的小組成員可以遠端加入。</span><span class="sxs-lookup"><span data-stu-id="dabc4-173">Care team members who aren't on site can join remotely.</span></span>

<span data-ttu-id="dabc4-174">以下是為患者舍入設定的範例清單。</span><span class="sxs-lookup"><span data-stu-id="dabc4-174">Here's an example list which was set up for patient rounding.</span></span>

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者舍入範例清單的螢幕擷取畫面":::

<span data-ttu-id="dabc4-176">若要深入瞭解，請參閱 [在團隊中管理貴組織的清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-176">To learn more, see [Manage the Lists app for your organization in Teams](../../manage-lists-app.md).</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="dabc4-177">安全訊息</span><span class="sxs-lookup"><span data-stu-id="dabc4-177">Secure Messaging</span></span>

<span data-ttu-id="dabc4-178">安全訊息支援在護理小組中共同作業，包括幾個新功能：</span><span class="sxs-lookup"><span data-stu-id="dabc4-178">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="dabc4-179">郵件寄件者可以為郵件設定特殊的優先順序，所以收件者會反復收到通知，直到他們閱讀郵件為止。</span><span class="sxs-lookup"><span data-stu-id="dabc4-179">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="dabc4-180">郵件寄件者可以要求讀信回條，當郵件收件者閱讀郵件時，就會收到通知。</span><span class="sxs-lookup"><span data-stu-id="dabc4-180">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="dabc4-181">總之，這些功能可讓您更快速地注意到緊急訊息，並確信郵件已被接收和讀取。</span><span class="sxs-lookup"><span data-stu-id="dabc4-181">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="dabc4-182">使用這些功能的新的護理團隊可以在每個患者上建立。</span><span class="sxs-lookup"><span data-stu-id="dabc4-182">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="dabc4-183">這些功能都是以原則為基礎，而且可以指派給個人或整個團隊。</span><span class="sxs-lookup"><span data-stu-id="dabc4-183">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="dabc4-184">如需進一步的詳細資料，請參閱 [開始使用醫療保健組織的安全訊息原則](messaging-policies-hc.md) 。</span><span class="sxs-lookup"><span data-stu-id="dabc4-184">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="dabc4-185">此外，與安全訊息相關的功能，也是由醫療保健組織聯盟的其他租使用者，允許更豐富的租使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="dabc4-185">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="dabc4-186"> (請參閱 [在 Microsoft 團隊) 中的 [管理外部存取 (同盟) ](../../manage-external-access.md) ]。</span><span class="sxs-lookup"><span data-stu-id="dabc4-186">(See [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="dabc4-187">第一線員工工作人員整合</span><span class="sxs-lookup"><span data-stu-id="dabc4-187">Firstline Worker integration</span></span>

<span data-ttu-id="dabc4-188">Microsoft 團隊會與第一線員工工作人員整合，這可以用來共同調整倒班人員的功能。</span><span class="sxs-lookup"><span data-stu-id="dabc4-188">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span> <span data-ttu-id="dabc4-189">請參閱 [在 Microsoft 團隊中管理貴組織的倒班應用程式](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dabc4-189">See [Manage the Shifts app for your organization in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
