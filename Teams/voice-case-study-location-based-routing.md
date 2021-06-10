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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785968"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="63f56-103">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="63f56-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="63f56-104">Location-Based路由 (LBR) 是一項功能，根據撥打或接收通話時，根據策略和使用者實際位置限制免付費。</span><span class="sxs-lookup"><span data-stu-id="63f56-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="63f56-105">概觀</span><span class="sxs-lookup"><span data-stu-id="63f56-105">Overview</span></span>

<span data-ttu-id="63f56-106">Contoso 在一個國家/地區有兩個辦公室，而忽略公用交換電話網絡 (PSTN) ，以降低長途通話成本。</span><span class="sxs-lookup"><span data-stu-id="63f56-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="63f56-107">主辦公室有由主要辦公室和第二個辦公室使用的網際網路連接。</span><span class="sxs-lookup"><span data-stu-id="63f56-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="63f56-108">每個辦公室都有自己的會話邊界控制器 (SBC) PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="63f56-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="63f56-109">在這個國家/地區，Contoso 已針對他們的部署商務用 Skype LBR。</span><span class="sxs-lookup"><span data-stu-id="63f56-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="63f56-110">若要決定如何設定 LBR Teams，Contoso 請閱讀直接路由Location-Based[路由方案](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="63f56-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="63f56-111">Contoso 決定 Teams 和 商務用 Skype 在何時可以撥打、何時可以接收、PSTN 通話可以轉接給 Teams 使用者，以及何時可以將另一個 Teams 使用者轉接到 PSTN 通話時，遵循相同的案例。</span><span class="sxs-lookup"><span data-stu-id="63f56-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="63f56-112">針對商務用 Skype，LBR 已使用會話邊界控制器 (SBC) SIP 主幹連接到 PSTN 電信電信公司。</span><span class="sxs-lookup"><span data-stu-id="63f56-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="63f56-113">針對此 SBC，Contoso 已審查認證 [SBC](direct-routing-border-controllers.md) 清單，並判定所部署的 SBC 已通過直接路由認證，但未通過媒體旁路認證。</span><span class="sxs-lookup"><span data-stu-id="63f56-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="63f56-114">若要支援 LBR，直接路由必須配置至 SBC 現場，需要有一個本地網際網路出口，而 SBC 必須針對媒體旁路進行配置。</span><span class="sxs-lookup"><span data-stu-id="63f56-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="63f56-115">根據這項資訊，Contoso 決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="63f56-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="63f56-116">若要延遲啟用 LBR Teams，直到現有 SBC 通過媒體旁路認證。</span><span class="sxs-lookup"><span data-stu-id="63f56-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="63f56-117">Contoso 決定使用主要網站 SBC 進行直接路由Office 365。</span><span class="sxs-lookup"><span data-stu-id="63f56-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="63f56-118">主網站 SBC 是遠端網站的 Proxy SBC。</span><span class="sxs-lookup"><span data-stu-id="63f56-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="63f56-119">Contoso 使用印度的協力廠商顧問，協助國內電話公司進行 LBR 組組認證。</span><span class="sxs-lookup"><span data-stu-id="63f56-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="63f56-120">為了支援公司外部使用者撥打 PSTN 電話，公司已發行行動電話給員工。</span><span class="sxs-lookup"><span data-stu-id="63f56-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="63f56-121">下列圖表顯示國家/地區部署之前和之後，其電話法規需要Location-Based路由：</span><span class="sxs-lookup"><span data-stu-id="63f56-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="63f56-122">**原始部署**</span><span class="sxs-lookup"><span data-stu-id="63f56-122">**Original deployment**</span></span>

![顯示狀態前圖表](media/voice-case-study-5.png)

<span data-ttu-id="63f56-124">**使用直接路由進行部署**</span><span class="sxs-lookup"><span data-stu-id="63f56-124">**Deployment with Direct Routing**</span></span>

![顯示狀態前圖表](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="63f56-126">配置：</span><span class="sxs-lookup"><span data-stu-id="63f56-126">Configuration:</span></span> 

<span data-ttu-id="63f56-127">若要在 Teams 中設定網路元件，Contoso 遵循管理雲端語音功能的網路拓撲[中的指示](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="63f56-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="63f56-128">Contoso 已完成下列設定路由Location-Based步驟：</span><span class="sxs-lookup"><span data-stu-id="63f56-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="63f56-129">定義網路區域 - 已定義一個網路區域。</span><span class="sxs-lookup"><span data-stu-id="63f56-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="63f56-130">定義網路網站 - 已定義兩個網路網站。</span><span class="sxs-lookup"><span data-stu-id="63f56-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="63f56-131">針對地區中每個辦公室位置的一個網站。</span><span class="sxs-lookup"><span data-stu-id="63f56-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="63f56-132">定義網路子網 - 辦公室位置內的每個樓層都有自己的有線和無線網路子網。</span><span class="sxs-lookup"><span data-stu-id="63f56-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="63f56-133">此組配置導致 Contoso 有 20 個子網。</span><span class="sxs-lookup"><span data-stu-id="63f56-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="63f56-134">定義信任的 IP 位址 - SBC 的外部 IP 位址已新加到信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="63f56-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

