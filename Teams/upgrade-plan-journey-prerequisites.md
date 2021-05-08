---
title: 升級至 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用此指南來瞭解在組織中部署Teams的先決條件及環境相依性
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282160"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="9ed51-103">環境的先決條件及環境相依性Teams</span><span class="sxs-lookup"><span data-stu-id="9ed51-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="9ed51-104">![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="9ed51-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="9ed51-105">本文是升級過程中技術整備階段的一部分，此階段是您與使用者整備階段同時完成的活動。</span><span class="sxs-lookup"><span data-stu-id="9ed51-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="9ed51-106">繼續進行之前，請確認您已完成上述階段的活動：</span><span class="sxs-lookup"><span data-stu-id="9ed51-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="9ed51-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="9ed51-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9ed51-108">已定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="9ed51-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="9ed51-109">瞭解共同使用和商務用 Skype互通性Teams</span><span class="sxs-lookup"><span data-stu-id="9ed51-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="9ed51-110">已選擇升級旅程</span><span class="sxs-lookup"><span data-stu-id="9ed51-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="9ed51-111">Teams合併多個Microsoft 365 Office 365服務，因此取決於這些服務的正確實現與運作。</span><span class="sxs-lookup"><span data-stu-id="9ed51-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="9ed51-112">這些服務包括但不限於線上、SharePoint、Exchange Online和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="9ed51-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="9ed51-113">雖然並非所有服務都為必填專案，我們強烈建議您全部實現。</span><span class="sxs-lookup"><span data-stu-id="9ed51-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="9ed51-114">如果您選擇不實行特定服務，將會影響貴組織Teams的功能。</span><span class="sxs-lookup"><span data-stu-id="9ed51-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="9ed51-115">例如，雖然不需要執行 SharePoint Online，Teams 確實會仰賴 SharePoint Online 來使用群組交談中的檔案共用等特定功能，因此不執行這項服務將會減少透過用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="9ed51-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="9ed51-116">請參閱下列文章以瞭解先決條件，以及Teams與其他技術互動的方式：</span><span class="sxs-lookup"><span data-stu-id="9ed51-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="9ed51-117">如果貴組織尚未部署任何Microsoft 365或Office 365，請參閱[開始使用](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="9ed51-118">如果貴組織尚未新增或為網域新增或Microsoft 365驗證Office 365，請參閱[網域常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="9ed51-119">如果貴組織尚未將身分識別同步Azure Active Directory，請參閱在 Microsoft Teams 中識別[Microsoft Teams。](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="9ed51-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="9ed51-120">如果您的組織沒有 Exchange Online，請參閱[了解 Exchange 和 Microsoft Teams 如何互動](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="9ed51-121">如果您的組織沒有 SharePoint Online，請參閱[了解 SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="9ed51-122">若要瞭解如何[Microsoft 365群組Microsoft Teams互動](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="9ed51-123">如果貴組織是教育機構，而且您使用學生資訊系統，[請參閱](/schooldatasync)在部署 Microsoft 學校資料同步處理之前Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9ed51-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="9ed51-124">如果貴組織考慮公用交換電話網路 (PSTN) 通話選項，請參閱語音 - 電話系統 和[PSTN](cloud-voice-landing-page.md)連接、哪[](calling-plan-landing-page.md)一個通話方案適合您，以及 電話系統[路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed51-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="9ed51-125">若要在推出前確保所有網路需求都符合Teams，請參閱準備貴組織的網路[Microsoft Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="9ed51-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="9ed51-126">如果您目前使用 商務用 Skype Online Connector 來管理您的服務，您必須移至 PowerShell 模組Teams並更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="9ed51-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="9ed51-127">請參閱[從線上連接器商務用 Skype移至 powerShell Teams模組以](teams-powershell-move-from-sfbo.md)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9ed51-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="9ed51-128">確認您的環境符合所有適用的先決條件之後，請評估您目前[Teams。](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="9ed51-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>