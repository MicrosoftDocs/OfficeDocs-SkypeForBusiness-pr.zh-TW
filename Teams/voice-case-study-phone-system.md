---
title: 團隊語音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785974"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="f7d59-103">Contoso 案例研究：電話系統</span><span class="sxs-lookup"><span data-stu-id="f7d59-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="f7d59-104">根據地理位置和其他因素，Contoso 擁有使用下列電話解決方案的辦公室：</span><span class="sxs-lookup"><span data-stu-id="f7d59-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="f7d59-105">網站類型 A：商務用 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f7d59-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="f7d59-106">網站類型 B：傳統舊版電話系統</span><span class="sxs-lookup"><span data-stu-id="f7d59-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="f7d59-107">網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="f7d59-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="f7d59-108">若要針對其整個組織實施 Microsoft Phone 系統方案，Contoso 必須 &mdash; 針對每個網站類型決定要 &mdash; 與手機系統搭配使用的下列選項，才能連線到公用的交換電話網絡（PSTN）：</span><span class="sxs-lookup"><span data-stu-id="f7d59-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="f7d59-109">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="f7d59-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="f7d59-110">透過直接佈線提供給自己 PSTN 載體的電話系統</span><span class="sxs-lookup"><span data-stu-id="f7d59-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="f7d59-111">透過直接佈線，搭配電話系統與呼叫方案和電話系統搭配擁有 PSTN 載體</span><span class="sxs-lookup"><span data-stu-id="f7d59-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="f7d59-112">若要針對其組織判斷合適的解決方案，Contoso 使用[microsoft 電話解決方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)和[microsoft 團隊中](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)的 Ignite 2019 會話通話。</span><span class="sxs-lookup"><span data-stu-id="f7d59-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="f7d59-113">網站類型 A：商務用 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f7d59-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="f7d59-114">Contoso 商務用 Skype Enterprise Voice 已設定為中心和分支。</span><span class="sxs-lookup"><span data-stu-id="f7d59-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="f7d59-115">這裡有一個中央位置，可在區域中維護 PSTN 閘道，在該區域中提供與商務用 Skype Enterprise Voice 使用者的 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="f7d59-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="f7d59-116">這些衛星辦公室通常沒有自己的網際網路出口。</span><span class="sxs-lookup"><span data-stu-id="f7d59-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="f7d59-117">這些使用者的數位駐留在 SIP 主幹上與現有的 SBC 連接。</span><span class="sxs-lookup"><span data-stu-id="f7d59-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="f7d59-118">為了判斷已部署的 SBC 是否已認證以進行直接路由及媒體旁路，Contoso 已核取已[認證以直接路由的會話框線控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d59-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="f7d59-119">使用者的撥號習慣是使用延伸來撥打舊版電話系統上的使用者，即使使用者有適用于對等音訊的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f7d59-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="f7d59-120">Contoso 根據下列問題進行決策：</span><span class="sxs-lookup"><span data-stu-id="f7d59-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f7d59-121">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-121">Q.</span></span> <span data-ttu-id="f7d59-122">我們需要保留我們內部部署所提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f7d59-123">是.</span><span class="sxs-lookup"><span data-stu-id="f7d59-123">A.</span></span> <span data-ttu-id="f7d59-124">否</span><span class="sxs-lookup"><span data-stu-id="f7d59-124">No</span></span> 

- <span data-ttu-id="f7d59-125">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-125">Q.</span></span> <span data-ttu-id="f7d59-126">我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="f7d59-127">是.</span><span class="sxs-lookup"><span data-stu-id="f7d59-127">A.</span></span> <span data-ttu-id="f7d59-128">否</span><span class="sxs-lookup"><span data-stu-id="f7d59-128">No</span></span> 

- <span data-ttu-id="f7d59-129">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-129">Q.</span></span> <span data-ttu-id="f7d59-130">我們需要保留我們目前的協力廠商運營商嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f7d59-131">答. 是（管控國家）和 No</span><span class="sxs-lookup"><span data-stu-id="f7d59-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="f7d59-132">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-132">Q.</span></span> <span data-ttu-id="f7d59-133">我們需要取得在 SBCs 上部署的 ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="f7d59-134">答. 是和否</span><span class="sxs-lookup"><span data-stu-id="f7d59-134">A. Yes and No</span></span>  

- <span data-ttu-id="f7d59-135">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-135">Q.</span></span> <span data-ttu-id="f7d59-136">此地區提供 Microsoft PSTN 通話方案嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="f7d59-137">答. 是和否</span><span class="sxs-lookup"><span data-stu-id="f7d59-137">A. Yes and No</span></span> 

<span data-ttu-id="f7d59-138">根據問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="f7d59-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="f7d59-139">移動位於區域中的使用者，該區域中有 PSTN 通話方案可供電話系統使用通話方案。</span><span class="sxs-lookup"><span data-stu-id="f7d59-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="f7d59-140">移動不在可使用 PSTN 通話方案之區域中的使用者、位於 SBCs 中的 ROI 仍需符合的網站，以及駐留在具有直接路線之電話系統的國家/地區中的使用者。</span><span class="sxs-lookup"><span data-stu-id="f7d59-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="f7d59-141">下圖顯示最初的商務用 Skype 企業語音部署，以及此部署如何遷移到 Microsoft 通話方案和直接路由：</span><span class="sxs-lookup"><span data-stu-id="f7d59-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![顯示在狀態之前和之後的圖表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="f7d59-143">網站類型 B：傳統舊版電話系統</span><span class="sxs-lookup"><span data-stu-id="f7d59-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="f7d59-144">Contoso 擁有許多利用舊版電話系統的辦公室。</span><span class="sxs-lookup"><span data-stu-id="f7d59-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="f7d59-145">有一個使用者子集有一個電子1.64 電話號碼，而其他人只有一個副檔名。</span><span class="sxs-lookup"><span data-stu-id="f7d59-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="f7d59-146">這些數位是駐留在 TDM 主幹上的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f7d59-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="f7d59-147">站內撥號是利用延伸前的網站程式碼來設定，以決定路由通話的位置。</span><span class="sxs-lookup"><span data-stu-id="f7d59-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="f7d59-148">使用者的撥號習慣是透過副檔名撥號。</span><span class="sxs-lookup"><span data-stu-id="f7d59-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="f7d59-149">Contoso 根據下列問題進行決策：</span><span class="sxs-lookup"><span data-stu-id="f7d59-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f7d59-150">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-150">Q.</span></span> <span data-ttu-id="f7d59-151">我們需要保留我們內部部署所提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f7d59-152">是.</span><span class="sxs-lookup"><span data-stu-id="f7d59-152">A.</span></span> <span data-ttu-id="f7d59-153">否</span><span class="sxs-lookup"><span data-stu-id="f7d59-153">No</span></span> 

- <span data-ttu-id="f7d59-154">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-154">Q.</span></span> <span data-ttu-id="f7d59-155">我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="f7d59-156">答. 是</span><span class="sxs-lookup"><span data-stu-id="f7d59-156">A. Yes</span></span>

- <span data-ttu-id="f7d59-157">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-157">Q.</span></span> <span data-ttu-id="f7d59-158">我們需要保留我們目前的協力廠商運營商嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f7d59-159">答. 沒有</span><span class="sxs-lookup"><span data-stu-id="f7d59-159">A. No</span></span> 

- <span data-ttu-id="f7d59-160">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-160">Q.</span></span> <span data-ttu-id="f7d59-161">我們的地區提供 Microsoft PSTN 的通話方案嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="f7d59-162">答. 是和否</span><span class="sxs-lookup"><span data-stu-id="f7d59-162">A. Yes and No</span></span> 

<span data-ttu-id="f7d59-163">根據問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="f7d59-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="f7d59-164">移動位於區域中的使用者，該區域中有 PSTN 通話方案可供電話系統使用通話方案。</span><span class="sxs-lookup"><span data-stu-id="f7d59-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="f7d59-165">將沒有位於 PSTN 通話方案的區域中的使用者移至可直接傳送的電話系統。</span><span class="sxs-lookup"><span data-stu-id="f7d59-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="f7d59-166">維護與業務關鍵型類比裝置的 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="f7d59-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="f7d59-167">下列圖表顯示具有遠端網站的原始舊版系統部署，以及使用本機媒體優化進行直接路由部署的遷移：</span><span class="sxs-lookup"><span data-stu-id="f7d59-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="f7d59-168">**原始舊版部署**  
 ![顯示在狀態之前和之後的圖表](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="f7d59-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="f7d59-169">**使用直接路由進行部署**</span><span class="sxs-lookup"><span data-stu-id="f7d59-169">**Deployment with Direct Routing**</span></span>

![顯示在狀態之前和之後的圖表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="f7d59-171">網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="f7d59-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="f7d59-172">Contoso 商務用 Skype Enterprise Voice 使用者的電話號碼是由電信公司在 SIP 主幹中駐留給 SBC。</span><span class="sxs-lookup"><span data-stu-id="f7d59-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="f7d59-173">傳統電話系統的數位駐留在 TDM 幹線上，是 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f7d59-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="f7d59-174">Contoso 根據下列問題進行決策：</span><span class="sxs-lookup"><span data-stu-id="f7d59-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f7d59-175">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-175">Q.</span></span> <span data-ttu-id="f7d59-176">我們需要保留我們內部部署所提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f7d59-177">是.</span><span class="sxs-lookup"><span data-stu-id="f7d59-177">A.</span></span> <span data-ttu-id="f7d59-178">否</span><span class="sxs-lookup"><span data-stu-id="f7d59-178">No</span></span> 

- <span data-ttu-id="f7d59-179">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-179">Q.</span></span> <span data-ttu-id="f7d59-180">我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="f7d59-181">答. 沒有</span><span class="sxs-lookup"><span data-stu-id="f7d59-181">A. No</span></span> 

- <span data-ttu-id="f7d59-182">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-182">Q.</span></span> <span data-ttu-id="f7d59-183">我們需要保留我們目前的協力廠商運營商嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f7d59-184">答. 沒有</span><span class="sxs-lookup"><span data-stu-id="f7d59-184">A. No</span></span> 

- <span data-ttu-id="f7d59-185">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-185">Q.</span></span> <span data-ttu-id="f7d59-186">我們需要取得在 SBCs 上部署的 ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="f7d59-187">答. 是和否</span><span class="sxs-lookup"><span data-stu-id="f7d59-187">A. Yes and No</span></span>  

- <span data-ttu-id="f7d59-188">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-188">Q.</span></span> <span data-ttu-id="f7d59-189">此地區提供 Microsoft 的 PSTN 通話方案嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="f7d59-190">答. 沒有</span><span class="sxs-lookup"><span data-stu-id="f7d59-190">A. No</span></span> 

<span data-ttu-id="f7d59-191">根據問題的答案，Contoso 決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="f7d59-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="f7d59-192">針對將啟用直接路由的舊版電話使用者，Contoso 會將 TDM 主幹中的數位移植到 SBC 的 SIP 幹線，因為 SBC 已認證直接路由。</span><span class="sxs-lookup"><span data-stu-id="f7d59-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="f7d59-193">若要支援移至電話系統的使用者子集，並允許持續路由透過舊版系統，舊版電話系統會設定為 SBC 的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="f7d59-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="f7d59-194">此外，為了鼓勵使用者行為變更並移除在站內延伸撥號的相依性，Contoso 提供的指導方針將團隊用於所有內部通話。</span><span class="sxs-lookup"><span data-stu-id="f7d59-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="f7d59-195">下列圖表顯示原始商務用 Skype Enterprise Voice 與舊版電話系統部署，以及使用直接路由進行混合式部署的遷移：</span><span class="sxs-lookup"><span data-stu-id="f7d59-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="f7d59-196">**原始混合式部署** 
 ![在狀態之前顯示的圖表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="f7d59-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="f7d59-197">**使用直接路由** 
 ![ 進行混合式部署在狀態之前顯示的圖表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="f7d59-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="f7d59-198">通話方案</span><span class="sxs-lookup"><span data-stu-id="f7d59-198">Calling Plans</span></span>

<span data-ttu-id="f7d59-199">為了判斷通話方案的設定需求，Contoso 已檢查[通話方案核心部署決定](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="f7d59-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="f7d59-200">產生的決定如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7d59-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="f7d59-201">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-201">Q.</span></span> <span data-ttu-id="f7d59-202">我的使用者需要國際通話嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-202">Do my users need international calling?</span></span><br> <span data-ttu-id="f7d59-203">答. 是</span><span class="sxs-lookup"><span data-stu-id="f7d59-203">A. Yes</span></span> 

- <span data-ttu-id="f7d59-204">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-204">Q.</span></span> <span data-ttu-id="f7d59-205">我的使用者是否每個都有直接向內撥電話號碼？</span><span class="sxs-lookup"><span data-stu-id="f7d59-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="f7d59-206">答. 並非今天。</span><span class="sxs-lookup"><span data-stu-id="f7d59-206">A. Not today.</span></span> <span data-ttu-id="f7d59-207">所有啟用的使用者都會收到已執行的動作。</span><span class="sxs-lookup"><span data-stu-id="f7d59-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="f7d59-208">答疑.</span><span class="sxs-lookup"><span data-stu-id="f7d59-208">Q.</span></span> <span data-ttu-id="f7d59-209">我想要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="f7d59-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="f7d59-210">答. 使用者的本機號碼會遮罩為 Contoso 的當地號碼。</span><span class="sxs-lookup"><span data-stu-id="f7d59-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="f7d59-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="f7d59-211">Direct Routing</span></span>

<span data-ttu-id="f7d59-212">Contoso 已參與 Ignite，以維持目前的 Office 365 功能，包括可在手機系統和直接路由中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="f7d59-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="f7d59-213">技術領導和架構師使用 Ignite 2019 期間提供的指導方針來決定其方向。</span><span class="sxs-lookup"><span data-stu-id="f7d59-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="f7d59-214">所用的主要會話：</span><span class="sxs-lookup"><span data-stu-id="f7d59-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="f7d59-215">使用 Microsoft 團隊直接路由來規劃成功</span><span class="sxs-lookup"><span data-stu-id="f7d59-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="f7d59-216">直接路由的更新</span><span class="sxs-lookup"><span data-stu-id="f7d59-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="f7d59-217">Configuration</span><span class="sxs-lookup"><span data-stu-id="f7d59-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="f7d59-218">通話方案網站</span><span class="sxs-lookup"><span data-stu-id="f7d59-218">Calling Plans sites</span></span>

<span data-ttu-id="f7d59-219">若要取得授權並將電話號碼指派給使用者，Contoso 請按照[設定通話方案](set-up-calling-plans.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="f7d59-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="f7d59-220">由於需要指派電話號碼的使用者數目，Contoso 決定要使用 PowerShell 來指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f7d59-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="f7d59-221">若要進一步瞭解如何使用 PowerShell 指派數位， &mdash; 除了其他設定 &mdash; Contoso 使用[團隊 PowerShell](teams-powershell-overview.md)外。</span><span class="sxs-lookup"><span data-stu-id="f7d59-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="f7d59-222">直接路由網站</span><span class="sxs-lookup"><span data-stu-id="f7d59-222">Direct Routing sites</span></span>

<span data-ttu-id="f7d59-223">若要將 Contoso 的內部部署電話結構連線至 Microsoft 團隊，Contoso 的系統管理員遵循[設定直接路由](direct-routing-configure.md)及查看[microsoft 團隊中的視頻直接路由中](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)的步驟以取得指導方針。</span><span class="sxs-lookup"><span data-stu-id="f7d59-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="f7d59-224">Contoso 也會參照由認證的 SBC 轉銷商提供的直接路由部署檔。</span><span class="sxs-lookup"><span data-stu-id="f7d59-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="f7d59-225">在 SBC 與 Microsoft Phone 系統之間設定直接路由之後，Contoso 必須對其進行測試。</span><span class="sxs-lookup"><span data-stu-id="f7d59-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="f7d59-226">若要這樣做，Contoso 系統管理員會使用 SIP 測試者用戶端，在[Ignite 2019 的直接路由會話更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)中討論。</span><span class="sxs-lookup"><span data-stu-id="f7d59-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="f7d59-227">SIP 測試者用戶端腳本和檔都是從 PowerShell 腳本下載，以測試直接路由會話框線控制器連線。</span><span class="sxs-lookup"><span data-stu-id="f7d59-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="f7d59-228">本機媒體優化</span><span class="sxs-lookup"><span data-stu-id="f7d59-228">Local Media Optimization</span></span>

<span data-ttu-id="f7d59-229">Contoso 在全球不同地區看到了利用本機媒體優化的機會。</span><span class="sxs-lookup"><span data-stu-id="f7d59-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="f7d59-230">Contoso 的支援案例將在[本機媒體優化中說明，以進行直接路由](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d59-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="f7d59-231">以下是由 SBC 供應商和 Microsoft 提供的指導方針完成本機媒體優化的設定。</span><span class="sxs-lookup"><span data-stu-id="f7d59-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="f7d59-232">本機媒體優化的設定步驟包括：</span><span class="sxs-lookup"><span data-stu-id="f7d59-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="f7d59-233">設定使用者和 SBC 網站</span><span class="sxs-lookup"><span data-stu-id="f7d59-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="f7d59-234">根據 SBC 廠商的規格來設定 SBC，</span><span class="sxs-lookup"><span data-stu-id="f7d59-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="f7d59-235">將外部信任的 IP 位址新增到用於本機媒體優化的每個網站</span><span class="sxs-lookup"><span data-stu-id="f7d59-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="f7d59-236">定義網路拓撲</span><span class="sxs-lookup"><span data-stu-id="f7d59-236">Define the network topology</span></span> 

- <span data-ttu-id="f7d59-237">定義虛擬網路拓撲</span><span class="sxs-lookup"><span data-stu-id="f7d59-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="f7d59-238">判斷模式：總是略過或只適用于本機使用者</span><span class="sxs-lookup"><span data-stu-id="f7d59-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="f7d59-239">網路考慮</span><span class="sxs-lookup"><span data-stu-id="f7d59-239">Networking considerations</span></span>

<span data-ttu-id="f7d59-240">Contoso 有許多使用者需要在啟用電話系統之後，在一段時間內進行遠端作業。</span><span class="sxs-lookup"><span data-stu-id="f7d59-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="f7d59-241">使用者使用 VPN 存取特定的商務應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d59-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="f7d59-242">在 VPN 上，電話系統使用者遇到通話品質下降的情況。</span><span class="sxs-lookup"><span data-stu-id="f7d59-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="f7d59-243">若要解決品質問題，Contoso 已實現 VPN 分割隧道，允許其 Office 365 通訊在與內部 app 連線之後，在 VPN 上保留。</span><span class="sxs-lookup"><span data-stu-id="f7d59-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="f7d59-244">若要實現 VPN 分割隧道，Contoso 遵循[針對 Office 365 實現 vpn 分割隧道的](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)指導方針。</span><span class="sxs-lookup"><span data-stu-id="f7d59-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





