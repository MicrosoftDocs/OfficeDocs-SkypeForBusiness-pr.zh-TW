---
title: Microsoft 團隊訓練 |IT 支援系統管理問題
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何在您的組織中準備 IT 員工來部署和支援 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 15c7c38b31586d0eec73e34702d873514938020e
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085899"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="408b5-103">為您的 Microsoft 團隊準備 IT 員工</span><span class="sxs-lookup"><span data-stu-id="408b5-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="408b5-104">![升級歷程圖表，強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段，重點放在技術準備階段")</span><span class="sxs-lookup"><span data-stu-id="408b5-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="408b5-105">本文是您升級歷程的技術就緒階段（您可以與使用者準備階段並行完成的活動）的一部分。</span><span class="sxs-lookup"><span data-stu-id="408b5-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="408b5-106">繼續之前，請先確認您已從先前階段完成這些活動：</span><span class="sxs-lookup"><span data-stu-id="408b5-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="408b5-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="408b5-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="408b5-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="408b5-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="408b5-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="408b5-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="408b5-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="408b5-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="408b5-111">您的 Microsoft 365 或 Office 365 組織系統管理員、技術主管及支援中心都有責任推動高品質的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="408b5-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="408b5-112">這包括確保您的網路已準備好支援小組、為使用者設定小組，以及能夠有效地疑難排解並解決可能發生的問題。</span><span class="sxs-lookup"><span data-stu-id="408b5-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="408b5-113">與您的 IT 員工成員共用下列資源，並確認他們已準備好支援使用者，然後才能開始升級至團隊：</span><span class="sxs-lookup"><span data-stu-id="408b5-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="408b5-114">Microsoft 團隊的系統管理訓練</span><span class="sxs-lookup"><span data-stu-id="408b5-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="408b5-115">連絡商務產品的客戶支援 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="408b5-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="408b5-116">針對 Microsoft Teams 用戶端的連線問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="408b5-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="408b5-117">在 Microsoft 團隊的疑難排解中使用記錄檔</span><span class="sxs-lookup"><span data-stu-id="408b5-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="408b5-119">決策點</span><span class="sxs-lookup"><span data-stu-id="408b5-119">Decision points</span></span>|<ul><li><span data-ttu-id="408b5-120">您是否有任何可能參與部署和支援小組的支援人員？</span><span class="sxs-lookup"><span data-stu-id="408b5-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="408b5-121">您是否已開發在升級時加入其他人員的訓練計畫？</span><span class="sxs-lookup"><span data-stu-id="408b5-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="408b5-123">後續步驟</span><span class="sxs-lookup"><span data-stu-id="408b5-123">Next steps</span></span>|<ul><li><span data-ttu-id="408b5-124">確認 IT 人員擁有他們所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="408b5-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="408b5-125">在新功能發行時，請重新訪問您的訓練和準備方案。</span><span class="sxs-lookup"><span data-stu-id="408b5-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="408b5-126">在您為團隊準備好 IT 員工之後，請確認您的環境符合所有[先決條件](upgrade-plan-journey-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="408b5-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
