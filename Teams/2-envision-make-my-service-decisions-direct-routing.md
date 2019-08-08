---
title: 撥打手機系統直通路線服務決策-Microsoft 團隊
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 瞭解直接路由、授權及需要進行的決定。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa92fcf7c30ecd8dfcecb84c3463f70ba13ee7ef
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240804"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="1d693-103">進行我的服務決策</span><span class="sxs-lookup"><span data-stu-id="1d693-103">Make my service decisions</span></span>

<span data-ttu-id="1d693-104">若要規劃手機系統 Direct 路由的技術實施 (「直接路由」), 您必須提前進行一系列的服務決策, 以進一步準備貴組織, 以符合您所定義的商業需求。</span><span class="sxs-lookup"><span data-stu-id="1d693-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="1d693-105">在團隊中通話</span><span class="sxs-lookup"><span data-stu-id="1d693-105">Calling in Teams</span></span>

<span data-ttu-id="1d693-106">透過 Microsoft 團隊, 您的使用者可以撥打或接聽公用交換電話網絡 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="1d693-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="1d693-107">您的使用者可以使用自己的專用電話號碼, 從小組用戶端應用程式撥打及接聽國內和國際電話 (包括語音信箱)。</span><span class="sxs-lookup"><span data-stu-id="1d693-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="1d693-108">直接路由</span><span class="sxs-lookup"><span data-stu-id="1d693-108">Direct Routing</span></span>

<span data-ttu-id="1d693-109">若要讓團隊使用者能夠撥打電話並接收 PSTN 通話, 必須在 Office 365 中啟用電話系統的功能。</span><span class="sxs-lookup"><span data-stu-id="1d693-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="1d693-110">若要啟用 PSTN 連線, 您可以使用直接路由, 讓貴組織中的人員能夠透過 PSTN 撥打及接聽組織外部的電話撥打電話。</span><span class="sxs-lookup"><span data-stu-id="1d693-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="1d693-111">透過直接佈線, 由協力廠商提供的 PSTN 連線功能可讓您繼續使用 PSTN 服務提供者所提供的現有 PSTN trunks。</span><span class="sxs-lookup"><span data-stu-id="1d693-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="1d693-112">此功能可讓您在含有通話方案 ("通話方案") 的電話系統中, 或在已有的 PSTN 服務提供者合約需要維護或與特定內部部署系統進行互通性的部署中進行部署必填。</span><span class="sxs-lookup"><span data-stu-id="1d693-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="1d693-113">直接路由的可用性</span><span class="sxs-lookup"><span data-stu-id="1d693-113">Availability of Direct Routing</span></span>

<span data-ttu-id="1d693-114">您可以在 Office 365 的任何國家/地區取得直接傳送。</span><span class="sxs-lookup"><span data-stu-id="1d693-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="1d693-115">請參閱[國際可用性](https://products.office.com/business/international-availability), 取得這些國家/地區的清單。</span><span class="sxs-lookup"><span data-stu-id="1d693-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="1d693-116">確認貴組織可以取得電話系統功能之後, 請根據可用國家和地區的清單, 將您要實施電話系統的使用者位置或分支機搆的清單進行編譯。</span><span class="sxs-lookup"><span data-stu-id="1d693-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="1d693-117">此外, 還要找出您要為每個位置啟用通話方案或直接路由的使用者。</span><span class="sxs-lookup"><span data-stu-id="1d693-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-118">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-118">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-119">找出您要在其中實施電話系統的使用者位置或辦公室。</span><span class="sxs-lookup"><span data-stu-id="1d693-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="1d693-120">針對您所擁有的每個位置, 找出您要為其啟用通話方案或直接傳送的使用者。</span><span class="sxs-lookup"><span data-stu-id="1d693-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-121">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-121">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-122">將啟用電話系統的使用者位置或辦公室記錄在檔中。</span><span class="sxs-lookup"><span data-stu-id="1d693-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="1d693-123">針對您要啟用呼叫方案或針對您所擁有的每個位置的直接傳送來記錄使用者清單</span><span class="sxs-lookup"><span data-stu-id="1d693-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="1d693-124">以下是直接路由網站啟用清單的範例。</span><span class="sxs-lookup"><span data-stu-id="1d693-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="1d693-125">**辦事處**</span><span class="sxs-lookup"><span data-stu-id="1d693-125">**Office**</span></span>                     | <span data-ttu-id="1d693-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="1d693-126">**Location**</span></span>   | <span data-ttu-id="1d693-127">**電話系統服務**</span><span class="sxs-lookup"><span data-stu-id="1d693-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="1d693-128">單一 Epping 道路</span><span class="sxs-lookup"><span data-stu-id="1d693-128">One Epping Road</span></span>                | <span data-ttu-id="1d693-129">澳大利亞</span><span class="sxs-lookup"><span data-stu-id="1d693-129">Australia</span></span>      | <span data-ttu-id="1d693-130">舊版 PSTN 服務</span><span class="sxs-lookup"><span data-stu-id="1d693-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="1d693-131">100 Cyberport 公路</span><span class="sxs-lookup"><span data-stu-id="1d693-131">100 Cyberport Road</span></span>             | <span data-ttu-id="1d693-132">香港特別行政區</span><span class="sxs-lookup"><span data-stu-id="1d693-132">Hong Kong SAR</span></span>  | <span data-ttu-id="1d693-133">電話系統直向路由</span><span class="sxs-lookup"><span data-stu-id="1d693-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="1d693-134">一個 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="1d693-134">One Marina Boulevard</span></span>           | <span data-ttu-id="1d693-135">新加坡</span><span class="sxs-lookup"><span data-stu-id="1d693-135">Singapore</span></span>      | <span data-ttu-id="1d693-136">電話系統直向路由</span><span class="sxs-lookup"><span data-stu-id="1d693-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="1d693-137">32倫敦 Bridge 大街</span><span class="sxs-lookup"><span data-stu-id="1d693-137">32 London Bridge Street</span></span>        | <span data-ttu-id="1d693-138">英國</span><span class="sxs-lookup"><span data-stu-id="1d693-138">United Kingdom</span></span> | <span data-ttu-id="1d693-139">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="1d693-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="1d693-140">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="1d693-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="1d693-141">法國</span><span class="sxs-lookup"><span data-stu-id="1d693-141">France</span></span>         | <span data-ttu-id="1d693-142">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="1d693-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="1d693-143">電話號碼和緊急位置</span><span class="sxs-lookup"><span data-stu-id="1d693-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="1d693-144">[電話系統] 需要貴組織中的每位使用者都有唯一的直向內撥號 (已撥) 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1d693-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="1d693-145">透過直接路由, 電話號碼和緊急服務是由您的 PSTN 服務提供者所提供。</span><span class="sxs-lookup"><span data-stu-id="1d693-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="1d693-146">透過直接路由, 您的使用者可以繼續使用 PSTN 服務提供者所提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1d693-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="1d693-147">您可以使用下列範本來記錄電話號碼的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1d693-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="1d693-148">使用者名</span><span class="sxs-lookup"><span data-stu-id="1d693-148">User</span></span> |<span data-ttu-id="1d693-149">電話號碼</span><span class="sxs-lookup"><span data-stu-id="1d693-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="1d693-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="1d693-150">Emily Braun</span></span> | <span data-ttu-id="1d693-151">+ 44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="1d693-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="1d693-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="1d693-152">Lidia Holloway</span></span> | <span data-ttu-id="1d693-153">+ 44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="1d693-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="1d693-154">港 Lahr</span><span class="sxs-lookup"><span data-stu-id="1d693-154">Louis Lahr</span></span> | <span data-ttu-id="1d693-155">+ 44 23 4567 8921</span><span class="sxs-lookup"><span data-stu-id="1d693-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="1d693-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="1d693-156">Marcel Beauchamp</span></span> | <span data-ttu-id="1d693-157">TBA</span><span class="sxs-lookup"><span data-stu-id="1d693-157">TBA</span></span> |
> |<span data-ttu-id="1d693-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="1d693-158">Rachelle Cormier</span></span> | <span data-ttu-id="1d693-159">TBA</span><span class="sxs-lookup"><span data-stu-id="1d693-159">TBA</span></span> |
> |<span data-ttu-id="1d693-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="1d693-160">Isabell Potvin</span></span> | <span data-ttu-id="1d693-161">TBA</span><span class="sxs-lookup"><span data-stu-id="1d693-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="1d693-162">語音信箱</span><span class="sxs-lookup"><span data-stu-id="1d693-162">Voicemail</span></span>

<span data-ttu-id="1d693-163">雲端語音信箱 (由 Azure 語音信箱服務提供支援) 只支援將語音信箱存款至 Exchange 信箱, 且不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="1d693-163">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="1d693-164">雲端語音信箱包括語音信箱, 預設會針對貴組織中的所有使用者啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="1d693-164">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="1d693-165">您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="1d693-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="1d693-166">如果您的組織決定將語音信箱保持在啟用狀態, 您也必須考慮是否要啟用語音信箱要求語言。</span><span class="sxs-lookup"><span data-stu-id="1d693-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="1d693-167">如需詳細資訊, 請參閱[設定貴組織的語音信箱原則](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="1d693-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="1d693-168">如需手機系統實現中語音信箱的詳細資訊, 請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="1d693-168">For more information about voicemail in a Phone System implementation, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-169">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-169">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-170">決定是否要在直接路由實現中啟用雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="1d693-170">Decide whether you’ll enable Cloud Voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="1d693-171">決定是否要在整個組織或特定使用者中啟用或停用語音信箱或語音信箱。</span><span class="sxs-lookup"><span data-stu-id="1d693-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-172">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-172">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-173">如果適用, 請將決策點記錄在支援雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="1d693-173">If applicable, document the decision points to support Cloud Voicemail.</span></span><li><span data-ttu-id="1d693-174">如果您要啟用或停用語音信箱、語音信箱, 以及語音信箱只針對特定使用者提供猥褻遮罩, 請記錄該使用者清單。</span><span class="sxs-lookup"><span data-stu-id="1d693-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="1d693-175">[雲端語音信箱] 的詳細資料會記錄在下表中。</span><span class="sxs-lookup"><span data-stu-id="1d693-175">Cloud Voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="1d693-176">**使用者名**</span><span class="sxs-lookup"><span data-stu-id="1d693-176">**User**</span></span>         | <span data-ttu-id="1d693-177">**Exchange 信箱**</span><span class="sxs-lookup"><span data-stu-id="1d693-177">**Exchange mailbox**</span></span> | <span data-ttu-id="1d693-178">**啟用語音信箱嗎？**</span><span class="sxs-lookup"><span data-stu-id="1d693-178">**Enable voicemail?**</span></span> | <span data-ttu-id="1d693-179">**語音信箱**</span><span class="sxs-lookup"><span data-stu-id="1d693-179">**Voicemail transcription**</span></span> | <span data-ttu-id="1d693-180">**語音信箱的褻瀆遮罩**</span><span class="sxs-lookup"><span data-stu-id="1d693-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="1d693-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="1d693-181">Emily Braun</span></span>      | <span data-ttu-id="1d693-182">Online</span><span class="sxs-lookup"><span data-stu-id="1d693-182">Online</span></span>               | <span data-ttu-id="1d693-183">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-183">Yes</span></span>                   | <span data-ttu-id="1d693-184">後</span><span class="sxs-lookup"><span data-stu-id="1d693-184">Enabled</span></span>                     | <span data-ttu-id="1d693-185">後</span><span class="sxs-lookup"><span data-stu-id="1d693-185">Enabled</span></span>                                       |
> | <span data-ttu-id="1d693-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="1d693-186">Lidia Holloway</span></span>   | <span data-ttu-id="1d693-187">Online</span><span class="sxs-lookup"><span data-stu-id="1d693-187">Online</span></span>               | <span data-ttu-id="1d693-188">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-188">Yes</span></span>                   | <span data-ttu-id="1d693-189">後</span><span class="sxs-lookup"><span data-stu-id="1d693-189">Enabled</span></span>                     | <span data-ttu-id="1d693-190">禁止</span><span class="sxs-lookup"><span data-stu-id="1d693-190">Disabled</span></span>                                      |
> | <span data-ttu-id="1d693-191">港 Lahr</span><span class="sxs-lookup"><span data-stu-id="1d693-191">Louis Lahr</span></span>       | <span data-ttu-id="1d693-192">內部部署</span><span class="sxs-lookup"><span data-stu-id="1d693-192">On-premises</span></span>          | <span data-ttu-id="1d693-193">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-193">Yes</span></span>                   | <span data-ttu-id="1d693-194">後</span><span class="sxs-lookup"><span data-stu-id="1d693-194">Enabled</span></span>                     | <span data-ttu-id="1d693-195">後</span><span class="sxs-lookup"><span data-stu-id="1d693-195">Enabled</span></span>                                       |
> | <span data-ttu-id="1d693-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="1d693-196">Marcel Beauchamp</span></span> | <span data-ttu-id="1d693-197">內部部署</span><span class="sxs-lookup"><span data-stu-id="1d693-197">On-premises</span></span>          | <span data-ttu-id="1d693-198">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-198">Yes</span></span>                   | <span data-ttu-id="1d693-199">禁止</span><span class="sxs-lookup"><span data-stu-id="1d693-199">Disabled</span></span>                    | <span data-ttu-id="1d693-200">N/A</span><span class="sxs-lookup"><span data-stu-id="1d693-200">N/A</span></span>                                           |
> | <span data-ttu-id="1d693-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="1d693-201">Rachelle Cormier</span></span> | <span data-ttu-id="1d693-202">Online</span><span class="sxs-lookup"><span data-stu-id="1d693-202">Online</span></span>               | <span data-ttu-id="1d693-203">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-203">Yes</span></span>                   | <span data-ttu-id="1d693-204">禁止</span><span class="sxs-lookup"><span data-stu-id="1d693-204">Disabled</span></span>                    | <span data-ttu-id="1d693-205">N/A</span><span class="sxs-lookup"><span data-stu-id="1d693-205">N/A</span></span>                                           |
> | <span data-ttu-id="1d693-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="1d693-206">Isabell Potvin</span></span>   | <span data-ttu-id="1d693-207">內部部署</span><span class="sxs-lookup"><span data-stu-id="1d693-207">On-premises</span></span>          | <span data-ttu-id="1d693-208">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-208">Yes</span></span>                   | <span data-ttu-id="1d693-209">禁止</span><span class="sxs-lookup"><span data-stu-id="1d693-209">Disabled</span></span>                    | <span data-ttu-id="1d693-210">N/A</span><span class="sxs-lookup"><span data-stu-id="1d693-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="1d693-211">若要使用團隊和語音信箱, 您的使用者必須擁有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="1d693-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="1d693-212">如需更多詳細資料, 請參閱[Exchange 與 Microsoft 團隊的互動方式](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="1d693-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="1d693-213">直接路由的授權</span><span class="sxs-lookup"><span data-stu-id="1d693-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="1d693-214">如果您的組織想要使用直接路由, 您必須取得所需的授權。</span><span class="sxs-lookup"><span data-stu-id="1d693-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="1d693-215">直接傳送的使用者必須具備下列 Office 365 中指派的授權:</span><span class="sxs-lookup"><span data-stu-id="1d693-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="1d693-216">Microsoft Phone 系統</span><span class="sxs-lookup"><span data-stu-id="1d693-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="1d693-217">Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="1d693-217">Microsoft Teams</span></span>

-   <span data-ttu-id="1d693-218">音訊會議</span><span class="sxs-lookup"><span data-stu-id="1d693-218">Audio Conferencing</span></span>

<span data-ttu-id="1d693-219">若要將外部參與者加入排程的會議, 請撥打電話給他們, 或提供撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="1d693-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="1d693-220">在撥出外部參與者之後, 音訊會議服務會使用線上呼叫功能來撥打通話。</span><span class="sxs-lookup"><span data-stu-id="1d693-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="1d693-221">[音訊會議授權] 是選擇性的, 而且只對將加入音訊會議的小組會議所需的使用者才是必要的。</span><span class="sxs-lookup"><span data-stu-id="1d693-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="1d693-222">若要提供免付費的會議橋接電話號碼, 並支援會議撥出到國際電話號碼, 您應該為您的組織設定[通訊點數](what-are-communications-credits.md)。</span><span class="sxs-lookup"><span data-stu-id="1d693-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="1d693-223">音訊會議和電話系統可以為擁有 Office 365 E3 或 E1 訂閱者案之現有客戶的附加元件服務另行授權;它們已包含在 Office 365 E5 訂閱者案中。</span><span class="sxs-lookup"><span data-stu-id="1d693-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="1d693-224">您也可以在將呼叫安排傳送給協力廠商 Pbx 時, 針對啟用呼叫方案的使用者使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="1d693-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="1d693-225">如需詳細資訊, 請參閱[直接路由的授權與其他需求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="1d693-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-226">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-226">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-227">如果您的組織沒有必要的電話系統授權, 請決定是否要取得電話系統授權, 方法是逐步執行您現有的 Office 365 訂閱, 或購買 [電話系統] 附加元件服務。</span><span class="sxs-lookup"><span data-stu-id="1d693-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="1d693-228">針對直接路由實現, 決定您是否需要通訊點數。</span><span class="sxs-lookup"><span data-stu-id="1d693-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-229">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-229">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-230">記錄 [分部]、[部門]、[office] 或 [使用者群組] 您將指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="1d693-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="1d693-231">如果音訊會議有免付費電話號碼, 請記錄 [分部]、[部門]、[office] 或 [使用者群組], 您將會啟用通訊點數。</span><span class="sxs-lookup"><span data-stu-id="1d693-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="1d693-232">Office 365 考慮</span><span class="sxs-lookup"><span data-stu-id="1d693-232">Office 365 considerations</span></span>

<span data-ttu-id="1d693-233">任何將啟用直接路由的使用者, 都必須駐留在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="1d693-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="1d693-234">針對使用內部部署商務用 Skype Server 或 Lync Server 的混合式部署, 您必須先將使用者移至商務用 Skype Online, 然後才能將其設定為搭配團隊直接傳送。</span><span class="sxs-lookup"><span data-stu-id="1d693-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="1d693-235">必須針對團隊啟用直接路由實施範圍中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1d693-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="1d693-236">您必須在一或多個網域中啟用您的 Office 365 租使用者\*, 因為 onmicrosoft.com 網域無法與直接路由搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1d693-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="1d693-237">如需網域和 Office 365 租使用者的詳細資訊, 請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="1d693-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-238">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-238">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-239">決定是否任何使用者都需要遷移到商務用 Skype Online, 以支援直接傳送。</span><span class="sxs-lookup"><span data-stu-id="1d693-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="1d693-240">找出需要為團隊啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="1d693-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-241">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-241">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-242">記錄需要移至商務用 Skype Online 且可供團隊使用的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="1d693-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="1d693-243">SBC 考慮</span><span class="sxs-lookup"><span data-stu-id="1d693-243">SBC considerations</span></span>

<span data-ttu-id="1d693-244">您需要使用經過驗證且支援的會話邊界控制器 (SBCs), 而這兩者必須要與直接路由服務配對, 為您的使用者提供 PSTN 連線能力。</span><span class="sxs-lookup"><span data-stu-id="1d693-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="1d693-245">如需已驗證的 SBCs 清單, 請參閱[支援的會話框線控制器](direct-routing-plan.md#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="1d693-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="1d693-246">視您的環境、位置數量及語音路由需求而定, 您可能需要部署多個 SBCs, 才能支援您的使用者基底。</span><span class="sxs-lookup"><span data-stu-id="1d693-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="1d693-247">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="1d693-247">SBC domain names</span></span>

<span data-ttu-id="1d693-248">您與直接路由配對的每個 SBC 都必須有唯一的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="1d693-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="1d693-249">SBC DNS 名稱必須來自于 Office 365 租使用者註冊的其中一個功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1d693-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="1d693-250">如果您的租使用者已獲指派多個功能變數名稱, 您可以在規劃 SBCs 的 DNS 名稱時, 使用下列任何功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1d693-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d693-251">不允許對 SBC DNS 名稱使用 \*. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="1d693-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="1d693-252">證書</span><span class="sxs-lookup"><span data-stu-id="1d693-252">Certificates</span></span>

<span data-ttu-id="1d693-253">使用直接路由部署的每個 SBC, 都需要從支援的認證頒發機構清單中取得的憑證。</span><span class="sxs-lookup"><span data-stu-id="1d693-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="1d693-254">憑證必須在 subject、subject 替換名稱或公用名稱欄位中包含 SBC DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="1d693-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="1d693-255">也支援使用 SBCs 的萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="1d693-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="1d693-256">如需詳細資訊以及支援的認證機構清單, 請參閱[適用于 SBC 的公用信任憑證](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="1d693-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="1d693-257">SBC IP 位址與埠</span><span class="sxs-lookup"><span data-stu-id="1d693-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="1d693-258">每個 SBC 都必須使用可從 Office 365 資料中心存取的公用 IP 位址進行設定。</span><span class="sxs-lookup"><span data-stu-id="1d693-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="1d693-259">您也可以設定網路位址轉譯 (NAT), 將您的 SBCs 發佈至 Office 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="1d693-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="1d693-260">SBCs 需要雙向連線才能與雲端服務通訊以取得信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="1d693-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="1d693-261">[發信號] 是由名為 [ *SIP Proxy*] 的元件處理, 媒體由*媒體處理器*來處理。</span><span class="sxs-lookup"><span data-stu-id="1d693-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="1d693-262">您必須在每個 SBC 上針對 SIP 信號和媒體定義特定的埠號碼, 並將您的防火牆設定為允許對這些埠及其相關 IP 位址進行雙向通訊。</span><span class="sxs-lookup"><span data-stu-id="1d693-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="1d693-263">如需詳細資訊, 請參閱[SIP 信號: fqdn 和防火牆埠](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports)及[媒體流量: 埠範圍](direct-routing-plan.md#media-traffic-port-ranges)。</span><span class="sxs-lookup"><span data-stu-id="1d693-263">For more details, see [SIP Signaling: FQDNs and firewall ports](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="1d693-264">我們強烈建議根據 SBC 模型, 為每個 SBC 設定最大併發會話限制。</span><span class="sxs-lookup"><span data-stu-id="1d693-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="1d693-265">這個限制會在 SBC 執行或接近其容量時觸發通知。</span><span class="sxs-lookup"><span data-stu-id="1d693-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-266">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-266">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-267">決定您要將半形部署到哪個位置。</span><span class="sxs-lookup"><span data-stu-id="1d693-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="1d693-268">針對您打算部署的每個 SBC, 決定一個 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="1d693-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="1d693-269">根據 SBC 功能變數名稱決定, 決定您要使用萬用字元憑證來支援部署中的所有半形, 或每個 SBC 專用的憑證。</span><span class="sxs-lookup"><span data-stu-id="1d693-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="1d693-270">決定您要從哪個公用憑證授權單位取得您的 SBCs 證書。</span><span class="sxs-lookup"><span data-stu-id="1d693-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="1d693-271">針對您要部署的每個 SBC 定義公用 IP 位址/埠組, 並決定您是否要將公用 IP 位址指派給 SBCs 或使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="1d693-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="1d693-272">找出每個 SBC 支援或可以處理的併發會話數目上限。</span><span class="sxs-lookup"><span data-stu-id="1d693-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="1d693-273">使用 [媒體旁路] 來決定要設定哪一個 SBCs。</span><span class="sxs-lookup"><span data-stu-id="1d693-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-274">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-274">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-275">使用下列範例資料表, 將針對 SBCs 所做的每個決策進行檔記錄。</span><span class="sxs-lookup"><span data-stu-id="1d693-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="1d693-276">使用下列範本來記錄直接路由部署的 SBC 詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1d693-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="1d693-277">**SBC DNS 名稱 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="1d693-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="1d693-278">**SBC 與模型**</span><span class="sxs-lookup"><span data-stu-id="1d693-278">**SBC make and model**</span></span> | <span data-ttu-id="1d693-279">**憑證**</span><span class="sxs-lookup"><span data-stu-id="1d693-279">**Certificate**</span></span> | <span data-ttu-id="1d693-280">**位置**</span><span class="sxs-lookup"><span data-stu-id="1d693-280">**Location**</span></span>  | <span data-ttu-id="1d693-281">**IP 位址**</span><span class="sxs-lookup"><span data-stu-id="1d693-281">**IP address**</span></span> | <span data-ttu-id="1d693-282">**SIP 信號埠**</span><span class="sxs-lookup"><span data-stu-id="1d693-282">**SIP signaling port**</span></span> | <span data-ttu-id="1d693-283">**NAT-T?**</span><span class="sxs-lookup"><span data-stu-id="1d693-283">**NAT?**</span></span> | <span data-ttu-id="1d693-284">**最大併發會話數**</span><span class="sxs-lookup"><span data-stu-id="1d693-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="1d693-285">**已啟用媒體旁路功能嗎？**</span><span class="sxs-lookup"><span data-stu-id="1d693-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="1d693-286">SBC-Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="1d693-287">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-287">TBD</span></span> | <span data-ttu-id="1d693-288">\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-288">\*.contoso.com</span></span> | <span data-ttu-id="1d693-289">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="1d693-289">Amsterdam</span></span> | <span data-ttu-id="1d693-290">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-290">TBD</span></span> | <span data-ttu-id="1d693-291">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-291">TBD</span></span> | <span data-ttu-id="1d693-292">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-292">Yes</span></span> | <span data-ttu-id="1d693-293">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-293">TBD</span></span> | <span data-ttu-id="1d693-294">不</span><span class="sxs-lookup"><span data-stu-id="1d693-294">No</span></span> |
> | <span data-ttu-id="1d693-295">SBC-Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="1d693-296">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-296">TBD</span></span> | <span data-ttu-id="1d693-297">\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-297">\*.contoso.com</span></span> | <span data-ttu-id="1d693-298">香港特別行政區</span><span class="sxs-lookup"><span data-stu-id="1d693-298">Hong Kong SAR</span></span> | <span data-ttu-id="1d693-299">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-299">TBD</span></span> | <span data-ttu-id="1d693-300">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-300">TBD</span></span> | <span data-ttu-id="1d693-301">不</span><span class="sxs-lookup"><span data-stu-id="1d693-301">No</span></span> | <span data-ttu-id="1d693-302">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-302">TBD</span></span> | <span data-ttu-id="1d693-303">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-303">Yes</span></span> |
> | <span data-ttu-id="1d693-304">SBC-Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="1d693-305">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-305">TBD</span></span> | <span data-ttu-id="1d693-306">\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-306">\*.contoso.com</span></span> | <span data-ttu-id="1d693-307">Johannesburg</span><span class="sxs-lookup"><span data-stu-id="1d693-307">Johannesburg</span></span> | <span data-ttu-id="1d693-308">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-308">TBD</span></span> | <span data-ttu-id="1d693-309">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-309">TBD</span></span> | <span data-ttu-id="1d693-310">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-310">Yes</span></span> | <span data-ttu-id="1d693-311">TBD</span><span class="sxs-lookup"><span data-stu-id="1d693-311">TBD</span></span> | <span data-ttu-id="1d693-312">是的</span><span class="sxs-lookup"><span data-stu-id="1d693-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="1d693-313">語音路由</span><span class="sxs-lookup"><span data-stu-id="1d693-313">Voice routing</span></span>

<span data-ttu-id="1d693-314">您需要設定 Microsoft Phone 系統, 以將呼叫路由到特定的 SBCs, 以進行直接路由。</span><span class="sxs-lookup"><span data-stu-id="1d693-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="1d693-315">您可以根據下列專案設定語音路由:</span><span class="sxs-lookup"><span data-stu-id="1d693-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="1d693-316">名為 [數位模式]。</span><span class="sxs-lookup"><span data-stu-id="1d693-316">Called number pattern.</span></span>

-   <span data-ttu-id="1d693-317">呼叫數位模式 + 撥打電話的使用者。</span><span class="sxs-lookup"><span data-stu-id="1d693-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="1d693-318">[通話路由] 是由下列元素所組成:</span><span class="sxs-lookup"><span data-stu-id="1d693-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="1d693-319">語音路由策略– PSTN 用途的容器;可以指派給使用者或多位使用者</span><span class="sxs-lookup"><span data-stu-id="1d693-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="1d693-320">PSTN 用途–語音路由和 PSTN 用途的容器;可以在不同的語音路由策略中共用</span><span class="sxs-lookup"><span data-stu-id="1d693-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="1d693-321">語音路由-數位模式和一組線上 PSTN 閘道, 用於撥打電話號碼符合模式的呼叫</span><span class="sxs-lookup"><span data-stu-id="1d693-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="1d693-322">線上 PSTN 閘道-位於 SBC 的指標, 也會儲存透過 SBC 發出通話時所套用的設定, 例如轉寄 P 斷言身分識別 (PAI) 或首選編解碼器;可以新增到語音路由</span><span class="sxs-lookup"><span data-stu-id="1d693-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="1d693-323">您可以使用直接路由來設定語音路由, 以便與通話方案共存。</span><span class="sxs-lookup"><span data-stu-id="1d693-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="1d693-324">這項設定可讓通話方案使用直接路由, 將某些呼叫路由到特定的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="1d693-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="1d693-325">SBCs 可以指定為 [ \*\* 作用中] 和 [*備份*]。</span><span class="sxs-lookup"><span data-stu-id="1d693-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="1d693-326">這表示當被設定為適用于此數值模式的 SBC (或數位模式 + 特定使用者) 無法使用時, 會將呼叫路由至 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="1d693-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-327">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-327">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-328">決定您要建立的語音路由策略、PSTN 使用及語音路由, 以便在直接路由實現的範圍內支援使用者位置或辦公室。</span><span class="sxs-lookup"><span data-stu-id="1d693-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-329">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-329">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-330">為您的組織記錄語音路由策略、PSTN 用途及語音路線。</span><span class="sxs-lookup"><span data-stu-id="1d693-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="1d693-331">將指派給您所定義之每個語音路由策略的使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="1d693-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="1d693-332">使用下列範本來記錄直接路由部署的語音原則。</span><span class="sxs-lookup"><span data-stu-id="1d693-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="1d693-333">**PSTN 使用量**</span><span class="sxs-lookup"><span data-stu-id="1d693-333">**PSTN usage**</span></span> | <span data-ttu-id="1d693-334">**語音路線**</span><span class="sxs-lookup"><span data-stu-id="1d693-334">**Voice route**</span></span> | <span data-ttu-id="1d693-335">**數位模式**</span><span class="sxs-lookup"><span data-stu-id="1d693-335">**Number pattern**</span></span> | <span data-ttu-id="1d693-336">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="1d693-336">**Priority**</span></span> | <span data-ttu-id="1d693-337">**SBC**</span><span class="sxs-lookup"><span data-stu-id="1d693-337">**SBC**</span></span> | <span data-ttu-id="1d693-338">**說明**</span><span class="sxs-lookup"><span data-stu-id="1d693-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="1d693-339">僅限美國</span><span class="sxs-lookup"><span data-stu-id="1d693-339">US only</span></span> | <span data-ttu-id="1d693-340">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="1d693-340">“Redmond 1”</span></span> | <span data-ttu-id="1d693-341">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="1d693-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="1d693-342">sr-1</span><span class="sxs-lookup"><span data-stu-id="1d693-342">1</span></span> | <span data-ttu-id="1d693-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="1d693-344">呼叫號碼 + 1 425 XXX XX xx 美元或 + 1 206 XXX XX xx 的活動路由</span><span class="sxs-lookup"><span data-stu-id="1d693-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="1d693-345">僅限美國</span><span class="sxs-lookup"><span data-stu-id="1d693-345">US only</span></span> | <span data-ttu-id="1d693-346">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="1d693-346">“Redmond 2”</span></span> | <span data-ttu-id="1d693-347">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="1d693-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="1d693-348">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1d693-348">2</span></span> | <span data-ttu-id="1d693-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="1d693-350">呼叫號碼的備份路由 + 1 425 XXX XX XX or + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="1d693-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="1d693-351">僅限美國</span><span class="sxs-lookup"><span data-stu-id="1d693-351">US only</span></span> | <span data-ttu-id="1d693-352">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="1d693-352">"Other +1”</span></span> | <span data-ttu-id="1d693-353">\^\\+ 1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="1d693-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="1d693-354">3</span><span class="sxs-lookup"><span data-stu-id="1d693-354">3</span></span> | <span data-ttu-id="1d693-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="1d693-356">呼叫號碼的路由 + 1 XXX XXX XXX xx (除 + 1 425 XXX XX 或 + 1 206 XXX XX xx 以外)</span><span class="sxs-lookup"><span data-stu-id="1d693-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="1d693-357">國際</span><span class="sxs-lookup"><span data-stu-id="1d693-357">International</span></span> | <span data-ttu-id="1d693-358">國際</span><span class="sxs-lookup"><span data-stu-id="1d693-358">International</span></span> | <span data-ttu-id="1d693-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="1d693-359">\\d+</span></span> | <span data-ttu-id="1d693-360">4</span><span class="sxs-lookup"><span data-stu-id="1d693-360">4</span></span> | <span data-ttu-id="1d693-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d693-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="1d693-362">任何數位模式的路線</span><span class="sxs-lookup"><span data-stu-id="1d693-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="1d693-363">語音路由策略中的 PSTN 用法會依順序套用, 如果在第一次使用中發現相符, 就不會評估其他用法。</span><span class="sxs-lookup"><span data-stu-id="1d693-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="1d693-364">通話和交互操作原則</span><span class="sxs-lookup"><span data-stu-id="1d693-364">Calling and Interop policies</span></span>

<span data-ttu-id="1d693-365">只有 Microsoft 團隊支援直接傳送。</span><span class="sxs-lookup"><span data-stu-id="1d693-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="1d693-366">若要透過直接佈線來撥打或接聽 PSTN 電話, 您必須設定必要的原則, 以確保在團隊中接收來電。</span><span class="sxs-lookup"><span data-stu-id="1d693-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="1d693-367">啟用直接路由的使用者無法使用商務用 Skype 來放置或接收直接路由呼叫, 因此必須部署團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="1d693-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="1d693-368">您可以使用下列兩種方法的其中一種, 設定您的使用者將團隊設為其首選用戶端通話:</span><span class="sxs-lookup"><span data-stu-id="1d693-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="1d693-369">針對僅限團隊模式設定使用者</span><span class="sxs-lookup"><span data-stu-id="1d693-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="1d693-370">指派 TeamsCallingPolicy 和 TeamsInteropPolicy, 將團隊設定為首選的呼叫用戶端。</span><span class="sxs-lookup"><span data-stu-id="1d693-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="1d693-371">如需詳細資訊, 請參閱[將 Microsoft 團隊設定為使用者的首選呼叫用戶端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。</span><span class="sxs-lookup"><span data-stu-id="1d693-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1d693-372">決策點</span><span class="sxs-lookup"><span data-stu-id="1d693-372">Decision points</span></span>|<ul><li><span data-ttu-id="1d693-373">決定您要使用哪種方法將團隊設定為 [呼叫的首選用戶端]。</span><span class="sxs-lookup"><span data-stu-id="1d693-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1d693-374">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1d693-374">Next steps</span></span>|<ul><li><span data-ttu-id="1d693-375">將使用者設定為使用互通性和呼叫原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="1d693-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="1d693-376">當使用者設定為 [僅限團隊] 模式時, 此使用者就無法再登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1d693-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="1d693-377">若要讓您的使用者在團隊用戶端中看到 [通話] 索引標籤, 您必須在租使用者的組織層級啟用私人通話。</span><span class="sxs-lookup"><span data-stu-id="1d693-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="1d693-378">如需如何啟用私人通話的詳細資訊, 請參閱[啟用 Microsoft 團隊通話](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="1d693-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="1d693-379">檔服務決策</span><span class="sxs-lookup"><span data-stu-id="1d693-379">Document service decisions</span></span>

<span data-ttu-id="1d693-380">使用本文前幾節中的資訊來記錄您的服務決策。</span><span class="sxs-lookup"><span data-stu-id="1d693-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="1d693-381">一般來說, 本檔將包含下列主要章節:</span><span class="sxs-lookup"><span data-stu-id="1d693-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="1d693-382">含通話方案網站啟用清單的電話系統</span><span class="sxs-lookup"><span data-stu-id="1d693-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="1d693-383">語音信箱配置詳細資料</span><span class="sxs-lookup"><span data-stu-id="1d693-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="1d693-384">電話系統直接路由使用者的授權指派</span><span class="sxs-lookup"><span data-stu-id="1d693-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="1d693-385">SBC 配置詳細資料</span><span class="sxs-lookup"><span data-stu-id="1d693-385">SBC configuration details</span></span>

-   <span data-ttu-id="1d693-386">語音路由策略與路由詳細資料</span><span class="sxs-lookup"><span data-stu-id="1d693-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="1d693-387">互通性與通話原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="1d693-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
