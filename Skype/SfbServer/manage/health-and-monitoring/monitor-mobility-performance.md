---
title: 監視行動在商務用 Skype Server 中的效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：瞭解商務用 Skype Server 中的行動服務（Mcx）和整合通訊網頁 API （UCWA）。
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817832"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="70d0c-103">監視行動在商務用 Skype Server 中的效能</span><span class="sxs-lookup"><span data-stu-id="70d0c-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="70d0c-104">**摘要：** 瞭解商務用 Skype Server 中的行動服務（Mcx）和整合通訊網頁 API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="70d0c-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="70d0c-105">商務用 Skype Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）會增加前端伺服器和前端池的負載。</span><span class="sxs-lookup"><span data-stu-id="70d0c-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="70d0c-106">即使在行動應用程式已最小化（例如 Android 2010 和執行 Lync 2013 Mobile 的 Apple 裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置等），仍會維持伺服器連線的行動裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置所強加的負載比當行動應用程式最小化時，中斷與伺服器的連線。</span><span class="sxs-lookup"><span data-stu-id="70d0c-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="70d0c-107">隨著行動使用量的增加，您必須監視行動效能，以判斷何時需要增加您的容量。</span><span class="sxs-lookup"><span data-stu-id="70d0c-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="70d0c-108">MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="70d0c-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="70d0c-109">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="70d0c-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="70d0c-110">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="70d0c-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="70d0c-111">數個限制會影響行動效能：</span><span class="sxs-lookup"><span data-stu-id="70d0c-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="70d0c-112">可用記憶體</span><span class="sxs-lookup"><span data-stu-id="70d0c-112">Available memory</span></span>
    
- <span data-ttu-id="70d0c-113">要求佇列限制</span><span class="sxs-lookup"><span data-stu-id="70d0c-113">Request queue limit</span></span>
    
- <span data-ttu-id="70d0c-114">併發連接</span><span class="sxs-lookup"><span data-stu-id="70d0c-114">Concurrent connections</span></span>
    
- <span data-ttu-id="70d0c-115">IIS 佇列長度</span><span class="sxs-lookup"><span data-stu-id="70d0c-115">IIS queue length</span></span>
    
<span data-ttu-id="70d0c-116">可能影響行動效能之伺服器的其他限制，最多可有12個併發登入、驗證、會話重新啟用和終止。</span><span class="sxs-lookup"><span data-stu-id="70d0c-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="70d0c-117">對於大部分的部署而言，不需要修改這些最大的。</span><span class="sxs-lookup"><span data-stu-id="70d0c-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="70d0c-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="70d0c-118">In this section</span></span>

- [<span data-ttu-id="70d0c-119">監視商務用 Skype Server 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="70d0c-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="70d0c-120">在商務用 Skype Server 中監視行動服務與 UCWA 使用量</span><span class="sxs-lookup"><span data-stu-id="70d0c-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="70d0c-121">在商務用 Skype Server 中設定行動服務以取得高效能</span><span class="sxs-lookup"><span data-stu-id="70d0c-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="70d0c-122">在商務用 Skype Server 中監控 IIS 要求追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="70d0c-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="70d0c-123">商務用 Skype Server 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="70d0c-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

