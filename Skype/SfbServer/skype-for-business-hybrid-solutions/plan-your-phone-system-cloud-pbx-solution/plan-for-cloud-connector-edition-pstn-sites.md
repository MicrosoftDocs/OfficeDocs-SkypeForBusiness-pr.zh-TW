---
title: 規劃雲端連接器版本 PSTN 網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 請閱讀本主題, 瞭解如何規劃雲端連接器版本 PSTN 網站, 以確保高效且經濟高效的呼叫路由。
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190723"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="15e9f-103">規劃雲端連接器版本 PSTN 網站</span><span class="sxs-lookup"><span data-stu-id="15e9f-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="15e9f-104">請閱讀本主題, 瞭解如何規劃雲端連接器版本 PSTN 網站, 以確保高效且經濟高效的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="15e9f-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="15e9f-105">本主題描述您需要瞭解的雲端連接器版本及呼叫路由, 讓您可以規劃雲端連接器 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="15e9f-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="15e9f-106">PSTN 網站是雲端連接器裝置的組合, 可在相同的位置部署, 以及與其連接的常見 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="15e9f-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="15e9f-107">本主題重點說明如何設定您的雲端連接器網站拓朴, 以確保您的雲端連接器網站能以最經濟高效且有效的方式來處理指派給網站的所有使用者的輸入和輸出路由。</span><span class="sxs-lookup"><span data-stu-id="15e9f-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="15e9f-108">如需雲端連接器的詳細資訊和 PSTN 網站的優點, 請務必閱讀[商務用 Skype 雲端連接器版本的規劃](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="15e9f-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="15e9f-109">雲端連接器 PSTN 網站和通話路由</span><span class="sxs-lookup"><span data-stu-id="15e9f-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="15e9f-110">雲端連接器 PSTN 網站是建立拓撲結構, 可避免不必要的長途與全國間 tariffs, 以及確保輸出緊急呼叫路由至適當的幹線。</span><span class="sxs-lookup"><span data-stu-id="15e9f-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="15e9f-111">為了確保經濟高效且高效地路由通話, 包括呼叫緊急服務, 您必須仔細規劃 PSTN 網站, 以及如何將使用者指派給每一個網站。</span><span class="sxs-lookup"><span data-stu-id="15e9f-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="15e9f-112">在您規劃雲端連接器的過程中, 請務必與您的運營商通話, 瞭解辦公室和使用者的位置, 以及 PSTN trunks 從載波終止的位置。</span><span class="sxs-lookup"><span data-stu-id="15e9f-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="15e9f-113">您必須使用您的運營商來判斷緊急通話的傳送方式, 然後使用該資訊來定義雲端連接器 PSTN 網站, 並將使用者指派給適當的網站。</span><span class="sxs-lookup"><span data-stu-id="15e9f-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="15e9f-114">例如, 您應該確保將 PSTN 網站延伸的資料中心終止的 trunks 設定為處理指派給該網站使用者的所有號碼的輸入和輸出路由。</span><span class="sxs-lookup"><span data-stu-id="15e9f-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="15e9f-115">每個雲端連接器裝置都可以連線到幾個 IP 閘道、IP Pbx 或會話邊界控制器 (SBCs)。</span><span class="sxs-lookup"><span data-stu-id="15e9f-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="15e9f-116">因為閘道和 Pbx 已連接至電訊 trunks (PRI 或 SIP trunks), 所以雲端連接器裝置會以邏輯方式連線到 PSTN trunks, 以進行撥入和撥出通話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="15e9f-117">透過雲端連接器和內部部署 PSTN 連線, 您就能從本機運營商取得主幹及相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="15e9f-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="15e9f-118">如果您的企業是大型企業, 您可能會有一個以上的電信公司, 尤其是當您的公司超過一個城市、州或國家/地區時。</span><span class="sxs-lookup"><span data-stu-id="15e9f-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="15e9f-119">因為您的承運人擁有電話號碼, 所以電信公司負責處理緊急通話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="15e9f-120">商務用 Skype Online 會同等地對待網站中的所有雲端連接器裝置, 並會以旋轉方式將撥出電話路由至相同網站中的雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="15e9f-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="15e9f-121">網站中的每個雲端連接器都與同一組 PSTN trunks (完全網狀) 相交。</span><span class="sxs-lookup"><span data-stu-id="15e9f-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="15e9f-122">因為每個使用者都與一個雲端連接器 PSTN 網站相關聯, 所以來自該使用者的任何出站呼叫 (正常或緊急) 都將指派給使用者所關聯的 PSTN 網站中的其中一個雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="15e9f-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="15e9f-123">雲端連接器會將靜態呼叫路由至其連接的 IP 閘道、IP-Pbx、SBCs 或直接 PSTN trunks。</span><span class="sxs-lookup"><span data-stu-id="15e9f-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="15e9f-124">雲端連接器還不能根據目的地 (最小成本路由) 或根據原產地 (靜態或動態緊急通話) 來動態路由到主幹。</span><span class="sxs-lookup"><span data-stu-id="15e9f-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="15e9f-125">輸入通話不是問題, 因為呼叫只能來自與號碼相關聯的幹線。</span><span class="sxs-lookup"><span data-stu-id="15e9f-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="15e9f-126">不過, 呼出通話可以移至網站中的任何雲端連接器裝置 (以及延伸連接至該雲端連接器裝置的 PSTN trunks), 這可能會導致不需要的長途電話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="15e9f-127">此外, 如果雲端連接器 PSTN 網站是透過不同的區功能變數代碼或運營公司延伸跨資料中心, 緊急通話就不會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="15e9f-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="15e9f-128">範例</span><span class="sxs-lookup"><span data-stu-id="15e9f-128">An example</span></span>

<span data-ttu-id="15e9f-129">下列範例說明如何將 trunks 群組至 PSTN 網站, 以及如何將使用者指派給網站。</span><span class="sxs-lookup"><span data-stu-id="15e9f-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="15e9f-130">若是 Contoso 公司, 請假設下列事項:</span><span class="sxs-lookup"><span data-stu-id="15e9f-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="15e9f-131">有四個使用者:</span><span class="sxs-lookup"><span data-stu-id="15e9f-131">There are four users:</span></span> 
    
  - <span data-ttu-id="15e9f-132">雷德蒙 WA (美國) 中的使用者 A</span><span class="sxs-lookup"><span data-stu-id="15e9f-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="15e9f-133">Bellevue WA 中的使用者 B (美國)</span><span class="sxs-lookup"><span data-stu-id="15e9f-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="15e9f-134">Centralia WA 中的使用者 C (美國)</span><span class="sxs-lookup"><span data-stu-id="15e9f-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="15e9f-135">前或 (美國) 的使用者 D</span><span class="sxs-lookup"><span data-stu-id="15e9f-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="15e9f-136">電信公司 A 在下列情況中提供電話號碼與 trunks:</span><span class="sxs-lookup"><span data-stu-id="15e9f-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="15e9f-137">雷德蒙 (區域碼 425)</span><span class="sxs-lookup"><span data-stu-id="15e9f-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="15e9f-138">Bellevue (區功能變數代碼 425)</span><span class="sxs-lookup"><span data-stu-id="15e9f-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="15e9f-139">Centralia (區功能變數代碼 360)</span><span class="sxs-lookup"><span data-stu-id="15e9f-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="15e9f-140">電信公司 B 在下列專案中提供電話號碼與 trunks:</span><span class="sxs-lookup"><span data-stu-id="15e9f-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="15e9f-141">上海 (區功能變數代碼 503)</span><span class="sxs-lookup"><span data-stu-id="15e9f-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="15e9f-142">因為使用者 A 在雷蒙德 (資料中心 A) 和 Bellevue 中的使用者 B (資料中心 B) 彼此相鄰, 且在相同的區號 (425) 中, 因此, 電信公司 A 應該能夠在 Bellevue 中的主幹上的使用者 A 進行緊急通話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="15e9f-143">因此, 使用者 A 和 B 以及 Bellevue 和雷德蒙的雲端連接器 trunks 可能位於同一個雲端連接器 PSTN 網站, 如下圖中所示。</span><span class="sxs-lookup"><span data-stu-id="15e9f-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="15e9f-144">一個辦公室中的使用者緊急通話可以傳送至另一個辦公室中的 trunks。</span><span class="sxs-lookup"><span data-stu-id="15e9f-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="15e9f-145">不過, 您應該與您的運營商確認這將會運作。</span><span class="sxs-lookup"><span data-stu-id="15e9f-145">You should, however, check with your carrier that this will work.</span></span>
  
![如何設定 PSTN 網站](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="15e9f-147">您也可以考慮下列範例:</span><span class="sxs-lookup"><span data-stu-id="15e9f-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="15e9f-148">Centralia 中的使用者 C (由電信公司 A 提供) 是兩個小時的磁片磁碟機, 並在不同的區號 (360) 中, 與其他運營商在 Bellevue 和雷德蒙425區功能變數代碼中的使用者。</span><span class="sxs-lookup"><span data-stu-id="15e9f-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="15e9f-149">因此, 即使來電是來自載波 A, 在 Centralia 區號360中, 電信公司的呼叫路由軟體可能會拒絕來自 Bellevue 區域程式碼425中的使用者 B 的傳入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="15e9f-150">在這種情況下, 載體確認雲端連接器及其在 Centralia PSTN 網站中的關聯 trunks 可以跨距離和區功能變數代碼處理通話。</span><span class="sxs-lookup"><span data-stu-id="15e9f-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="15e9f-151">中的使用者 D 使用由載體 B 提供的數位和主幹, 因此, 不太可能是由載體 B 所擁有的電話號碼撥打緊急電話。因此, trunks 中的使用者 D 和雲端連接器裝置和相關聯的將必須位於不同的 PSTN 網站中。</span><span class="sxs-lookup"><span data-stu-id="15e9f-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

