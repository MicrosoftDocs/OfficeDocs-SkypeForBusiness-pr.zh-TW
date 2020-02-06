---
title: 在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 針對使用 SIP 中繼提供者的 E9-1 1 部署，在商務用 Skype Server Enterprise Voice 中規劃 SIP 中繼拓撲。
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803073"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="b0400-103">在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="b0400-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="b0400-104">針對使用 SIP 中繼提供者的 E9-1 1 部署，在商務用 Skype Server Enterprise Voice 中規劃 SIP 中繼拓撲。</span><span class="sxs-lookup"><span data-stu-id="b0400-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b0400-105">商務用 Skype 伺服器使用 SIP trunks，將緊急呼叫連線至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="b0400-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="b0400-106">您可以在一個中央網站、多個中央網站或每個分支網站上設定 E9-1-1 的緊急服務 SIP trunks。</span><span class="sxs-lookup"><span data-stu-id="b0400-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="b0400-107">不過，如果呼叫者的網站與託管緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則在斷開連接的網站上由使用者所撥的通話將需要使用者語音原則中的特殊電話使用記錄，將呼叫路由至ECRC 透過本機的公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="b0400-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b0400-108">如果通話許可控制併發通話限制生效，就是如此。</span><span class="sxs-lookup"><span data-stu-id="b0400-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="b0400-109">在商務用 Skype Server 環境中，有兩種方式可以實施 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="b0400-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="b0400-110">使用多宿主的出局轉送伺服器，使用其向外公開路由介面與 SIP 中繼提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="b0400-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="b0400-111">使用內部部署會話邊界控制器（SBC），在中繼伺服器與 SIP 中繼提供者的服務之間提供安全的 demarcation 點。</span><span class="sxs-lookup"><span data-stu-id="b0400-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="b0400-112">如果您選擇後一個方法，請確定您所選擇的 SBC 與模型已獲認證，並且支援將目前狀態資訊資料格式位置物件（PIDF-LO）位置資料傳送成其 SIP 邀請的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0400-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="b0400-113">否則，來電將會在緊急服務服務提供者去除其位置資訊時收到。</span><span class="sxs-lookup"><span data-stu-id="b0400-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="b0400-114">如需有關驗證的 SBCs 的詳細資料，請參閱「適用[于 Microsoft Lync 的基礎結構合格](https://go.microsoft.com/fwlink/p/?LinkId=248425)」和「[商務用 Skype 的電話架構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」。</span><span class="sxs-lookup"><span data-stu-id="b0400-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="b0400-115">E9-1-1 服務提供者會提供一組半形的存取權，以實現冗余。</span><span class="sxs-lookup"><span data-stu-id="b0400-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="b0400-116">您需要針對中繼伺服器拓撲和呼叫路由設定進行數個決策。</span><span class="sxs-lookup"><span data-stu-id="b0400-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="b0400-117">您會將 SBCs 視為同等對等，並使用迴圈式路由來進行呼叫，或是將一個 SBC 指派為主要的，另一個是副？</span><span class="sxs-lookup"><span data-stu-id="b0400-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="b0400-118">如需在商務用 Skype Server 中部署 SIP 幹線的詳細資料，請參閱[商務用 Skype 伺服器中的 sip 中繼](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="b0400-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="b0400-119">下列問題將協助您決定如何部署 E9 的 SIP trunks-1-1。</span><span class="sxs-lookup"><span data-stu-id="b0400-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="b0400-120">**您是否應該透過專用租使用者或共用的網際網路連線來部署 SIP 幹線？**</span><span class="sxs-lookup"><span data-stu-id="b0400-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="b0400-121">緊急通話永遠都是重要的。</span><span class="sxs-lookup"><span data-stu-id="b0400-121">It is important that emergency calls always connect.</span></span> <span data-ttu-id="b0400-122">專用線路提供的連線功能不會被網路上的其他流量搶佔，並可讓您實現服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="b0400-122">A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS).</span></span> <span data-ttu-id="b0400-123">請記住，如果您是透過公用網際網路連線到緊急服務服務提供者，而且您需要保證緊急通話的機密性，則需要進行 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="b0400-123">Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="b0400-124">**您的 E9-1-1 部署是否專為災難耐受性而設計？**</span><span class="sxs-lookup"><span data-stu-id="b0400-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="b0400-125">因為這是緊急解決方案，所以復原非常重要。</span><span class="sxs-lookup"><span data-stu-id="b0400-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="b0400-126">在災難容錯位置部署主要和次要轉送伺服器和 SIP trunks。</span><span class="sxs-lookup"><span data-stu-id="b0400-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="b0400-127">建議您部署最接近支援的使用者的主要轉送伺服器，並透過次要轉送伺服器（位於不同的地理位置）路由容錯移轉呼叫。</span><span class="sxs-lookup"><span data-stu-id="b0400-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="b0400-128">**您是否應該針對每個分支機搆部署個別的 SIP 幹線？**</span><span class="sxs-lookup"><span data-stu-id="b0400-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="b0400-129">商務用 Skype 伺服器提供幾項策略，可處理分支辦公室中的語音復原，包括：擁有彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將呼叫推送到本機閘道。</span><span class="sxs-lookup"><span data-stu-id="b0400-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="b0400-130">如需詳細資訊，請參閱[商務用 Skype 伺服器中的 SIP 中繼](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="b0400-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="b0400-131">**已啟用呼叫許可控制（CAC）嗎？**</span><span class="sxs-lookup"><span data-stu-id="b0400-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="b0400-132">商務用 Skype 伺服器不會處理緊急呼叫（與一般通話不同）。</span><span class="sxs-lookup"><span data-stu-id="b0400-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="b0400-133">基於這個原因，頻寬管理或呼叫許可控制（CAC）會對 E9-1-1 設定造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="b0400-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="b0400-134">如果啟用了 CAC，緊急通話會遭到封鎖，或路由到本機 PSTN 閘道，且在路由緊急通話的連結上超過設定的限制。</span><span class="sxs-lookup"><span data-stu-id="b0400-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="b0400-135">如本主題前面所示，此類呼叫將沒有位置資料，必須手動路由至 ECRC。</span><span class="sxs-lookup"><span data-stu-id="b0400-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

