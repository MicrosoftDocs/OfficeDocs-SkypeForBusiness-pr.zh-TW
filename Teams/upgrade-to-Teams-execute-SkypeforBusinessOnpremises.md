---
title: 將商務用 Skype 內部部署升級為 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從內部部署Microsoft Teams組織商務用 Skype內部部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115551"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="7d31f-103">從內部部署商務用 Skype升級至Teams</span><span class="sxs-lookup"><span data-stu-id="7d31f-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="7d31f-104">![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="7d31f-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="7d31f-105">本文是升級歷程的部署與執行階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="7d31f-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="7d31f-106">繼續進行之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="7d31f-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="7d31f-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="7d31f-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7d31f-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="7d31f-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="7d31f-109">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="7d31f-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="7d31f-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="7d31f-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="7d31f-111">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="7d31f-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="7d31f-112">準備您的組織</span><span class="sxs-lookup"><span data-stu-id="7d31f-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="7d31f-113">進行試驗</span><span class="sxs-lookup"><span data-stu-id="7d31f-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="7d31f-114">如果您已經部署 商務用 Skype 或 Microsoft Lync 內部部署，且貴組織想要選擇性地升級至 Microsoft Teams ，請遵循本文中的指引，使用多種共存模式或全功能。</span><span class="sxs-lookup"><span data-stu-id="7d31f-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="7d31f-115">步驟 1：部署混合式連接</span><span class="sxs-lookup"><span data-stu-id="7d31f-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="7d31f-116">將使用者升級至 Teams的關鍵先決條件是部署混合式連接。</span><span class="sxs-lookup"><span data-stu-id="7d31f-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="7d31f-117">詳細資訊，請參閱在 商務用 Skype Server 與[商務用 Skype 之間部署混合式連線](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="7d31f-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="7d31f-118">步驟 2：為貴組織執行您所選擇的升級歷程</span><span class="sxs-lookup"><span data-stu-id="7d31f-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="7d31f-119">完成混合式設定之後，您可以規劃將使用者移至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7d31f-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="7d31f-120">詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7d31f-120">For more information, see:</span></span>

- <span data-ttu-id="7d31f-121">[TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7d31f-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="7d31f-122">[將使用者從內部部署移至 商務用 Skype Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="7d31f-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="7d31f-123">電話系統Teams升級</span><span class="sxs-lookup"><span data-stu-id="7d31f-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="7d31f-124">從內部部署電話系統轉換至 Teams 將允許您使用 電話系統 直接路由 ("直接路由") 或 Microsoft 提供的 Microsoft 365 或 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="7d31f-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="7d31f-125">如果您不是使用通話方案，您必須將企業語音部署切換至 電話系統直接路由，作為升級至 Teams。</span><span class="sxs-lookup"><span data-stu-id="7d31f-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="7d31f-126">詳細資訊，請參閱[直接路由的其他電話系統考慮](./direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="7d31f-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="7d31f-127">如果您打算使用通話方案，請參閱我們的指引，將電話號碼轉接到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7d31f-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>