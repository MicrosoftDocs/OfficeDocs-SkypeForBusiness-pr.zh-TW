---
title: Teams Contoso 案例研究
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
description: Teams多國公司的語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101029"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="3513d-103">Contoso 案例研究：電話系統</span><span class="sxs-lookup"><span data-stu-id="3513d-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="3513d-104">根據地理位置和其他因素，Contoso 有使用下列電話解決方案的辦公室：</span><span class="sxs-lookup"><span data-stu-id="3513d-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="3513d-105">網站類型 A：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="3513d-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="3513d-106">網站類型 B：傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="3513d-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="3513d-107">網站類型 C：傳統商務用 Skype 企業語音傳統電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="3513d-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="3513d-108">若要為整個組織Microsoft 電話系統解決方案，Contoso 必須針對每個網站類型決定下列哪些選項會與 電話系統 一起使用，以連接到公用交換電話網絡 &mdash; &mdash; (PSTN) ：</span><span class="sxs-lookup"><span data-stu-id="3513d-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="3513d-109">電話系統通話方案</span><span class="sxs-lookup"><span data-stu-id="3513d-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="3513d-110">電話系統直接路由使用自己的 PSTN 電信公司</span><span class="sxs-lookup"><span data-stu-id="3513d-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="3513d-111">透過直接路由電話系統電話方案與電話系統 PSTN 電信公司之間的通話組合</span><span class="sxs-lookup"><span data-stu-id="3513d-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="3513d-112">為了判斷適合其組織的解決方案，Contoso 在 Microsoft Teams 中使用[Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)電話解決方案和 Ignite 2019[會話Microsoft Teams。](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="3513d-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="3513d-113">網站類型 A：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="3513d-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="3513d-114">Contoso 商務用 Skype 企業語音設定為樞紐和分支。</span><span class="sxs-lookup"><span data-stu-id="3513d-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="3513d-115">有一個中央位置維護了地區的 PSTN 閘道，為國家/地區的使用者商務用 Skype 企業語音 PSTN。</span><span class="sxs-lookup"><span data-stu-id="3513d-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="3513d-116">這些衛星辦公室通常沒有自己的網際網路出口。</span><span class="sxs-lookup"><span data-stu-id="3513d-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="3513d-117">這些使用者的數位會位於連接到現有 SBC 的 SIP 主幹上。</span><span class="sxs-lookup"><span data-stu-id="3513d-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="3513d-118">若要判斷已部署的 SBC 是否通過直接路由和媒體旁路的認證，Contoso 檢查了已通過直接路由認證的會話 [框線控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="3513d-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="3513d-119">使用者的撥號習慣是使用分機撥打舊版電話系統上的使用者，即使使用者有 商務用 Skype 用戶端可供對等音訊使用。</span><span class="sxs-lookup"><span data-stu-id="3513d-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="3513d-120">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="3513d-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="3513d-121">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-121">Q.</span></span> <span data-ttu-id="3513d-122">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="3513d-123">A。</span><span class="sxs-lookup"><span data-stu-id="3513d-123">A.</span></span> <span data-ttu-id="3513d-124">否</span><span class="sxs-lookup"><span data-stu-id="3513d-124">No</span></span> 

- <span data-ttu-id="3513d-125">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-125">Q.</span></span> <span data-ttu-id="3513d-126">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="3513d-127">A。</span><span class="sxs-lookup"><span data-stu-id="3513d-127">A.</span></span> <span data-ttu-id="3513d-128">否</span><span class="sxs-lookup"><span data-stu-id="3513d-128">No</span></span> 

- <span data-ttu-id="3513d-129">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-129">Q.</span></span> <span data-ttu-id="3513d-130">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="3513d-131">A。是 (國家/地區) 和否</span><span class="sxs-lookup"><span data-stu-id="3513d-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="3513d-132">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-132">Q.</span></span> <span data-ttu-id="3513d-133">我們需要部署 SBCs 的ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="3513d-134">A。是與否</span><span class="sxs-lookup"><span data-stu-id="3513d-134">A. Yes and No</span></span>  

- <span data-ttu-id="3513d-135">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-135">Q.</span></span> <span data-ttu-id="3513d-136">此地區是否提供 Microsoft PSTN 通話方案？</span><span class="sxs-lookup"><span data-stu-id="3513d-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="3513d-137">A。是與否</span><span class="sxs-lookup"><span data-stu-id="3513d-137">A. Yes and No</span></span> 

<span data-ttu-id="3513d-138">根據他們問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="3513d-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="3513d-139">移動位於 PSTN 通話方案可用區域的使用者，電話系統通話方案。</span><span class="sxs-lookup"><span data-stu-id="3513d-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="3513d-140">移動不在提供 PSTN 通話方案區域的使用者、位於 SBC 上尚未達到ROI 的網站的使用者，以及居住在具有電話法規的國家/地區使用直接路由電話系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="3513d-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="3513d-141">下圖顯示部署商務用 Skype 企業語音部署，以及此部署如何移移至 Microsoft 通話方案與直接路由：</span><span class="sxs-lookup"><span data-stu-id="3513d-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![顯示狀態之前和之後圖表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="3513d-143">網站類型 B：傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="3513d-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="3513d-144">Contoso 有許多運用舊版電話系統的辦公室。</span><span class="sxs-lookup"><span data-stu-id="3513d-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="3513d-145">有一部分使用者擁有 E1.64 電話號碼，而其他人則只有分機號碼。</span><span class="sxs-lookup"><span data-stu-id="3513d-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="3513d-146">這些號碼會位於 TDM 主幹到 PSTN 閘道上。</span><span class="sxs-lookup"><span data-stu-id="3513d-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="3513d-147">網站內部撥號是利用分機前方的網站代碼來決定撥號位置所配置的。</span><span class="sxs-lookup"><span data-stu-id="3513d-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="3513d-148">使用者的撥號習慣是按分機撥號。</span><span class="sxs-lookup"><span data-stu-id="3513d-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="3513d-149">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="3513d-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="3513d-150">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-150">Q.</span></span> <span data-ttu-id="3513d-151">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="3513d-152">A。</span><span class="sxs-lookup"><span data-stu-id="3513d-152">A.</span></span> <span data-ttu-id="3513d-153">否</span><span class="sxs-lookup"><span data-stu-id="3513d-153">No</span></span> 

- <span data-ttu-id="3513d-154">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-154">Q.</span></span> <span data-ttu-id="3513d-155">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="3513d-156">A。是的</span><span class="sxs-lookup"><span data-stu-id="3513d-156">A. Yes</span></span>

- <span data-ttu-id="3513d-157">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-157">Q.</span></span> <span data-ttu-id="3513d-158">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="3513d-159">A。不</span><span class="sxs-lookup"><span data-stu-id="3513d-159">A. No</span></span> 

- <span data-ttu-id="3513d-160">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-160">Q.</span></span> <span data-ttu-id="3513d-161">我們地區是否提供 Microsoft PSTN 的通話方案？</span><span class="sxs-lookup"><span data-stu-id="3513d-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="3513d-162">A。是與否</span><span class="sxs-lookup"><span data-stu-id="3513d-162">A. Yes and No</span></span> 

<span data-ttu-id="3513d-163">根據他們問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="3513d-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="3513d-164">移動位於 PSTN 通話方案可用區域的使用者，電話系統通話方案。</span><span class="sxs-lookup"><span data-stu-id="3513d-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="3513d-165">移動不在 PSTN 通話方案可用區域的使用者，電話系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="3513d-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="3513d-166">維護與商務關鍵型類比裝置之間的 PSTN 連接。</span><span class="sxs-lookup"><span data-stu-id="3513d-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="3513d-167">下列圖表顯示使用遠端網站的原始舊版系統部署，以及使用 Local Media 優化將系統移至直接路由部署：</span><span class="sxs-lookup"><span data-stu-id="3513d-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="3513d-168">**原始舊版部署**  
 ![顯示狀態之前和之後圖表](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="3513d-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="3513d-169">**使用直接路由進行部署**</span><span class="sxs-lookup"><span data-stu-id="3513d-169">**Deployment with Direct Routing**</span></span>

![顯示狀態之前和之後圖表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="3513d-171">網站類型 C：商務用 Skype 企業語音傳統傳統電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="3513d-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="3513d-172">Contoso 商務用 Skype 企業語音使用者的號碼會位於從電信電信企業到 SBC 的 SIP 主幹上。</span><span class="sxs-lookup"><span data-stu-id="3513d-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="3513d-173">傳統電話系統的數位會位於 PSTN 閘道的 TDM 主幹上。</span><span class="sxs-lookup"><span data-stu-id="3513d-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="3513d-174">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="3513d-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="3513d-175">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-175">Q.</span></span> <span data-ttu-id="3513d-176">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="3513d-177">A。</span><span class="sxs-lookup"><span data-stu-id="3513d-177">A.</span></span> <span data-ttu-id="3513d-178">否</span><span class="sxs-lookup"><span data-stu-id="3513d-178">No</span></span> 

- <span data-ttu-id="3513d-179">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-179">Q.</span></span> <span data-ttu-id="3513d-180">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="3513d-181">A。不</span><span class="sxs-lookup"><span data-stu-id="3513d-181">A. No</span></span> 

- <span data-ttu-id="3513d-182">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-182">Q.</span></span> <span data-ttu-id="3513d-183">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="3513d-184">A。不</span><span class="sxs-lookup"><span data-stu-id="3513d-184">A. No</span></span> 

- <span data-ttu-id="3513d-185">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-185">Q.</span></span> <span data-ttu-id="3513d-186">我們需要部署 SBCs 的ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="3513d-187">A。是與否</span><span class="sxs-lookup"><span data-stu-id="3513d-187">A. Yes and No</span></span>  

- <span data-ttu-id="3513d-188">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-188">Q.</span></span> <span data-ttu-id="3513d-189">Microsoft 的 PSTN 通話方案是否在此地區提供？</span><span class="sxs-lookup"><span data-stu-id="3513d-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="3513d-190">A。不</span><span class="sxs-lookup"><span data-stu-id="3513d-190">A. No</span></span> 

<span data-ttu-id="3513d-191">根據他們問題的答案，Contoso 決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="3513d-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="3513d-192">針對將啟用直接路由的舊版電話使用者，Contoso 將 TDM 主幹中的號碼移植到 SBC 的 SIP 主幹，因為 SBC 已通過直接路由認證。</span><span class="sxs-lookup"><span data-stu-id="3513d-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="3513d-193">為了支援一部分使用者移往 電話系統並允許繼續透過舊版系統路由，舊版電話系統已設定為 SBC 的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="3513d-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="3513d-194">此外，為了鼓勵使用者行為變更，並移除對網站間和內部分機撥號的相依性，Contoso 提供所有內部電話Teams通話使用指南。</span><span class="sxs-lookup"><span data-stu-id="3513d-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="3513d-195">下列圖表顯示原始電話商務用 Skype 企業語音和舊版電話系統部署，以及使用直接路由移入混合式部署：</span><span class="sxs-lookup"><span data-stu-id="3513d-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="3513d-196">**原始混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="3513d-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="3513d-197">**使用直接路由混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="3513d-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="3513d-198">通話方案</span><span class="sxs-lookup"><span data-stu-id="3513d-198">Calling Plans</span></span>

<span data-ttu-id="3513d-199">若要判斷通話方案的配置需求，Contoso 已審查通話 [方案核心部署決策](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="3513d-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="3513d-200">已做出以下決策：</span><span class="sxs-lookup"><span data-stu-id="3513d-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="3513d-201">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-201">Q.</span></span> <span data-ttu-id="3513d-202">我的使用者是否需要國際電話？</span><span class="sxs-lookup"><span data-stu-id="3513d-202">Do my users need international calling?</span></span><br> <span data-ttu-id="3513d-203">A。是的</span><span class="sxs-lookup"><span data-stu-id="3513d-203">A. Yes</span></span> 

- <span data-ttu-id="3513d-204">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-204">Q.</span></span> <span data-ttu-id="3513d-205">我的使用者是否都有直接向內 DID 的電話號碼？</span><span class="sxs-lookup"><span data-stu-id="3513d-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="3513d-206">答：今天沒有。</span><span class="sxs-lookup"><span data-stu-id="3513d-206">A. Not today.</span></span> <span data-ttu-id="3513d-207">啟用的所有使用者都會收到 DID。</span><span class="sxs-lookup"><span data-stu-id="3513d-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="3513d-208">問。</span><span class="sxs-lookup"><span data-stu-id="3513d-208">Q.</span></span> <span data-ttu-id="3513d-209">我要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="3513d-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="3513d-210">A。使用者的本機號碼將會遮罩到 Contoso 的當地號碼。</span><span class="sxs-lookup"><span data-stu-id="3513d-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="3513d-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="3513d-211">Direct Routing</span></span>

<span data-ttu-id="3513d-212">Contoso 參與 Ignite，以隨時Office 365功能，包括系統電話和直接路由提供的功能。</span><span class="sxs-lookup"><span data-stu-id="3513d-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="3513d-213">技術領導者和架構設計師使用 Ignite 2019 期間所提供的指引來判斷其方向。</span><span class="sxs-lookup"><span data-stu-id="3513d-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="3513d-214">使用的關鍵會話：</span><span class="sxs-lookup"><span data-stu-id="3513d-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="3513d-215">使用直接路由規劃Microsoft Teams成功</span><span class="sxs-lookup"><span data-stu-id="3513d-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="3513d-216">直接路由的更新</span><span class="sxs-lookup"><span data-stu-id="3513d-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="3513d-217">配置</span><span class="sxs-lookup"><span data-stu-id="3513d-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="3513d-218">通話方案網站</span><span class="sxs-lookup"><span data-stu-id="3513d-218">Calling Plans sites</span></span>

<span data-ttu-id="3513d-219">若要取得授權並指派電話號碼給使用者，Contoso 遵循設定 [通話方案中的步驟](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="3513d-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="3513d-220">由於需要指派電話號碼的使用者數目，Contoso 決定使用 PowerShell 來指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3513d-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="3513d-221">若要瞭解如何使用 PowerShell 來指派數位，除了其他設定之外 &mdash; &mdash; ，Contoso Teams [PowerShell 概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3513d-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="3513d-222">直接路由網站</span><span class="sxs-lookup"><span data-stu-id="3513d-222">Direct Routing sites</span></span>

<span data-ttu-id="3513d-223">若要將 Contoso 內部部署電話基礎結構連接到 Microsoft Teams，Contoso 的系統管理員遵循設定直接路由中的步驟，並[](direct-routing-configure.md)查看 Microsoft Teams 中的影片直接路由以[尋求](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)指引。</span><span class="sxs-lookup"><span data-stu-id="3513d-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="3513d-224">Contoso 也提及認證 SBC 廠商的直接路由部署檔。</span><span class="sxs-lookup"><span data-stu-id="3513d-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="3513d-225">在 SBC 和 Microsoft 電話 之間進行直接路由之後，Contoso 必須測試該組配置。</span><span class="sxs-lookup"><span data-stu-id="3513d-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="3513d-226">若要這麼做，Contoso 系統管理員使用 SIP 測試程式用戶端，該用戶端在 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)的直接路由更新會話中已討論。</span><span class="sxs-lookup"><span data-stu-id="3513d-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="3513d-227">SIP 測試程式用戶端腳本和檔是從 PowerShell 腳本下載，以測試直接路由會話邊界控制器連接。</span><span class="sxs-lookup"><span data-stu-id="3513d-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="3513d-228">Local Media 優化</span><span class="sxs-lookup"><span data-stu-id="3513d-228">Local Media Optimization</span></span>

<span data-ttu-id="3513d-229">Contoso 看到在全球不同區域運用 Local Media 優化的機會。</span><span class="sxs-lookup"><span data-stu-id="3513d-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="3513d-230">Contoso 的支援案例在直接路由的 Local [Media 優化中說明](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="3513d-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="3513d-231">根據 SBC 廠商和 Microsoft 提供的指導，完成本地媒體優化的組配置。</span><span class="sxs-lookup"><span data-stu-id="3513d-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="3513d-232">Local Media 優化的組組步驟包括：</span><span class="sxs-lookup"><span data-stu-id="3513d-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="3513d-233">設定使用者和 SBC 網站</span><span class="sxs-lookup"><span data-stu-id="3513d-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="3513d-234">根據 SBC 廠商規格設定 SBC，</span><span class="sxs-lookup"><span data-stu-id="3513d-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="3513d-235">新增外部信任的 IP 位址至每個用於 Local Media 優化的網站</span><span class="sxs-lookup"><span data-stu-id="3513d-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="3513d-236">定義網路拓撲</span><span class="sxs-lookup"><span data-stu-id="3513d-236">Define the network topology</span></span> 

- <span data-ttu-id="3513d-237">定義虛擬網路拓撲</span><span class="sxs-lookup"><span data-stu-id="3513d-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="3513d-238">決定模式：一直忽略或僅適用于本地使用者</span><span class="sxs-lookup"><span data-stu-id="3513d-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="3513d-239">網路考慮</span><span class="sxs-lookup"><span data-stu-id="3513d-239">Networking considerations</span></span>

<span data-ttu-id="3513d-240">Contoso 有一些使用者需要長時間遠端工作，才能使用 電話系統。</span><span class="sxs-lookup"><span data-stu-id="3513d-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="3513d-241">使用者使用 VPN 存取特定的商務用應用程式。</span><span class="sxs-lookup"><span data-stu-id="3513d-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="3513d-242">使用 VPN 時，電話系統通話品質降低。</span><span class="sxs-lookup"><span data-stu-id="3513d-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="3513d-243">若要解決品質問題，Contoso 已實施 VPN 分割管道，允許其Office 365流量在內部應用程式的連接維持在 VPN 上時，可以橫穿網際網路。</span><span class="sxs-lookup"><span data-stu-id="3513d-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="3513d-244">若要執行 VPN 分割傳輸，Contoso 遵循了針對 Office 365 的實現 VPN 分割[Office 365。](/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="3513d-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

