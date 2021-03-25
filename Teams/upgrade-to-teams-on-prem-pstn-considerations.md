---
title: 從商務用 Skype 升級到 Teams 時，PSTN 考慮
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級到 Teams 的語音考慮
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72a12cf1dbcb69af7b71bf259568e4a53d1a3a33
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115541"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a><span data-ttu-id="672ef-103">從商務用 Skype 內部部署升級至 Teams 的 PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="672ef-103">PSTN considerations for upgrading to Teams from Skype for Business on-premises</span></span>

<span data-ttu-id="672ef-104">本文將說明公用交換電話網絡 (PSTN) 升級至 Teams 時考慮的問題。</span><span class="sxs-lookup"><span data-stu-id="672ef-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span>   


<span data-ttu-id="672ef-105">此外，下列文章說明重要的升級概念和共存行為：</span><span class="sxs-lookup"><span data-stu-id="672ef-105">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="672ef-106">Teams 與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="672ef-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="672ef-107">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="672ef-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="672ef-108">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="672ef-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - <span data-ttu-id="672ef-109">只有在使用者進入 TeamsOnly 模式時，才支援在 Teams 中使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="672ef-109">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="672ef-110">如果使用者是群島模式，則只有商務用 Skype 支援電話系統。</span><span class="sxs-lookup"><span data-stu-id="672ef-110">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 
 > - <span data-ttu-id="672ef-111">商務用 Skype 的任何呼叫轉轉、小組通話群組和委派設定不會移轉，且必須重新建立 Teams。</span><span class="sxs-lookup"><span data-stu-id="672ef-111">Any call forwarding, team-call group, and delegation settings from Skype for Business are not migrated and will need to be re-recreated for Teams.</span></span>
 > - <span data-ttu-id="672ef-112">有關 Microsoft Teams 雲端語音功能的一般概觀，以及協助決定適合貴組織的 Microsoft 語音解決方案，請參閱 [規劃您的 Teams 語音解決方案](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="672ef-112">For a general overview of Microsoft Teams cloud voice features, and help deciding which Microsoft voice solution is right for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="672ef-113">PSTN 通話案例</span><span class="sxs-lookup"><span data-stu-id="672ef-113">PSTN calling scenarios</span></span>

<span data-ttu-id="672ef-114">移至 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="672ef-114">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="672ef-115">[商務用 Skype Online 中的使用者，具有 Microsoft 通話方案](#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="672ef-115">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="672ef-116">升級後，此使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="672ef-116">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="672ef-117">[商務用 Skype Online](#from-skype-for-business-online-with-on-premises-voice) 中的使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。</span><span class="sxs-lookup"><span data-stu-id="672ef-117">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="672ef-118">使用者升級至 Teams 時，必須協調使用者的移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="672ef-118">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="672ef-119">[商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="672ef-119">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="672ef-120">將此使用者移轉至 Teams，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。</span><span class="sxs-lookup"><span data-stu-id="672ef-120">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="672ef-121">[在商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)內部部署中使用企業語音的使用者，該使用者將會移往線上，並且使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="672ef-121">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="672ef-122">將該使用者移轉至 Teams 時，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並配合 A) 將該使用者電話號碼的埠移至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="672ef-122">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="672ef-123">本文僅提供高層次概觀。</span><span class="sxs-lookup"><span data-stu-id="672ef-123">This article provides a high-level overview only.</span></span> <span data-ttu-id="672ef-124">詳細資訊，請參閱電話[系統直接路由和](direct-routing-landing-page.md)[通話方案](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="672ef-124">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="672ef-125">從商務用 Skype Online 與 Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="672ef-125">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="672ef-126">這是涉及語音最簡單的升級案例。</span><span class="sxs-lookup"><span data-stu-id="672ef-126">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="672ef-127">請確定使用者已指派 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="672ef-127">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="672ef-128">根據預設，當您指派 Microsoft 365 或 Office 365 授權時，Teams 會啟用，因此除非您先前停用 Teams 授權，否則不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="672ef-128">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="672ef-129">如果使用者已經有包含電話號碼的 Microsoft 通話方案，則唯一必要的變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="672ef-129">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="672ef-130">在指派 TeamsOnly 模式之前，傳入的 PSTN 通話會登入使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="672ef-130">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="672ef-131">升級至 TeamsOnly 模式之後，傳入的 PSTN 通話會登入使用者的 Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="672ef-131">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="672ef-132">從商務用 Skype Online 與內部部署語音</span><span class="sxs-lookup"><span data-stu-id="672ef-132">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="672ef-133">在此情境中，使用者已在商務用 Skype Online 中，但他們的 PSTN 連線是內部部署，無論是使用混合式模式的商務用 Skype Server 或雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="672ef-133">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="672ef-134">使用 PSTN 功能將這些使用者移入 TeamsOnly 模式，表示讓他們能夠直接路由，其中 PSTN 主幹會透過內部部署會話邊界控制器 (SBC) ，直接連接到雲端中的直接路由服務。</span><span class="sxs-lookup"><span data-stu-id="672ef-134">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="672ef-135">以下列出基本步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-135">The basic steps are listed below.</span></span>  <span data-ttu-id="672ef-136">步驟 1-4 會以建議的順序列出，但可以以任何順序完成。</span><span class="sxs-lookup"><span data-stu-id="672ef-136">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="672ef-137">關鍵在於在步驟 5 之前應完成所有步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-137">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="672ef-138">如果您要將租使用者範圍的政策設定為其中一種商務用 Skype 模式，請務必如先前所述，明確指派任何現有的群島使用者，以將群島模式指派給他們。</span><span class="sxs-lookup"><span data-stu-id="672ef-138">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="672ef-139">設定您的租使用者進行直接路由。</span><span class="sxs-lookup"><span data-stu-id="672ef-139">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="672ef-140">請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="672ef-140">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="672ef-141">如果需要，請針對這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-141">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="672ef-142">這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組式，最好在使用者升級至 TeamsOnly 模式之前執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="672ef-142">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="672ef-143">準備選取的使用者進行語音移移：</span><span class="sxs-lookup"><span data-stu-id="672ef-143">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="672ef-144">如有需要，請指派 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="672ef-144">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="672ef-145">假設使用者已在商務用 Skype Online 內部部署語音中運作，則使用者已經擁有商務用 Skype 方案 2 以及 Microsoft Phone System。</span><span class="sxs-lookup"><span data-stu-id="672ef-145">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="672ef-146">讓這兩個方案保持啟用狀態，包括商務用 Skype Online 方案 2 授權。</span><span class="sxs-lookup"><span data-stu-id="672ef-146">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="672ef-147">指派所需的 OnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="672ef-147">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="672ef-148">升級使用者：這些步驟必須協調一致。</span><span class="sxs-lookup"><span data-stu-id="672ef-148">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="672ef-149">在 Microsoft 365 或 Office 365 中，將使用者升級至 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-149">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="672ef-150">在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。</span><span class="sxs-lookup"><span data-stu-id="672ef-150">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="672ef-151">從內部部署商務用 Skype Server 使用企業語音，到直接路由</span><span class="sxs-lookup"><span data-stu-id="672ef-151">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="672ef-152">在此情況下，使用者仍位於內部部署商務用 Skype 中，而且他們的 PSTN 連接也是內部部署。</span><span class="sxs-lookup"><span data-stu-id="672ef-152">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="672ef-153">使用 PSTN 功能將這些使用者移往 TeamsOnly 模式，即表示啟用這些使用者進行直接路由，然後將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="672ef-153">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="672ef-154">以下列出基本步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-154">The basic steps are listed below.</span></span>  <span data-ttu-id="672ef-155">步驟 1-5 會以建議的順序列出，但可以按照任何循序執行。</span><span class="sxs-lookup"><span data-stu-id="672ef-155">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="672ef-156">關鍵在於在步驟 6 之前完成所有步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-156">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="672ef-157">如果您將整個租使用者範圍的政策設定為其中一種商務用 Skype 模式，請務必像先前所述明確指派群島模式，以將現有群島使用者指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="672ef-157">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="672ef-158">如果您尚未這麼做，請設定商務用 [Skype 混合式組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="672ef-158">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="672ef-159">設定您的租使用者進行直接路由。</span><span class="sxs-lookup"><span data-stu-id="672ef-159">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="672ef-160">請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="672ef-160">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="672ef-161">如果需要，請針對這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-161">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="672ef-162">這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組組，最好在使用者升級至 TeamsOnly 之前執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="672ef-162">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="672ef-163">視需要指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="672ef-163">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="672ef-164">使用者應該同時擁有 Teams 和商務用 Skype Online 方案 2，以及電話系統。</span><span class="sxs-lookup"><span data-stu-id="672ef-164">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="672ef-165">如果商務用 Skype Online 方案 2 已停用，請重新啟用。</span><span class="sxs-lookup"><span data-stu-id="672ef-165">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="672ef-166">升級使用者：這些步驟必須協調一致。</span><span class="sxs-lookup"><span data-stu-id="672ef-166">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="672ef-167">使用內部部署商務用 Skype 工具，使用 -MoveToTeams Move-CsUser執行所有操作。</span><span class="sxs-lookup"><span data-stu-id="672ef-167">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="672ef-168">如果您使用的是不支援 -MoveToTeams 切換的商務用 Skype Server 版本，請先執行 Move-CsUser，然後在租使用者遠端 PowerShell 或 Teams 系統管理主控台中指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="672ef-168">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="672ef-169">在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。</span><span class="sxs-lookup"><span data-stu-id="672ef-169">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="672ef-170">在 Microsoft 365 或 Office 365 中：指派相關的 OnlineVoiceRoutingPolicy 以啟用撥出通話。</span><span class="sxs-lookup"><span data-stu-id="672ef-170">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="672ef-171">從內部部署商務用 Skype Server 與企業語音，到 Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="672ef-171">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="672ef-172">在此情況下，使用者仍位於內部部署商務用 Skype 中，而且他們的 PSTN 連接也是內部部署。</span><span class="sxs-lookup"><span data-stu-id="672ef-172">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="672ef-173">使用 PSTN 功能將這些使用者移往 TeamsOnly 模式，即表示將使用者移往雲端，並將他們的號碼從舊的電信公司移往 Microsoft 通話方案，或指派新號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="672ef-173">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="672ef-174">以下列出基本步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-174">The basic steps are listed below.</span></span><span data-ttu-id="672ef-175">步驟 1-5 會以建議的順序列出，但可以按照任何循序執行。</span><span class="sxs-lookup"><span data-stu-id="672ef-175">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="672ef-176">關鍵在於在步驟 6 之前完成所有步驟。</span><span class="sxs-lookup"><span data-stu-id="672ef-176">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="672ef-177">如果您將整個租使用者範圍的政策設定為其中一種商務用 Skype 模式，請務必像先前所述明確指派群島模式，以將現有群島使用者指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="672ef-177">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="672ef-178">如果您尚未這麼做，請設定商務用 [Skype 混合式組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="672ef-178">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="672ef-179">如果需要，請針對這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-179">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="672ef-180">這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組組，最好在使用者升級至 TeamsOnly 之前執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="672ef-180">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="672ef-181">視需要指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="672ef-181">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="672ef-182">使用者應該同時擁有 Teams 和商務用 Skype Online 方案 2，以及電話系統。</span><span class="sxs-lookup"><span data-stu-id="672ef-182">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="672ef-183">如果商務用 Skype Online 方案 2 已停用，請重新啟用。</span><span class="sxs-lookup"><span data-stu-id="672ef-183">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="672ef-184">取得使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="672ef-184">Get phone numbers for your users.</span></span> <span data-ttu-id="672ef-185"> (詳細資料請參閱 [管理](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)貴組織的電話號碼 .) </span><span class="sxs-lookup"><span data-stu-id="672ef-185">(For details see [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)</span></span>

   - <span data-ttu-id="672ef-186">如果您要重新使用這些號碼，請提交一份移植要求給電信公司。</span><span class="sxs-lookup"><span data-stu-id="672ef-186">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="672ef-187">或者，您也可以直接從 Microsoft 取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="672ef-187">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="672ef-188">升級使用者，並根據需要指派 LineUri。</span><span class="sxs-lookup"><span data-stu-id="672ef-188">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="672ef-189">使用內部部署商務用 Skype 工具，Move-CsUser -MoveToTeams 切換執行。</span><span class="sxs-lookup"><span data-stu-id="672ef-189">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="672ef-190">如果您要將數位移植到 Microsoft，您應該協調此作業的時機，以在埠出現時執行。</span><span class="sxs-lookup"><span data-stu-id="672ef-190">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="672ef-191">如果您使用的是 Microsoft 的新號碼，您必須變更使用者的 LineUri。</span><span class="sxs-lookup"><span data-stu-id="672ef-191">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="672ef-192">在使用 Set-CsOnlineVoiceUser 將使用者移至線上之後，必須執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="672ef-192">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="672ef-193">直接路由的每個租使用者組組摘要</span><span class="sxs-lookup"><span data-stu-id="672ef-193">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="672ef-194">請檢閱此清單， (SBC) 直接路由支援會話邊界 [控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="672ef-194">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="672ef-195">您也必須確保您擁有正確的固件版本。</span><span class="sxs-lookup"><span data-stu-id="672ef-195">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="672ef-196">將內部部署 SBC 與 Teams Direct 路由服務配對。</span><span class="sxs-lookup"><span data-stu-id="672ef-196">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="672ef-197">詳細資料請參閱 [將 SBC 配對至電話系統的直接路由服務](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="672ef-197">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="672ef-198">此組式基本上是內部部署配置的鏡像。</span><span class="sxs-lookup"><span data-stu-id="672ef-198">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="672ef-199">線上組組包括：</span><span class="sxs-lookup"><span data-stu-id="672ef-199">The online configuration consists of:</span></span> 
   - <span data-ttu-id="672ef-200">OnlineVoiceRoutingPolicy (根據內部部署 VoiceRoutingPolicy 從商務用 Skype Online 移移使用者，以及使用企業語音) 從內部部署移移使用者的 VoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="672ef-200">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="672ef-201">OnlinePSTNUsage 物件 (內部部署 PSTN 使用量) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-201">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="672ef-202">OnlineVoiceRoute 物件 (內部部署 VoiceRoute) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-202">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="672ef-203">詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="672ef-203">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="672ef-204">在移移期間管理 EnterpriseVoiceEnabled 屬性</span><span class="sxs-lookup"><span data-stu-id="672ef-204">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="672ef-205">無論使用直接路由還是 Microsoft 通話方案，使用者都必須在 Azure AD 中擁有 EnterpriseVoiceEnabled=true，使用者必須具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="672ef-205">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="672ef-206">EnterpriseVoiceEnabled (「啟用 EV") 是一種屬性 (而非存在於內部部署目錄和雲端) 之策略) 。</span><span class="sxs-lookup"><span data-stu-id="672ef-206">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="672ef-207">雲端中的值對於 Teams 來說很重要。</span><span class="sxs-lookup"><span data-stu-id="672ef-207">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="672ef-208">啟用 EV 的方式設定為 True 的確切邏輯取決於下列案例：</span><span class="sxs-lookup"><span data-stu-id="672ef-208">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="672ef-209">如果使用者在內部部署商務用 Skype Server 中已啟用 EV，且在使用 Move-CsUser 將使用者移至雲端之前，已指派電話系統授權給使用者，則線上使用者會以 EV-enabled=true 進行配置。</span><span class="sxs-lookup"><span data-stu-id="672ef-209">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="672ef-210">如果現有的 TeamsOnly 或商務用 Skype Online 使用者已指派電話系統授權，則根據預設，啟用 EV 的使用者不會設定為 True。</span><span class="sxs-lookup"><span data-stu-id="672ef-210">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="672ef-211">在指派電話系統授權之前，內部部署使用者已移至雲端的情況也一樣。</span><span class="sxs-lookup"><span data-stu-id="672ef-211">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="672ef-212">在這兩種情況下，系統管理員都必須指定下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="672ef-212">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="672ef-213">相關連結</span><span class="sxs-lookup"><span data-stu-id="672ef-213">Related links</span></span>

[<span data-ttu-id="672ef-214">規劃您的 Teams 語音解決方案</span><span class="sxs-lookup"><span data-stu-id="672ef-214">Plan your Teams voice solution</span></span>](cloud-voice-landing-page.md)

[<span data-ttu-id="672ef-215">使用 Teams 與商務用 Skype 的組織移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="672ef-215">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="672ef-216">設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="672ef-216">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="672ef-217">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="672ef-217">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="672ef-218">設定您的共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="672ef-218">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="672ef-219">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="672ef-219">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="672ef-220">使用會議移 (MMS) </span><span class="sxs-lookup"><span data-stu-id="672ef-220">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)