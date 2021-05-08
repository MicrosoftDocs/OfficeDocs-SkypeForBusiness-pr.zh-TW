---
title: 準備升級至 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解組織準備共同合作和雲端語音服務的需求，Teams。
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
ms.openlocfilehash: 2ad5887c50b15efc2dcddd000a8f117c2f350ac5
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282184"
---
# <a name="prepare-your-service-for-upgrading-to-teams"></a><span data-ttu-id="51901-103">準備升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="51901-103">Prepare your service for upgrading to Teams</span></span>

<span data-ttu-id="51901-104">![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="51901-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="51901-105">本文是升級過程中技術整備階段的一部分，此階段是一項與使用者整備階段同時完成的活動。</span><span class="sxs-lookup"><span data-stu-id="51901-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="51901-106">繼續進行之前，請確認您已完成上述階段的活動：</span><span class="sxs-lookup"><span data-stu-id="51901-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="51901-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="51901-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="51901-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="51901-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="51901-109">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="51901-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="51901-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="51901-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="51901-111">本文概觀說明組織準備共同合作和雲端語音服務Teams。</span><span class="sxs-lookup"><span data-stu-id="51901-111">This article gives an overview of the requirements for preparing your organization for collaboration and cloud voice services with Teams.</span></span> <span data-ttu-id="51901-112">通過正確準備，您可以確定準備好要提供這些功能給貴組織。</span><span class="sxs-lookup"><span data-stu-id="51901-112">By preparing properly, you can be sure you're ready to provide these capabilities to your organization.</span></span>

## <a name="onboarding-checklists-and-landing-pages-for-microsoft-teams-rollout"></a><span data-ttu-id="51901-113">登陸檢查清單和登陸頁面Microsoft Teams推出</span><span class="sxs-lookup"><span data-stu-id="51901-113">Onboarding checklists and landing pages for Microsoft Teams rollout</span></span>

<span data-ttu-id="51901-114">下列檢查清單和登陸頁面會流覽在組織中部署Microsoft Teams步驟：</span><span class="sxs-lookup"><span data-stu-id="51901-114">The following checklists and landing pages walk you through the steps for deploying Microsoft Teams in your organization:</span></span>

- [<span data-ttu-id="51901-115">準備Microsoft 365或Office 365 Teams</span><span class="sxs-lookup"><span data-stu-id="51901-115">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

- [<span data-ttu-id="51901-116">設定Teams核心功能</span><span class="sxs-lookup"><span data-stu-id="51901-116">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

- [<span data-ttu-id="51901-117">準備您的網路</span><span class="sxs-lookup"><span data-stu-id="51901-117">Prepare your network</span></span>](prepare-network.md)

- [<span data-ttu-id="51901-118">聊天、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="51901-118">Chat, teams, channels, and apps</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

- [<span data-ttu-id="51901-119">會議和音訊會議</span><span class="sxs-lookup"><span data-stu-id="51901-119">Meetings and audio conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

- [<span data-ttu-id="51901-120">電話系統 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="51901-120">Phone System and PSTN connectivity options</span></span>](cloud-voice-landing-page.md)


<span data-ttu-id="51901-121">這些檢查清單內的工作和活動是核心的「工作」專案，適用于每個使用共同作業和語音功能部署Teams。</span><span class="sxs-lookup"><span data-stu-id="51901-121">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of collaboration and voice capabilities with Teams.</span></span> <span data-ttu-id="51901-122">您可以自訂檢查清單，以包含您自己的行程中特有的活動Teams工作。</span><span class="sxs-lookup"><span data-stu-id="51901-122">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

<span data-ttu-id="51901-123">使用提供的檢查清單來追蹤每個個別活動和工作的狀態，並確保您未略過任何重要步驟。</span><span class="sxs-lookup"><span data-stu-id="51901-123">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="51901-124">每個活動包含所需動作的詳細描述，以及可用於完成該活動之額外資訊的參照。</span><span class="sxs-lookup"><span data-stu-id="51901-124">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="51901-125">雖然我們建議您依序遵循檢查清單，但確切的順序會視您的部署範圍，以及您環境的組組和複雜度而決定。</span><span class="sxs-lookup"><span data-stu-id="51901-125">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="51901-126">他們組織起來可支援「greenfield」Teams部署 (之前沒有 商務用 Skype Online 目前狀態) ，或從 商務用 Skype Online 升級至 Teams。</span><span class="sxs-lookup"><span data-stu-id="51901-126">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or upgrading from Skype for Business Online to Teams.</span></span> <span data-ttu-id="51901-127">如果您是從 商務用 Skype Online 升級，您可能已經完成其中一些活動，現在可以忽略這些活動。</span><span class="sxs-lookup"><span data-stu-id="51901-127">If you're upgrading from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="51901-128">當您以每個網站為基礎啟動使用者時，強烈建議您使用 Voice [ (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)) 網站啟用 Playbook) 做為這些檢查清單的補充指南。</span><span class="sxs-lookup"><span data-stu-id="51901-128">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="51901-129">大部分的設定設定在 Teams 和 商務用 Skype 之間商務用 Skype常見。</span><span class="sxs-lookup"><span data-stu-id="51901-129">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="51901-130">您可以使用系統管理Microsoft Teams設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="51901-130">You use the Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="51901-131">決策點</span><span class="sxs-lookup"><span data-stu-id="51901-131">Decision point</span></span></td><td><ul><li><span data-ttu-id="51901-132">神秘將負責監督上機檢查清單的完成情況？</span><span class="sxs-lookup"><span data-stu-id="51901-132">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="51901-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="51901-133">Next steps</span></span></td><td><ul><li><span data-ttu-id="51901-134">下載上機檢查清單。</span><span class="sxs-lookup"><span data-stu-id="51901-134">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="51901-135">依照貴組織的部署計畫，逐步完成上載檢查清單專案。</span><span class="sxs-lookup"><span data-stu-id="51901-135">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="51901-136">繼續上機</span><span class="sxs-lookup"><span data-stu-id="51901-136">Continue onboarding</span></span>

<span data-ttu-id="51901-137">完成這份檢查清單之後，請繼續進行下一個步驟： [進行使用者試驗](pilot-essentials.md)</span><span class="sxs-lookup"><span data-stu-id="51901-137">After you complete this checklist, proceed to the next step: [Conduct a user pilot](pilot-essentials.md)</span></span>

[//]: # (@Turgay，我將下一個段落注釋掉，因為這是雲端語音專用。)
<!--
As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site to cloud voice, and help ensure that you plan and execute important site-specific activities.
-->