---
title: 快速入門手冊 - 配置通話方案
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在 Microsoft Teams 中設定通話方案的快速入門手冊，方便您設定一組使用者並執行。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101179"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="4a1ce-103">快速入門手冊：設定 Microsoft Teams 中的通話方案</span><span class="sxs-lookup"><span data-stu-id="4a1ce-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="4a1ce-104">本指南可協助您設定並執行一組使用者，以便他們探索 Teams 中的通話方案。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="4a1ce-105">閱讀 2017 年 12 月 12 日 Teams 通話方案公告：智慧通訊在 Teams 中採用通話 [的下一個步驟](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="4a1ce-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="4a1ce-106">我們建議您在閱讀此快速入門手冊的同時，閱讀具有通話方案的電話系統[](calling-plan-landing-page.md)與[FastTrack，](https://aka.ms/cloudvoice)以規劃並推動成功推出。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="4a1ce-107">透過新增通話方案 -由商務用 Skype 提供之 Microsoft 365 和 Office 365 功能，您現在可以使用 Teams，透過公用交換電話網路 (PSTN) 撥打或接聽陸上電話和行動電話的電話。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![顯示 Teams 中連絡人頁面的螢幕擷取畫面](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="4a1ce-109">在 Teams 中啟用 **通話資料表** 的先決條件</span><span class="sxs-lookup"><span data-stu-id="4a1ce-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="4a1ce-110">若要啟用Teams 中的通話功能，使用者必須啟用 Teams 中的 1：1 通話，且使用支援 1：1 Teams 通話的 Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="4a1ce-111">若要瞭解如何在 Teams 中管理 1：1 通話，請閱讀 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="4a1ce-112">若要瞭解哪些用戶端支援通話，請閱讀 [Microsoft Teams 的限制和規格](./limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4a1ce-113">目前，除非使用者已啟用 PSTN 通話功能，否則語音信箱無法于 [通話> 選項卡中提供。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="4a1ce-114">在 Teams 中啟用 **撥號鍵台** 的先決條件</span><span class="sxs-lookup"><span data-stu-id="4a1ce-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="4a1ce-115">若要在 Teams 中啟用 [ **撥號鍵** 台」 的選項卡，並允許使用者撥打和接聽 PSTN 通話，您必須為 [電話系統及通話方案> 配置使用者。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="4a1ce-116">若要瞭解如何設定通話方案，請參閱 [設定通話方案](./set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="4a1ce-117">此外，對於僅適用于 Teams 的使用者，您必須確保 Teams 通話政策中已啟用「允許私人通話」。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="4a1ce-118">請參閱 [在轉換至](./manage-teams-skypeforbusiness-admin-center.md) 新 Microsoft Teams 系統管理中心期間管理 Teams 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="4a1ce-119">您也可以使用直接路由，讓使用者撥打和接聽 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="4a1ce-120">若要瞭解如何設定直接路由，請參閱 [設定直接路由](./direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="4a1ce-121">使用 TeamsUpgradePolicy 控制通話到何處</span><span class="sxs-lookup"><span data-stu-id="4a1ce-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="4a1ce-122">若要控制來電 (和聊天) 是否位於 Teams 或商務用 Skype 中，系統管理員可以使用 TeamsUpgradePolicy，使用[Microsoft Teams](https://aka.ms/teamsadmincenter)系統管理中心，或使用遠端 Windows PowerShell 會話與商務用 Skype Cmdlet。 [](/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="4a1ce-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="4a1ce-123">TeamsUpgradePolicy 的預設組式為群島模式，其設計目的是確保現有的商務工作流程不會在 Teams 部署期間中斷。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="4a1ce-124">根據預設，VoIP、PSTN 和向使用者撥打的聯盟通話會繼續路由至商務用 Skype，直到您更新策略以啟用來電至 Teams。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="4a1ce-125">當收件者進入島嶼模式時：</span><span class="sxs-lookup"><span data-stu-id="4a1ce-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="4a1ce-126">來自商務用 Skype 的來電一直位於收件者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="4a1ce-127">如果寄件者和收件者位於同一租使用者中，則來自 Teams 的傳入 VOIP 通話會登入 *Teams。*</span><span class="sxs-lookup"><span data-stu-id="4a1ce-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="4a1ce-128">內聯 VOIP (無論哪一個用戶端) PSTN 通話一直位於收件者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="4a1ce-129">若要確保傳入的 VOIP 和 PSTN 通話一直登入使用者的 Teams 用戶端，請更新使用者的並存模式為 TeamsOnly (這表示，請指派他們 TeamsUpgradePolicy 的 「UpgradeToTeams」實例。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="4a1ce-130">有關共存模式和 TeamsUpgradePolicy 詳細資訊，請參閱使用 Teams 與商務用 Skype 的組織移移及互通性 [指南](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="4a1ce-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="4a1ce-131">**筆記**</span><span class="sxs-lookup"><span data-stu-id="4a1ce-131">**NOTES**</span></span>
 - <span data-ttu-id="4a1ce-132">商務用 Skype IP 電話會接聽來電，即使使用者位於 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="4a1ce-133">已布備電話系統與通話方案授權以用於商務用 Skype Online (例如，已指派 OnlineVoiceRoutingPolicy) 值的使用者，將可在 Teams 中啟用 [通話> 選項卡，而且不需要系統管理員執行任何系統管理動作，即可從 Teams 進行外撥 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="4a1ce-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="4a1ce-134">如何設定使用者以在 Teams 中接聽所有傳入的 VOIP 和 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="4a1ce-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="4a1ce-135">若要確保使用者在 Teams 中接聽所有傳入的 VOIP 和 PSTN 通話，請設定使用者的並存模式至 Microsoft Teams 系統管理中心的 TeamsOnly，或使用商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4a1ce-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="4a1ce-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4a1ce-136">See also</span></span>
[<span data-ttu-id="4a1ce-137">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="4a1ce-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="4a1ce-138">使用 Teams 與商務用 Skype 的組織移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="4a1ce-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="4a1ce-139">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="4a1ce-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="4a1ce-140">商務用 Skype PowerShell Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="4a1ce-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)