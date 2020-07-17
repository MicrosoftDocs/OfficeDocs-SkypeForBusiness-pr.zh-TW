---
title: Microsoft 團隊升級 |環境評估、探索問題
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 使用本指導方針，瞭解如何正確評估您目前的環境以升級至團隊的需求。
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
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158741"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="f2266-103">升級至團隊之前先評估您的環境</span><span class="sxs-lookup"><span data-stu-id="f2266-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="f2266-104">![升級歷程圖表，強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段，重點放在技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="f2266-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="f2266-105">本文是您升級歷程的技術就緒階段（您可以與使用者準備階段並行完成的活動）的一部分。</span><span class="sxs-lookup"><span data-stu-id="f2266-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="f2266-106">繼續之前，請先確認您已從先前階段完成這些活動：</span><span class="sxs-lookup"><span data-stu-id="f2266-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="f2266-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="f2266-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f2266-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="f2266-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="f2266-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="f2266-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="f2266-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="f2266-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="f2266-111">本文將提供正確評估您目前的運營團隊環境需求的概覽。</span><span class="sxs-lookup"><span data-stu-id="f2266-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="f2266-112">您可以評估您的環境，找出會影響整體部署的風險與需求。</span><span class="sxs-lookup"><span data-stu-id="f2266-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="f2266-113">透過預先識別這些專案，您可以調整您的規劃來促進成功。</span><span class="sxs-lookup"><span data-stu-id="f2266-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="f2266-114">探索問卷問卷簡介</span><span class="sxs-lookup"><span data-stu-id="f2266-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="f2266-115">為了達到您的目標金鑰結果（OKRs），您先前已進行重要的服務決策。</span><span class="sxs-lookup"><span data-stu-id="f2266-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="f2266-116">下一步是執行環保探索，以評估與您 IT 基礎結構、網路和作業相關的所有方面，以確認貴組織已準備好要實施方案。</span><span class="sxs-lookup"><span data-stu-id="f2266-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="f2266-117">探索是您在規劃團隊歷程時所採取的第一項重要步驟之一。</span><span class="sxs-lookup"><span data-stu-id="f2266-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="f2266-118">環境探索必須包含網路準備情況評估，以確保您的網路可支援升級至團隊。</span><span class="sxs-lookup"><span data-stu-id="f2266-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="f2266-119">您可以對您的環境進行詳細探索，以更清楚地瞭解其目前狀態，並揭示任何困難或甚至更重要，也就是可能的封鎖程式可執行您的小組推出。</span><span class="sxs-lookup"><span data-stu-id="f2266-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="f2266-120">您可以在環境評估與採納準備情況評估中識別技術風險，並針對每個已識別的風險開發緩解方案。</span><span class="sxs-lookup"><span data-stu-id="f2266-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="f2266-121">您應該將此資訊納入風險登記簿中。</span><span class="sxs-lookup"><span data-stu-id="f2266-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="f2266-122">與您現有的共同作業基礎結構及 Microsoft 365 或 Office 365 組織、網路、端點、作業以及採納及準備相關的所有相關事項，都包含在環境探索問卷問卷中。</span><span class="sxs-lookup"><span data-stu-id="f2266-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="f2266-123">與您的專案小組合作，以盡可能詳細地提供要求的資訊，以協助您的規劃活動。</span><span class="sxs-lookup"><span data-stu-id="f2266-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="f2266-124">[問卷](upgrade-plan-journey-discovery-questionnaire.md)分為下列各節，以確認貴組織在幾個主要區域中的小組部署準備就緒：</span><span class="sxs-lookup"><span data-stu-id="f2266-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="f2266-125">Microsoft 365 或 Office 365 組織詳細資料</span><span class="sxs-lookup"><span data-stu-id="f2266-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="f2266-126">現有的共同作業平臺摘要</span><span class="sxs-lookup"><span data-stu-id="f2266-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="f2266-127">共同作業平臺部署詳細資料</span><span class="sxs-lookup"><span data-stu-id="f2266-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="f2266-128">網路和存取 Microsoft 365 或 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="f2266-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="f2266-129">端點</span><span class="sxs-lookup"><span data-stu-id="f2266-129">Endpoints</span></span>
- <span data-ttu-id="f2266-130">營運</span><span class="sxs-lookup"><span data-stu-id="f2266-130">Operations</span></span>
- <span data-ttu-id="f2266-131">採納與準備</span><span class="sxs-lookup"><span data-stu-id="f2266-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="f2266-132">您可以從將問卷問卷複製到 Microsoft Word 檔開始。</span><span class="sxs-lookup"><span data-stu-id="f2266-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="f2266-133">當您在移動時，請嘗試回答所有問題，並捕獲所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2266-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="f2266-134">決策點</span><span class="sxs-lookup"><span data-stu-id="f2266-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="f2266-135">誰負責完成環境評估？</span><span class="sxs-lookup"><span data-stu-id="f2266-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="f2266-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f2266-136">Next step</span></span></td><td><ul><li><span data-ttu-id="f2266-137">記錄環境評估的結果。</span><span class="sxs-lookup"><span data-stu-id="f2266-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="f2266-138">專案小組</span><span class="sxs-lookup"><span data-stu-id="f2266-138">Project team</span></span>

<span data-ttu-id="f2266-139">確定您已將合適的人員用於您的專案小組。</span><span class="sxs-lookup"><span data-stu-id="f2266-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="f2266-140">確認您在[登記專案干係人](upgrade-enlist-stakeholders.md)時所完成的步驟。</span><span class="sxs-lookup"><span data-stu-id="f2266-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="f2266-141">在您評估您的環境之後，請繼續執行下一個步驟：[準備您的服務](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="f2266-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
