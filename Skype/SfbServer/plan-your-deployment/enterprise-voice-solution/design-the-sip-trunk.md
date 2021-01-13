---
title: 在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 在商務用 Skype Server Enterprise Voice 中，規劃使用 SIP 主幹提供者的 E9-1-1 部署的 SIP 主幹拓撲。
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825793"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="a4873-103">在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="a4873-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="a4873-104">在商務用 Skype Server Enterprise Voice 中，規劃使用 SIP 主幹提供者的 E9-1-1 部署的 SIP 主幹拓撲。</span><span class="sxs-lookup"><span data-stu-id="a4873-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a4873-105">商務用 Skype Server 使用 SIP 主幹，將緊急通話連接至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="a4873-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="a4873-106">您可以在一個中央網台、多個中央網台或每個分支網站上設定 E9-1-1 的緊急服務 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="a4873-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="a4873-107">不過，如果來電者的網站與主控緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則使用者的語音原則中將需要特殊的電話使用方式記錄，以便透過本機公用交換電話網路 (PSTN) 閘道將通話路由傳送至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="a4873-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="a4873-108">如果通話許可控制並行通話限制有效，則有同樣的需求。</span><span class="sxs-lookup"><span data-stu-id="a4873-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="a4873-109">在商務用 Skype 伺服器環境中，有兩種方式可以執行 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="a4873-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="a4873-110">使用多宿主的轉送伺服器，利用其向外公開路由的介面與 SIP 主幹提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="a4873-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="a4873-111">使用內部部署會話邊界控制器 (SBC) ，以在轉送伺服器和 SIP 主幹提供者的服務之間提供安全的分割點。</span><span class="sxs-lookup"><span data-stu-id="a4873-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="a4873-112">如果您選擇後者，請確定您所選擇的 SBC 品牌與型號已取得認證，並且支援傳遞「目前狀態資訊資料格式位置物件」(PIDF-LO) 位置資料做為其 SIP INVITE 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a4873-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="a4873-113">否則電話將會送達去除其位置資訊的緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="a4873-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="a4873-114">如需認證 SBCs 的詳細資訊，請參閱「   [Microsoft Lync 的基礎結構合格](https://go.microsoft.com/fwlink/p/?LinkId=248425) 」和「 [商務用 Skype 的電話語音基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」。</span><span class="sxs-lookup"><span data-stu-id="a4873-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="a4873-115">E9-1-1 服務提供者為您提供一組 SBC 的存取做為後備之用。</span><span class="sxs-lookup"><span data-stu-id="a4873-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="a4873-116">您需要對轉送伺服器拓撲及通話路由設定進行幾項決策。</span><span class="sxs-lookup"><span data-stu-id="a4873-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="a4873-117">您是要將兩台 SBC 視為對等，並對它們之間的通話使用循環配置資源路由；或是要將一個 SBC 指派為主要，而另一個指派為次要呢？</span><span class="sxs-lookup"><span data-stu-id="a4873-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="a4873-118">如需在商務用 Skype Server 中部署 SIP 主幹的詳細資訊，請參閱 [商務用 Skype server 中的 sip](sip-trunking.md)主幹。</span><span class="sxs-lookup"><span data-stu-id="a4873-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="a4873-119">為了協助決定如何部署 E9-1-1 的 SIP 主幹，您應該先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="a4873-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="a4873-120">**您應該在專用的租用網際網路連線上還是共用的網際網路連線上部署 SIP 主幹？**</span><span class="sxs-lookup"><span data-stu-id="a4873-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="a4873-p105">重點是一定要能夠接通緊急通話。專用線路可提供不被網路上其他流量佔用的連線，並讓您能夠實作服務品質 (QoS)。請記住，如果您透過公用網際網路連線至緊急服務服務提供者，而且需要保證緊急電話的機密性，則需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="a4873-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="a4873-124">**您的 E9-1-1 部署是針對嚴重損壞而設計嗎？**</span><span class="sxs-lookup"><span data-stu-id="a4873-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="a4873-125">因為這是緊急解決方案，所以恢復能力很重要。</span><span class="sxs-lookup"><span data-stu-id="a4873-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="a4873-126">在災難容錯位置部署主要和次要轉送伺服器和 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="a4873-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="a4873-127">最好是部署最接近其支援之使用者的主要轉送伺服器，並將容錯移轉呼叫路由傳送至位於不同地理位置) 中的次要轉送伺服器 (。</span><span class="sxs-lookup"><span data-stu-id="a4873-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="a4873-128">**您是否應該為每個分公司部署個別的 SIP 主幹？**</span><span class="sxs-lookup"><span data-stu-id="a4873-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="a4873-129">商務用 Skype 伺服器提供數個策略，用來處理分支辦公室中的語音彈性，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將呼叫推出至本機閘道。</span><span class="sxs-lookup"><span data-stu-id="a4873-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="a4873-130">如需詳細資訊，請參閱 [商務用 Skype Server 中的 SIP](sip-trunking.md)主幹。</span><span class="sxs-lookup"><span data-stu-id="a4873-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="a4873-131">**是否啟用通話許可控制 (CAC)?**</span><span class="sxs-lookup"><span data-stu-id="a4873-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="a4873-132">商務用 Skype 伺服器不會處理緊急通話，其方式不是一般通話。</span><span class="sxs-lookup"><span data-stu-id="a4873-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="a4873-133">因此，頻寬管理或通話許可控制 (CAC) 可能對 E9-1-1 組態有負面影響。</span><span class="sxs-lookup"><span data-stu-id="a4873-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="a4873-134">如果啟用 CAC，且在路由緊急通話的連結上的流量超出設定的限制，則緊急通話可能會被封鎖或路由至本機 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="a4873-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="a4873-135">如同本主題稍早所述，這類通話將會沒有位置資料，並且必須以手動方式路由至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="a4873-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

