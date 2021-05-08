---
title: 將升級升級至 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 根據您的目前部署Microsoft Teams最佳升級路徑商務用 Skype路徑。
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
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282370"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="13ddf-103">執行升級概觀</span><span class="sxs-lookup"><span data-stu-id="13ddf-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="13ddf-104">![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")</span><span class="sxs-lookup"><span data-stu-id="13ddf-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="13ddf-105">本文是升級歷程的部署與執行階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="13ddf-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="13ddf-106">先決條件規劃活動</span><span class="sxs-lookup"><span data-stu-id="13ddf-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13ddf-107">繼續進行升級實施之前，請確認您從規劃升級開始閱讀規劃內容，以確保您[](upgrade-plan-journey.md)已完成所有先決條件規劃活動。</span><span class="sxs-lookup"><span data-stu-id="13ddf-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="13ddf-108">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="13ddf-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="13ddf-109">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="13ddf-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="13ddf-110">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="13ddf-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="13ddf-111">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="13ddf-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="13ddf-112">已規劃使用者試驗</span><span class="sxs-lookup"><span data-stu-id="13ddf-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="13ddf-113">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="13ddf-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="13ddf-114">準備您的組織</span><span class="sxs-lookup"><span data-stu-id="13ddf-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="13ddf-115">選擇升級起點</span><span class="sxs-lookup"><span data-stu-id="13ddf-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="13ddf-116">您執行升級至 Teams的步驟取決於您目前部署商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="13ddf-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="13ddf-117">根據您的目前環境，選擇您的起點：</span><span class="sxs-lookup"><span data-stu-id="13ddf-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="13ddf-118">**如果您要從** 商務用 Skype Online 升級至 Teams，請遵循從 商務用 Skype Online 升級至 [Teams。](./upgrade-to-teams-execute-skypeforbusinessonline.md)</span><span class="sxs-lookup"><span data-stu-id="13ddf-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="13ddf-119">**如果您是從** 商務用 Skype 內部部署環境升級，您必須執行一些額外步驟，在將使用者移至 Teams 之前，先設定內部部署與線上環境之間的連線。</span><span class="sxs-lookup"><span data-stu-id="13ddf-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="13ddf-120">詳細資訊，請參閱將[內部商務用 Skype升級至 Teams。](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="13ddf-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]