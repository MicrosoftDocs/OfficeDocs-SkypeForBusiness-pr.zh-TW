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
description: 在 Microsoft Teams 中設定通話方案的快速入門手冊，以便讓一組使用者開始使用。
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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="f9857-103">快速入門手冊：設定 Microsoft Teams 中的通話方案</span><span class="sxs-lookup"><span data-stu-id="f9857-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="f9857-104">本指南可協助您設定並執行一組使用者，以便他們探索 Teams。</span><span class="sxs-lookup"><span data-stu-id="f9857-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="f9857-105">閱讀 2017 年 12 月 12 日于 Teams 中宣佈的通話[方案：智慧](https://aka.ms/ipyqus)通訊在 Teams</span><span class="sxs-lookup"><span data-stu-id="f9857-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="f9857-106">我們建議您在閱讀此快速入門手冊的同時，閱讀電話系統通話方案與[](calling-plan-landing-page.md)[FastTrack](https://aka.ms/cloudvoice)來規劃及推動成功推出。</span><span class="sxs-lookup"><span data-stu-id="f9857-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="f9857-107">透過新增通話方案 -Microsoft 365 和 Office 365 由 商務用 Skype 提供的功能 ，您現在可以使用 Teams，透過公用交換電話網路 (PSTN) 撥打或接聽陸上電話和行動電話的電話。</span><span class="sxs-lookup"><span data-stu-id="f9857-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![顯示連絡人頁面的螢幕擷取畫面Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="f9857-109">在通話中 **啟用通話Teams**</span><span class="sxs-lookup"><span data-stu-id="f9857-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="f9857-110">若要啟用Teams 中的 Teams 使用者必須啟用 Teams 中的 1：1 通話，並且使用支援 1：1 通話的 Teams 用戶端Teams通話。</span><span class="sxs-lookup"><span data-stu-id="f9857-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="f9857-111">若要瞭解如何在 Teams 中管理 1：1 通話，請參閱[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9857-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="f9857-112">若要瞭解哪些用戶端支援通話，請閱讀適用于[Microsoft Teams 的限制Microsoft Teams。](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f9857-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9857-113">目前，除非使用者已啟用 PSTN 通話功能，否則語音信箱無法于 [通話> 選項卡中提供。</span><span class="sxs-lookup"><span data-stu-id="f9857-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="f9857-114">在鍵盤上啟用 **撥號鍵台** Teams</span><span class="sxs-lookup"><span data-stu-id="f9857-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="f9857-115">若要啟用 **[撥號** 鍵台Teams並允許使用者撥打和接聽 PSTN 通話，您必須為 [撥號電話系統方案提供使用者。</span><span class="sxs-lookup"><span data-stu-id="f9857-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="f9857-116">若要瞭解如何設定通話方案，請參閱 [設定通話方案](./set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="f9857-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="f9857-117">此外，Teams使用者，您必須在通話規則中，確保已啟用「允許Teams通話」。</span><span class="sxs-lookup"><span data-stu-id="f9857-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="f9857-118">請參閱在Teams系統管理中心轉換期間管理Microsoft Teams[管理中心以](./manage-teams-skypeforbusiness-admin-center.md)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f9857-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="f9857-119">您也可以使用直接路由，讓使用者撥打和接聽 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="f9857-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="f9857-120">若要瞭解如何設定直接路由，請參閱 [設定直接路由](./direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="f9857-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="f9857-121">使用 TeamsUpgradePolicy 控制通話到何處</span><span class="sxs-lookup"><span data-stu-id="f9857-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="f9857-122">若要控制來電 (和聊天) 是否位於 Teams 或 商務用 Skype，系統管理員可以使用 TeamsUpgradePolicy、使用[Microsoft Teams](https://aka.ms/teamsadmincenter)系統管理中心或使用遠端 Windows PowerShell 會話與[商務用 Skype](/powershell/module/skype) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9857-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="f9857-123">TeamsUpgradePolicy 的預設組式為群島模式，其設計可確保現有商務工作流程在部署期間不會Teams中斷。</span><span class="sxs-lookup"><span data-stu-id="f9857-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="f9857-124">根據預設，VoIP、PSTN 和向使用者撥打的聯盟通話會繼續路由至 商務用 Skype，直到您更新策略以啟用來電到 Teams。</span><span class="sxs-lookup"><span data-stu-id="f9857-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="f9857-125">當收件者進入島嶼模式時：</span><span class="sxs-lookup"><span data-stu-id="f9857-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="f9857-126">來自客戶的來電商務用 SKYPE電話一直位於收件者商務用 Skype用戶端。</span><span class="sxs-lookup"><span data-stu-id="f9857-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="f9857-127">如果寄件者和收件者位於同一租使用者Teams內Teams內陸的 VOIP *通話*。</span><span class="sxs-lookup"><span data-stu-id="f9857-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="f9857-128">內聯 VOIP (來自哪個用戶端) PSTN 通話一直位於收件者商務用 Skype用戶端。</span><span class="sxs-lookup"><span data-stu-id="f9857-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="f9857-129">若要確保傳入的 VOIP 和 PSTN 通話一直登入使用者的 Teams 用戶端，請更新使用者的並存模式為 TeamsOnly (，也就是說，請指派他們 TeamsUpgradePolicy 的 「UpgradeToTeams」實例。</span><span class="sxs-lookup"><span data-stu-id="f9857-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="f9857-130">如要進一步瞭解共存模式和 TeamsUpgradePolicy，請參閱移Teams組織與商務用 Skype [](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="f9857-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="f9857-131">**筆記**</span><span class="sxs-lookup"><span data-stu-id="f9857-131">**NOTES**</span></span>
 - <span data-ttu-id="f9857-132">商務用 SkypeIP 電話會接聽來電，即使使用者位於 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="f9857-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="f9857-133">已布備 電話系統 和通話方案授權以用於 商務用 Skype Online (的使用者，例如，已指派值 OnlineVoiceRoutingPolicy) 的使用者，將在 Teams 中啟用 [通話> 選項卡，而且可以從 Teams 撥打外撥 PSTN 通話，而系統管理員不需要執行任何系統管理動作。</span><span class="sxs-lookup"><span data-stu-id="f9857-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="f9857-134">如何設定使用者以在通話中接聽所有傳入的 VOIP 和 PSTN Teams</span><span class="sxs-lookup"><span data-stu-id="f9857-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="f9857-135">若要確保使用者在 Teams 中接聽所有傳入的 VOIP 和 PSTN 通話，請設定使用者的並存模式至 Microsoft Teams 系統管理中心的 TeamsOnly，或使用 商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9857-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="f9857-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9857-136">See also</span></span>
[<span data-ttu-id="f9857-137">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="f9857-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="f9857-138">適用于與應用程式一起使用Teams的移商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f9857-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="f9857-139">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="f9857-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="f9857-140">商務用 SkypePowerShell Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="f9857-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)