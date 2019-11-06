---
title: 將商務用 Skype 混合式部署升級至 Microsoft 團隊 |通向
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 從商務用 Skype 混合式部署升級至團隊的考慮。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7729cd65ff5d58d348229c4ec5ec6182f06aa5de
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "36235901"
---
<span data-ttu-id="b9d84-103">![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="b9d84-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b9d84-104">本文是升級歷程部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9d84-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b9d84-105">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="b9d84-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="b9d84-106">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="b9d84-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b9d84-107">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="b9d84-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b9d84-108">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="b9d84-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b9d84-109">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="b9d84-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b9d84-110">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="b9d84-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="b9d84-111">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="b9d84-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="b9d84-112">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="b9d84-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="b9d84-113">從商務用 Skype 混合式部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="b9d84-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="b9d84-114">如果您已部署商務用 Skype 或 Microsoft Lync 內部部署，且已在與您的 Office 365 租使用者混合式部署中進行設定，且貴組織想要使用多個專案升級至小組，請按照本文中的指導方針進行：共存模式（或全式）。</span><span class="sxs-lookup"><span data-stu-id="b9d84-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="b9d84-115">針對升級歷程，您必須將使用者移至商務用 Skype Online （如果尚未在線上），然後指派適當的共存與升級模式。</span><span class="sxs-lookup"><span data-stu-id="b9d84-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="b9d84-116">步驟1：將使用者移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b9d84-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="b9d84-117">此步驟適用于目前駐留內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="b9d84-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="b9d84-118">如需將這些使用者移至商務用 Skype Online 的詳細資訊，請參閱[將使用者從內部部署移至商務用 Skype online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="b9d84-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="b9d84-119">步驟2：指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="b9d84-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="b9d84-120">將使用者移至商務用 Skype Online 之後，您就可以根據貴組織所選擇的升級歷程，指派適當的共存模式。</span><span class="sxs-lookup"><span data-stu-id="b9d84-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="b9d84-121">如需詳細資訊，請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy：管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="b9d84-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="b9d84-122">在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中，您將能夠執行步驟1（將使用者移至商務用 Skype Online），並在單一步驟中執行步驟2（升級使用者至小組）。</span><span class="sxs-lookup"><span data-stu-id="b9d84-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="b9d84-123">在發行商務用 Skype Server 2019 之後，將會提供更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b9d84-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b9d84-124">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="b9d84-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b9d84-125">如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統，Microsoft 將是您的公用交換電話網絡（PSTN）供應商，並假設您已完成電話號碼移植：升級您的使用者以團隊會自動將入站 PSTN 通話轉場至團隊。</span><span class="sxs-lookup"><span data-stu-id="b9d84-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b9d84-126">如果無法使用通話方案，或是您想要使用現有的 PSTN 連線提供者，您必須轉換企業語音部署，或使用您現有內部部署或雲端連接器版本的混合式語音部署，以Microsoft Phone 系統 Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="b9d84-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b9d84-127">若要將您的使用者升級至小組，請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d84-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
