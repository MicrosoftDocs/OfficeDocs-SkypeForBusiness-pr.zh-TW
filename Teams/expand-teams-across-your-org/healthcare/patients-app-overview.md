---
title: '適用于團隊管理員的患者應用程式 '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: 適用于團隊管理員的患者應用程式
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749555"
---
# <a name="patients-app-overview"></a><span data-ttu-id="2dfc6-103">患者 app 概述</span><span class="sxs-lookup"><span data-stu-id="2dfc6-103">Patients app overview</span></span>

<span data-ttu-id="2dfc6-104">患者應用程式是適用于所有團隊使用者的 Microsoft 團隊商店應用程式。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="2dfc6-105">應用程式可讓患者護理小組（例如護士、醫生、社會工人）彙整和審閱患者的清單，這些案例包括從倒圓角和 interdisciplinary 團隊會議到一般患者監控等。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="2dfc6-106">App 有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="2dfc6-106">The app has two modes:</span></span> 

- <span data-ttu-id="2dfc6-107">透過 FHIR 連接至 EMRs 的 EMR 連線模式。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="2dfc6-108">EMR 連線模式 app 會保留在私人預覽中，感興趣的客戶或系統管理員可能會透過在 teamsforhealthcare@service.microsoft.com 中除去 Microsoft 電子郵件，並提供其 Office 365 租使用者的相關資訊，以要求存取 app。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="2dfc6-109">[手動] 模式可讓護理小組手動新增/攜帶患者資訊。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="2dfc6-110">您可以在 [團隊 app] 商店中找到該應用程式，預設會供使用者下載，且位於公用預覽中。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="2dfc6-111">在 Microsoft 團隊中，您可以使用[應用程式設定原則](../../teams-app-setup-policies.md)，將 app 限制在某些使用者區段中</span><span class="sxs-lookup"><span data-stu-id="2dfc6-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="2dfc6-112">用法範例</span><span class="sxs-lookup"><span data-stu-id="2dfc6-112">Usage example</span></span>

<span data-ttu-id="2dfc6-113">在醫學 wards 的每個倒班期間，臨床醫師在 nursing 站上收集，以在 ward 中與患者進行最新的更新。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="2dfc6-114">它們會醒目提示重要的度量單位（不一定是醫療，或是其在患者病歷上的明確），並確保患者在適當的 glide 路徑上，以根據其診斷來放電。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="2dfc6-115">為了圍繞這些患者，[費用護士] 會在新增所有臨床醫師的小組中設定患者應用程式，並將患者新增至患者清單。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="2dfc6-116">在舍入期間，在行動裝置上的患者 access Microsoft 團隊和患者應用程式的護士與其他護理 givers，並更新其裝置上的相關患者資訊，並在護理小組中的其他人都能看到這些更新與記事，以及保持同步處理。一天兩次，在班次的開始和結束，他們也會有多位 displicinary 小組會議，透過患者清單進行，並使用患者 App 來建立每個患者的相關資訊，並使用大型顯示畫面上的患者 app 分享有關每個患者的資訊。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="2dfc6-117">通常情況下，某些臨床醫師可能也會在遠端撥入這些團隊會議，而且仍是討論的一部分。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="2dfc6-118">設定患者 app</span><span class="sxs-lookup"><span data-stu-id="2dfc6-118">Configure Patients app</span></span>

<span data-ttu-id="2dfc6-119">如需如何準備您的環境以使用 EMR 模式患者 app 的詳細資訊，請參閱將[電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="2dfc6-120">您也需要[在 Microsoft 團隊中查看 [管理應用程式設定原則](../../teams-app-setup-policies.md)]，以便為您的組織啟用患者 app。</span><span class="sxs-lookup"><span data-stu-id="2dfc6-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="2dfc6-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="2dfc6-121">Related topics</span></span>

[<span data-ttu-id="2dfc6-122">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2dfc6-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
