---
title: 新增 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 若要在分支網站定義 Survivable Branch Appliance 的公用交換電話網路 (PSTN) 閘道，請指定下列各項：
ms.openlocfilehash: a911e94306999645b9f631f1e9b37d405bd1d155
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828603"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="66925-103">新增 Survivable Branch Appliance PSTN</span><span class="sxs-lookup"><span data-stu-id="66925-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="66925-104">若要在分支網站定義 Survivable Branch Appliance 的公用交換電話網路 (PSTN) 閘道，請指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="66925-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="66925-105">Survivable Branch Appliance 或 Survivable Branch 伺服器關聯之對等閘道的完整網域名稱 (FQDN) 或 IP 位址，以用於傳送撥入和撥出 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="66925-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66925-106">如果您是在定義 Survivable Branch Appliance，此為 Survivable Branch Appliance 內之中繼伺服器將會連線以進行 PSTN 連線功能的閘道。</span><span class="sxs-lookup"><span data-stu-id="66925-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="66925-p101">要用於工作階段初始通訊協定 (SIP) 訊息的聆聽連接埠。根據預設，在閘道、專用交換機 (PBX) 或工作階段界限控制器 (SBC) 上，連接埠為 5066 (針對傳輸控制通訊協定 (TCP)) 及 5067 (針對傳輸層安全性 (TLS))。在分支網站的 Survivable Branch Appliance，預設連接埠為 5081 (針對 TCP) 及 5082 (針對 TLS)。</span><span class="sxs-lookup"><span data-stu-id="66925-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="66925-p102">基於安全性考量，我們強烈建議您使用 TLS。如果您是在定義 Survivable Branch Appliance，請參閱您的 Survivable Branch Appliance 廠商文件，確認您的 Survivable Branch Appliance 支援 TLS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="66925-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66925-112">基於安全性考量，強烈建議您部署可以使用 TLS 的閘道。</span><span class="sxs-lookup"><span data-stu-id="66925-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66925-113">如果您想要新增 PSTN 閘道，您可以稍後再設定它，但在定義及設定好 PSTN 閘道之前，完整的功能將會受限。</span><span class="sxs-lookup"><span data-stu-id="66925-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

