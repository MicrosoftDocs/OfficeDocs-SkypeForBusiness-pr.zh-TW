---
title: '適用于團隊管理員的患者應用程式 '
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
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 適用于團隊管理員的患者應用程式
ms.openlocfilehash: 0c37909e6a72ed83c2c499eb3b7de449a9239f80
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361473"
---
# <a name="patients-app-overview"></a><span data-ttu-id="59b80-103">病患應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="59b80-103">Patients app overview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59b80-104">**2020年10月15日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="59b80-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="59b80-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="59b80-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="59b80-106">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="59b80-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="59b80-107">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="59b80-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="59b80-108">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="59b80-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="59b80-109">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="59b80-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="59b80-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="59b80-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="59b80-111">患者應用程式是適用于所有團隊使用者的 Microsoft 團隊商店應用程式。</span><span class="sxs-lookup"><span data-stu-id="59b80-111">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="59b80-112">App 啟用由臨床工人所組成的患者護理小組 (例如，護士、醫生、社交員工) 可以彙整及查看病人的患者清單，包括從倒圓角和 interdisciplinary 團隊會議到一般患者監視。</span><span class="sxs-lookup"><span data-stu-id="59b80-112">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>

<span data-ttu-id="59b80-113">App 有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="59b80-113">The app has two modes:</span></span>

- <span data-ttu-id="59b80-114">透過 FHIR 連接至 EMRs 的 EMR 連線模式。</span><span class="sxs-lookup"><span data-stu-id="59b80-114">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="59b80-115">EMR 連線模式 app 會保留在私人預覽中，感興趣的客戶或系統管理員可能會透過在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 中除去 microsoft 電子郵件，並提供其 Microsoft 365 組織的相關資訊，以要求存取 app。</span><span class="sxs-lookup"><span data-stu-id="59b80-115">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) with information about their Microsoft 365 organization.</span></span>
- <span data-ttu-id="59b80-116">[手動] 模式可讓護理小組手動新增/攜帶患者資訊。</span><span class="sxs-lookup"><span data-stu-id="59b80-116">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="59b80-117">您可以在 [小組 app] 商店中找到應用程式，讓使用者在私人預覽中下載。</span><span class="sxs-lookup"><span data-stu-id="59b80-117">The application is available in the Teams app store for end users to download in private preview.</span></span> <span data-ttu-id="59b80-118">在團隊中，您可以使用 [app 設定原則](../../teams-app-setup-policies.md) ，將 app 限制在特定的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="59b80-118">The app can be restricted to certain sections of users using [app setup policies](../../teams-app-setup-policies.md) in Teams.</span></span> <span data-ttu-id="59b80-119">若要取得 app 的存取權，您的租使用者必須是技術採納計畫的一部分 (輕觸) 。</span><span class="sxs-lookup"><span data-stu-id="59b80-119">To get access to the app, your tenant needs to be part of the Technology Adoption Program (TAP).</span></span> <span data-ttu-id="59b80-120">請在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 中放下我們的電子郵件，以啟動處理常式來要求存取權。</span><span class="sxs-lookup"><span data-stu-id="59b80-120">Please drop us an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) to start the process to request access.</span></span>

## <a name="usage-example"></a><span data-ttu-id="59b80-121">用法範例</span><span class="sxs-lookup"><span data-stu-id="59b80-121">Usage example</span></span>

<span data-ttu-id="59b80-122">在醫學 wards 的每個倒班期間，臨床醫師在 nursing 站上收集，以在 ward 中與患者進行最新的更新。</span><span class="sxs-lookup"><span data-stu-id="59b80-122">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="59b80-123">它們會醒目提示重要的度量標準， (不需要醫療，或是在患者的病歷) 上明確，並確保患者在適當的 glide 路徑上，以根據其診斷而放電。</span><span class="sxs-lookup"><span data-stu-id="59b80-123">They highlight the key critical metrics (not necessarily medical or that it's explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="59b80-124">為了圍繞這些患者，[費用護士] 會在新增所有臨床醫師的小組中設定患者應用程式，並將患者新增至患者清單。</span><span class="sxs-lookup"><span data-stu-id="59b80-124">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="59b80-125">在舍入期間，在行動裝置上的患者 access Microsoft 團隊和患者應用程式的護士與其他護理 givers，並在其裝置上更新相關的患者資訊，並在護理小組中的其他人都能看到這些更新與記事，並保持同步處理。每天兩次，在班次的開始和結束時，他們也會有多項專業團隊會議，透過患者清單進行，並使用患者 app 來建立每個患者的相關資訊，並使用大型顯示畫面上的患者 app 分享有關每個患者的資訊。</span><span class="sxs-lookup"><span data-stu-id="59b80-125">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-disciplinary team meetings to go over the patient list and use the Patients app to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="59b80-126">通常情況下，某些臨床醫師可能也會在遠端撥入這些團隊會議，而且仍是討論的一部分。</span><span class="sxs-lookup"><span data-stu-id="59b80-126">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span>

## <a name="configure-patients-app"></a><span data-ttu-id="59b80-127">設定患者 app</span><span class="sxs-lookup"><span data-stu-id="59b80-127">Configure Patients app</span></span>

<span data-ttu-id="59b80-128">如需如何準備您的環境以使用 EMR 模式患者 app 的詳細資訊，請參閱將 [電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="59b80-128">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="59b80-129">您也需要 [在 Microsoft 團隊中查看 [管理應用程式設定原則](../../teams-app-setup-policies.md) ]，以便為您的組織啟用患者 app。</span><span class="sxs-lookup"><span data-stu-id="59b80-129">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<span data-ttu-id="59b80-130">如需使用者如何存取並將患者 App 安裝至他們擁有或管理之小組的相關資訊，請參閱 [Microsoft 團隊患者快速入門](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。</span><span class="sxs-lookup"><span data-stu-id="59b80-130">For information on how your end users can access and install the Patients App to a team that they own or manage, see [Get started with Microsoft Teams Patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).</span></span>

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="59b80-131">常見問題 (常見問題) </span><span class="sxs-lookup"><span data-stu-id="59b80-131">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="59b80-132">**患者應用程式資料儲存在哪裡？**</span><span class="sxs-lookup"><span data-stu-id="59b80-132">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="59b80-133">使用者在患者 app 中輸入的所有資料（包括欄/欄位架構），在清單中輸入的實際資料以及清單專案 (（亦即患者) ）都儲存在 secure 相容性 Exchange Online 基礎結構中。</span><span class="sxs-lookup"><span data-stu-id="59b80-133">All of the data entered by end users into the Patients app, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="59b80-134">所有資料都儲存在與小組相關聯的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="59b80-134">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="59b80-135">這個架構可讓患者 App 輕鬆地完成資料派駐、政府雲端支援 (未來的) 以及 eDiscovery 支援等其他合規性/資訊保護功能。</span><span class="sxs-lookup"><span data-stu-id="59b80-135">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="59b80-136">患者 app 會在團隊範圍中運作。</span><span class="sxs-lookup"><span data-stu-id="59b80-136">The Patients app operates in a team scope.</span></span> <span data-ttu-id="59b80-137">您將需要安裝每個團隊的 app 實例。</span><span class="sxs-lookup"><span data-stu-id="59b80-137">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="59b80-138">**我可以從哪裡取得患者應用程式？**</span><span class="sxs-lookup"><span data-stu-id="59b80-138">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="59b80-139">如果患者 app 由其系統管理員啟用，任何使用者都可以移至 [小組] app 商店，並將患者 app 新增至他們所屬的小組。</span><span class="sxs-lookup"><span data-stu-id="59b80-139">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="59b80-140">如需詳細資訊，請參閱 [在 Microsoft 團隊中管理 app 設定原則](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="59b80-140">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="59b80-141">**我可以在小組中有多個患者應用程式實例，因為我的 ward/單元的運作方式為何？**</span><span class="sxs-lookup"><span data-stu-id="59b80-141">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="59b80-142">目前，您只能針對特定團隊安裝一個患者應用程式實例，且僅適用于 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="59b80-142">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="59b80-143">不過，在應用程式中，可以建立多個清單來處理多聲道或隔離/分隔案例。</span><span class="sxs-lookup"><span data-stu-id="59b80-143">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="59b80-144">根據預設，小組中的所有成員都會有權存取 [一般] 頻道中的 [患者] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="59b80-144">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="59b80-145">**我可以從患者 app 匯出所有資料嗎？**</span><span class="sxs-lookup"><span data-stu-id="59b80-145">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="59b80-146">目前尚不提供此功能，但即將推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="59b80-146">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="59b80-147">**因為這個 app 可容納 PHI，所以是否有審核來防止未經授權的存取或合規性遵從管理法規？**</span><span class="sxs-lookup"><span data-stu-id="59b80-147">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="59b80-148">是的，就是。</span><span class="sxs-lookup"><span data-stu-id="59b80-148">Yes, there is.</span></span> <span data-ttu-id="59b80-149">Microsoft 團隊使用者在患者 app 上執行的每個單一 UI 動作都會在安全性與合規性中心進行審核並提供。</span><span class="sxs-lookup"><span data-stu-id="59b80-149">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="59b80-150">詳細資料請見 [患者 app 的審核記錄](patients-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="59b80-150">The details are explained in [Audit logs for Patients app](patients-audit.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="59b80-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="59b80-151">Related topics</span></span>

[<span data-ttu-id="59b80-152">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59b80-152">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
