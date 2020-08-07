---
title: Microsoft 團隊中的共用線條外觀
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
description: 瞭解如何在 Microsoft 團隊中傳送電子郵件給使用者的音訊會議資訊。
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583832"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="ac731-103">Microsoft 團隊中的共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="ac731-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="ac731-104">共用線外觀是委派功能的一部分，可讓使用者選擇代表代表對方接聽或處理通話的代理人。</span><span class="sxs-lookup"><span data-stu-id="ac731-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="ac731-105">如果使用者有可定期處理使用者來電的系統管理小幫手，這項功能很有説明。</span><span class="sxs-lookup"><span data-stu-id="ac731-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="ac731-106">在共用線外觀的內容中，管理員是授權代理人代表自己撥打或接聽電話的人員，而代理人可以代表其他人撥打及接聽來電。</span><span class="sxs-lookup"><span data-stu-id="ac731-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac731-107">此功能僅適用于 [僅限團隊部署模式]。</span><span class="sxs-lookup"><span data-stu-id="ac731-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="ac731-108">如需有關團隊部署模式的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="ac731-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="ac731-109">需要授權</span><span class="sxs-lookup"><span data-stu-id="ac731-109">License required</span></span>

<span data-ttu-id="ac731-110">使用者必須具備 PSTN 連線的電話系統， (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 為代理人或設定委派，並允許其他人代表對方撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="ac731-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="ac731-111">管理員和代理人都需要有 PSTN 連線的電話系統 (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="ac731-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="ac731-112">共用線體驗是委派的一部分，且包含在手機系統中。</span><span class="sxs-lookup"><span data-stu-id="ac731-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="ac731-113">如需授權模型的其他詳細資料，請參閱[Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ac731-113">For additional details on the licensing model, See [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="ac731-114">設定委派和共用線外觀</span><span class="sxs-lookup"><span data-stu-id="ac731-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="ac731-115">委派和共用線外觀是使用者驅動的功能：沒有要設定的系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="ac731-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="ac731-116">如需如何使用此功能的詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="ac731-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="ac731-117">租使用者管理員可以透過**TeamsCallingPolicy AllowDelegation**設定或透過團隊管理入口網站來啟用委派，這項功能才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="ac731-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="ac731-118">租使用者管理員也可以設定小組系統管理中心中使用者的委派關聯性。</span><span class="sxs-lookup"><span data-stu-id="ac731-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="ac731-119">此外，使用者也可以直接在團隊中設定其委派關聯性。</span><span class="sxs-lookup"><span data-stu-id="ac731-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="ac731-120">租使用者管理員或使用者無法彼此封鎖設定，但是團隊系統管理中心和團隊用戶端應該在這兩個位置中正確顯示這種關聯性。</span><span class="sxs-lookup"><span data-stu-id="ac731-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ac731-121">當租使用者在 (開啟) 之後關閉該使用者的委派時，他們也需要在小組系統管理中心清除該使用者的委派關聯，以免呼叫路由不正確。</span><span class="sxs-lookup"><span data-stu-id="ac731-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="ac731-122">共用線外觀功能可用性</span><span class="sxs-lookup"><span data-stu-id="ac731-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="ac731-123">下列應用程式和裝置目前支援共用線外觀。</span><span class="sxs-lookup"><span data-stu-id="ac731-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="ac731-124">功能</span><span class="sxs-lookup"><span data-stu-id="ac731-124">Capability</span></span> | <span data-ttu-id="ac731-125">團隊桌面</span><span class="sxs-lookup"><span data-stu-id="ac731-125">Teams Desktop</span></span> | <span data-ttu-id="ac731-126">團隊 Mac 應用程式</span><span class="sxs-lookup"><span data-stu-id="ac731-126">Teams Mac App</span></span> | <span data-ttu-id="ac731-127">團隊 Web App (邊緣) </span><span class="sxs-lookup"><span data-stu-id="ac731-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="ac731-128">團隊行動 iOS/Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="ac731-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="ac731-129">團隊 IP 電話</span><span class="sxs-lookup"><span data-stu-id="ac731-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="ac731-130">設定委派</span><span class="sxs-lookup"><span data-stu-id="ac731-130">Set up delegation</span></span> | <span data-ttu-id="ac731-131">是</span><span class="sxs-lookup"><span data-stu-id="ac731-131">Yes</span></span> | <span data-ttu-id="ac731-132">是</span><span class="sxs-lookup"><span data-stu-id="ac731-132">Yes</span></span> | <span data-ttu-id="ac731-133">是</span><span class="sxs-lookup"><span data-stu-id="ac731-133">Yes</span></span> | <span data-ttu-id="ac731-134">否</span><span class="sxs-lookup"><span data-stu-id="ac731-134">No</span></span> | <span data-ttu-id="ac731-135">是</span><span class="sxs-lookup"><span data-stu-id="ac731-135">Yes</span></span> |
| <span data-ttu-id="ac731-136">代表其他方式接聽來電</span><span class="sxs-lookup"><span data-stu-id="ac731-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="ac731-137">是</span><span class="sxs-lookup"><span data-stu-id="ac731-137">Yes</span></span> | <span data-ttu-id="ac731-138">是</span><span class="sxs-lookup"><span data-stu-id="ac731-138">Yes</span></span> | <span data-ttu-id="ac731-139">是</span><span class="sxs-lookup"><span data-stu-id="ac731-139">Yes</span></span> | <span data-ttu-id="ac731-140">是</span><span class="sxs-lookup"><span data-stu-id="ac731-140">Yes</span></span> | <span data-ttu-id="ac731-141">是</span><span class="sxs-lookup"><span data-stu-id="ac731-141">Yes</span></span> |
| <span data-ttu-id="ac731-142">代表其他電話撥打電話號碼</span><span class="sxs-lookup"><span data-stu-id="ac731-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="ac731-143">是</span><span class="sxs-lookup"><span data-stu-id="ac731-143">Yes</span></span> | <span data-ttu-id="ac731-144">是</span><span class="sxs-lookup"><span data-stu-id="ac731-144">Yes</span></span> | <span data-ttu-id="ac731-145">是</span><span class="sxs-lookup"><span data-stu-id="ac731-145">Yes</span></span> | <span data-ttu-id="ac731-146">是</span><span class="sxs-lookup"><span data-stu-id="ac731-146">Yes</span></span> | <span data-ttu-id="ac731-147">是</span><span class="sxs-lookup"><span data-stu-id="ac731-147">Yes</span></span> |
| <span data-ttu-id="ac731-148">代表其他使用者呼叫團隊使用者</span><span class="sxs-lookup"><span data-stu-id="ac731-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="ac731-149">是</span><span class="sxs-lookup"><span data-stu-id="ac731-149">Yes</span></span> | <span data-ttu-id="ac731-150">是</span><span class="sxs-lookup"><span data-stu-id="ac731-150">Yes</span></span> | <span data-ttu-id="ac731-151">是</span><span class="sxs-lookup"><span data-stu-id="ac731-151">Yes</span></span> | <span data-ttu-id="ac731-152">是</span><span class="sxs-lookup"><span data-stu-id="ac731-152">Yes</span></span> | <span data-ttu-id="ac731-153">是</span><span class="sxs-lookup"><span data-stu-id="ac731-153">Yes</span></span> |
| <span data-ttu-id="ac731-154">查看共用線的系統管理視圖</span><span class="sxs-lookup"><span data-stu-id="ac731-154">See the admin view of shared lines</span></span> | <span data-ttu-id="ac731-155">是</span><span class="sxs-lookup"><span data-stu-id="ac731-155">Yes</span></span> | <span data-ttu-id="ac731-156">是</span><span class="sxs-lookup"><span data-stu-id="ac731-156">Yes</span></span> | <span data-ttu-id="ac731-157">是</span><span class="sxs-lookup"><span data-stu-id="ac731-157">Yes</span></span> | <span data-ttu-id="ac731-158">否</span><span class="sxs-lookup"><span data-stu-id="ac731-158">No</span></span> | <span data-ttu-id="ac731-159">否</span><span class="sxs-lookup"><span data-stu-id="ac731-159">No</span></span> |
| <span data-ttu-id="ac731-160">請參閱管理員的通話活動管理檢視</span><span class="sxs-lookup"><span data-stu-id="ac731-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="ac731-161">是</span><span class="sxs-lookup"><span data-stu-id="ac731-161">Yes</span></span> | <span data-ttu-id="ac731-162">是</span><span class="sxs-lookup"><span data-stu-id="ac731-162">Yes</span></span> | <span data-ttu-id="ac731-163">是</span><span class="sxs-lookup"><span data-stu-id="ac731-163">Yes</span></span> | <span data-ttu-id="ac731-164">否</span><span class="sxs-lookup"><span data-stu-id="ac731-164">No</span></span> | <span data-ttu-id="ac731-165">否</span><span class="sxs-lookup"><span data-stu-id="ac731-165">No</span></span> |
| <span data-ttu-id="ac731-166">請參閱代理人的管理員視圖</span><span class="sxs-lookup"><span data-stu-id="ac731-166">See the manager view of delegates</span></span> | <span data-ttu-id="ac731-167">是</span><span class="sxs-lookup"><span data-stu-id="ac731-167">Yes</span></span> | <span data-ttu-id="ac731-168">是</span><span class="sxs-lookup"><span data-stu-id="ac731-168">Yes</span></span> | <span data-ttu-id="ac731-169">是</span><span class="sxs-lookup"><span data-stu-id="ac731-169">Yes</span></span> | <span data-ttu-id="ac731-170">否</span><span class="sxs-lookup"><span data-stu-id="ac731-170">No</span></span> | <span data-ttu-id="ac731-171">否</span><span class="sxs-lookup"><span data-stu-id="ac731-171">No</span></span> |
| <span data-ttu-id="ac731-172">系統管理員或經理可以保留或繼續</span><span class="sxs-lookup"><span data-stu-id="ac731-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="ac731-173">是</span><span class="sxs-lookup"><span data-stu-id="ac731-173">Yes</span></span> | <span data-ttu-id="ac731-174">是</span><span class="sxs-lookup"><span data-stu-id="ac731-174">Yes</span></span> | <span data-ttu-id="ac731-175">是</span><span class="sxs-lookup"><span data-stu-id="ac731-175">Yes</span></span> | <span data-ttu-id="ac731-176">否</span><span class="sxs-lookup"><span data-stu-id="ac731-176">No</span></span> | <span data-ttu-id="ac731-177">否</span><span class="sxs-lookup"><span data-stu-id="ac731-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="ac731-178">有限</span><span class="sxs-lookup"><span data-stu-id="ac731-178">Limitations</span></span>

<span data-ttu-id="ac731-179">管理員最多可以新增25個代理人，而代理人最多可有25個經理。</span><span class="sxs-lookup"><span data-stu-id="ac731-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="ac731-180">可在租使用者中建立的委派關聯數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="ac731-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="ac731-181">如果 delegator 和委派不在同一個地理位置，則由 PSTN 提供者允許撥打電話給委派 (的不同地理位置，代表) 通話。</span><span class="sxs-lookup"><span data-stu-id="ac731-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="ac731-182">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ac731-182">More information</span></span>

[<span data-ttu-id="ac731-183">與代理人共用電話線路</span><span class="sxs-lookup"><span data-stu-id="ac731-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
