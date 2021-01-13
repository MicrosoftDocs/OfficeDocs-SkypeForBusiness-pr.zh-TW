---
title: 商務用 Skype Server 中的 PSTN 連線元件
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 深入瞭解商務用 Skype Server 中的企業語音 SIP 主幹及 PSTN 閘道。
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813533"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="8744d-103">商務用 Skype Server 中的 PSTN 連線元件</span><span class="sxs-lookup"><span data-stu-id="8744d-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="8744d-104">深入瞭解商務用 Skype Server 中的企業語音 SIP 主幹及 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="8744d-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8744d-p101">企業等級的 VoIP 解決方案必須提供與公用交換電話網路 (PSTN) 之間的往來通話，且不犧牲任何服務品質 (QoS)。此外，使用者在撥號及接聽電話時應該不會意識到此基礎技術的存在。就使用者的觀點而言，Enterprise Voice 基礎結構與 PSTN 之間的通話應該就像是另一個 SIP 工作階段。</span><span class="sxs-lookup"><span data-stu-id="8744d-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="8744d-108">針對 PSTN 連線，您可以使用 PBX （也稱為直接 SIP 連結）或沒有 PBX) 部署 SIP 主幹或 PSTN 閘道 (。</span><span class="sxs-lookup"><span data-stu-id="8744d-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="8744d-109">SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="8744d-109">SIP Trunking</span></span>

<span data-ttu-id="8744d-p102">若不使用 PSTN 閘道，替代的方法是使用 SIP 主幹將企業語音解決方案連線至 PSTN。SIP 主幹可啟用下列案例：</span><span class="sxs-lookup"><span data-stu-id="8744d-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="8744d-112">公司防火牆內外的企業使用者可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。</span><span class="sxs-lookup"><span data-stu-id="8744d-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="8744d-113">任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。</span><span class="sxs-lookup"><span data-stu-id="8744d-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="8744d-114">使用這個部署解決方案必須有 SIP 主幹服務提供者。</span><span class="sxs-lookup"><span data-stu-id="8744d-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="8744d-115">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="8744d-115">PSTN gateways</span></span>

<span data-ttu-id="8744d-116">PSTN 閘道是協力廠商裝置，可轉譯企業語音基礎結構與 PSTN 或 PBX 之間的訊號和媒體。</span><span class="sxs-lookup"><span data-stu-id="8744d-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="8744d-117">PSTN 閘道與中繼伺服器搭配運作，以向企業語音用戶端呈現 PSTN 或 PBX 通話。</span><span class="sxs-lookup"><span data-stu-id="8744d-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="8744d-118">中繼伺服器也會向 PSTN 閘道呈現來自企業語音用戶端的通話，以路由傳送至 PSTN 或 PBX。</span><span class="sxs-lookup"><span data-stu-id="8744d-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="8744d-119">如需與 Microsoft 合作以提供與商務用 Skype Server 搭配使用之裝置的合作夥伴清單，請參閱  [Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="8744d-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="8744d-120">專用交換機</span><span class="sxs-lookup"><span data-stu-id="8744d-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="8744d-121">如果現有的語音基礎結構使用專用交換機 (PBX) ，您可以搭配 Enterprise Voice 使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="8744d-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="8744d-122">支援的企業語音 PBX 整合案例如下：</span><span class="sxs-lookup"><span data-stu-id="8744d-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="8744d-123">支援媒體旁路且含有中繼伺服器的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="8744d-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="8744d-124">需要獨立 PSTN 閘道的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="8744d-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="8744d-125">含有獨立 PSTN 閘道的分時多工 (TDM) PBX。</span><span class="sxs-lookup"><span data-stu-id="8744d-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8744d-126">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="8744d-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="8744d-127">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="8744d-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="8744d-128">只有在 [整合通訊開啟互通性計畫-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)所列的產品及版本支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="8744d-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="8744d-129">如需提供企業語音解決方案之合作夥伴的詳細資訊，請參閱 [Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="8744d-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="8744d-130">如需提供企業語音硬體解決方案（包括 PSTN 閘道）合作夥伴的詳細資訊，請參閱 [Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="8744d-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

