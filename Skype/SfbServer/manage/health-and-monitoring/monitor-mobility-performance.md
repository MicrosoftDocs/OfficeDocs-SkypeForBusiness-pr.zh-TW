---
title: 在商務用 Skype Server 中監視行動性以取得效能
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：瞭解商務用 Skype Server 中的行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816833"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="9a8c2-103">在商務用 Skype Server 中監視行動性以取得效能</span><span class="sxs-lookup"><span data-stu-id="9a8c2-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="9a8c2-104">**摘要：** 深入瞭解行動服務 (Mcx) 和商務用 Skype Server 中的整合通訊網頁 API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="9a8c2-105">商務用 Skype Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 提高前端伺服器和前端集區的負載。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="9a8c2-106">即使在行動應用程式最小化時，也會維持伺服器連線的行動裝置，例如執行 Lync 2010 Mobile 的 Android 和 Nokia 裝置，以及執行 Lync 2013 Mobile 之 Android 和 Apple 裝置的負載，會比裝置在最小化行動電話應用程式時終止其連線的裝置的負載更大。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="9a8c2-107">隨著行動使用量的增加，您必須監視行動性效能，以決定何時需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="9a8c2-108">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="9a8c2-109">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="9a8c2-110">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="9a8c2-111">一些限制會影響行動效能：</span><span class="sxs-lookup"><span data-stu-id="9a8c2-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="9a8c2-112">可用記憶體</span><span class="sxs-lookup"><span data-stu-id="9a8c2-112">Available memory</span></span>
    
- <span data-ttu-id="9a8c2-113">要求佇列限制</span><span class="sxs-lookup"><span data-stu-id="9a8c2-113">Request queue limit</span></span>
    
- <span data-ttu-id="9a8c2-114">同時連接</span><span class="sxs-lookup"><span data-stu-id="9a8c2-114">Concurrent connections</span></span>
    
- <span data-ttu-id="9a8c2-115">IIS 佇列長度</span><span class="sxs-lookup"><span data-stu-id="9a8c2-115">IIS queue length</span></span>
    
<span data-ttu-id="9a8c2-116">可影響行動效能的伺服器上的其他限制，最多可有12個同時登入、驗證、會話續訂及終止。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="9a8c2-117">在大多數的部署中，不需要修改這些最大值。</span><span class="sxs-lookup"><span data-stu-id="9a8c2-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9a8c2-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="9a8c2-118">In this section</span></span>

- [<span data-ttu-id="9a8c2-119">監視商務用 Skype Server 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="9a8c2-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="9a8c2-120">在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況</span><span class="sxs-lookup"><span data-stu-id="9a8c2-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="9a8c2-121">在商務用 Skype Server 中設定高效能的行動服務</span><span class="sxs-lookup"><span data-stu-id="9a8c2-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="9a8c2-122">在商務用 Skype Server 中監控 IIS 要求的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="9a8c2-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="9a8c2-123">商務用 Skype Server 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="9a8c2-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

