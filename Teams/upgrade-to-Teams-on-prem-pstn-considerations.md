---
title: 從商務用 Skype 內部部署升級至團隊時的 PSTN 考慮
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至團隊的語音考慮
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686429"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a><span data-ttu-id="533a7-103">從商務用 Skype 內部部署升級至團隊的 PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="533a7-103">PSTN considerations for upgrading to Teams from Skype for Business on-premises</span></span>

<span data-ttu-id="533a7-104">本文將說明升級至小組時的公用交換電話網絡 (PSTN) 考慮。</span><span class="sxs-lookup"><span data-stu-id="533a7-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span>   


<span data-ttu-id="533a7-105">此外，下列文章說明重要的升級概念與共存行為：</span><span class="sxs-lookup"><span data-stu-id="533a7-105">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="533a7-106">團隊與商務用 Skype 的共存</span><span class="sxs-lookup"><span data-stu-id="533a7-106">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="533a7-107">共存模式-參考</span><span class="sxs-lookup"><span data-stu-id="533a7-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="533a7-108">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="533a7-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - <span data-ttu-id="533a7-109">只有在使用者處於 TeamsOnly 模式時，才會支援將電話系統與團隊一起使用。</span><span class="sxs-lookup"><span data-stu-id="533a7-109">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="533a7-110">如果使用者使用的是孤島模式，則只有商務用 Skype 支援電話系統。</span><span class="sxs-lookup"><span data-stu-id="533a7-110">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 
 > - <span data-ttu-id="533a7-111">商務用 Skype 中的任何來電轉接、團隊通話群組和委派設定都不會被遷移，且需要為小組重新建立。</span><span class="sxs-lookup"><span data-stu-id="533a7-111">Any call forwarding, team-call group, and delegation settings from Skype for Business are not migrated and will need to be re-recreated for Teams.</span></span>
 > - <span data-ttu-id="533a7-112">如需 Microsoft 團隊雲端語音功能的一般概覽，並協助您 [規劃團隊的語音方案，請參閱規劃您的小組語音方案](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="533a7-112">For a general overview of Microsoft Teams cloud voice features, and help deciding which Microsoft voice solution is right for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="533a7-113">PSTN 通話案例</span><span class="sxs-lookup"><span data-stu-id="533a7-113">PSTN calling scenarios</span></span>

<span data-ttu-id="533a7-114">移至 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="533a7-114">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="533a7-115">[商務用 Skype Online 中的使用者，包含 Microsoft 通話方案](#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="533a7-115">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="533a7-116">升級時，此使用者將會繼續進行 Microsoft 通話計畫。</span><span class="sxs-lookup"><span data-stu-id="533a7-116">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="533a7-117">[商務用 Skype Online 中的使用者，](#from-skype-for-business-online-with-on-premises-voice) 可透過商務用 skype 內部部署或雲端連接器版本使用內部部署語音功能。</span><span class="sxs-lookup"><span data-stu-id="533a7-117">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="533a7-118">使用者在小組中的升級需要與使用者遷移以直接傳送路由，以確保 TeamsOnly 使用者有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="533a7-118">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="533a7-119">[在商務用 Skype 內部部署中使用企業語音的使用者](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，他們將會移至線上並保留內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="533a7-119">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="533a7-120">將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將使用者的遷移轉移至直接傳送路線。</span><span class="sxs-lookup"><span data-stu-id="533a7-120">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="533a7-121">[在商務用 Skype 內部部署中使用企業語音的使用者](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，他們將會移至線上並使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="533a7-121">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="533a7-122">將此使用者遷移至小組需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將該使用者電話號碼的埠與) 的埠進行協調，) 從可用的地區指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="533a7-122">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="533a7-123">本文僅提供高層次的概覽。</span><span class="sxs-lookup"><span data-stu-id="533a7-123">This article provides a high-level overview only.</span></span> <span data-ttu-id="533a7-124">如需詳細資訊，請參閱 [手機系統 Direct 路由](direct-routing-landing-page.md) 與 [通話方案](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="533a7-124">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="533a7-125">使用 Microsoft 通話方案從商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="533a7-125">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="533a7-126">這是包括語音在內的最簡單的升級案例。</span><span class="sxs-lookup"><span data-stu-id="533a7-126">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="533a7-127">請確定使用者已獲指派團隊授權。</span><span class="sxs-lookup"><span data-stu-id="533a7-127">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="533a7-128">根據預設，當您指派 Microsoft 365 或 Office 365 授權時，系統會啟用團隊，所以除非您先前已停用團隊授權，否則不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="533a7-128">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="533a7-129">如果使用者已有電話號碼的 Microsoft 通話方案，唯一的必要變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="533a7-129">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="533a7-130">在指派 TeamsOnly 模式之前，傳入的 PSTN 呼叫將會居住在使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="533a7-130">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="533a7-131">升級至 TeamsOnly 模式之後，傳入的 PSTN 呼叫會集中在使用者的團隊用戶端中。</span><span class="sxs-lookup"><span data-stu-id="533a7-131">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="533a7-132">從商務用 Skype Online （含內部部署語音）</span><span class="sxs-lookup"><span data-stu-id="533a7-132">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="533a7-133">在這種情況下，使用者已經在商務用 Skype Online 中，但其 PSTN 連線是內部部署的，在混合模式或雲端連接器版本中使用商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="533a7-133">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="533a7-134">透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，就是透過內部部署會話邊界控制器 (SBC) ，讓 PSTN trunks 直接連線到雲端中的直接路由服務。</span><span class="sxs-lookup"><span data-stu-id="533a7-134">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="533a7-135">下列基本步驟如下所示。</span><span class="sxs-lookup"><span data-stu-id="533a7-135">The basic steps are listed below.</span></span>  <span data-ttu-id="533a7-136">步驟1-4 會列在建議的順序中，但它們可以以任何順序完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-136">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="533a7-137">金鑰是所有這些都應該在步驟5之前完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-137">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="533a7-138">如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必透過明確指派 grandfather 任何現有的孤島使用者，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="533a7-138">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="533a7-139">針對直接路由設定您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="533a7-139">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="533a7-140">請參閱 [直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="533a7-140">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="533a7-141">如有需要，請針對這些使用者設定各種小組原則 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-141">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="533a7-142">您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 模式前執行此動作。</span><span class="sxs-lookup"><span data-stu-id="533a7-142">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="533a7-143">準備選取要語音遷移的使用者：</span><span class="sxs-lookup"><span data-stu-id="533a7-143">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="533a7-144">如有需要，請指派 [團隊授權]。</span><span class="sxs-lookup"><span data-stu-id="533a7-144">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="533a7-145">假設使用者已在商務用 Skype Online 內部部署語音中運作，則使用者已經有商務用 Skype 方案2以及 Microsoft 手機系統。</span><span class="sxs-lookup"><span data-stu-id="533a7-145">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="533a7-146">讓這些方案保持啟用，包括商務用 Skype Online 方案2授權。</span><span class="sxs-lookup"><span data-stu-id="533a7-146">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="533a7-147">指派所需的 OnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="533a7-147">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="533a7-148">升級使用者：必須協調這些步驟。</span><span class="sxs-lookup"><span data-stu-id="533a7-148">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="533a7-149">在 Microsoft 365 或 Office 365 中，將使用者升級為 TeamsOnly 模式 (授與 CsTeamsUpgradePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-149">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="533a7-150">在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。</span><span class="sxs-lookup"><span data-stu-id="533a7-150">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="533a7-151">從商務用 Skype Server 內部部署（含企業語音）到直接路由</span><span class="sxs-lookup"><span data-stu-id="533a7-151">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="533a7-152">在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。</span><span class="sxs-lookup"><span data-stu-id="533a7-152">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="533a7-153">使用 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，可以讓他們直接路由，然後將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="533a7-153">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="533a7-154">下列基本步驟如下所示。</span><span class="sxs-lookup"><span data-stu-id="533a7-154">The basic steps are listed below.</span></span>  <span data-ttu-id="533a7-155">步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-155">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="533a7-156">金鑰是所有這些都應該在步驟6之前完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-156">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="533a7-157">如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。</span><span class="sxs-lookup"><span data-stu-id="533a7-157">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="533a7-158">如果您尚未這麼做，請 [針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="533a7-158">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="533a7-159">針對直接路由設定您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="533a7-159">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="533a7-160">請參閱 [直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="533a7-160">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="533a7-161">如有需要，請針對這些使用者設定不同的小組原則 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-161">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="533a7-162">您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。</span><span class="sxs-lookup"><span data-stu-id="533a7-162">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="533a7-163">如有需要，請指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="533a7-163">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="533a7-164">使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="533a7-164">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="533a7-165">如果商務用 Skype Online 方案2已停用，請重新啟用它。</span><span class="sxs-lookup"><span data-stu-id="533a7-165">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="533a7-166">升級使用者：必須協調這些步驟。</span><span class="sxs-lookup"><span data-stu-id="533a7-166">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="533a7-167">使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="533a7-167">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="533a7-168">如果您使用的是不支援-MoveToTeams 開關的商務用 Skype Server 版本，請先執行 Move-CsUser 然後在租使用者遠端 PowerShell 或團隊管理主控台中指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="533a7-168">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="533a7-169">在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。</span><span class="sxs-lookup"><span data-stu-id="533a7-169">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="533a7-170">在 Microsoft 365 或 Office 365 中：指派相關的 OnlineVoiceRoutingPolicy 來啟用撥出通話。</span><span class="sxs-lookup"><span data-stu-id="533a7-170">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="533a7-171">從商務用 Skype Server 內部部署（含企業語音）到 Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="533a7-171">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="533a7-172">在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。</span><span class="sxs-lookup"><span data-stu-id="533a7-172">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="533a7-173">透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，意味著將使用者移至雲端，並將其號碼從舊的運營商移植到 Microsoft 通話方案，或為使用者指派新的號碼。</span><span class="sxs-lookup"><span data-stu-id="533a7-173">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="533a7-174">下列基本步驟如下所示。</span><span class="sxs-lookup"><span data-stu-id="533a7-174">The basic steps are listed below.</span></span><span data-ttu-id="533a7-175">步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-175">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="533a7-176">金鑰是所有這些都應該在步驟6之前完成。</span><span class="sxs-lookup"><span data-stu-id="533a7-176">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="533a7-177">如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。</span><span class="sxs-lookup"><span data-stu-id="533a7-177">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="533a7-178">如果您尚未這麼做，請 [針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="533a7-178">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="533a7-179">如有需要，請針對這些使用者設定各種小組原則 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-179">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="533a7-180">您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。</span><span class="sxs-lookup"><span data-stu-id="533a7-180">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="533a7-181">如有需要，請指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="533a7-181">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="533a7-182">使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="533a7-182">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="533a7-183">如果商務用 Skype Online 方案2已停用，請重新啟用它。</span><span class="sxs-lookup"><span data-stu-id="533a7-183">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="533a7-184">為您的使用者取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="533a7-184">Get phone numbers for your users.</span></span> <span data-ttu-id="533a7-185"> (如需詳細資訊，請參閱 [管理貴組織的電話號碼](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。 ) </span><span class="sxs-lookup"><span data-stu-id="533a7-185">(For details see [Manage phone numbers for your organization](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)</span></span>

   - <span data-ttu-id="533a7-186">如果您要重複使用這些號碼，請將移植要求提交給您的運營商。</span><span class="sxs-lookup"><span data-stu-id="533a7-186">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="533a7-187">或者，您也可以直接從 Microsoft 取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="533a7-187">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="533a7-188">升級使用者並視需要指派 LineUri。</span><span class="sxs-lookup"><span data-stu-id="533a7-188">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="533a7-189">使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="533a7-189">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="533a7-190">如果您要將號碼移植到 Microsoft，您應該將這個作業的時間調整為在埠出現時進行。</span><span class="sxs-lookup"><span data-stu-id="533a7-190">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="533a7-191">如果您使用的是 Microsoft 的新號碼，您需要變更該使用者的 LineUri。</span><span class="sxs-lookup"><span data-stu-id="533a7-191">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="533a7-192">這必須在使用者使用設定 CsOnlineVoiceUser 進行線上移動之後進行。</span><span class="sxs-lookup"><span data-stu-id="533a7-192">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="533a7-193">直接路由的每個租使用者配置摘要</span><span class="sxs-lookup"><span data-stu-id="533a7-193">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="533a7-194">透過查看 [此清單](direct-routing-border-controllers.md)，確保您的會話邊界控制器 (SBC) 支援直接路由。</span><span class="sxs-lookup"><span data-stu-id="533a7-194">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="533a7-195">您也必須確定您的固件版本正確。</span><span class="sxs-lookup"><span data-stu-id="533a7-195">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="533a7-196">將您的內部部署 SBC 與團隊直向路由服務配對。</span><span class="sxs-lookup"><span data-stu-id="533a7-196">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="533a7-197">如需詳細資訊，請參閱將 [SBC 與電話系統的直接路由服務](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="533a7-197">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="533a7-198">此設定實質上是內部部署設定的鏡像。</span><span class="sxs-lookup"><span data-stu-id="533a7-198">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="533a7-199">線上配置包括：</span><span class="sxs-lookup"><span data-stu-id="533a7-199">The online configuration consists of:</span></span> 
   - <span data-ttu-id="533a7-200">如果您是從商務用 Skype Online 遷移使用者，且從使用企業語音) 的內部部署遷移使用者，請根據 VoicePolicy 來 OnlineVoiceRoutingPolicy 根據內部部署 VoiceRoutingPolicy 的 (。</span><span class="sxs-lookup"><span data-stu-id="533a7-200">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="533a7-201">OnlinePSTNUsage 物件 (根據內部部署的 PSTN 使用量) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-201">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="533a7-202">OnlineVoiceRoute 物件 (基於內部部署 VoiceRoute) 。</span><span class="sxs-lookup"><span data-stu-id="533a7-202">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="533a7-203">如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="533a7-203">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="533a7-204">在遷移期間管理 EnterpriseVoiceEnabled 屬性</span><span class="sxs-lookup"><span data-stu-id="533a7-204">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="533a7-205">無論是使用直接路由或 Microsoft 通話方案，使用者在 Azure AD 中都必須有 EnterpriseVoiceEnabled = true，才能讓使用者擁有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="533a7-205">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="533a7-206">EnterpriseVoiceEnabled ( "EV-enabled" ) 是一個 (不在內部部署目錄和雲端中的原則) 的屬性。</span><span class="sxs-lookup"><span data-stu-id="533a7-206">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="533a7-207">雲端中的值是對團隊而言重要的。</span><span class="sxs-lookup"><span data-stu-id="533a7-207">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="533a7-208">如何將 EV 啟用的確切邏輯設定為 true，視下列情況而定：</span><span class="sxs-lookup"><span data-stu-id="533a7-208">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="533a7-209">如果使用者在內部部署商務用 Skype 伺服器中啟用 EV，且在將使用者移至雲端且使用 Move-csuser 時，系統會為使用者指派電話系統授權，則會使用 EV-enabled = true 來預配線上使用者。</span><span class="sxs-lookup"><span data-stu-id="533a7-209">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="533a7-210">如果現有的 TeamsOnly 或商務用 Skype Online 使用者已獲指派電話系統授權，則 EV-enabled 預設不會設定為 true。</span><span class="sxs-lookup"><span data-stu-id="533a7-210">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="533a7-211">如果在指派電話系統授權之前，將內部部署使用者移至雲端，也會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="533a7-211">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="533a7-212">不論是哪一種情況，管理員都必須指定下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="533a7-212">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="533a7-213">相關連結</span><span class="sxs-lookup"><span data-stu-id="533a7-213">Related links</span></span>

[<span data-ttu-id="533a7-214">規劃您的小組語音方案</span><span class="sxs-lookup"><span data-stu-id="533a7-214">Plan your Teams voice solution</span></span>](cloud-voice-landing-page.md)

[<span data-ttu-id="533a7-215">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="533a7-215">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="533a7-216">在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="533a7-216">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="533a7-217">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="533a7-217">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="533a7-218">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="533a7-218">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="533a7-219">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="533a7-219">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="533a7-220">使用會議遷移服務 (MMS) </span><span class="sxs-lookup"><span data-stu-id="533a7-220">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

