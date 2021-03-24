---
title: Teams Voice Contoso 案例研究
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
description: 多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101029"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="4b467-103">Contoso 案例研究：電話系統</span><span class="sxs-lookup"><span data-stu-id="4b467-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="4b467-104">根據地理位置和其他因素，Contoso 的辦公室會使用下列電話解決方案：</span><span class="sxs-lookup"><span data-stu-id="4b467-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="4b467-105">網站類型 A：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="4b467-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="4b467-106">網站類型 B：傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="4b467-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="4b467-107">網站類型 C：商務用 Skype 企業語音與傳統傳統電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="4b467-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="4b467-108">若要為整個組織執行 Microsoft Phone System 解決方案，Contoso 必須針對每個網站類型決定下列哪些選項會用於電話系統以連接到公用交換電話網絡 &mdash; &mdash; (PSTN) ：</span><span class="sxs-lookup"><span data-stu-id="4b467-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="4b467-109">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="4b467-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="4b467-110">透過直接路由使用自己的 PSTN 電信公司的電話系統</span><span class="sxs-lookup"><span data-stu-id="4b467-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="4b467-111">電話系統與通話方案的組合，以及透過直接路由使用自己的 PSTN 電信公司的電話系統組合</span><span class="sxs-lookup"><span data-stu-id="4b467-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="4b467-112">為了判斷適合其組織的解決方案，Contoso 使用 [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) 電話解決方案和 Microsoft Teams 中的 Ignite 2019 [會話通話](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="4b467-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="4b467-113">網站類型 A：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="4b467-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="4b467-114">Contoso 商務用 Skype 企業語音已設定為中樞和語音。</span><span class="sxs-lookup"><span data-stu-id="4b467-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="4b467-115">有一個中央位置維護了地區的 PSTN 閘道，為國家/地區的商務用 Skype 企業語音使用者提供 PSTN 的連接。</span><span class="sxs-lookup"><span data-stu-id="4b467-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="4b467-116">這些衛星辦公室通常沒有自己的網際網路出口。</span><span class="sxs-lookup"><span data-stu-id="4b467-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="4b467-117">這些使用者的數位會位於連接到現有 SBC 的 SIP 主幹上。</span><span class="sxs-lookup"><span data-stu-id="4b467-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="4b467-118">若要判斷已部署的 SBC 是否通過直接路由和媒體旁路的認證，Contoso 檢查了已通過直接路由認證的會話 [框線控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="4b467-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="4b467-119">使用者的撥號習慣是使用分機撥打舊版電話系統上的使用者，即使使用者有適用于對等音訊的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b467-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="4b467-120">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="4b467-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4b467-121">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-121">Q.</span></span> <span data-ttu-id="4b467-122">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4b467-123">A。</span><span class="sxs-lookup"><span data-stu-id="4b467-123">A.</span></span> <span data-ttu-id="4b467-124">否</span><span class="sxs-lookup"><span data-stu-id="4b467-124">No</span></span> 

- <span data-ttu-id="4b467-125">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-125">Q.</span></span> <span data-ttu-id="4b467-126">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="4b467-127">A。</span><span class="sxs-lookup"><span data-stu-id="4b467-127">A.</span></span> <span data-ttu-id="4b467-128">否</span><span class="sxs-lookup"><span data-stu-id="4b467-128">No</span></span> 

- <span data-ttu-id="4b467-129">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-129">Q.</span></span> <span data-ttu-id="4b467-130">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4b467-131">A。是 (國家/地區) 和否</span><span class="sxs-lookup"><span data-stu-id="4b467-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="4b467-132">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-132">Q.</span></span> <span data-ttu-id="4b467-133">我們需要部署 SBCs 的ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="4b467-134">A。是與否</span><span class="sxs-lookup"><span data-stu-id="4b467-134">A. Yes and No</span></span>  

- <span data-ttu-id="4b467-135">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-135">Q.</span></span> <span data-ttu-id="4b467-136">此地區是否提供 Microsoft PSTN 通話方案？</span><span class="sxs-lookup"><span data-stu-id="4b467-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="4b467-137">A。是與否</span><span class="sxs-lookup"><span data-stu-id="4b467-137">A. Yes and No</span></span> 

<span data-ttu-id="4b467-138">根據他們問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="4b467-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="4b467-139">移動位於 PSTN 通話方案可供電話系統使用之地區的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b467-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="4b467-140">將不在提供 PSTN 通話方案的地區的使用者、位於 SBC 上尚未達到ROI 的網站的使用者，以及居住在具有電話法規的國家/地區中的使用者移至具有直接路由的電話系統。</span><span class="sxs-lookup"><span data-stu-id="4b467-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="4b467-141">下圖顯示初始商務用 Skype 企業語音部署，以及此部署如何移遷移到 Microsoft 通話方案與直接路由：</span><span class="sxs-lookup"><span data-stu-id="4b467-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![顯示狀態之前和之後圖表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="4b467-143">網站類型 B：傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="4b467-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="4b467-144">Contoso 有許多運用舊版電話系統的辦公室。</span><span class="sxs-lookup"><span data-stu-id="4b467-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="4b467-145">有一部分使用者擁有 E1.64 電話號碼，而其他人則只有分機號碼。</span><span class="sxs-lookup"><span data-stu-id="4b467-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="4b467-146">這些號碼會位於 TDM 主幹到 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="4b467-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="4b467-147">網站內部撥號是利用分機前方的網站代碼來決定撥號位置所配置的。</span><span class="sxs-lookup"><span data-stu-id="4b467-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="4b467-148">使用者的撥號習慣是按分機撥號。</span><span class="sxs-lookup"><span data-stu-id="4b467-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="4b467-149">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="4b467-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4b467-150">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-150">Q.</span></span> <span data-ttu-id="4b467-151">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4b467-152">A。</span><span class="sxs-lookup"><span data-stu-id="4b467-152">A.</span></span> <span data-ttu-id="4b467-153">否</span><span class="sxs-lookup"><span data-stu-id="4b467-153">No</span></span> 

- <span data-ttu-id="4b467-154">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-154">Q.</span></span> <span data-ttu-id="4b467-155">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="4b467-156">A。是的</span><span class="sxs-lookup"><span data-stu-id="4b467-156">A. Yes</span></span>

- <span data-ttu-id="4b467-157">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-157">Q.</span></span> <span data-ttu-id="4b467-158">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4b467-159">A。不</span><span class="sxs-lookup"><span data-stu-id="4b467-159">A. No</span></span> 

- <span data-ttu-id="4b467-160">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-160">Q.</span></span> <span data-ttu-id="4b467-161">我們地區是否提供 Microsoft PSTN 的通話方案？</span><span class="sxs-lookup"><span data-stu-id="4b467-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="4b467-162">A。是與否</span><span class="sxs-lookup"><span data-stu-id="4b467-162">A. Yes and No</span></span> 

<span data-ttu-id="4b467-163">根據他們問題的答案，Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="4b467-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="4b467-164">移動位於 PSTN 通話方案可供電話系統使用之地區的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b467-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="4b467-165">移動不在 PSTN 通話方案可供電話系統直接路由的地區的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b467-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="4b467-166">維護與商務關鍵型類比裝置之間的 PSTN 連接。</span><span class="sxs-lookup"><span data-stu-id="4b467-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="4b467-167">下列圖表顯示使用遠端網站的原始舊版系統部署，以及使用 Local Media 優化將系統移至直接路由部署：</span><span class="sxs-lookup"><span data-stu-id="4b467-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="4b467-168">**原始舊版部署**  
 ![顯示狀態之前和之後圖表](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="4b467-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="4b467-169">**使用直接路由進行部署**</span><span class="sxs-lookup"><span data-stu-id="4b467-169">**Deployment with Direct Routing**</span></span>

![顯示狀態之前和之後圖表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="4b467-171">網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合</span><span class="sxs-lookup"><span data-stu-id="4b467-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="4b467-172">Contoso 商務用 Skype Enterprise Voice 使用者的數位會位於從電信業者到 SBC 的 SIP 主幹上。</span><span class="sxs-lookup"><span data-stu-id="4b467-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="4b467-173">傳統電話系統的數位會位於 PSTN 閘道的 TDM 主幹上。</span><span class="sxs-lookup"><span data-stu-id="4b467-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="4b467-174">Contoso 是根據下列問題做出決策：</span><span class="sxs-lookup"><span data-stu-id="4b467-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4b467-175">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-175">Q.</span></span> <span data-ttu-id="4b467-176">我們需要保留內部部署提供的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4b467-177">A。</span><span class="sxs-lookup"><span data-stu-id="4b467-177">A.</span></span> <span data-ttu-id="4b467-178">否</span><span class="sxs-lookup"><span data-stu-id="4b467-178">No</span></span> 

- <span data-ttu-id="4b467-179">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-179">Q.</span></span> <span data-ttu-id="4b467-180">我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="4b467-181">A。不</span><span class="sxs-lookup"><span data-stu-id="4b467-181">A. No</span></span> 

- <span data-ttu-id="4b467-182">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-182">Q.</span></span> <span data-ttu-id="4b467-183">我們需要保留目前的協力廠商電信公司嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4b467-184">A。不</span><span class="sxs-lookup"><span data-stu-id="4b467-184">A. No</span></span> 

- <span data-ttu-id="4b467-185">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-185">Q.</span></span> <span data-ttu-id="4b467-186">我們需要部署 SBCs 的ROI 嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="4b467-187">A。是與否</span><span class="sxs-lookup"><span data-stu-id="4b467-187">A. Yes and No</span></span>  

- <span data-ttu-id="4b467-188">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-188">Q.</span></span> <span data-ttu-id="4b467-189">Microsoft 的 PSTN 通話方案是否在此地區提供？</span><span class="sxs-lookup"><span data-stu-id="4b467-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="4b467-190">A。不</span><span class="sxs-lookup"><span data-stu-id="4b467-190">A. No</span></span> 

<span data-ttu-id="4b467-191">根據他們問題的答案，Contoso 決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="4b467-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="4b467-192">針對將啟用直接路由的舊版電話使用者，Contoso 將 TDM 主幹中的號碼移植到 SBC 的 SIP 主幹，因為 SBC 已通過直接路由認證。</span><span class="sxs-lookup"><span data-stu-id="4b467-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="4b467-193">為了支援移往電話系統的使用者子集，並允許繼續透過舊版系統路由，舊版電話系統已設定為 SBC 的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="4b467-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="4b467-194">此外，為了鼓勵使用者行為變更，並移除網站間和內部分機撥號的相依性，Contoso 提供所有內部通話使用 Teams 的指引。</span><span class="sxs-lookup"><span data-stu-id="4b467-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="4b467-195">下圖顯示原始商務用 Skype 企業語音和舊版電話系統部署，以及使用直接路由移入混合式部署：</span><span class="sxs-lookup"><span data-stu-id="4b467-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="4b467-196">**原始混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="4b467-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="4b467-197">**使用直接路由混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="4b467-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="4b467-198">通話方案</span><span class="sxs-lookup"><span data-stu-id="4b467-198">Calling Plans</span></span>

<span data-ttu-id="4b467-199">若要判斷通話方案的配置需求，Contoso 已審查通話 [方案核心部署決策](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="4b467-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="4b467-200">已做出以下決策：</span><span class="sxs-lookup"><span data-stu-id="4b467-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="4b467-201">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-201">Q.</span></span> <span data-ttu-id="4b467-202">我的使用者是否需要國際通話？</span><span class="sxs-lookup"><span data-stu-id="4b467-202">Do my users need international calling?</span></span><br> <span data-ttu-id="4b467-203">A。是的</span><span class="sxs-lookup"><span data-stu-id="4b467-203">A. Yes</span></span> 

- <span data-ttu-id="4b467-204">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-204">Q.</span></span> <span data-ttu-id="4b467-205">我的使用者是否都有直接向內 DID 的電話號碼？</span><span class="sxs-lookup"><span data-stu-id="4b467-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="4b467-206">答：今天沒有。</span><span class="sxs-lookup"><span data-stu-id="4b467-206">A. Not today.</span></span> <span data-ttu-id="4b467-207">啟用的所有使用者都會收到 DID。</span><span class="sxs-lookup"><span data-stu-id="4b467-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="4b467-208">問。</span><span class="sxs-lookup"><span data-stu-id="4b467-208">Q.</span></span> <span data-ttu-id="4b467-209">我要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="4b467-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="4b467-210">A。使用者的本機號碼會遮罩為 Contoso 的當地號碼。</span><span class="sxs-lookup"><span data-stu-id="4b467-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="4b467-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="4b467-211">Direct Routing</span></span>

<span data-ttu-id="4b467-212">Contoso 參與 Ignite，以隨時瞭解 Office 365 功能，包括電話系統和直接路由提供的功能。</span><span class="sxs-lookup"><span data-stu-id="4b467-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="4b467-213">技術領導者和架構設計師使用 Ignite 2019 期間所提供的指引來判斷其方向。</span><span class="sxs-lookup"><span data-stu-id="4b467-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="4b467-214">使用的關鍵會話：</span><span class="sxs-lookup"><span data-stu-id="4b467-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="4b467-215">使用 Microsoft Teams 直接路由規劃成功</span><span class="sxs-lookup"><span data-stu-id="4b467-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="4b467-216">直接路由的更新</span><span class="sxs-lookup"><span data-stu-id="4b467-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="4b467-217">配置</span><span class="sxs-lookup"><span data-stu-id="4b467-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="4b467-218">通話方案網站</span><span class="sxs-lookup"><span data-stu-id="4b467-218">Calling Plans sites</span></span>

<span data-ttu-id="4b467-219">若要取得授權並指派電話號碼給使用者，Contoso 遵循設定 [通話方案中的步驟](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="4b467-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="4b467-220">由於需要指派電話號碼的使用者數目，Contoso 決定使用 PowerShell 來指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4b467-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="4b467-221">若要瞭解如何使用 PowerShell 來指派數位，除了其他設定之外 &mdash; &mdash; ，Contoso 還使用 [Teams PowerShell 概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4b467-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="4b467-222">直接路由網站</span><span class="sxs-lookup"><span data-stu-id="4b467-222">Direct Routing sites</span></span>

<span data-ttu-id="4b467-223">若要將 Contoso 內部部署電話基礎結構連接到 Microsoft Teams，Contoso 的系統管理員遵循設定直接路由[](direct-routing-configure.md)中的步驟，並查看 Microsoft [Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)中的直接路由影片以尋求指引。</span><span class="sxs-lookup"><span data-stu-id="4b467-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="4b467-224">Contoso 也提及認證 SBC 廠商的直接路由部署檔。</span><span class="sxs-lookup"><span data-stu-id="4b467-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="4b467-225">在 SBC 和 Microsoft Phone 系統之間已建立直接路由之後，Contoso 必須測試該組配置。</span><span class="sxs-lookup"><span data-stu-id="4b467-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="4b467-226">若要這麼做，Contoso 系統管理員使用 SIP 測試程式用戶端，該用戶端在 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)的直接路由更新會話中已討論。</span><span class="sxs-lookup"><span data-stu-id="4b467-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="4b467-227">SIP 測試程式用戶端腳本和檔是從 PowerShell 腳本下載，以測試直接路由會話邊界控制器連接。</span><span class="sxs-lookup"><span data-stu-id="4b467-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="4b467-228">Local Media 優化</span><span class="sxs-lookup"><span data-stu-id="4b467-228">Local Media Optimization</span></span>

<span data-ttu-id="4b467-229">Contoso 看到在全球不同區域運用 Local Media 優化的機會。</span><span class="sxs-lookup"><span data-stu-id="4b467-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="4b467-230">Contoso 的支援案例在直接路由的 Local [Media 優化中說明](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="4b467-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="4b467-231">根據 SBC 廠商和 Microsoft 提供的指導，完成了本地媒體優化的組配置。</span><span class="sxs-lookup"><span data-stu-id="4b467-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="4b467-232">Local Media 優化的組組步驟包括：</span><span class="sxs-lookup"><span data-stu-id="4b467-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="4b467-233">設定使用者和 SBC 網站</span><span class="sxs-lookup"><span data-stu-id="4b467-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="4b467-234">根據 SBC 廠商規格設定 SBC，</span><span class="sxs-lookup"><span data-stu-id="4b467-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="4b467-235">新增外部信任的 IP 位址至每個用於 Local Media 優化的網站</span><span class="sxs-lookup"><span data-stu-id="4b467-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="4b467-236">定義網路拓撲</span><span class="sxs-lookup"><span data-stu-id="4b467-236">Define the network topology</span></span> 

- <span data-ttu-id="4b467-237">定義虛擬網路拓撲</span><span class="sxs-lookup"><span data-stu-id="4b467-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="4b467-238">決定模式：一直忽略或僅適用于當地使用者</span><span class="sxs-lookup"><span data-stu-id="4b467-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="4b467-239">網路考慮</span><span class="sxs-lookup"><span data-stu-id="4b467-239">Networking considerations</span></span>

<span data-ttu-id="4b467-240">Contoso 有一些使用者在啟用電話系統之後，需要長時間遠端工作。</span><span class="sxs-lookup"><span data-stu-id="4b467-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="4b467-241">使用者使用 VPN 存取特定的商務用應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b467-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="4b467-242">使用 VPN 時，電話系統使用者遇到通話品質降低的問題。</span><span class="sxs-lookup"><span data-stu-id="4b467-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="4b467-243">若要解決品質問題，Contoso 已實施 VPN 分割管道，允許其 Office 365 流量在內部 App 的連接維持在 VPN 上時，可以橫穿網際網路。</span><span class="sxs-lookup"><span data-stu-id="4b467-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="4b467-244">若要執行 VPN 分割管道，Contoso 遵循為 [Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel)執行 VPN 分割管道中的指引。</span><span class="sxs-lookup"><span data-stu-id="4b467-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

