---
title: Microsoft 團隊中的共用線條外觀
ms.author: lolaj
author: LolaJacobsen
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
f1keywords:
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
ms.custom:
- Phone System
description: 共用線外觀可讓使用者選擇代表代表對方接聽或處理通話的代理人。
ms.openlocfilehash: aed55d29f2b9fc45c66040390d4d698acaf25258
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571755"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="71ae1-103">Microsoft 團隊中的共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="71ae1-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="71ae1-104">共用線外觀是委派功能的一部分，可讓使用者選擇代表代表對方接聽或處理通話的代理人。</span><span class="sxs-lookup"><span data-stu-id="71ae1-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="71ae1-105">如果使用者有可定期處理使用者來電的系統管理小幫手，這項功能很有説明。</span><span class="sxs-lookup"><span data-stu-id="71ae1-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="71ae1-106">在共用線外觀的內容中，管理員是授權代理人代表自己撥打或接聽電話的人員，而代理人可以代表其他人撥打及接聽來電。</span><span class="sxs-lookup"><span data-stu-id="71ae1-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ae1-107">此功能僅適用于 [僅限團隊部署模式]。</span><span class="sxs-lookup"><span data-stu-id="71ae1-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="71ae1-108">如需有關團隊部署模式的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="71ae1-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="71ae1-109">需要授權</span><span class="sxs-lookup"><span data-stu-id="71ae1-109">License required</span></span>

<span data-ttu-id="71ae1-110">使用者必須是企業語音使用者，才能成為代理人或設定委派，並允許其他人代表自己撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="71ae1-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="71ae1-111">管理員和代理人都必須具備企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="71ae1-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="71ae1-112">共用的線路體驗是委派的一部分，且不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="71ae1-112">The shared line experience is part of delegation and requires no additional license.</span></span> <span data-ttu-id="71ae1-113">如需授權模型的其他詳細資料，請參閱[Microsoft 團隊適用的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="71ae1-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="71ae1-114">設定委派和共用線外觀</span><span class="sxs-lookup"><span data-stu-id="71ae1-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="71ae1-115">委派和共用線外觀是使用者驅動的功能：沒有要設定的系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="71ae1-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="71ae1-116">如需如何使用此功能的詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="71ae1-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="71ae1-117">租使用者管理員可以透過**TeamsCallingPolicy AllowDelegation**設定或透過團隊管理入口網站來啟用委派，這項功能才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="71ae1-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="71ae1-118">租使用者管理員也可以設定小組系統管理中心中使用者的委派關聯性。</span><span class="sxs-lookup"><span data-stu-id="71ae1-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="71ae1-119">此外，使用者也可以直接在團隊中設定其委派關聯性。</span><span class="sxs-lookup"><span data-stu-id="71ae1-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="71ae1-120">租使用者管理員或使用者無法彼此封鎖設定，但是團隊系統管理中心和團隊用戶端應該在這兩個位置中正確顯示這種關聯性。</span><span class="sxs-lookup"><span data-stu-id="71ae1-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="71ae1-121">當租使用者系統管理員關閉使用者的委派功能之後（開啟之後），他們也必須在小組系統管理中心清除該使用者的委派關聯，以免呼叫路由不正確。</span><span class="sxs-lookup"><span data-stu-id="71ae1-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="71ae1-122">共用線外觀功能可用性</span><span class="sxs-lookup"><span data-stu-id="71ae1-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="71ae1-123">下列應用程式和裝置目前支援共用線外觀。</span><span class="sxs-lookup"><span data-stu-id="71ae1-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="71ae1-124">功能</span><span class="sxs-lookup"><span data-stu-id="71ae1-124">Capability</span></span> | <span data-ttu-id="71ae1-125">團隊桌面</span><span class="sxs-lookup"><span data-stu-id="71ae1-125">Teams Desktop</span></span> | <span data-ttu-id="71ae1-126">團隊 Mac 應用程式</span><span class="sxs-lookup"><span data-stu-id="71ae1-126">Teams Mac App</span></span> | <span data-ttu-id="71ae1-127">小組 Web App （邊緣）</span><span class="sxs-lookup"><span data-stu-id="71ae1-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="71ae1-128">團隊行動 iOS/Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="71ae1-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="71ae1-129">團隊 IP 電話</span><span class="sxs-lookup"><span data-stu-id="71ae1-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="71ae1-130">設定委派</span><span class="sxs-lookup"><span data-stu-id="71ae1-130">Set up delegation</span></span> | <span data-ttu-id="71ae1-131">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-131">Yes</span></span> | <span data-ttu-id="71ae1-132">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-132">Yes</span></span> | <span data-ttu-id="71ae1-133">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-133">Yes</span></span> | <span data-ttu-id="71ae1-134">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-134">No</span></span> | <span data-ttu-id="71ae1-135">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-135">No</span></span> |
| <span data-ttu-id="71ae1-136">代表其他方式接聽來電</span><span class="sxs-lookup"><span data-stu-id="71ae1-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="71ae1-137">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-137">Yes</span></span> | <span data-ttu-id="71ae1-138">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-138">Yes</span></span> | <span data-ttu-id="71ae1-139">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-139">Yes</span></span> | <span data-ttu-id="71ae1-140">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-140">Yes</span></span> | <span data-ttu-id="71ae1-141">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-141">Yes</span></span> |
| <span data-ttu-id="71ae1-142">代表其他電話撥打電話號碼</span><span class="sxs-lookup"><span data-stu-id="71ae1-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="71ae1-143">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-143">Yes</span></span> | <span data-ttu-id="71ae1-144">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-144">Yes</span></span> | <span data-ttu-id="71ae1-145">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-145">Yes</span></span> | <span data-ttu-id="71ae1-146">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-146">Yes</span></span> | <span data-ttu-id="71ae1-147">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-147">Yes</span></span> |
| <span data-ttu-id="71ae1-148">代表其他使用者呼叫團隊使用者</span><span class="sxs-lookup"><span data-stu-id="71ae1-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="71ae1-149">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-149">Yes</span></span> | <span data-ttu-id="71ae1-150">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-150">Yes</span></span> | <span data-ttu-id="71ae1-151">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-151">Yes</span></span> | <span data-ttu-id="71ae1-152">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-152">Yes</span></span> | <span data-ttu-id="71ae1-153">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-153">Yes</span></span> |
| <span data-ttu-id="71ae1-154">查看共用線的系統管理視圖</span><span class="sxs-lookup"><span data-stu-id="71ae1-154">See the admin view of shared lines</span></span> | <span data-ttu-id="71ae1-155">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-155">Yes</span></span> | <span data-ttu-id="71ae1-156">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-156">Yes</span></span> | <span data-ttu-id="71ae1-157">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-157">Yes</span></span> | <span data-ttu-id="71ae1-158">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-158">No</span></span> | <span data-ttu-id="71ae1-159">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-159">No</span></span> |
| <span data-ttu-id="71ae1-160">請參閱管理員的通話活動管理檢視</span><span class="sxs-lookup"><span data-stu-id="71ae1-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="71ae1-161">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-161">Yes</span></span> | <span data-ttu-id="71ae1-162">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-162">Yes</span></span> | <span data-ttu-id="71ae1-163">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-163">Yes</span></span> | <span data-ttu-id="71ae1-164">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-164">No</span></span> | <span data-ttu-id="71ae1-165">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-165">No</span></span> |
| <span data-ttu-id="71ae1-166">請參閱代理人的管理員視圖</span><span class="sxs-lookup"><span data-stu-id="71ae1-166">See the manager view of delegates</span></span> | <span data-ttu-id="71ae1-167">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-167">Yes</span></span> | <span data-ttu-id="71ae1-168">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-168">Yes</span></span> | <span data-ttu-id="71ae1-169">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-169">Yes</span></span> | <span data-ttu-id="71ae1-170">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-170">No</span></span> | <span data-ttu-id="71ae1-171">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-171">No</span></span> |
| <span data-ttu-id="71ae1-172">系統管理員或經理可以保留或繼續</span><span class="sxs-lookup"><span data-stu-id="71ae1-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="71ae1-173">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-173">Yes</span></span> | <span data-ttu-id="71ae1-174">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-174">Yes</span></span> | <span data-ttu-id="71ae1-175">是的</span><span class="sxs-lookup"><span data-stu-id="71ae1-175">Yes</span></span> | <span data-ttu-id="71ae1-176">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-176">No</span></span> | <span data-ttu-id="71ae1-177">不</span><span class="sxs-lookup"><span data-stu-id="71ae1-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="71ae1-178">有限</span><span class="sxs-lookup"><span data-stu-id="71ae1-178">Limitations</span></span>

<span data-ttu-id="71ae1-179">管理員最多可以新增25個代理人，而代理人最多可有25個經理。</span><span class="sxs-lookup"><span data-stu-id="71ae1-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="71ae1-180">可在租使用者中建立的委派關聯數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="71ae1-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="71ae1-181">如果 delegator 和委派不在同一個地理位置，則由 PSTN 提供者允許從不同地理位置針對委派（代表的）通話顯示呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="71ae1-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="71ae1-182">其他資訊</span><span class="sxs-lookup"><span data-stu-id="71ae1-182">More information</span></span>

[<span data-ttu-id="71ae1-183">與代理人共用電話線路</span><span class="sxs-lookup"><span data-stu-id="71ae1-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
