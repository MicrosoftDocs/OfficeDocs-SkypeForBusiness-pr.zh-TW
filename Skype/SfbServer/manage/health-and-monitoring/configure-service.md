---
title: 在商務用 Skype Server 中設定高效能的行動服務
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要：瞭解商務用 Skype Server 中的行動服務。
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817033"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="ccd32-103">在商務用 Skype Server 中設定高效能的行動服務</span><span class="sxs-lookup"><span data-stu-id="ccd32-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="ccd32-104">**摘要：** 深入瞭解商務用 Skype Server 中的行動服務。</span><span class="sxs-lookup"><span data-stu-id="ccd32-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ccd32-105">本主題只適用于商務用 Skype Server 行動服務 (Mcx) ，而且不會套用到「整合通訊 Web API (UCWA) （在 Lync Server 2013 的累計更新中傳遞）：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="ccd32-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="ccd32-106">當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時，行動性服務安裝程式會在前端伺服器上設定某些效能設定。</span><span class="sxs-lookup"><span data-stu-id="ccd32-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="ccd32-107">建議您使用 IIS 7.5 以用於行動性。</span><span class="sxs-lookup"><span data-stu-id="ccd32-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="ccd32-108">這些設定會影響並行使用者要求數目上限，以及行動性服務所允許的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="ccd32-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="ccd32-109">效能設定如下：</span><span class="sxs-lookup"><span data-stu-id="ccd32-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="ccd32-110">IIS 7.5 上的 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="ccd32-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="ccd32-111">**maxConcurrentThreadsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="ccd32-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="ccd32-112">**maxConcurrentRequestsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="ccd32-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="ccd32-113">ASP.NET 進程模型設定為僅) IIS 7.5 的自動設定 (。</span><span class="sxs-lookup"><span data-stu-id="ccd32-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="ccd32-114">HTTP.sys 佇列限制預設設定為 1000 () 。</span><span class="sxs-lookup"><span data-stu-id="ccd32-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

