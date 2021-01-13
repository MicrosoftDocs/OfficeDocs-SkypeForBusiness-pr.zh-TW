---
title: 商務用 Skype Server 中的多個主幹支援
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 功能支援閘道和轉送伺服器之間的多重關聯。 這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。 使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826223"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="d19ec-105">商務用 Skype Server 中的多個主幹支援</span><span class="sxs-lookup"><span data-stu-id="d19ec-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="d19ec-106">商務用 Skype Server 功能支援閘道和轉送伺服器之間的多重關聯。</span><span class="sxs-lookup"><span data-stu-id="d19ec-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="d19ec-107">這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。</span><span class="sxs-lookup"><span data-stu-id="d19ec-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="d19ec-108">使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。</span><span class="sxs-lookup"><span data-stu-id="d19ec-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="d19ec-109">若要在商務用 Skype Server 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="d19ec-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="d19ec-110">主幹包含下列關聯：轉送伺服器的完整功能變數名稱 (FQDN) 、轉送伺服器接聽埠、閘道 FQDN 及閘道聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="d19ec-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="d19ec-111">若要設定多個主幹，您可以在同一個閘道和轉送伺服器之間建立多個關聯。</span><span class="sxs-lookup"><span data-stu-id="d19ec-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="d19ec-112">這為企業語音基礎結構提供額外的復原能力，尤其適用于私人分公司 exchange (PBX) interoperational 案例。</span><span class="sxs-lookup"><span data-stu-id="d19ec-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="d19ec-113">定義主幹時，它必須與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="d19ec-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="d19ec-114">若要將主幹關聯至路由，您可以在拓撲產生器中定義主幹的簡易名稱。</span><span class="sxs-lookup"><span data-stu-id="d19ec-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="d19ec-115">在商務用 Skype Server 控制台中，這個簡易名稱是用來做為主幹名稱，主幹可以與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="d19ec-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="d19ec-116">簡易主幹名稱會當做商務用 Skype Server 管理命令介面的閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="d19ec-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="d19ec-117">管理員必須選取與轉送伺服器相關聯的預設主幹。</span><span class="sxs-lookup"><span data-stu-id="d19ec-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="d19ec-118">在 [拓撲產生器] 中，以滑鼠右鍵按一下關聯的轉送伺服器，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d19ec-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="d19ec-119">指定轉送伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="d19ec-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="d19ec-120">下圖說明為每個轉送伺服器和閘道定義的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="d19ec-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![多重主幹指派](../../media/multiple-trunk-assignments.jpg)
