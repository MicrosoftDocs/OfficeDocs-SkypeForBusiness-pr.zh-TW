---
title: 在商務用 Skype Server 中規劃 PSTN 連通性
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 在商務用 Skype Server 的企業語音中規劃 PSTN 連線。
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802543"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="b36aa-103">在商務用 Skype Server 中規劃 PSTN 連通性</span><span class="sxs-lookup"><span data-stu-id="b36aa-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="b36aa-104">在商務用 Skype Server 的企業語音中規劃 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="b36aa-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="b36aa-105">企業級 VoIP 解決方案必須提供呼叫及從公開的交換電話網絡（PSTN）撥打電話，而不會拒絕服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="b36aa-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="b36aa-106">撥打及接聽來電的使用者不應該知道基礎技術：從使用者的角度來看，企業語音結構和 PSTN 之間的通話看起來就像是另一個電話撥。</span><span class="sxs-lookup"><span data-stu-id="b36aa-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="b36aa-107">商務用 Skype 伺服器可透過使用下列選項，提供可靠且可伸縮的 PSTN 連線：</span><span class="sxs-lookup"><span data-stu-id="b36aa-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="b36aa-108">**SIP trunks**至網際網路電話服務提供者（ITSP）</span><span class="sxs-lookup"><span data-stu-id="b36aa-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="b36aa-109">**直接將 SIP**連線至 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="b36aa-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="b36aa-110">**直接將 SIP**連線至 PBX</span><span class="sxs-lookup"><span data-stu-id="b36aa-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="b36aa-111">根據其大小、地理覆蓋及現有的語音基礎結構，企業可能會在不同的位置使用其中一個、兩個以上的選項。</span><span class="sxs-lookup"><span data-stu-id="b36aa-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="b36aa-112">如需這些選項的詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="b36aa-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b36aa-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="b36aa-113">In this section</span></span>

- [<span data-ttu-id="b36aa-114">商務用 Skype Server 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="b36aa-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="b36aa-115">商務用 Skype Server 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="b36aa-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="b36aa-116">商務用 Skype Server 中的 M:N 幹線</span><span class="sxs-lookup"><span data-stu-id="b36aa-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="b36aa-117">商務用 Skype Server 中的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="b36aa-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="b36aa-118">在商務用 Skype Server 中規劃出站語音路由</span><span class="sxs-lookup"><span data-stu-id="b36aa-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

