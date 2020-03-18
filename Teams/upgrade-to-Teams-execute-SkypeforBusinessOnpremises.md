---
title: 將商務用 Skype 內部部署升級至 Microsoft 團隊 |部署 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 從商務用 Skype 內部部署升級至團隊的考慮。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6815c805c9f5bcf47d6ee88a6c43c559b932d3
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706643"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="1826c-103">從商務用 Skype 內部部署升級到團隊</span><span class="sxs-lookup"><span data-stu-id="1826c-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="1826c-104">![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="1826c-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1826c-105">本文是升級歷程的部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="1826c-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1826c-106">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="1826c-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="1826c-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="1826c-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1826c-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="1826c-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1826c-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="1826c-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1826c-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="1826c-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1826c-111">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="1826c-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="1826c-112">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="1826c-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="1826c-113">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="1826c-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="1826c-114">如果您已部署商務用 Skype 或 Microsoft Lync 內部部署，且您的組織想要以選擇性升級至 Microsoft 團隊，請遵循本文中的指導方針，只要使用多個共存模式（或多功能）。</span><span class="sxs-lookup"><span data-stu-id="1826c-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="1826c-115">步驟1：部署混合式連接</span><span class="sxs-lookup"><span data-stu-id="1826c-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="1826c-116">將您的使用者升級至小組所需的主要先決條件就是部署混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="1826c-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="1826c-117">如需詳細資訊，請參閱[在商務用 Skype Server 和商務用 Skype Online 之間部署混合式連接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="1826c-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="1826c-118">步驟2：針對您的組織執行您選擇的升級歷程</span><span class="sxs-lookup"><span data-stu-id="1826c-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="1826c-119">完成混合式設定之後，您可以規劃將使用者移至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1826c-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="1826c-120">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1826c-120">For more information, see:</span></span>

- <span data-ttu-id="1826c-121">[TeamsUpgradePolicy：管理遷移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="1826c-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="1826c-122">[將使用者從內部部署移至商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="1826c-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="1826c-123">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="1826c-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="1826c-124">從內部部署電話系統過渡至團隊可讓您充分利用手機系統直通路由（「直接路由」）或 Microsoft 提供的 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="1826c-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="1826c-125">如果您使用的不是 Office 365 中的通話方案，您必須將企業語音部署轉場轉換為「手機系統」直接路由，成為團隊的升級的一部分。</span><span class="sxs-lookup"><span data-stu-id="1826c-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="1826c-126">如需詳細資訊，請參閱[手機系統直接路由的其他考慮](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="1826c-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="1826c-127">如果您打算在 Office 365 中使用通話方案，請參閱我們關於將您的[電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="1826c-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>