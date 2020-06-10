---
title: 將商務用 Skype 內部部署升級為 Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解如何從商務用 Skype 內部部署，將貴組織升級至 Microsoft 團隊。
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
ms.openlocfilehash: 4cd9b38f09d4936d2db895f3ae8861bcf65b8a4e
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666025"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="0d011-103">從商務用 Skype 內部部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="0d011-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="0d011-104">![升級歷程圖表，強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")</span><span class="sxs-lookup"><span data-stu-id="0d011-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0d011-105">本文是升級歷程部署與實施階段的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d011-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="0d011-106">繼續之前，請確認您已完成下列活動：</span><span class="sxs-lookup"><span data-stu-id="0d011-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="0d011-107">已登記您的專案干係人</span><span class="sxs-lookup"><span data-stu-id="0d011-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="0d011-108">已定義您的專案範圍</span><span class="sxs-lookup"><span data-stu-id="0d011-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="0d011-109">已瞭解商務用 Skype 與團隊的共存與互通性</span><span class="sxs-lookup"><span data-stu-id="0d011-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="0d011-110">已選擇升級歷程</span><span class="sxs-lookup"><span data-stu-id="0d011-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="0d011-111">準備好您的環境</span><span class="sxs-lookup"><span data-stu-id="0d011-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="0d011-112">準備好貴組織</span><span class="sxs-lookup"><span data-stu-id="0d011-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="0d011-113">已進行試驗</span><span class="sxs-lookup"><span data-stu-id="0d011-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="0d011-114">如果您已部署商務用 Skype Server 或 Microsoft Lync 內部部署，且貴組織想要升級至小組，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0d011-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="0d011-115">您需要設定與您的 Microsoft 365 或 Office 365 組織混合式連線，並判斷您在幾個階段將使用者移至團隊時的共存需求。</span><span class="sxs-lookup"><span data-stu-id="0d011-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0d011-116">商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。</span><span class="sxs-lookup"><span data-stu-id="0d011-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="0d011-117">若要最大限度取得效益並確保貴組織有適當的時間來實施升級，我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0d011-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="0d011-118">請記住，成功的升級會將技術與使用者的就緒性相符，因此請務必在您向 Microsoft 團隊流覽您的旅程時，在本文中利用指導方針。</span><span class="sxs-lookup"><span data-stu-id="0d011-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="0d011-119">步驟1：設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="0d011-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="0d011-120">將內部部署使用者升級至團隊的主要必要，就是針對您的商務用 Skype Server 內部部署設定混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="0d011-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="0d011-121">首先，請閱讀 [規劃混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)，然後依照[設定混合式連接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)中所述的工作。</span><span class="sxs-lookup"><span data-stu-id="0d011-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="0d011-122">步驟2：設定過渡型共存模式（選用）</span><span class="sxs-lookup"><span data-stu-id="0d011-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="0d011-123">商務用 Skype 與團隊用戶端與使用者之間的共存與互通性是由團隊升級模式所定義。</span><span class="sxs-lookup"><span data-stu-id="0d011-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="0d011-124">根據預設，組織處於孤島模式，讓使用者可以並排使用團隊和商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="0d011-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="0d011-125">對於移至團隊的組織而言，TeamsOnly 模式是每個使用者的最終目的地，不過並非所有使用者都需要同時指派 TeamsOnly （或任何其他模式）。</span><span class="sxs-lookup"><span data-stu-id="0d011-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="0d011-126">在使用者進入 TeamsOnly 模式之前，組織可以選擇使用任何商務用 Skype 共存模式，以確保處於 TeamsOnly 模式的使用者與尚未使用的使用者之間可預測的通訊。</span><span class="sxs-lookup"><span data-stu-id="0d011-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="0d011-127">商務用 Skype 共存模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）的用途，是提供使用者的簡單且可預測的體驗，就像是組織從商務用 Skype 轉換到團隊。</span><span class="sxs-lookup"><span data-stu-id="0d011-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="0d011-128">當使用者處於任何商務用 Skype 模式時，所有傳入聊天和通話會傳送到使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="0d011-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="0d011-129">若要避免使用者混淆並確保正確的路由，小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時停用。</span><span class="sxs-lookup"><span data-stu-id="0d011-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="0d011-130">同樣地，在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，小組中的會議排程會明確停用，且在使用者處於 SfBWithTeamsCollabAndMeetings 模式時明確啟用。</span><span class="sxs-lookup"><span data-stu-id="0d011-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="0d011-131">視您的需求而定，您可以根據貴組織所選取的升級路徑指派適當的共存模式。</span><span class="sxs-lookup"><span data-stu-id="0d011-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="0d011-132">如需詳細資訊，請參閱與商務用 Skype 搭配使用團隊以及[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)[的組織的遷移與互通性指導](migration-interop-guidance-for-teams-with-skype.md)方針。</span><span class="sxs-lookup"><span data-stu-id="0d011-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="0d011-133">步驟3：將使用者從商務用 Skype 內部部署移至團隊</span><span class="sxs-lookup"><span data-stu-id="0d011-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="0d011-134">最後，您會想要將使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0d011-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="0d011-135">根據您目前的內部部署環境，這可能會涉及一兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="0d011-135">This might involve one or two steps depending on your current on-premises environment.</span></span>  

<span data-ttu-id="0d011-136">如需詳細資訊，請參閱 [在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)，以及[將使用者從內部部署移至團隊](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="0d011-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 



## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="0d011-137">手機系統與團隊升級</span><span class="sxs-lookup"><span data-stu-id="0d011-137">Phone System and Teams upgrade</span></span>

<span data-ttu-id="0d011-138">如果您要將商務用 Skype 部署轉換為含通話方案的電話系統，Microsoft 將是您公用的交換電話網絡（PSTN）提供者。</span><span class="sxs-lookup"><span data-stu-id="0d011-138">If you are transitioning your Skype for Business deployment to Phone System with Calling Plans, Microsoft will be your public switched telephone network (PSTN) provider.</span></span> <span data-ttu-id="0d011-139">假設您已完成電話號碼移植，將您的使用者升級至團隊會自動將入站 PSTN 通話轉場給小組。</span><span class="sxs-lookup"><span data-stu-id="0d011-139">Assuming that you've completed the phone number porting--upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="0d011-140">如果您要將商務用 Skype 部署轉換為手機系統，但不是使用通話方案，您必須將企業語音部署轉場至 Microsoft Phone 系統 Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="0d011-140">If you are transitioning your Skype for Business deployment to Phone System but are not using Calling Plans, you  need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="0d011-141">如需詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="0d011-141">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>
