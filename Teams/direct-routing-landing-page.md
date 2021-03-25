---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解直接路由，例如組態、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122207"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="a6005-103">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-103">Phone System Direct Routing</span></span>

<span data-ttu-id="a6005-104">您已完成[開始使用](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="a6005-105">您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="a6005-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="a6005-106">您可能已經部署會議 [&會議](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="a6005-107">現在，您已準備好新增雲端語音工作負載，而且您決定使用自己的電話電信業者來使用公用交換電話網路 (PSTN) 電話系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="a6005-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="a6005-108">透過直接路由，您就可以實際地透過任何電信運營公司使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="a6005-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="a6005-109">本文將說明直接路由的核心部署決策，以及您可能想要根據貴組織的需求考慮的其他考慮。</span><span class="sxs-lookup"><span data-stu-id="a6005-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="a6005-110">您也應該閱讀 [Microsoft Teams 中的雲端語音](cloud-voice-landing-page.md) ，以瞭解更多關於 Microsoft 雲端語音產品的資訊。</span><span class="sxs-lookup"><span data-stu-id="a6005-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="a6005-111">深入瞭解直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="a6005-112">下列文章提供有關配置及使用電話系統直接路由的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="a6005-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="a6005-113">要配置直接路由，必須瞭解 PSTN 路由設計。</span><span class="sxs-lookup"><span data-stu-id="a6005-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="a6005-114">您應該閱讀所有這些文章，瞭解如何規劃及設定直接路由：</span><span class="sxs-lookup"><span data-stu-id="a6005-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="a6005-115">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="a6005-116">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="a6005-117">通過直接路由認證的工作階段邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="a6005-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="a6005-118">監視和疑難排解直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="a6005-119">此外，根據您的需求，您可能會想要閱讀下列文章：</span><span class="sxs-lookup"><span data-stu-id="a6005-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="a6005-120">設定多個租用戶的工作階段邊界控制器</span><span class="sxs-lookup"><span data-stu-id="a6005-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="a6005-121">移轉至直接路由</span><span class="sxs-lookup"><span data-stu-id="a6005-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="a6005-122">含有 PSTN 連線功能的混合式環境中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a6005-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="a6005-123">觀看下列會話以深入瞭解直接路由 [：Microsoft Teams 中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a6005-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="a6005-124">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="a6005-124">Core deployment decisions</span></span>

<span data-ttu-id="a6005-125">這些是直接路由應考慮的核心決策。</span><span class="sxs-lookup"><span data-stu-id="a6005-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="a6005-126">問問自己</span><span class="sxs-lookup"><span data-stu-id="a6005-126">Ask yourself</span></span>|<span data-ttu-id="a6005-127">動作</span><span class="sxs-lookup"><span data-stu-id="a6005-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="a6005-128">我要為哪些使用者啟用直接路由？</span><span class="sxs-lookup"><span data-stu-id="a6005-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="a6005-129">詳細資訊，請參閱啟用 [使用者進行直接路由服務](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="a6005-130">我是否擁有直接路由所需的授權？</span><span class="sxs-lookup"><span data-stu-id="a6005-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="a6005-131">詳細資訊，請參閱 [授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a6005-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="a6005-132">會話邊界控制器 (SBC) 考慮</span><span class="sxs-lookup"><span data-stu-id="a6005-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="a6005-133">使用直接路由，您可以直接將您自己的會話邊界控制器 (SBC) 電話系統。</span><span class="sxs-lookup"><span data-stu-id="a6005-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="a6005-134">有關認證 SBCs 的清單，請參閱 [支援的會話邊界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="a6005-135">問問自己</span><span class="sxs-lookup"><span data-stu-id="a6005-135">Ask yourself</span></span>|<span data-ttu-id="a6005-136">動作</span><span class="sxs-lookup"><span data-stu-id="a6005-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a6005-137">我要在哪裡以及如何部署 SBCs？</span><span class="sxs-lookup"><span data-stu-id="a6005-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="a6005-138">詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a6005-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="a6005-139">我有多個租使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="a6005-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="a6005-140">詳細資訊，請參閱為多個租使用者設定 [會話邊界控制器](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="a6005-141">語音路由考慮</span><span class="sxs-lookup"><span data-stu-id="a6005-141">Voice routing considerations</span></span>

<span data-ttu-id="a6005-142">您必須設定電話系統，將通話路由至特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="a6005-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="a6005-143">問問自己</span><span class="sxs-lookup"><span data-stu-id="a6005-143">Ask yourself</span></span>|<span data-ttu-id="a6005-144">動作</span><span class="sxs-lookup"><span data-stu-id="a6005-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a6005-145">我需要建立哪些語音路由策略、PSTN 使用量和語音路由？</span><span class="sxs-lookup"><span data-stu-id="a6005-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="a6005-146">若要瞭解語音路由資訊，請參閱 [設定語音路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="a6005-147">哪些使用者會指派給我定義的語音路由策略？</span><span class="sxs-lookup"><span data-stu-id="a6005-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="a6005-148">請參閱設定語音 [路由中的範例](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="a6005-149">使用 TeamsUpgradePolicy 確保 Teams 用戶端內接來電</span><span class="sxs-lookup"><span data-stu-id="a6005-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="a6005-150">只有 Microsoft Teams 支援直接路由。</span><span class="sxs-lookup"><span data-stu-id="a6005-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="a6005-151">若要透過直接路由接收 PSTN 通話，您必須設定 TeamsUpgradePolicy，以確保在 Teams 中接聽來電。</span><span class="sxs-lookup"><span data-stu-id="a6005-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="a6005-152">使用者必須進入 Teams Only 模式，您可以指派 TeamsUpgradePolicy 的 「UpgradeToTeams」實例給他們。</span><span class="sxs-lookup"><span data-stu-id="a6005-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="a6005-153">問問自己</span><span class="sxs-lookup"><span data-stu-id="a6005-153">Ask yourself</span></span>|<span data-ttu-id="a6005-154">動作</span><span class="sxs-lookup"><span data-stu-id="a6005-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="a6005-155">Teams Only 模式是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="a6005-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="a6005-156">詳細資訊請參閱將 Teams 與商務用 Skype 一起 [使用的組織](./migration-interop-guidance-for-teams-with-skype.md)移移和互通性指南。</span><span class="sxs-lookup"><span data-stu-id="a6005-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="a6005-157">其他部署考慮</span><span class="sxs-lookup"><span data-stu-id="a6005-157">Additional deployment considerations</span></span>

<span data-ttu-id="a6005-158">您可能會想要根據貴組織的需求和組組來考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="a6005-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="a6005-159">問問自己</span><span class="sxs-lookup"><span data-stu-id="a6005-159">Ask yourself</span></span>| <span data-ttu-id="a6005-160">動作</span><span class="sxs-lookup"><span data-stu-id="a6005-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="a6005-161">您是否有已配置混合式連接的現有商務用 Skype Server 部署？</span><span class="sxs-lookup"><span data-stu-id="a6005-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="a6005-162">若要瞭解混合式環境中使用者帳戶的部署與管理方式，請參閱使用 PSTN 連接的混合 [式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="a6005-163">您是否從通話方案或商務用 Skype 內部部署環境移向直接路由？</span><span class="sxs-lookup"><span data-stu-id="a6005-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="a6005-164">若要進一瞭解從現有環境移向直接路由，請參閱 [移遷移到直接路由](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="a6005-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||