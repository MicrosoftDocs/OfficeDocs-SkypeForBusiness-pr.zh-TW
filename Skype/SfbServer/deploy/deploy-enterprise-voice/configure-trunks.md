---
title: 在商務用 Skype Server 中設定主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要：瞭解如何在商務用 Skype Server 中設定企業語音的轉送伺服器和對等間主幹。
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824953"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="122eb-103">在商務用 Skype Server 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="122eb-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="122eb-104">**摘要：** 瞭解如何在商務用 Skype Server 中設定企業語音的轉送伺服器和對等間主幹。</span><span class="sxs-lookup"><span data-stu-id="122eb-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="122eb-105">在企業語音部署中，您可以設定轉送伺服器與一或多個下列對等間的主幹，為組織中的 Enterprise Voice 用戶端和裝置提供公用交換電話網路 (PSTN) 連線能力：</span><span class="sxs-lookup"><span data-stu-id="122eb-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="122eb-106">網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線</span><span class="sxs-lookup"><span data-stu-id="122eb-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="122eb-107">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="122eb-107">PSTN gateway</span></span>
    
- <span data-ttu-id="122eb-108">專用交換機 (Private branch exchange，PBX)</span><span class="sxs-lookup"><span data-stu-id="122eb-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="122eb-109">如需詳細資訊，請參閱 [Plan FOR PSTN connectivity In 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="122eb-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="122eb-110">商務用 Skype Server 功能支援閘道和轉送伺服器之間的多重關聯。</span><span class="sxs-lookup"><span data-stu-id="122eb-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="122eb-111">這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。</span><span class="sxs-lookup"><span data-stu-id="122eb-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="122eb-112">使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。</span><span class="sxs-lookup"><span data-stu-id="122eb-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="122eb-113">若要在商務用 Skype Server 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="122eb-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="122eb-114">主幹包含下列關聯：轉送伺服器的完整功能變數名稱 (FQDN) 、轉送伺服器接聽埠、閘道 FQDN 及閘道聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="122eb-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="122eb-115">若要設定多個主幹，您可以在同一個閘道和轉送伺服器之間建立多個關聯。</span><span class="sxs-lookup"><span data-stu-id="122eb-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="122eb-116">這為企業語音基礎結構提供額外的復原能力，尤其適用于私人分公司 exchange (PBX) interoperational 案例。</span><span class="sxs-lookup"><span data-stu-id="122eb-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="122eb-117">定義主幹時，它必須與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="122eb-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="122eb-118">若要將主幹關聯至路由，您可以在拓撲產生器中定義主幹的簡易名稱。</span><span class="sxs-lookup"><span data-stu-id="122eb-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="122eb-119">在商務用 Skype Server 控制台中，這個簡易名稱是用來做為主幹名稱，主幹可以與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="122eb-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="122eb-120">簡易主幹名稱會當做商務用 Skype Server 管理命令介面的閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="122eb-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="122eb-121">管理員必須選取與轉送伺服器相關聯的預設主幹。</span><span class="sxs-lookup"><span data-stu-id="122eb-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="122eb-122">在 [拓撲產生器] 中，以滑鼠右鍵按一下關聯的轉送伺服器，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="122eb-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="122eb-123">指定轉送伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="122eb-123">Specify the default gateway for the Mediation Server.</span></span> 
  

