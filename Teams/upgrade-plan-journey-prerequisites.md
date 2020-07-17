---
title: Microsoft 團隊先決條件 |相依性採納升級
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指導方針來瞭解在貴組織中部署小組所需的先決條件與環境相依性
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
ms.openlocfilehash: 1199bacde9ed41152cde6054975963cfd5a19ae9
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158731"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="ecbdb-103">團隊的先決條件與環境相依性</span><span class="sxs-lookup"><span data-stu-id="ecbdb-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="ecbdb-104">![升級歷程圖表，強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段，重點放在技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="ecbdb-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ecbdb-105">本文是您升級歷程的技術就緒階段（您可以與使用者準備階段並行完成的活動）的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ecbdb-106">繼續之前，請先確認您已從先前階段完成這些活動：</span><span class="sxs-lookup"><span data-stu-id="ecbdb-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ecbdb-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="ecbdb-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ecbdb-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="ecbdb-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ecbdb-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="ecbdb-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ecbdb-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="ecbdb-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ecbdb-111">團隊結合了多個 Microsoft 365 和 Office 365 服務，因此依賴于這些服務的正確實現與運作。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="ecbdb-112">這些服務包括（但不限於） SharePoint Online、Exchange Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="ecbdb-113">雖然並非所有服務都是必要的，但我們強烈建議您實現所有服務。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="ecbdb-114">如果您選擇不執行某些服務，會影響團隊可為您的組織提供的功能。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="ecbdb-115">例如，雖然您不需要執行 SharePoint Online，但小組會針對特定的功能（例如群組交談中的檔案共用）而依賴 SharePoint Online，因此不需要執行此服務就能減少透過用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="ecbdb-116">請參閱下列文章以瞭解先決條件，以及團隊如何與其他技術互動：</span><span class="sxs-lookup"><span data-stu-id="ecbdb-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="ecbdb-117">如果您的組織尚未部署任何 Microsoft 365 或 Office 365 的工作負荷，請參閱[快速入門](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="ecbdb-118">如果您的組織尚未新增或設定 Microsoft 365 或 Office 365 的驗證網域，請參閱[網域常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="ecbdb-119">如果您的組織尚未將身分識別與 Azure Active Directory 同步處理，請參閱[Microsoft 團隊中的身分識別模型和驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="ecbdb-120">如果您的組織沒有 Exchange Online，請參閱[瞭解 exchange 與 Microsoft 團隊互動的方式](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="ecbdb-121">如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="ecbdb-122">瞭解[microsoft 365 群組與 Microsoft 團隊互動](Office-365-groups.md)的方式。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="ecbdb-123">如果您的組織是教育機構，且您使用的是學生資訊系統，請參閱在部署 Microsoft 團隊之前[歡迎使用 Microsoft 學校資料同步](https://docs.microsoft.com/schooldatasync)處理。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="ecbdb-124">如果您的組織正在考慮公用交換電話網絡（PSTN）通話選項，請參閱[語音電話系統和 PSTN](cloud-voice-landing-page.md)連線，[這是您最適合您](calling-plan-landing-page.md)的通話方案，以及[電話系統直式路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="ecbdb-125">若要確保在推出小組之前已符合所有的網路需求，請參閱[準備貴組織的 Microsoft 團隊網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="ecbdb-126">確認您的環境符合所有適用的先決條件之後，請[評估您目前的團隊環境](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbdb-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
