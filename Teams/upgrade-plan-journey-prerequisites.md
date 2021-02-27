---
title: 升級到 Teams 的先決條件及環境相依性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用此指南以瞭解在組織中部署 Teams 的先決條件及環境相依性
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
ms.openlocfilehash: b0ad5716dbbe1925a93f4fbfadca7084e39a9599
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347804"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="281e1-103">Teams 的先決條件與環境相依性</span><span class="sxs-lookup"><span data-stu-id="281e1-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="281e1-104">![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級階段，強調技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="281e1-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="281e1-105">本文是升級過程中的技術整備階段之一，此為您與使用者整備階段同時完成的活動。</span><span class="sxs-lookup"><span data-stu-id="281e1-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="281e1-106">繼續進行之前，請確認您已完成上述階段的活動：</span><span class="sxs-lookup"><span data-stu-id="281e1-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="281e1-107">已招募專案專案關係人</span><span class="sxs-lookup"><span data-stu-id="281e1-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="281e1-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="281e1-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="281e1-109">瞭解商務用 Skype 和 Teams 的共存和互通性</span><span class="sxs-lookup"><span data-stu-id="281e1-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="281e1-110">已選擇您的升級旅程</span><span class="sxs-lookup"><span data-stu-id="281e1-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="281e1-111">Teams 結合多個 Microsoft 365 和 Office 365 服務，因此必須依賴這些服務的正確執行與運作。</span><span class="sxs-lookup"><span data-stu-id="281e1-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="281e1-112">這些服務包括但不限於 SharePoint Online、Exchange Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="281e1-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="281e1-113">雖然並非所有服務都為必填專案，但我們強烈建議您執行所有服務。</span><span class="sxs-lookup"><span data-stu-id="281e1-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="281e1-114">如果您選擇不執行特定服務，將會影響 Teams 可以提供貴組織的功能。</span><span class="sxs-lookup"><span data-stu-id="281e1-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="281e1-115">例如，雖然不需要執行 SharePoint Online，但 Teams 確實仰賴 SharePoint Online 提供群組交談中的檔案共用等特定功能，因此不執行此服務將會減少透過用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="281e1-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="281e1-116">請參閱下列文章以瞭解先決條件，以及 Teams 如何與其他技術互動：</span><span class="sxs-lookup"><span data-stu-id="281e1-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="281e1-117">如果貴組織尚未部署任何 Microsoft 365 或 Office 365 工作負載 [，請參閱開始使用](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="281e1-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="281e1-118">如果貴組織尚未新增或安裝 Microsoft 365 或 Office 365 的驗證網域，請參閱 [網域常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="281e1-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="281e1-119">如果貴組織尚未將身分識別同步到 Azure Active Directory，請參閱 Microsoft Teams 中的身分識別 [模型和驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="281e1-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="281e1-120">如果貴組織沒有 Exchange Online，請參閱瞭解 Exchange 和 [Microsoft Teams 的互動方式](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="281e1-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="281e1-121">如果貴組織沒有 SharePoint Online，請參閱瞭解 [SharePoint Online](SharePoint-OneDrive-interact.md)和商務用 OneDrive 如何與 Microsoft Teams 互動。</span><span class="sxs-lookup"><span data-stu-id="281e1-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="281e1-122">若要瞭解 [Microsoft 365 群組和 Microsoft Teams 的互動方式](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="281e1-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="281e1-123">如果貴組織是教育機構，而且您使用學生資訊系統，請參閱部署 Microsoft Teams 之前歡迎使用 [Microsoft 學校](https://docs.microsoft.com/schooldatasync) 資料同步處理。</span><span class="sxs-lookup"><span data-stu-id="281e1-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="281e1-124">如果貴組織考慮公用交換電話網路 (PSTN) 通話選項，請參閱語音 - 電話系統與 [PSTN](cloud-voice-landing-page.md)連接、 [哪](calling-plan-landing-page.md)一種通話方案適合您，以及電話 [系統直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="281e1-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="281e1-125">若要在推出 Teams 之前確保所有網路需求都獲得滿足，請參閱準備貴組織的 [Microsoft Teams 網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="281e1-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="281e1-126">如果您目前使用商務用 Skype Online Connector 來管理服務，您必須移至 Teams PowerShell 模組並更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="281e1-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="281e1-127">詳細資訊 [請參閱從商務用 Skype Online Connector](teams-powershell-move-from-sfbo.md) 移至 Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="281e1-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="281e1-128">確認您的環境符合所有適用的先決條件之後，請評估 [您目前](upgrade-plan-journey-evaluate-environment.md)Teams 的環境。</span><span class="sxs-lookup"><span data-stu-id="281e1-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
