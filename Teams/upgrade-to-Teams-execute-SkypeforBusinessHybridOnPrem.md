---
title: 從商務用 Skype 混合式或內部部署 (Microsoft 團隊) 升級至團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 從商務用 Skype 混合式或內部部署升級至團隊時的考慮。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185217"
---
<span data-ttu-id="5ea50-103">![升級歷程圖表, 強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段, 重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="5ea50-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5ea50-104">本文是升級歷程部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ea50-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="5ea50-105">繼續之前, 請確認您已完成下列活動:</span><span class="sxs-lookup"><span data-stu-id="5ea50-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="5ea50-106">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="5ea50-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="5ea50-107">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="5ea50-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="5ea50-108">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="5ea50-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="5ea50-109">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="5ea50-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="5ea50-110">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="5ea50-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="5ea50-111">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="5ea50-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="5ea50-112">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="5ea50-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="5ea50-113">從商務用 Skype 混合式或內部部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="5ea50-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="5ea50-114">如果您已部署商務用 Skype 或 Microsoft Lync 內部部署, 且您的組織想要使用多個共存模式 (或全式), 請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="5ea50-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="5ea50-115">第一個步驟是設定與您的 Office 365 租使用者的混合式連線, 然後將您的使用者移至商務用 Skype Online, 並指派適當的共存和升級模式。</span><span class="sxs-lookup"><span data-stu-id="5ea50-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5ea50-116">商務用 Skype Online 將于2021年7月31日停用, 之後就不能再存取或支援。</span><span class="sxs-lookup"><span data-stu-id="5ea50-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="5ea50-117">若要最大限度取得效益並確保貴組織有適當的時間來實施升級, 我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="5ea50-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="5ea50-118">請記住, 成功的升級會將技術與使用者的就緒性相符, 因此請務必在您向 Microsoft 團隊流覽您的旅程時, 在本文中利用指導方針。</span><span class="sxs-lookup"><span data-stu-id="5ea50-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="5ea50-119">步驟 1: 部署混合式連接</span><span class="sxs-lookup"><span data-stu-id="5ea50-119">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="5ea50-120">將您的使用者升級至小組所需的主要先決條件就是部署混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="5ea50-120">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="5ea50-121">這可能會涉及針對現有的商務用 Skype 或 Lync 部署部署新的外部連線, 或只需將混合式關聯與您的 Office 365 租使用者進行配置。</span><span class="sxs-lookup"><span data-stu-id="5ea50-121">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="5ea50-122">如需詳細資訊, 請參閱 [在商務用 Skype 伺服器與商務用 Skype Online 之間部署混合式連接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="5ea50-122">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="5ea50-123">步驟 2: 將使用者移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5ea50-123">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="5ea50-124">完成混合式設定之後, 請將使用者移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="5ea50-124">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="5ea50-125">如需詳細資訊, 請參閱 [將使用者從內部部署移至商務用 Skype Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="5ea50-125">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="5ea50-126">步驟 3: 指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="5ea50-126">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="5ea50-127">將使用者移至商務用 Skype Online 之後, 您就可以根據貴組織所選擇的升級歷程, 指派適當的共存模式。</span><span class="sxs-lookup"><span data-stu-id="5ea50-127">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="5ea50-128">如需詳細資訊, 請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy: 管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="5ea50-128">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="5ea50-129">在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中, 您將能夠執行步驟 2 (將使用者移至商務用 Skype Online), 並在單一步驟中執行步驟 3 (升級使用者至小組)。</span><span class="sxs-lookup"><span data-stu-id="5ea50-129">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="5ea50-130">在發行商務用 Skype Server 2019 之後, 將會提供更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5ea50-130">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="5ea50-131">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="5ea50-131">Phone System and Teams upgrade</span></span>

<span data-ttu-id="5ea50-132">如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統, Microsoft 將是您的公用交換電話網絡 (PSTN) 供應商, 並假設您已完成電話號碼移植: 升級您的使用者以團隊會自動將入站 PSTN 通話轉場至團隊。</span><span class="sxs-lookup"><span data-stu-id="5ea50-132">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="5ea50-133">如果通話方案無法使用, 您需要將企業語音部署轉換為 Microsoft Phone 系統 Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="5ea50-133">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="5ea50-134">若要將您的使用者升級至小組, 請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5ea50-134">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
