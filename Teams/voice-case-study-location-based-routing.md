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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785968"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="1e5c6-103">Contoso 案例研究：以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="1e5c6-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="1e5c6-104">位置式路由（LBR）是一項功能，可根據原則與使用者在撥打電話或接聽電話時的物理位置來限制付費略過。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="1e5c6-105">概觀</span><span class="sxs-lookup"><span data-stu-id="1e5c6-105">Overview</span></span>

<span data-ttu-id="1e5c6-106">Contoso 在國家/地區中有兩個辦事處，在這種情況下，不能避開公開的交換電話網絡（PSTN）提供者來減少長途通話成本。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="1e5c6-107">主要辦事處有一個由主要辦公室和第二個辦公室使用的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="1e5c6-108">每個辦公室都有自己的會話邊界控制器（SBC）連線至 PSTN 運營商。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="1e5c6-109">在此國家/地區，Contoso 已針對其商務用 Skype 部署設定 LBR。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="1e5c6-110">若要決定如何設定團隊的 LBR，請按 Contoso 讀取[方案位置，直接傳送路由](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="1e5c6-111">Contoso 已決定在撥打電話時，小組和商務用 Skype 會在相同的案例中進行，當您收到來電時，可以將 PSTN 來電轉接給小組使用者，以及您可以將另一個小組使用者轉接至 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="1e5c6-112">在商務用 Skype 中，LBR 是使用會話邊界控制器（SBC） SIP 幹線（連接至 PSTN 載波）進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="1e5c6-113">針對這個 SBC，Contoso 已檢查[經過驗證的 SBCs 清單](direct-routing-border-controllers.md)，並判斷已部署的 SBC 已認證以直接路由，但尚未針對媒體旁路進行認證。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="1e5c6-114">若要支援 LBR，直接路由必須設定至 SBC 現場，必須是局域網出口，而 SBC 必須針對媒體旁路進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="1e5c6-115">根據這項資訊，Contoso 決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="1e5c6-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="1e5c6-116">若要推遲團隊 LBR 的啟用，直到現有的 SBC 驗證了媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="1e5c6-117">Contoso 決定使用主要網站 SBC 來取得 Office 365 的直接路線。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="1e5c6-118">主網站 SBC 將是遠端網站的 proxy SBC。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="1e5c6-119">Contoso 使用以印度為基礎的協力廠商顧問，協助 LBR 設定與國家/地區的電話公司進行認證。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="1e5c6-120">若要支援從辦公室以外的使用者進行 PSTN 通話，提供給員工的公司頒發的行動電話。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="1e5c6-121">下列圖表顯示符合需要以位置為基礎路由之電話規章之國家/地區的部署之前和之後的情況：</span><span class="sxs-lookup"><span data-stu-id="1e5c6-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="1e5c6-122">**原始部署**</span><span class="sxs-lookup"><span data-stu-id="1e5c6-122">**Original deployment**</span></span>

![在狀態之前顯示的圖表](media/voice-case-study-5.png)

<span data-ttu-id="1e5c6-124">**使用直接路由進行部署**</span><span class="sxs-lookup"><span data-stu-id="1e5c6-124">**Deployment with Direct Routing**</span></span>

![在狀態之前顯示的圖表](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="1e5c6-126">Configuration</span><span class="sxs-lookup"><span data-stu-id="1e5c6-126">Configuration:</span></span> 

<span data-ttu-id="1e5c6-127">若要設定團隊中的網路元件，Contoso 按照[管理雲端語音功能之網路拓撲](manage-your-network-topology.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="1e5c6-128">Contoso 已完成下列步驟以設定以位置為基礎的路由：</span><span class="sxs-lookup"><span data-stu-id="1e5c6-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="1e5c6-129">定義網路區域-已定義一個網路區域。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="1e5c6-130">定義網路網站-定義了兩個網路網站。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="1e5c6-131">在區域中的每個辦公室位置都有一個網站。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="1e5c6-132">定義網路子網-辦公室位置中的每個樓層都有自己的有線和無線網路子網。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="1e5c6-133">此設定會針對 Contoso 產生20個子網。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="1e5c6-134">定義信任的 IP 位址-SBC 的外部點對點 IP 位址已新增至信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1e5c6-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

