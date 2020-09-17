---
title: 將商務用 Skype 混合式部署升級至團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從商務用 Skype 混合式部署將您的組織升級至 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72786dc2ef5cefe7c3c87c5a376cc01d93a2c22c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940513"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="85f96-103">從商務用 Skype 混合式部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="85f96-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="85f96-104">![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="85f96-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="85f96-105">本文是升級歷程部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="85f96-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="85f96-106">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="85f96-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="85f96-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="85f96-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="85f96-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="85f96-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="85f96-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="85f96-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="85f96-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="85f96-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="85f96-111">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="85f96-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="85f96-112">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="85f96-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="85f96-113">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="85f96-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="85f96-114">如果您已部署商務用 Skype 或 Microsoft Lync 內部部署，且已在與您的 Microsoft 365 或 Office 365 組織進行混合式部署中進行設定，且您的組織想要使用多個共存模式（或全式），將其升級至團隊，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="85f96-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="85f96-115">針對升級歷程，您必須將使用者移至商務用 Skype Online (（如果尚未在) 線上進行），然後再指派適當的共存與升級模式。</span><span class="sxs-lookup"><span data-stu-id="85f96-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="85f96-116">步驟1：將使用者移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="85f96-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="85f96-117">此步驟適用于目前駐留內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="85f96-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="85f96-118">如需將這些使用者移至商務用 Skype Online 的詳細資訊，請參閱 [將使用者從內部部署移至商務用 Skype online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="85f96-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="85f96-119">步驟2：指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="85f96-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="85f96-120">將使用者移至商務用 Skype Online 之後，您就可以根據貴組織所選擇的升級歷程，指派適當的共存模式。</span><span class="sxs-lookup"><span data-stu-id="85f96-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="85f96-121">如需詳細資訊，請參閱 [設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence) 及 [TeamsUpgradePolicy：管理移植與共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="85f96-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85f96-122">在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中，您就可以執行步驟 1 (將使用者移至商務用 Skype Online) 並步驟 2 (將使用者升級至團隊) 一步。</span><span class="sxs-lookup"><span data-stu-id="85f96-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="85f96-123">在發行商務用 Skype Server 2019 之後，將會提供更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="85f96-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="85f96-124">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="85f96-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="85f96-125">如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統，Microsoft 將是您的公開交換電話網絡 (PSTN) 提供者—並假設您已完成電話號碼移植，將您的使用者升級至團隊後，就會自動將入站 PSTN 通話轉場給小組。</span><span class="sxs-lookup"><span data-stu-id="85f96-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="85f96-126">如果通話方案無法使用，或您想要使用現有的 PSTN 連線提供者，您必須將企業語音部署（或使用您現有內部部署或雲端連接器版本的混合式語音部署）轉換為 Microsoft 手機系統 Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="85f96-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="85f96-127">若要將您的使用者升級至小組，請參閱 [手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="85f96-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
