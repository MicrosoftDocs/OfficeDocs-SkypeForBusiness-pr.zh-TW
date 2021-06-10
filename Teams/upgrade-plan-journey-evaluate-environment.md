---
title: 升級至 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解正確評估您目前環境以升級到 Teams。
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
ms.openlocfilehash: aeb236edddea69c1c112b695c9323de19da46092
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282200"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="de2a4-103">升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="de2a4-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="de2a4-104">![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="de2a4-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="de2a4-105">本文是升級過程中技術整備階段的一部分，此階段是您與使用者整備階段同時完成的活動。</span><span class="sxs-lookup"><span data-stu-id="de2a4-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="de2a4-106">在繼續進行之前，請確認您已完成上述階段的活動：</span><span class="sxs-lookup"><span data-stu-id="de2a4-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="de2a4-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="de2a4-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="de2a4-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="de2a4-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="de2a4-109">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="de2a4-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="de2a4-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="de2a4-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="de2a4-111">本文概觀了正確評估您目前環境以執行Teams。</span><span class="sxs-lookup"><span data-stu-id="de2a4-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="de2a4-112">您可以評估您的環境，找出會影響整體部署的風險和需求。</span><span class="sxs-lookup"><span data-stu-id="de2a4-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="de2a4-113">您可以事先識別這些專案，以調整您的規劃以推動成功。</span><span class="sxs-lookup"><span data-stu-id="de2a4-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="de2a4-114">探索問卷簡介</span><span class="sxs-lookup"><span data-stu-id="de2a4-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="de2a4-115">若要在 OKRs (達成) ，您先前會做出重要的服務決策。</span><span class="sxs-lookup"><span data-stu-id="de2a4-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="de2a4-116">下一個步驟是執行環境探索，評估與 IT 基礎結構、網路和作業相關的所有層面，以確認貴組織已準備好執行解決方案。</span><span class="sxs-lookup"><span data-stu-id="de2a4-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="de2a4-117">探索是規劃您進行探索之旅時，您首先採取的重要Teams。</span><span class="sxs-lookup"><span data-stu-id="de2a4-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="de2a4-118">環境探索必須包含網路就緒性評定，以確保您的網路能夠支援升級至Teams。</span><span class="sxs-lookup"><span data-stu-id="de2a4-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="de2a4-119">您可以執行環境的詳細探索，以進一步瞭解其目前狀態，並揭露任何困難，或甚至是可能封鎖者，以執行您的Teams推出。</span><span class="sxs-lookup"><span data-stu-id="de2a4-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="de2a4-120">您將技術風險識別為環境評估與採用準備評估的一部分，並針對每個已識別的風險制定緩解計畫。</span><span class="sxs-lookup"><span data-stu-id="de2a4-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="de2a4-121">您應該在風險註冊簿中加入這項資訊。</span><span class="sxs-lookup"><span data-stu-id="de2a4-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="de2a4-122">所有與現有共同作業基礎結構Microsoft 365或Office 365組織、網路、端點、作業、採用和準備相關的事項，都包含在環境探索問卷中。</span><span class="sxs-lookup"><span data-stu-id="de2a4-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="de2a4-123">請與專案小組合作，盡可能提供要求的資訊，以利規劃活動。</span><span class="sxs-lookup"><span data-stu-id="de2a4-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="de2a4-124">[問卷分為](upgrade-plan-journey-discovery-questionnaire.md)下列各節，以確認貴組織在幾個主要Teams部署準備就緒：</span><span class="sxs-lookup"><span data-stu-id="de2a4-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="de2a4-125">Microsoft 365或Office 365組織詳細資料</span><span class="sxs-lookup"><span data-stu-id="de2a4-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="de2a4-126">現有的共同合作平臺摘要</span><span class="sxs-lookup"><span data-stu-id="de2a4-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="de2a4-127">共同合作平臺部署詳細資料</span><span class="sxs-lookup"><span data-stu-id="de2a4-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="de2a4-128">網路和存取Microsoft 365或Office 365服務</span><span class="sxs-lookup"><span data-stu-id="de2a4-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="de2a4-129">端點</span><span class="sxs-lookup"><span data-stu-id="de2a4-129">Endpoints</span></span>
- <span data-ttu-id="de2a4-130">營運</span><span class="sxs-lookup"><span data-stu-id="de2a4-130">Operations</span></span>
- <span data-ttu-id="de2a4-131">採用與準備</span><span class="sxs-lookup"><span data-stu-id="de2a4-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="de2a4-132">首先，您可以將問卷複製到Microsoft Word檔中。</span><span class="sxs-lookup"><span data-stu-id="de2a4-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="de2a4-133">嘗試回答所有問題，並捕獲所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="de2a4-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="de2a4-134">決策點</span><span class="sxs-lookup"><span data-stu-id="de2a4-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="de2a4-135">神秘負責完成環境評定嗎？</span><span class="sxs-lookup"><span data-stu-id="de2a4-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="de2a4-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="de2a4-136">Next step</span></span></td><td><ul><li><span data-ttu-id="de2a4-137">記錄環境評定的結果。</span><span class="sxs-lookup"><span data-stu-id="de2a4-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="de2a4-138">Project小組</span><span class="sxs-lookup"><span data-stu-id="de2a4-138">Project team</span></span>

<span data-ttu-id="de2a4-139">請確保您已與專案小組的合適人員合作。</span><span class="sxs-lookup"><span data-stu-id="de2a4-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="de2a4-140">驗證在招募專案專案關係 [人中完成的步驟](upgrade-enlist-stakeholders.md)。</span><span class="sxs-lookup"><span data-stu-id="de2a4-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="de2a4-141">評估您的環境之後，請繼續進行下一個步驟： [準備您的服務](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="de2a4-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>