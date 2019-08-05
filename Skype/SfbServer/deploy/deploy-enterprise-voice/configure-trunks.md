---
title: 在商務用 Skype Server 中設定 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '摘要: 瞭解如何在商務用 Skype Server 的中繼伺服器與對等企業語音之間設定幹線。'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191359"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="fe1bb-103">在商務用 Skype Server 中設定 trunks</span><span class="sxs-lookup"><span data-stu-id="fe1bb-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="fe1bb-104">**摘要:** 瞭解如何在商務用 Skype Server 的中繼伺服器與對等企業語音之間設定幹線。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="fe1bb-105">在企業語音部署中, 您可以設定在中繼伺服器與一或多個下列對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線:</span><span class="sxs-lookup"><span data-stu-id="fe1bb-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="fe1bb-106">網際網路電話服務提供者 (ITSP) 的 SIP 中繼連線</span><span class="sxs-lookup"><span data-stu-id="fe1bb-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="fe1bb-107">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="fe1bb-107">PSTN gateway</span></span>
    
- <span data-ttu-id="fe1bb-108">私人分支 exchange (PBX)</span><span class="sxs-lookup"><span data-stu-id="fe1bb-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="fe1bb-109">如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃 PSTN](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)連線。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="fe1bb-110">商務用 Skype Server 功能支援閘道與中繼伺服器之間的多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="fe1bb-111">這些關聯是透過定義幹線來建立的, 這是中繼伺服器池與公用交換式電話網絡 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP PBX 之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="fe1bb-112">使用 [拓撲建立器], 將閘道與中繼伺服器 (也就是 trunks) 建立關聯。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="fe1bb-113">若要在商務用 Skype Server 中指派或移除主幹, 您必須先在拓撲產生器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="fe1bb-114">主幹包含下列關聯: 中繼伺服器的完整功能變數名稱 (FQDN)、中繼伺服器偵聽埠、閘道 FQDN, 以及閘道偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="fe1bb-115">若要設定多個 trunks, 您可以在同一個閘道與中繼伺服器之間建立多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="fe1bb-116">這可為企業語音結構提供額外的復原能力, 這在私人分支 exchange (PBX) interoperational 案例中特別有用。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="fe1bb-117">定義主幹時, 必須與路由建立關聯。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="fe1bb-118">若要將主幹與路線建立關聯, 您可以在 [拓撲建立器] 中定義主幹的簡單名稱。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="fe1bb-119">在商務用 Skype Server [控制台] 中, 此簡單名稱會用來做為主幹名稱, 其中 trunks 可以與路線建立關聯。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="fe1bb-120">簡單的主幹名稱是從商務用 Skype Server Management Shell 中作為閘道名稱使用。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="fe1bb-121">系統管理員必須選取與中繼伺服器相關聯的預設主幹。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="fe1bb-122">從拓撲建立器, 以滑鼠右鍵按一下關聯的中繼伺服器, 然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="fe1bb-123">指定中繼伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="fe1bb-123">Specify the default gateway for the Mediation Server.</span></span> 
  

