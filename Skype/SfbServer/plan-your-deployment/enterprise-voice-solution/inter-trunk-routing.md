---
title: 商務用 Skype 伺服器中的中繼站間路由
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 瞭解商務用 Skype Server 企業版語音如何支援站間路由。
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802853"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="8e283-103">商務用 Skype 伺服器中的中繼站間路由</span><span class="sxs-lookup"><span data-stu-id="8e283-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="8e283-104">瞭解商務用 Skype Server 企業版語音如何支援站間路由。</span><span class="sxs-lookup"><span data-stu-id="8e283-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="8e283-105">商務用 Skype 伺服器提供基本的會話管理，並支援 intertrunk 路由。</span><span class="sxs-lookup"><span data-stu-id="8e283-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="8e283-106">這可讓商務用 Skype Server 提供對下游電話系統的呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="8e283-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="8e283-107">Intertrunk 路由可以將 IP PBX 互連至公用的交換電話網絡（PSTN）閘道，讓來自私人分支 exchange （PBX）電話的呼叫可以路由到 PSTN，而且傳入 PSTN 呼叫可以路由到 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="8e283-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="8e283-108">同樣地，商務用 Skype 伺服器可以相互連接兩個或多個 IP PBX 系統，以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。</span><span class="sxs-lookup"><span data-stu-id="8e283-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="8e283-109">下圖說明在 PSTN 閘道與 IP PBX 之間提供 interconnectivity 的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8e283-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="8e283-111">下圖說明連接兩個 IP PBX 系統的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8e283-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![交互連接 IP-PAX 系統圖表的 Lync Server](../../media/inter_trunk02.jpg)
  

