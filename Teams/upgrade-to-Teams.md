---
title: 升級至 Microsoft 團隊 |商務用 Skype 小組藍圖
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 根據您目前的商務用 Skype 部署，決定 Microsoft 團隊的最佳升級路徑。
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
ms.openlocfilehash: 4a0e8ca9356704d471320e4474f48270375aea2d
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868490"
---
# <a name="overview"></a><span data-ttu-id="9aac0-103">概觀</span><span class="sxs-lookup"><span data-stu-id="9aac0-103">Overview</span></span>

<span data-ttu-id="9aac0-104">![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="9aac0-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9aac0-105">本文是升級歷程的部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="9aac0-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="9aac0-106">先決條件規劃活動</span><span class="sxs-lookup"><span data-stu-id="9aac0-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9aac0-107">在繼續進行升級前，請確認您已閱讀規劃內容開始規劃[升級](upgrade-plan-journey.md)，以確保您已完成所有必備的規劃活動。</span><span class="sxs-lookup"><span data-stu-id="9aac0-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="9aac0-108">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="9aac0-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9aac0-109">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="9aac0-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9aac0-110">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="9aac0-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9aac0-111">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="9aac0-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="9aac0-112">已規劃使用者試驗</span><span class="sxs-lookup"><span data-stu-id="9aac0-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="9aac0-113">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="9aac0-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="9aac0-114">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="9aac0-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="9aac0-115">選擇您的升級起始點</span><span class="sxs-lookup"><span data-stu-id="9aac0-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="9aac0-116">您針對團隊進行升級所採取的步驟，取決於您目前的商務用 Skype 部署：</span><span class="sxs-lookup"><span data-stu-id="9aac0-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="9aac0-117">根據您目前的環境，選擇您的起始點：</span><span class="sxs-lookup"><span data-stu-id="9aac0-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="9aac0-118">**如果您要從商務用 Skype online 升級至小組**，請按照[從商務用 skype Online 升級至團隊](https://aka.ms/SkypeToTeams-UpgradeOnline)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="9aac0-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="9aac0-119">**如果您是從商務用 Skype 內部部署環境升級**，您必須執行一些額外的步驟，才能在您的內部部署與線上環境之間設定連線，然後再將您的使用者移至團隊。</span><span class="sxs-lookup"><span data-stu-id="9aac0-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="9aac0-120">如需詳細資訊，請參閱[將商務用 Skype 內部部署升級至團隊](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)。</span><span class="sxs-lookup"><span data-stu-id="9aac0-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
