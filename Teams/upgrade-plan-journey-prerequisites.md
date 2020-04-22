---
title: Microsoft 團隊先決條件 |相依性採納升級
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
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
ms.openlocfilehash: f340146225d7e386233e727bb8c5d181db7f15fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776718"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="4db3c-103">團隊的先決條件與環境相依性</span><span class="sxs-lookup"><span data-stu-id="4db3c-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="4db3c-104">![升級歷程圖表，強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段，重點放在技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="4db3c-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="4db3c-105">本文是您升級歷程的技術就緒階段（您可以與使用者準備階段並行完成的活動）的一部分。</span><span class="sxs-lookup"><span data-stu-id="4db3c-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="4db3c-106">繼續之前，請先確認您已從先前階段完成這些活動：</span><span class="sxs-lookup"><span data-stu-id="4db3c-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="4db3c-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="4db3c-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="4db3c-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="4db3c-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="4db3c-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="4db3c-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="4db3c-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="4db3c-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="4db3c-111">團隊會結合多個 Office 365 服務，因此請視這些服務的正確實現與運作而定。</span><span class="sxs-lookup"><span data-stu-id="4db3c-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="4db3c-112">這些服務包括（但不限於） SharePoint Online、Exchange Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4db3c-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="4db3c-113">雖然並非所有服務都是必要的，但我們強烈建議您實現所有服務。</span><span class="sxs-lookup"><span data-stu-id="4db3c-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="4db3c-114">如果您選擇不執行某些服務，會影響團隊可為您的組織提供的功能。</span><span class="sxs-lookup"><span data-stu-id="4db3c-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="4db3c-115">例如，雖然您不需要執行 SharePoint Online，但小組會針對特定的功能（例如群組交談中的檔案共用）而依賴 SharePoint Online，因此不需要執行此服務就能減少透過用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="4db3c-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="4db3c-116">請參閱下列文章以瞭解先決條件，以及團隊如何與其他技術互動：</span><span class="sxs-lookup"><span data-stu-id="4db3c-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="4db3c-117">如果您的組織尚未部署任何 Office 365 工作負荷，請參閱[商務用 Office 365 快速入門](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-117">If your organization hasn't deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="4db3c-118">如果您的組織尚未新增或設定 Office 365 的驗證網域，請參閱[驗證您的 office 365 網域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-118">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="4db3c-119">如果您的組織尚未將身分識別與 Azure Active Directory 同步處理，請參閱[Microsoft 團隊中的身分識別模型和驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="4db3c-120">如果您的組織是沒有 Exchange Online 的<sup>1</sup>，請參閱[瞭解 Exchange 與 Microsoft 團隊互動的方式](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="4db3c-121">如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="4db3c-122">瞭解[microsoft 365 群組與 Microsoft 團隊互動](Office-365-groups.md)的方式。</span><span class="sxs-lookup"><span data-stu-id="4db3c-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="4db3c-123">如果您的組織是教育機構，且您是使用學生資訊系統，請在部署 Microsoft 團隊之前先[部署學校資料同步](https://docs.microsoft.com/schooldatasync)處理。</span><span class="sxs-lookup"><span data-stu-id="4db3c-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="4db3c-124">確認您的環境符合所有適用的先決條件之後，請[評估您目前的團隊環境](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="4db3c-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
