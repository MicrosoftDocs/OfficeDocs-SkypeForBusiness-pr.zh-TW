---
title: 共用線條外觀Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中傳送包含其音訊會議資訊Microsoft Teams。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117041"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="924d2-103">共用線條外觀Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="924d2-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="924d2-104">共用線路外觀是委派功能中的一部分，讓使用者選擇代理人來代表他們接聽或處理通話。</span><span class="sxs-lookup"><span data-stu-id="924d2-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="924d2-105">如果使用者有系統管理助理定期處理使用者的通話，這項功能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="924d2-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="924d2-106">在共用線路外觀中，主管是授權代理人代表代理人撥打或接聽電話的人，而代理人可以代表其他人撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="924d2-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="924d2-107">此功能僅適用于僅部署Teams模式。</span><span class="sxs-lookup"><span data-stu-id="924d2-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="924d2-108">有關部署模式Teams，請參閱瞭解Microsoft Teams及商務用 Skype[互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="924d2-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="924d2-109">需要授權</span><span class="sxs-lookup"><span data-stu-id="924d2-109">License required</span></span>

<span data-ttu-id="924d2-110">使用者必須擁有電話系統 PSTN 連線 (電話方案授權或直接路由 OnlineVoiceRoutingPolicy) 才能成為代理人或設定委派，並讓他人代表他們撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="924d2-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="924d2-111">管理員和代理人必須電話系統 PSTN 連線 (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="924d2-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="924d2-112">共用行體驗是委派的一部分，並包含在電話系統。</span><span class="sxs-lookup"><span data-stu-id="924d2-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="924d2-113">有關授權模型的其他詳細資料，請參閱Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="924d2-113">For additional details on the licensing model, See [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="924d2-114">配置委派和共用行外觀</span><span class="sxs-lookup"><span data-stu-id="924d2-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="924d2-115">委派和共用行外觀是使用者導向的功能：不需要設定系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="924d2-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="924d2-116">若要瞭解如何使用此功能，請參閱與代理人共用 [電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="924d2-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="924d2-117">租使用者系統管理員可以透過 **TeamsCallingPolicy AllowDelegation** 設定，或透過 Teams系統管理入口網站啟用委派，讓此功能能夠執行。</span><span class="sxs-lookup"><span data-stu-id="924d2-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="924d2-118">租使用者系統管理員也可以為系統管理中心中的使用者Teams關係。</span><span class="sxs-lookup"><span data-stu-id="924d2-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="924d2-119">此外，使用者也可以直接在 Teams 中設定其委派Teams。</span><span class="sxs-lookup"><span data-stu-id="924d2-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="924d2-120">租使用者系統管理員或使用者無法彼此封鎖該組Teams系統管理中心Teams用戶端應該在這兩個地方正確顯示此關係。</span><span class="sxs-lookup"><span data-stu-id="924d2-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="924d2-121">當租使用者系統管理員在) 開啟使用者 (後關閉使用者的委派時，他們也需要在 Teams 系統管理中心清理該使用者的委派關係，以避免不正確的通話路由。</span><span class="sxs-lookup"><span data-stu-id="924d2-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="924d2-122">共用線條外觀功能可用性</span><span class="sxs-lookup"><span data-stu-id="924d2-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="924d2-123">下列應用程式與裝置目前支援共用線路外觀。</span><span class="sxs-lookup"><span data-stu-id="924d2-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="924d2-124">功能</span><span class="sxs-lookup"><span data-stu-id="924d2-124">Capability</span></span> | <span data-ttu-id="924d2-125">Teams桌面</span><span class="sxs-lookup"><span data-stu-id="924d2-125">Teams Desktop</span></span> | <span data-ttu-id="924d2-126">TeamsMac App</span><span class="sxs-lookup"><span data-stu-id="924d2-126">Teams Mac App</span></span> | <span data-ttu-id="924d2-127">TeamsWeb App (Edge) </span><span class="sxs-lookup"><span data-stu-id="924d2-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="924d2-128">Teams行動版 iOS/Android App</span><span class="sxs-lookup"><span data-stu-id="924d2-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="924d2-129">TeamsIP 電話</span><span class="sxs-lookup"><span data-stu-id="924d2-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="924d2-130">設定委派</span><span class="sxs-lookup"><span data-stu-id="924d2-130">Set up delegation</span></span> | <span data-ttu-id="924d2-131">是</span><span class="sxs-lookup"><span data-stu-id="924d2-131">Yes</span></span> | <span data-ttu-id="924d2-132">是</span><span class="sxs-lookup"><span data-stu-id="924d2-132">Yes</span></span> | <span data-ttu-id="924d2-133">是</span><span class="sxs-lookup"><span data-stu-id="924d2-133">Yes</span></span> | <span data-ttu-id="924d2-134">否</span><span class="sxs-lookup"><span data-stu-id="924d2-134">No</span></span> | <span data-ttu-id="924d2-135">是</span><span class="sxs-lookup"><span data-stu-id="924d2-135">Yes</span></span> |
| <span data-ttu-id="924d2-136">代表另一人接聽來電</span><span class="sxs-lookup"><span data-stu-id="924d2-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="924d2-137">是</span><span class="sxs-lookup"><span data-stu-id="924d2-137">Yes</span></span> | <span data-ttu-id="924d2-138">是</span><span class="sxs-lookup"><span data-stu-id="924d2-138">Yes</span></span> | <span data-ttu-id="924d2-139">是</span><span class="sxs-lookup"><span data-stu-id="924d2-139">Yes</span></span> | <span data-ttu-id="924d2-140">是</span><span class="sxs-lookup"><span data-stu-id="924d2-140">Yes</span></span> | <span data-ttu-id="924d2-141">是</span><span class="sxs-lookup"><span data-stu-id="924d2-141">Yes</span></span> |
| <span data-ttu-id="924d2-142">代表另一個人撥打電話號碼</span><span class="sxs-lookup"><span data-stu-id="924d2-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="924d2-143">是</span><span class="sxs-lookup"><span data-stu-id="924d2-143">Yes</span></span> | <span data-ttu-id="924d2-144">是</span><span class="sxs-lookup"><span data-stu-id="924d2-144">Yes</span></span> | <span data-ttu-id="924d2-145">是</span><span class="sxs-lookup"><span data-stu-id="924d2-145">Yes</span></span> | <span data-ttu-id="924d2-146">是</span><span class="sxs-lookup"><span data-stu-id="924d2-146">Yes</span></span> | <span data-ttu-id="924d2-147">是</span><span class="sxs-lookup"><span data-stu-id="924d2-147">Yes</span></span> |
| <span data-ttu-id="924d2-148">代表Teams打電話給使用者</span><span class="sxs-lookup"><span data-stu-id="924d2-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="924d2-149">是</span><span class="sxs-lookup"><span data-stu-id="924d2-149">Yes</span></span> | <span data-ttu-id="924d2-150">是</span><span class="sxs-lookup"><span data-stu-id="924d2-150">Yes</span></span> | <span data-ttu-id="924d2-151">是</span><span class="sxs-lookup"><span data-stu-id="924d2-151">Yes</span></span> | <span data-ttu-id="924d2-152">是</span><span class="sxs-lookup"><span data-stu-id="924d2-152">Yes</span></span> | <span data-ttu-id="924d2-153">是</span><span class="sxs-lookup"><span data-stu-id="924d2-153">Yes</span></span> |
| <span data-ttu-id="924d2-154">查看共用行的系統管理員視圖</span><span class="sxs-lookup"><span data-stu-id="924d2-154">See the admin view of shared lines</span></span> | <span data-ttu-id="924d2-155">是</span><span class="sxs-lookup"><span data-stu-id="924d2-155">Yes</span></span> | <span data-ttu-id="924d2-156">是</span><span class="sxs-lookup"><span data-stu-id="924d2-156">Yes</span></span> | <span data-ttu-id="924d2-157">是</span><span class="sxs-lookup"><span data-stu-id="924d2-157">Yes</span></span> | <span data-ttu-id="924d2-158">否</span><span class="sxs-lookup"><span data-stu-id="924d2-158">No</span></span> | <span data-ttu-id="924d2-159">否</span><span class="sxs-lookup"><span data-stu-id="924d2-159">No</span></span> |
| <span data-ttu-id="924d2-160">查看管理員通話活動的系統管理員視圖</span><span class="sxs-lookup"><span data-stu-id="924d2-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="924d2-161">是</span><span class="sxs-lookup"><span data-stu-id="924d2-161">Yes</span></span> | <span data-ttu-id="924d2-162">是</span><span class="sxs-lookup"><span data-stu-id="924d2-162">Yes</span></span> | <span data-ttu-id="924d2-163">是</span><span class="sxs-lookup"><span data-stu-id="924d2-163">Yes</span></span> | <span data-ttu-id="924d2-164">否</span><span class="sxs-lookup"><span data-stu-id="924d2-164">No</span></span> | <span data-ttu-id="924d2-165">否</span><span class="sxs-lookup"><span data-stu-id="924d2-165">No</span></span> |
| <span data-ttu-id="924d2-166">查看代理人的管理員視圖</span><span class="sxs-lookup"><span data-stu-id="924d2-166">See the manager view of delegates</span></span> | <span data-ttu-id="924d2-167">是</span><span class="sxs-lookup"><span data-stu-id="924d2-167">Yes</span></span> | <span data-ttu-id="924d2-168">是</span><span class="sxs-lookup"><span data-stu-id="924d2-168">Yes</span></span> | <span data-ttu-id="924d2-169">是</span><span class="sxs-lookup"><span data-stu-id="924d2-169">Yes</span></span> | <span data-ttu-id="924d2-170">否</span><span class="sxs-lookup"><span data-stu-id="924d2-170">No</span></span> | <span data-ttu-id="924d2-171">否</span><span class="sxs-lookup"><span data-stu-id="924d2-171">No</span></span> |
| <span data-ttu-id="924d2-172">系統管理員或管理員可以保留或繼續</span><span class="sxs-lookup"><span data-stu-id="924d2-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="924d2-173">是</span><span class="sxs-lookup"><span data-stu-id="924d2-173">Yes</span></span> | <span data-ttu-id="924d2-174">是</span><span class="sxs-lookup"><span data-stu-id="924d2-174">Yes</span></span> | <span data-ttu-id="924d2-175">是</span><span class="sxs-lookup"><span data-stu-id="924d2-175">Yes</span></span> | <span data-ttu-id="924d2-176">否</span><span class="sxs-lookup"><span data-stu-id="924d2-176">No</span></span> | <span data-ttu-id="924d2-177">否</span><span class="sxs-lookup"><span data-stu-id="924d2-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="924d2-178">限制</span><span class="sxs-lookup"><span data-stu-id="924d2-178">Limitations</span></span>

<span data-ttu-id="924d2-179">管理員最多可以新增 25 個代理人，而代理人最多可以有 25 名主管。</span><span class="sxs-lookup"><span data-stu-id="924d2-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="924d2-180">在租使用者中可以建立委派關係的數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="924d2-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="924d2-181">如果委派者與代理人不在同一個地理位置，則由 PST (N 提供者代表) 通話，允許代理人從不同的地理位置顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="924d2-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="924d2-182">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="924d2-182">More information</span></span>

[<span data-ttu-id="924d2-183">與代理人共用電話線</span><span class="sxs-lookup"><span data-stu-id="924d2-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)