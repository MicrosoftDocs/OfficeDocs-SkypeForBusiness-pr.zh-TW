---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e146394b5f000ce984d7bfaff5e6674c2c091b98
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955883"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="5addb-103">從商務用 Skype 升級至 &mdash; 適用于 IT 系統管理員的小組</span><span class="sxs-lookup"><span data-stu-id="5addb-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="5addb-104">概觀</span><span class="sxs-lookup"><span data-stu-id="5addb-104">Overview</span></span>

<span data-ttu-id="5addb-105">當您從商務用 Skype 升級至小組時，某些組織必須逐步推出由其 IT 部門規劃和管理的漸進式推出。</span><span class="sxs-lookup"><span data-stu-id="5addb-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="5addb-106">本節中的文章主要適用于大型組織中的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="5addb-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="5addb-107">這些組織通常是內部部署的，但也可能是大型商務用 Skype Online 組織。</span><span class="sxs-lookup"><span data-stu-id="5addb-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="5addb-108">閱讀這些文章前，請務必閱讀 [您的小組升級](upgrade-start-here.md) 和 [升級架構](upgrade-framework.md)的入門。</span><span class="sxs-lookup"><span data-stu-id="5addb-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="5addb-109">下列文章將引導您完成貴組織的升級程式：</span><span class="sxs-lookup"><span data-stu-id="5addb-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="5addb-110">升級方法</span><span class="sxs-lookup"><span data-stu-id="5addb-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="5addb-111">管理升級的工具</span><span class="sxs-lookup"><span data-stu-id="5addb-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="5addb-112">使用商務用 Skype 內部部署之組織的其他考慮事項</span><span class="sxs-lookup"><span data-stu-id="5addb-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="5addb-113">實施您的升級</span><span class="sxs-lookup"><span data-stu-id="5addb-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="5addb-114">公用交換電話網絡 (PSTN) 考慮</span><span class="sxs-lookup"><span data-stu-id="5addb-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="5addb-115">此外，下列文章說明重要的升級概念與共存行為：</span><span class="sxs-lookup"><span data-stu-id="5addb-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="5addb-116">團隊與商務用 Skype 的共存</span><span class="sxs-lookup"><span data-stu-id="5addb-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="5addb-117">共存模式-參考</span><span class="sxs-lookup"><span data-stu-id="5addb-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="5addb-118">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="5addb-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="5addb-119">這些文章使用 [商務用 Skype Online]、[商務用 skype 伺服器內部部署] 和 [商務用 Skype] 這兩個術語。</span><span class="sxs-lookup"><span data-stu-id="5addb-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="5addb-120">後一詞指的是線上和內部部署版本。</span><span class="sxs-lookup"><span data-stu-id="5addb-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="5addb-121">在您開始之前，請注意，已遷移至團隊的使用者不再使用商務用 Skype 用戶端，除非加入在商務用 Skype 中託管的會議。</span><span class="sxs-lookup"><span data-stu-id="5addb-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="5addb-122">無論寄件者是使用小組或商務用 Skype，所有傳入聊天和呼叫使用者團隊用戶端中的土地。</span><span class="sxs-lookup"><span data-stu-id="5addb-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="5addb-123">由遷移使用者組織的任何新會議，都會排程為團隊會議。</span><span class="sxs-lookup"><span data-stu-id="5addb-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="5addb-124">如果使用者嘗試使用商務用 Skype 用戶端，就會封鎖聊天和通話的啟動。</span><span class="sxs-lookup"><span data-stu-id="5addb-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="5addb-125">不過，使用者可以 (，而且必須) 使用商務用 Skype 用戶端來加入受邀的商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="5addb-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="5addb-126"> (在2017之前隨附的舊版商務用 Skype 用戶端不提供 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="5addb-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="5addb-127">請確定您使用的是最新的商務用 Skype 用戶端。 ) </span><span class="sxs-lookup"><span data-stu-id="5addb-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="5addb-128">您可以使用 [模式](migration-interop-guidance-for-teams-with-skype.md)的概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的屬性）來管理您的使用者對團隊的轉場。</span><span class="sxs-lookup"><span data-stu-id="5addb-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="5addb-129">如上述所述，按照上述方式遷移至團隊的使用者，請參閱「TeamsOnly」模式。</span><span class="sxs-lookup"><span data-stu-id="5addb-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="5addb-130">對於遷移至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="5addb-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="5addb-131">還行。</span><span class="sxs-lookup"><span data-stu-id="5addb-131">OK.</span></span> <span data-ttu-id="5addb-132">讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="5addb-132">Let's get started.</span></span>  <span data-ttu-id="5addb-133">第一個步驟是瞭解 [您可以使用的升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="5addb-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="5addb-134">相關連結</span><span class="sxs-lookup"><span data-stu-id="5addb-134">Related links</span></span>

[<span data-ttu-id="5addb-135">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="5addb-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="5addb-136">在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="5addb-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="5addb-137">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="5addb-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="5addb-138">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="5addb-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="5addb-139">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="5addb-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="5addb-140">使用會議遷移服務 (MMS) </span><span class="sxs-lookup"><span data-stu-id="5addb-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

