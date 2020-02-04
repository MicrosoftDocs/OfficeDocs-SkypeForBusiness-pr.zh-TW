---
title: 新增 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 若要為分支網站上的 Survivable 分支裝置定義公用交換電話網絡（PSTN）閘道，請指定以下專案：
ms.openlocfilehash: 133f109c1d076432cd628bccde9e3c49518500c2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689728"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="80107-103">新增 Survivable Branch Appliance PSTN</span><span class="sxs-lookup"><span data-stu-id="80107-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="80107-104">若要為分支網站上的 Survivable 分支裝置定義公用交換電話網絡（PSTN）閘道，請指定以下專案：</span><span class="sxs-lookup"><span data-stu-id="80107-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="80107-105">閘道對等的完整功能變數名稱（FQDN）或 IP 位址，Survivable 分支裝置或 Survivable 分支伺服器會與路由輸入和輸出 PSTN 通話相關聯。</span><span class="sxs-lookup"><span data-stu-id="80107-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80107-106">如果您是定義 Survivable 分支裝置，則這是 Survivable 分支裝置中的中繼伺服器將連接至 PSTN 連接的閘道。</span><span class="sxs-lookup"><span data-stu-id="80107-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="80107-p101">要用於工作階段初始通訊協定 (SIP) 訊息的聆聽連接埠。根據預設，在閘道、專用交換機 (PBX) 或工作階段界限控制器 (SBC) 上，連接埠為 5066 (針對傳輸控制通訊協定 (TCP)) 及 5067 (針對傳輸層安全性 (TLS))。在分支網站的 Survivable Branch Appliance，預設連接埠為 5081 (針對 TCP) 及 5082 (針對 TLS)。</span><span class="sxs-lookup"><span data-stu-id="80107-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="80107-110">基於安全考量，強烈建議您使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="80107-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="80107-111">如果您是定義 Survivable 分支裝置，請參閱 Survivable 分支裝置轉銷商檔，確認您的 Survivable 分支裝置支援 TLS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="80107-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80107-112">基於安全性考量，強烈建議您部署可以使用 TLS 的閘道。</span><span class="sxs-lookup"><span data-stu-id="80107-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80107-113">如果您想要新增 PSTN 閘道，您可以稍後再設定它，但在定義及設定好 PSTN 閘道之前，完整的功能將會受限。</span><span class="sxs-lookup"><span data-stu-id="80107-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

