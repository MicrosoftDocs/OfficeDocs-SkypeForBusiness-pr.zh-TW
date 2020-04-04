---
title: 快速入門手冊-設定通話方案
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 配置 Microsoft 團隊通話方案的快速入門手冊。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a81cd7d3481c9c2f6e3e5c8874eef97dc0540431
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137773"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="21e6c-103">快速入門手冊：在 Microsoft 團隊中設定通話方案</span><span class="sxs-lookup"><span data-stu-id="21e6c-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="21e6c-104">本指南將協助您讓一組使用者開始並執行，讓他們能夠探索團隊中的通話方案。</span><span class="sxs-lookup"><span data-stu-id="21e6c-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="21e6c-105">閱讀2017年12月12日，在小組中發佈通話方案：[智慧型通訊採取下一個步驟與在團隊通話](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="21e6c-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="21e6c-106">我們建議您與此快速入門手冊並行，閱讀含通話方案和[FastTrack](https://aka.ms/cloudvoice)的[電話系統](calling-plan-landing-page.md)，以規劃並推動成功的推出。</span><span class="sxs-lookup"><span data-stu-id="21e6c-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="21e6c-107">透過新增通話方案（由商務用 Skype 提供的 Office 365 功能），您現在可以使用團隊撥打或接聽來自土地線路與行動電話的電話撥打電話，或透過公用交換電話網絡（PSTN）撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="21e6c-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![顯示小組中連絡人頁面的螢幕擷取畫面](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="21e6c-109">啟用團隊中的 [**通話**] 索引標籤的先決條件</span><span class="sxs-lookup"><span data-stu-id="21e6c-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="21e6c-110">若要在小組中啟用 [**通話**] 索引標籤，使用者必須在團隊中啟用1:1 通話，並使用支援1:1 團隊通話的團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="21e6c-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="21e6c-111">若要瞭解如何在團隊中管理1:1 通話，請閱讀[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="21e6c-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="21e6c-112">若要瞭解哪些用戶端支援通話，請閱讀[Microsoft 團隊的限制與規格](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。</span><span class="sxs-lookup"><span data-stu-id="21e6c-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="21e6c-113">目前，除非使用者啟用 PSTN 通話，否則 [通話] 索引標籤中不會提供語音信箱。</span><span class="sxs-lookup"><span data-stu-id="21e6c-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="21e6c-114">啟用團隊中的**撥號**鍵台的先決條件</span><span class="sxs-lookup"><span data-stu-id="21e6c-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="21e6c-115">若要在 [小組] 中啟用 [**撥號**鍵台] 索引標籤，並允許您的使用者撥打和接聽 PSTN 電話，您必須為使用者提供手機系統和通話方案的使用者。</span><span class="sxs-lookup"><span data-stu-id="21e6c-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="21e6c-116">若要瞭解如何設定通話方案，請參閱[設定通話方案](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="21e6c-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="21e6c-117">此外，對於團隊專用的使用者，您必須確認小組通話原則中已啟用 [允許私人通話]。</span><span class="sxs-lookup"><span data-stu-id="21e6c-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="21e6c-118">如需詳細資訊，請參閱[在切換至新的 Microsoft 團隊系統管理中心時管理團隊](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="21e6c-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="21e6c-119">您也可以使用 [直接路由]，讓您的使用者撥打及接聽 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="21e6c-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="21e6c-120">若要瞭解如何設定直接路由，請參閱設定[直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)。</span><span class="sxs-lookup"><span data-stu-id="21e6c-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="21e6c-121">使用 TeamsUpgradePolicy 控制呼叫土地的位置</span><span class="sxs-lookup"><span data-stu-id="21e6c-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="21e6c-122">若要控制在團隊或商務用 Skype 中是否有來電（和聊天）土地，管理員可以使用 TeamsUpgradePolicy，使用[Microsoft 團隊系統管理中心](https://aka.ms/teamsadmincenter)或與[商務用 skype](https://docs.microsoft.com/powershell/module/skype) Cmdlet 搭配使用遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="21e6c-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="21e6c-123">TeamsUpgradePolicy 的預設設定為 [孤島] 模式，可確保現有的商務工作流程不會在團隊部署期間中斷。</span><span class="sxs-lookup"><span data-stu-id="21e6c-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="21e6c-124">根據預設，VoIP、PSTN 和對使用者的同盟呼叫將會繼續路由到商務用 Skype，直到您更新原則以啟用到團隊的撥入通話。</span><span class="sxs-lookup"><span data-stu-id="21e6c-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="21e6c-125">當收件者處於孤島模式時：</span><span class="sxs-lookup"><span data-stu-id="21e6c-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="21e6c-126">在商務用 Skype 中產生的打入 VOIP 電話，在收件者的商務用 Skype 用戶端中永遠不會。</span><span class="sxs-lookup"><span data-stu-id="21e6c-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="21e6c-127">*如果寄件者和收件者在相同的租使用者中，則*會在團隊中的小組內站通話。</span><span class="sxs-lookup"><span data-stu-id="21e6c-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="21e6c-128">傳入的同盟 VOIP （無論是在哪個用戶端產生），而且 PSTN 通話永遠位於收件者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="21e6c-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="21e6c-129">若要確保內送 VOIP 和 PSTN 呼叫永遠位於使用者的團隊用戶端，請將使用者的共存模式更新為 [TeamsOnly] （這表示將 TeamsUpgradePolicy 的 [UpgradeToTeams] 實例指派給它們）。</span><span class="sxs-lookup"><span data-stu-id="21e6c-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="21e6c-130">如需共存模式與 TeamsUpgradePolicy 的詳細資訊，請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="21e6c-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="21e6c-131">**筆記**</span><span class="sxs-lookup"><span data-stu-id="21e6c-131">**NOTES**</span></span>
 - <span data-ttu-id="21e6c-132">商務用 Skype IP 手機將接聽通話，即使使用者處於 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="21e6c-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="21e6c-133">已針對商務用 Skype Online （例如已獲指派 OnlineVoiceRoutingPolicy）的手機系統和通話方案授權所提供的使用者，將會在團隊中啟用 [通話] 索引標籤，而且可以在不需要採取任何管理動作的情況下，將來自團隊的出站 PSTN 呼叫提供給您。</span><span class="sxs-lookup"><span data-stu-id="21e6c-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="21e6c-134">如何設定使用者接收小組中的所有打入 VOIP 和 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="21e6c-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="21e6c-135">若要確保使用者在團隊中接收所有內送 VOIP 和 PSTN 通話，請在 Microsoft 團隊系統管理中心將使用者的 [共存模式] 設定為 [TeamsOnly]，或使用商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="21e6c-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="21e6c-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21e6c-136">See also</span></span>
[<span data-ttu-id="21e6c-137">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="21e6c-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="21e6c-138">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="21e6c-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="21e6c-139">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="21e6c-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="21e6c-140">商務用 Skype PowerShell Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="21e6c-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

