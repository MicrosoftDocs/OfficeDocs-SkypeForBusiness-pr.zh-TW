---
title: 在商務用 Skype Server 中規劃 PSTN 連線能力
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 在商務用 Skype Server 中規劃 Enterprise Voice 的 PSTN 連線能力。
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813563"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="0cd20-103">在商務用 Skype Server 中規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="0cd20-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="0cd20-104">在商務用 Skype Server 中規劃 Enterprise Voice 的 PSTN 連線能力。</span><span class="sxs-lookup"><span data-stu-id="0cd20-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0cd20-105">企業等級的 VoIP 解決方案必須提供與公用交換電話網路 (PSTN) 之間的往來通話，且不犧牲任何服務品質 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="0cd20-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="0cd20-106">撥打和接聽電話的使用者應該不會注意到基礎技術：從使用者的觀點來看，在企業語音基礎結構和 PSTN 之間的呼叫似乎只是另一次通話。</span><span class="sxs-lookup"><span data-stu-id="0cd20-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="0cd20-107">商務用 Skype 伺服器透過使用下列選項，提供可靠、可伸縮的 PSTN 連線能力：</span><span class="sxs-lookup"><span data-stu-id="0cd20-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="0cd20-108">網際網路電話語音服務提供者 (ITSP) 的 **SIP 主幹**</span><span class="sxs-lookup"><span data-stu-id="0cd20-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="0cd20-109">對 PSTN 閘道的 **直接 SIP 連線**</span><span class="sxs-lookup"><span data-stu-id="0cd20-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="0cd20-110">對 PBX 的 **直接 SIP 連線**</span><span class="sxs-lookup"><span data-stu-id="0cd20-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="0cd20-111">視企業的規模、地理環境與現有語音基礎結構之不同，企業在不同的位置可使用其中一或兩個選項，甚至三個都使用。</span><span class="sxs-lookup"><span data-stu-id="0cd20-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="0cd20-112">如需這些選項的詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="0cd20-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0cd20-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="0cd20-113">In this section</span></span>

- [<span data-ttu-id="0cd20-114">商務用 Skype Server 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="0cd20-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="0cd20-115">在商務用 Skype Server 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="0cd20-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="0cd20-116">在商務用 Skype Server 中 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="0cd20-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="0cd20-117">商務用 Skype Server 中的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="0cd20-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="0cd20-118">在商務用 Skype Server 中規劃撥出語音路由</span><span class="sxs-lookup"><span data-stu-id="0cd20-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

