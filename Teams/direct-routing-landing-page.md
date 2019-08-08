---
title: 電話系統直向路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: 直接路由的登陸頁面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dca9fda99973931cff70301da089f6d0c3f4a9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236583"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="1e0bd-103">電話系統直向路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-103">Phone System Direct Routing</span></span>

<span data-ttu-id="1e0bd-104">您已完成[快速入門](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="1e0bd-105">您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="1e0bd-106">也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="1e0bd-107">現在您已經準備好要新增雲端語音工作負載, 而您決定要使用自己的電話運營公司來取得公用交換電話網絡 (PSTN) 連線, 方法是使用 [電話系統直向] 路由。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="1e0bd-108">透過直接路由, 您可以在幾乎任何電話運營商中使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="1e0bd-109">本文將說明直接路由的核心部署決策, 以及您可能想要考慮的其他考慮因素 (視貴組織的需求而定)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="1e0bd-110">您也應該閱讀[Microsoft 團隊中的雲端語音](cloud-voice-landing-page.md), 以取得關於 Microsoft 雲端語音服務的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="1e0bd-111">深入瞭解直接路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="1e0bd-112">下列文章提供有關設定和使用 [電話系統直接路由] 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="1e0bd-113">設定直接路由需要瞭解 PSTN 路由設計。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="1e0bd-114">您應該閱讀所有這些文章, 以瞭解如何規劃及設定直接路由:</span><span class="sxs-lookup"><span data-stu-id="1e0bd-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="1e0bd-115">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="1e0bd-116">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="1e0bd-117">認證以直接路由的會話邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="1e0bd-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="1e0bd-118">監控並疑難排解直接路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="1e0bd-119">此外, 根據您的需求, 您可能會想要閱讀下列文章:</span><span class="sxs-lookup"><span data-stu-id="1e0bd-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="1e0bd-120">針對多個承租人設定會話框線控制器</span><span class="sxs-lookup"><span data-stu-id="1e0bd-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="1e0bd-121">遷移至直接路由</span><span class="sxs-lookup"><span data-stu-id="1e0bd-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="1e0bd-122">具有 PSTN 連接的混合式環境中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1e0bd-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="1e0bd-123">觀看下列會話以深入瞭解直接路由: [Microsoft 團隊中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="1e0bd-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="1e0bd-124">核心部署決定</span><span class="sxs-lookup"><span data-stu-id="1e0bd-124">Core deployment decisions</span></span>

<span data-ttu-id="1e0bd-125">以下是直接路由所需考慮的核心決策。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="1e0bd-126">問自己</span><span class="sxs-lookup"><span data-stu-id="1e0bd-126">Ask yourself</span></span>|<span data-ttu-id="1e0bd-127">執行</span><span class="sxs-lookup"><span data-stu-id="1e0bd-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="1e0bd-128">我要對哪些使用者啟用直接路由？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="1e0bd-129">如需詳細資訊, 請參閱[啟用直接路由服務的使用者](direct-routing-configure.md#enable-users-for-direct-routing-service)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="1e0bd-130">我是否有直接路由所需的授權？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="1e0bd-131">如需詳細資訊, 請參閱[授權及其他需求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="1e0bd-132">會話邊界控制器 (SBC) 考慮</span><span class="sxs-lookup"><span data-stu-id="1e0bd-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="1e0bd-133">使用直接路由, 您可以直接將自己的會話邊界控制器 (SBC) 連線至 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="1e0bd-134">如需已驗證的 SBCs 清單, 請參閱[支援的會話框線控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="1e0bd-135">問自己</span><span class="sxs-lookup"><span data-stu-id="1e0bd-135">Ask yourself</span></span>|<span data-ttu-id="1e0bd-136">執行</span><span class="sxs-lookup"><span data-stu-id="1e0bd-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="1e0bd-137">我要如何部署 SBCs？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="1e0bd-138">如需詳細資訊, 請參閱[設定直接路由](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1e0bd-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="1e0bd-139">我有多個承租人嗎？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="1e0bd-140">如需詳細資訊, 請參閱為[多個承租人設定會話框線控制器](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="1e0bd-141">語音路由考慮</span><span class="sxs-lookup"><span data-stu-id="1e0bd-141">Voice routing considerations</span></span>

<span data-ttu-id="1e0bd-142">您必須設定 [電話系統], 將呼叫路由到特定的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="1e0bd-143">問自己</span><span class="sxs-lookup"><span data-stu-id="1e0bd-143">Ask yourself</span></span>|<span data-ttu-id="1e0bd-144">執行</span><span class="sxs-lookup"><span data-stu-id="1e0bd-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="1e0bd-145">我需要建立哪些語音路由策略、PSTN 使用及語音路由？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="1e0bd-146">如需語音路由資訊, 請參閱[設定語音路由](direct-routing-configure.md#configure-voice-routing)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="1e0bd-147">系統會將哪些使用者指派給我定義的語音路由策略？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="1e0bd-148">請參閱[設定語音路由](direct-routing-configure.md#configure-voice-routing)中的範例。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="1e0bd-149">通話和交互操作原則</span><span class="sxs-lookup"><span data-stu-id="1e0bd-149">Calling and interop policies</span></span>

<span data-ttu-id="1e0bd-150">只有 Microsoft 團隊支援直接傳送。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="1e0bd-151">若要透過直接佈線來撥打或接聽 PSTN 電話, 您必須設定必要的原則, 以確保在團隊中接收來電。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="1e0bd-152">您可以將團隊設定為 [僅限團隊] 模式, 或將團隊設定為首選呼叫用戶端 (方法是指派 TeamsCallingPolicy 和 TeamsInteropPolicy), 以將團隊設定為呼叫的首選用戶端。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="1e0bd-153">問自己</span><span class="sxs-lookup"><span data-stu-id="1e0bd-153">Ask yourself</span></span>|<span data-ttu-id="1e0bd-154">執行</span><span class="sxs-lookup"><span data-stu-id="1e0bd-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1e0bd-155">我要如何將團隊設定為適用于通話的首選用戶端？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="1e0bd-156">如需詳細資訊, 請參閱[將 Microsoft 團隊設定為使用者的首選呼叫用戶端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="1e0bd-157">其他部署考慮</span><span class="sxs-lookup"><span data-stu-id="1e0bd-157">Additional deployment considerations</span></span>

<span data-ttu-id="1e0bd-158">根據貴組織的需求和設定, 您可能會想要考慮下列事項:</span><span class="sxs-lookup"><span data-stu-id="1e0bd-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="1e0bd-159">問自己</span><span class="sxs-lookup"><span data-stu-id="1e0bd-159">Ask yourself</span></span>| <span data-ttu-id="1e0bd-160">執行</span><span class="sxs-lookup"><span data-stu-id="1e0bd-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="1e0bd-161">您是否有已設定混合式連線性的現有商務用 Skype 伺服器部署？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="1e0bd-162">若要瞭解混合式環境中的使用者帳戶是如何提供和管理的, 請參閱[在具有 PSTN 連線的混合式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="1e0bd-163">您是否要從通話方案或商務用 Skype 內部部署環境直接傳送路線？</span><span class="sxs-lookup"><span data-stu-id="1e0bd-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="1e0bd-164">若要深入瞭解從現有環境遷移至直接路由的詳細資訊, 請參閱[遷移至直接路由](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="1e0bd-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
