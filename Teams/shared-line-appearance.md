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
- Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共用線外觀可讓使用者選擇代表代表對方接聽或處理通話的代理人。
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182403"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="945e1-103">Microsoft 團隊中的共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="945e1-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="945e1-104">共用線外觀是委派功能的一部分, 可讓使用者選擇代表代表對方接聽或處理通話的代理人。</span><span class="sxs-lookup"><span data-stu-id="945e1-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="945e1-105">如果使用者有可定期處理使用者來電的系統管理小幫手, 這項功能很有説明。</span><span class="sxs-lookup"><span data-stu-id="945e1-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="945e1-106">在共用線外觀的內容中, 管理員是授權代理人代表自己撥打或接聽電話的人員, 而代理人可以代表其他人撥打及接聽來電。</span><span class="sxs-lookup"><span data-stu-id="945e1-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="945e1-107">此功能僅適用于 [僅限團隊部署模式]。</span><span class="sxs-lookup"><span data-stu-id="945e1-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="945e1-108">如需有關團隊部署模式的詳細資訊, 請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="945e1-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="945e1-109">需要授權</span><span class="sxs-lookup"><span data-stu-id="945e1-109">License required</span></span>

<span data-ttu-id="945e1-110">使用者必須是企業語音使用者, 才能成為代理人或設定委派, 並允許其他人代表自己撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="945e1-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="945e1-111">管理員和代理人都必須具備企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="945e1-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="945e1-112">共用的線路體驗是委派的一部分, 且不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="945e1-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="945e1-113">如需授權模型的其他詳細資料, 請參閱[Microsoft 團隊適用的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="945e1-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="945e1-114">設定委派和共用線外觀</span><span class="sxs-lookup"><span data-stu-id="945e1-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="945e1-115">委派和共用線外觀是使用者驅動的功能: 沒有要設定的系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="945e1-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="945e1-116">如需如何使用此功能的詳細資訊, 請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="945e1-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="945e1-117">租使用者管理員應該透過**TeamsCallingPolicy AllowDelegation**設定啟用委派, 才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="945e1-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="945e1-118">共用線外觀功能可用性</span><span class="sxs-lookup"><span data-stu-id="945e1-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="945e1-119">下列應用程式和裝置目前支援共用線外觀。</span><span class="sxs-lookup"><span data-stu-id="945e1-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="945e1-120">功能</span><span class="sxs-lookup"><span data-stu-id="945e1-120">Capability</span></span> | <span data-ttu-id="945e1-121">團隊桌面</span><span class="sxs-lookup"><span data-stu-id="945e1-121">Teams Desktop</span></span> | <span data-ttu-id="945e1-122">團隊 Mac 應用程式</span><span class="sxs-lookup"><span data-stu-id="945e1-122">Teams Mac App</span></span> | <span data-ttu-id="945e1-123">小組 Web App (邊緣)</span><span class="sxs-lookup"><span data-stu-id="945e1-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="945e1-124">團隊行動 iOS/Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="945e1-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="945e1-125">團隊 IP 電話</span><span class="sxs-lookup"><span data-stu-id="945e1-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="945e1-126">設定委派</span><span class="sxs-lookup"><span data-stu-id="945e1-126">Set up delegation</span></span> | <span data-ttu-id="945e1-127">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-127">Yes</span></span> | <span data-ttu-id="945e1-128">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-128">Yes</span></span> | <span data-ttu-id="945e1-129">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-129">Yes</span></span> | <span data-ttu-id="945e1-130">不</span><span class="sxs-lookup"><span data-stu-id="945e1-130">No</span></span> | <span data-ttu-id="945e1-131">不</span><span class="sxs-lookup"><span data-stu-id="945e1-131">No</span></span> |
| <span data-ttu-id="945e1-132">代表其他方式接聽來電</span><span class="sxs-lookup"><span data-stu-id="945e1-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="945e1-133">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-133">Yes</span></span> | <span data-ttu-id="945e1-134">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-134">Yes</span></span> | <span data-ttu-id="945e1-135">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-135">Yes</span></span> | <span data-ttu-id="945e1-136">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-136">Yes</span></span> | <span data-ttu-id="945e1-137">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-137">Yes</span></span> |
| <span data-ttu-id="945e1-138">代表其他電話撥打電話號碼</span><span class="sxs-lookup"><span data-stu-id="945e1-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="945e1-139">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-139">Yes</span></span> | <span data-ttu-id="945e1-140">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-140">Yes</span></span> | <span data-ttu-id="945e1-141">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-141">Yes</span></span> | <span data-ttu-id="945e1-142">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-142">Yes</span></span> | <span data-ttu-id="945e1-143">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-143">Yes</span></span> |
| <span data-ttu-id="945e1-144">代表其他使用者呼叫團隊使用者</span><span class="sxs-lookup"><span data-stu-id="945e1-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="945e1-145">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-145">Yes</span></span> | <span data-ttu-id="945e1-146">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-146">Yes</span></span> | <span data-ttu-id="945e1-147">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-147">Yes</span></span> | <span data-ttu-id="945e1-148">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-148">Yes</span></span> | <span data-ttu-id="945e1-149">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-149">Yes</span></span> |
| <span data-ttu-id="945e1-150">查看共用線的系統管理視圖</span><span class="sxs-lookup"><span data-stu-id="945e1-150">See the admin view of shared lines</span></span> | <span data-ttu-id="945e1-151">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-151">Yes</span></span> | <span data-ttu-id="945e1-152">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-152">Yes</span></span> | <span data-ttu-id="945e1-153">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-153">Yes</span></span> | <span data-ttu-id="945e1-154">不</span><span class="sxs-lookup"><span data-stu-id="945e1-154">No</span></span> | <span data-ttu-id="945e1-155">不</span><span class="sxs-lookup"><span data-stu-id="945e1-155">No</span></span> |
| <span data-ttu-id="945e1-156">請參閱管理員的通話活動管理檢視</span><span class="sxs-lookup"><span data-stu-id="945e1-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="945e1-157">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-157">Yes</span></span> | <span data-ttu-id="945e1-158">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-158">Yes</span></span> | <span data-ttu-id="945e1-159">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-159">Yes</span></span> | <span data-ttu-id="945e1-160">不</span><span class="sxs-lookup"><span data-stu-id="945e1-160">No</span></span> | <span data-ttu-id="945e1-161">不</span><span class="sxs-lookup"><span data-stu-id="945e1-161">No</span></span> |
| <span data-ttu-id="945e1-162">請參閱代理人的管理員視圖</span><span class="sxs-lookup"><span data-stu-id="945e1-162">See the manager view of delegates</span></span> | <span data-ttu-id="945e1-163">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-163">Yes</span></span> | <span data-ttu-id="945e1-164">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-164">Yes</span></span> | <span data-ttu-id="945e1-165">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-165">Yes</span></span> | <span data-ttu-id="945e1-166">不</span><span class="sxs-lookup"><span data-stu-id="945e1-166">No</span></span> | <span data-ttu-id="945e1-167">不</span><span class="sxs-lookup"><span data-stu-id="945e1-167">No</span></span> |
| <span data-ttu-id="945e1-168">系統管理員或經理可以保留或繼續</span><span class="sxs-lookup"><span data-stu-id="945e1-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="945e1-169">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-169">Yes</span></span> | <span data-ttu-id="945e1-170">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-170">Yes</span></span> | <span data-ttu-id="945e1-171">是的</span><span class="sxs-lookup"><span data-stu-id="945e1-171">Yes</span></span> | <span data-ttu-id="945e1-172">不</span><span class="sxs-lookup"><span data-stu-id="945e1-172">No</span></span> | <span data-ttu-id="945e1-173">不</span><span class="sxs-lookup"><span data-stu-id="945e1-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="945e1-174">有限</span><span class="sxs-lookup"><span data-stu-id="945e1-174">Limitations</span></span>

<span data-ttu-id="945e1-175">管理員最多可以新增25個代理人, 而代理人最多可有25個經理。</span><span class="sxs-lookup"><span data-stu-id="945e1-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="945e1-176">可在租使用者中建立的委派關聯數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="945e1-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="945e1-177">如果 delegator 和委派不在同一個地理位置, 則由 PSTN 提供者允許從不同地理位置針對委派 (代表的) 通話顯示呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="945e1-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="945e1-178">其他資訊</span><span class="sxs-lookup"><span data-stu-id="945e1-178">More information</span></span>

[<span data-ttu-id="945e1-179">與代理人共用電話線路</span><span class="sxs-lookup"><span data-stu-id="945e1-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
