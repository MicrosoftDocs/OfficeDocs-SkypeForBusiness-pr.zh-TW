---
title: 準備您的環境以升級至 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 在從商務用 Skype 升級至 Teams 之前，先驗證您的環境和網路準備狀態。
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
ms.openlocfilehash: f75d899f2b14915e265ce8d36c57daeaf0ce72d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119052"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="dd9d0-103">準備您的環境以升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="dd9d0-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="dd9d0-104">![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="dd9d0-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="dd9d0-105">本文是升級過程中技術整備階段的一部分，此階段是您與使用者整備階段同時完成的活動。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="dd9d0-106">繼續進行之前，請確認您已完成上述階段的活動：</span><span class="sxs-lookup"><span data-stu-id="dd9d0-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="dd9d0-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="dd9d0-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="dd9d0-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="dd9d0-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="dd9d0-109">瞭解商務用 Skype 和 Teams 的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="dd9d0-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="dd9d0-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="dd9d0-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="dd9d0-111">若要在貴組織中推動 Teams 升級成功，您必須驗證您目前的商務用 Skype 環境和您的網路準備狀態。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="dd9d0-112">準備您目前的環境，除了改善 Teams 中的使用者體驗品質之外，現在也有助於確保高品質的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="dd9d0-113">花時間規劃個別步驟有助於加速部署，並確保您未略過任何重要動作專案。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="dd9d0-114">在使用者準備準備的同時完成這些活動：</span><span class="sxs-lookup"><span data-stu-id="dd9d0-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="dd9d0-115">[準備您的 IT 員工](upgrade-prepare-IT-pros.md) ，協助確保他們擁有成功升級旅程所需的功能。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="dd9d0-116">確認您的環境 [符合所有先決條件](upgrade-plan-journey-prerequisites.md)，並瞭解 Microsoft 365 或 Office 365 服務和 Teams 之間的相依性。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="dd9d0-117">[使用範例問卷](upgrade-plan-journey-evaluate-environment.md) 來執行環境探索，以確認貴組織準備好要成功升級 Teams，以評估您的環境。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="dd9d0-118">[規劃、準備您的網路](prepare-network.md) ，並針對您的網路採取任何必要的補救步驟，以支援 Teams 工作負載。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="dd9d0-119">[使用登錄檢查](upgrade-prepare-environment-prepare-service.md) 清單準備服務以推出，確保您的 Teams 組組已準備就緒，可支援將使用者從商務用 Skype 移轉至 Teams。</span><span class="sxs-lookup"><span data-stu-id="dd9d0-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>