---
title: 在商務用 Skype Server 中設定行動服務以取得高效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '摘要: 瞭解商務用 Skype 伺服器中的行動服務。'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193761"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="5782c-103">在商務用 Skype Server 中設定行動服務以取得高效能</span><span class="sxs-lookup"><span data-stu-id="5782c-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="5782c-104">**摘要:** 瞭解商務用 Skype 伺服器中的行動服務。</span><span class="sxs-lookup"><span data-stu-id="5782c-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5782c-105">本主題只適用于商務用 Skype Server 行動服務 (Mcx), 且不適用於在 Lync Server 2013 的累積更新中提供的統一通訊 Web API (UCWA): 2 月2013。</span><span class="sxs-lookup"><span data-stu-id="5782c-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="5782c-106">當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時, 行動服務安裝程式會在前端伺服器上設定一些效能設定。</span><span class="sxs-lookup"><span data-stu-id="5782c-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="5782c-107">我們建議您使用 IIS 7.5 進行行動。</span><span class="sxs-lookup"><span data-stu-id="5782c-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="5782c-108">這些設定會影響並行使用者要求的數目上限, 以及行動服務所允許的最大執行緒數。</span><span class="sxs-lookup"><span data-stu-id="5782c-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="5782c-109">以下是效能設定:</span><span class="sxs-lookup"><span data-stu-id="5782c-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="5782c-110">IIS 7.5 上的 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="5782c-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="5782c-111">**maxConcurrentThreadsPerCPU**已設定為零 (0)。</span><span class="sxs-lookup"><span data-stu-id="5782c-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="5782c-112">**maxConcurrentRequestsPerCPU**已設定為零 (0)。</span><span class="sxs-lookup"><span data-stu-id="5782c-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="5782c-113">ASP.NET 程式模型已設定為自動設定 (僅適用于 IIS 7.5)。</span><span class="sxs-lookup"><span data-stu-id="5782c-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="5782c-114">Http.sys 佇列限制設定為 1000 (依預設)。</span><span class="sxs-lookup"><span data-stu-id="5782c-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

