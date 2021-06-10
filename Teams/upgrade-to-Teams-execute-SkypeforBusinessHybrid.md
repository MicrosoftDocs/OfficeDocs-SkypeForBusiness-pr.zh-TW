---
title: 將商務用 Skype混合式部署升級至 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從混合式部署Microsoft Teams升級商務用 Skype組織。
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104019"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="892a9-103">從混合式部署商務用 Skype升級至Teams</span><span class="sxs-lookup"><span data-stu-id="892a9-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="892a9-104">![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="892a9-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="892a9-105">本文是升級歷程的部署與執行階段之一。</span><span class="sxs-lookup"><span data-stu-id="892a9-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="892a9-106">繼續進行之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="892a9-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="892a9-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="892a9-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="892a9-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="892a9-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="892a9-109">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="892a9-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="892a9-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="892a9-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="892a9-111">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="892a9-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="892a9-112">準備您的組織</span><span class="sxs-lookup"><span data-stu-id="892a9-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="892a9-113">進行試驗</span><span class="sxs-lookup"><span data-stu-id="892a9-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="892a9-114">如果您已經部署 商務用 Skype 或 Microsoft Lync 內部部署，並且已與 Microsoft 365 或 Office 365 組織進行混合式部署，且貴組織想要選擇性地升級至 Teams，請遵循本文中的指引，使用多種共存模式或全內聯。</span><span class="sxs-lookup"><span data-stu-id="892a9-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="892a9-115">在任一升級過程中，如果使用者還沒有線上商務用 Skype，您必須將使用者移至 商務用 Skype Online (，然後指派適當的共存和升級模式) 然後指派他們適當的共存和升級模式。</span><span class="sxs-lookup"><span data-stu-id="892a9-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="892a9-116">步驟 1：將使用者移至 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="892a9-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="892a9-117">此步驟適用于目前位於內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="892a9-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="892a9-118">若要進一步將這些使用者移至線上商務用 Skype，請參閱將使用者從內部部署移至[商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="892a9-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="892a9-119">步驟 2：指派共存與升級模式</span><span class="sxs-lookup"><span data-stu-id="892a9-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="892a9-120">將使用者移至 商務用 Skype Online 之後，您可以根據貴組織所選擇的升級歷程，指派適當的共存模式。</span><span class="sxs-lookup"><span data-stu-id="892a9-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="892a9-121">詳細資訊，請參閱設定 [您的共存和升級設定](./setting-your-coexistence-and-upgrade-settings.md) 及 [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="892a9-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="892a9-122">使用 商務用 Skype Server 2019 和 商務用 Skype Server 2015 未來的累積更新，您將能夠執行步驟 1 (將使用者移動到 商務用 Skype Online) 和步驟 2 (將使用者升級至 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="892a9-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="892a9-123">2019 年 2019 商務用 Skype Server之後，將會提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="892a9-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="892a9-124">電話系統Teams升級</span><span class="sxs-lookup"><span data-stu-id="892a9-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="892a9-125">如果您要使用通話方案將 商務用 Skype 混合式部署切換到 電話系統，而 Microsoft 將會成為公用交換電話網路絡 (PSTN) 提供者 ，而且假設您已完成電話號碼轉口，將使用者升級為 Teams 會自動將內撥 PSTN 通話切換至 Teams。</span><span class="sxs-lookup"><span data-stu-id="892a9-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="892a9-126">如果通話方案無法使用，或您打算使用現有的 PSTN 連接提供者，您必須將使用現有內部部署或雲端連接器版的企業語音部署或混合式語音部署，轉換至 Microsoft 電話 System Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="892a9-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="892a9-127">若要將使用者升級至 Teams，請參閱直接路由的其他電話系統[考慮](./direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="892a9-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>