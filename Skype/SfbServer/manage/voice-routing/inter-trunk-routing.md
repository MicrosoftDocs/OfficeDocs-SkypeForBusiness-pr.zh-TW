---
title: 商務用 Skype Server 中的主幹間路由
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
description: '商務用 Skype 伺服器提供基本的會話管理，其支援主幹間路由。 '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814123"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="fc397-103">商務用 Skype Server 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="fc397-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="fc397-104">商務用 Skype 伺服器提供基本的會話管理，其支援主幹間路由。</span><span class="sxs-lookup"><span data-stu-id="fc397-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="fc397-105">這項功能可讓商務用 Skype Server 向下游電話語音系統提供呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="fc397-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="fc397-106">主幹間路由可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，使來自私營分公司 exchange (PBX) phone 的呼叫可以路由傳送至 PSTN，而且傳入 PSTN 通話可以路由傳送至 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="fc397-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="fc397-107">同樣地，商務用 Skype 伺服器也可以互連兩個或多個 IP-PBX 系統，這樣通話便可在不同 IP-PBX 系統的 PBX 電話間撥打及接收。</span><span class="sxs-lookup"><span data-stu-id="fc397-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="fc397-108">下圖說明在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity 的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc397-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN 閘道和 IP-PBX 之間的 Interconnectivity](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="fc397-110">下圖說明連接兩個 IP-PBX 系統之商務用 Skype Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc397-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![連接兩個 IP PGX 系統的商務用 Skype Server](../../media/two-ip-pbx-systems.jpg)

