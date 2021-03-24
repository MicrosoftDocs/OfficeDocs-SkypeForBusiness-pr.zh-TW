---
title: 規劃 Cloud Connector Edition PSTN 網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 閱讀此主題以瞭解如何規劃雲端連接器 Edition PSTN 網站，以確保有效且經濟划算的呼叫路由。
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096227"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="6c9b9-103">規劃 Cloud Connector Edition PSTN 網站</span><span class="sxs-lookup"><span data-stu-id="6c9b9-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="6c9b9-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6c9b9-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="6c9b9-106">閱讀此主題以瞭解如何規劃雲端連接器 Edition PSTN 網站，以確保有效且經濟划算的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="6c9b9-107">本主題說明您需要瞭解的雲端連接器版本和通話路由，以便您可以規劃雲端連接器 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="6c9b9-108">PSTN 網站是雲端連接器裝置的組合，部署于相同位置，並與通用 PSTN 閘道相連。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="6c9b9-109">本主題著重于如何設定您的雲端連接器網站拓撲，以確保您的雲端連接器網站可以以最具成本效益且有效的方式，處理所有指派給網站的使用者的輸入和輸出路由。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="6c9b9-110">如需雲端連接器及 PSTN 網站優點的詳細資訊，請務必閱讀 Plan for [Business 雲端 Connector Edition](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="6c9b9-111">雲端連接器 PSTN 網站與通話路由</span><span class="sxs-lookup"><span data-stu-id="6c9b9-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="6c9b9-112">雲端連接器 PSTN 網站是建立的拓撲結構構造，以避免不必要的長途和全國間 tariffs，以及確保輸出緊急通話路由傳送至適當的主幹。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="6c9b9-113">為了確保通話成本效益和有效地路由傳送（包括電話緊急服務），您必須仔細規劃 PSTN 網站，以及如何將使用者指派給每個網站。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="6c9b9-114">在您規劃雲端連接器時，請務必與您的電信公司交談，以瞭解您的辦事處和使用者的位置，以及 PSTN 主幹從載體終止的位置。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="6c9b9-115">您需要與您的電信公司合作，判斷緊急通話的路由方式，然後使用該資訊來定義雲端連接器 PSTN 網站，並將使用者指派給適當的網站。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="6c9b9-116">例如，您應該確定已設定 PSTN 網站的資料中心終止的主幹，該為所有指派給該網站使用者的號碼，處理輸入和輸出路由。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="6c9b9-117">每個雲端連接器裝置都可以連接至多個 IP 閘道、IP PBXs，或會話邊界控制器 (SBCs) 。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="6c9b9-118">因為閘道和 PBXs 會連接到電訊主幹 (PRI 或 SIP 主幹) ，所以雲端連接器裝置會以邏輯方式連線至 PSTN 主幹，以進行撥入和撥出電話。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="6c9b9-119">透過 Cloud Connector 和內部部署 PSTN 連線，您可以從您當地的載體取得主幹和相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="6c9b9-120">如果您的公司是大型企業，您可能會有一個以上的電信公司，尤其是當您的公司跨越一個以上的城市、省或 country 時。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="6c9b9-121">因為您的電信公司擁有電話號碼，所以電信公司負責處理緊急通話。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="6c9b9-122">商務用 Skype Online 會平等對待網站中的所有雲端連接器裝置，並將在同一網站中以旋轉方式將來電路由傳送至雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="6c9b9-123">網站中的每個雲端接頭都會與同一組 PSTN 主幹進行跨線連接 (完全網狀) 。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="6c9b9-124">因為每一位使用者都與雲端連接器 PSTN 網站相關聯，所以來自該使用者的任何撥出電話 (一般或緊急) 都會指派給使用者關聯之 PSTN 網站中的其中一個雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="6c9b9-125">雲端連接器會以靜態呼叫路由傳送至其連接的 IP 閘道、IP PBXs、SBCs 或 direct PSTN 主幹。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="6c9b9-126">雲端連接器尚未能夠根據目的地 (，針對最低成本路由) 或根據原產地 (靜態或動態緊急通話) ，以動態路由傳送至主幹。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="6c9b9-127">輸入呼叫不是問題，因為通話只會來自與號碼相關聯的主幹。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="6c9b9-128">不過，撥出電話可以移至網站中的任何雲端連接器裝置 (，也可以擴充連接至雲端連接器裝置的 PSTN 主幹，) 這可能會導致不需要的長途通話。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="6c9b9-129">此外，如果在具有不同區號或運營商的資料中心之間延伸雲端連接器 PSTN 網站，緊急通話不會經歷。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="6c9b9-130">示例</span><span class="sxs-lookup"><span data-stu-id="6c9b9-130">An example</span></span>

<span data-ttu-id="6c9b9-131">下列範例顯示如何將主幹群組為 PSTN 網站，以及如何將使用者指派至網站。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="6c9b9-132">若為 Contoso 公司，請假設下列事項：</span><span class="sxs-lookup"><span data-stu-id="6c9b9-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="6c9b9-133">有四個使用者：</span><span class="sxs-lookup"><span data-stu-id="6c9b9-133">There are four users:</span></span> 
    
  - <span data-ttu-id="6c9b9-134">華盛頓州的使用者 A (美國) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="6c9b9-135">Bellevue WA 中的使用者 B (美國) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="6c9b9-136">Centralia WA 中的使用者 C (美國) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="6c9b9-137">位於上海或 (USA 的使用者 D) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="6c9b9-138">電信公司 A 在下列專案中提供電話號碼和主幹：</span><span class="sxs-lookup"><span data-stu-id="6c9b9-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="6c9b9-139">Redmond (區功能變數代碼 425) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="6c9b9-140">Bellevue (地區碼 425) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="6c9b9-141">Centralia (地區碼 360) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="6c9b9-142">電信公司 B 在下列各項中提供電話號碼和主幹：</span><span class="sxs-lookup"><span data-stu-id="6c9b9-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="6c9b9-143">上海 (區域碼 503) </span><span class="sxs-lookup"><span data-stu-id="6c9b9-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="6c9b9-144">因為 Redmond (資料中心的使用者 A) 和使用者 B 在 Bellevue 中 (資料中心 B) 彼此相鄰，且在相同地區碼 (425) ，所以電信公司 A 應該能夠在 Bellevue 中主幹的使用者 A 進行緊急通話。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="6c9b9-145">因此，使用者 A 和 B，以及 Bellevue 和 Redmond 的雲端連接器主幹可能位於同一個雲端連接器 PSTN 網站，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="6c9b9-146">一個辦公室中的使用者緊急通話可以路由傳送到另一個辦公室中的主幹。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="6c9b9-147">不過，您應該檢查您的電信公司是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-147">You should, however, check with your carrier that this will work.</span></span>
  
![如何設定 PSTN 網站](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="6c9b9-149">請同時考慮下列範例：</span><span class="sxs-lookup"><span data-stu-id="6c9b9-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="6c9b9-150">Centralia 中的使用者 C （由電信公司 A 提供）是兩個小時的磁片磁碟機，在不同的區號中 (360) ，來自其他電信公司 A Bellevue 和 Redmond 425 區功能變數代碼中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="6c9b9-151">因此，即使來電來自載波 A，Centralia 區號360中的電信公司的呼叫路由軟體可能會拒絕來自 Bellevue 區功能變數代碼425中使用者 B 的傳入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="6c9b9-152">在此情況下，電信公司請務必確認 Centralia PSTN 網站中的雲端連接器和其相關聯的主幹可以跨距離和地區碼處理呼叫。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="6c9b9-153">中的使用者 D 使用由載體 B 所提供的號碼和主幹，因此，載體 B 不太可能會從電信公司 A 所擁有的電話號碼進行緊急通話。因此，使用者 D 和主幹中的雲端連接器裝置和關聯的必須位於不同的 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="6c9b9-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
