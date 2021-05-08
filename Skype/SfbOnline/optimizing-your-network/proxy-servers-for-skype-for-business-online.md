---
title: 適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有關在用戶端使用 proxy 伺服器商務用 Skype。
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240412"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="12385-103">適用于 商務用 Skype Online 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="12385-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="12385-104">本文提供有關在用戶端使用 proxy 伺服器商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="12385-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="12385-105">建議您不要使用 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="12385-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="12385-106">當涉及代理商務用 Skype流量時，Microsoft 建議忽略代理。</span><span class="sxs-lookup"><span data-stu-id="12385-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="12385-107">由於流量已加密商務用 Skype代理不會讓資料更安全。</span><span class="sxs-lookup"><span data-stu-id="12385-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="12385-108">而擁有 Proxy 可能會導致問題。</span><span class="sxs-lookup"><span data-stu-id="12385-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="12385-109">透過延遲和封包遺失，可能會將與績效相關的問題引入環境。</span><span class="sxs-lookup"><span data-stu-id="12385-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="12385-110">這類問題會導致音訊和視Teams或商務用 Skype等情況下的負面體驗，而即時資料流是不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="12385-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="12385-111">如果您需要使用 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="12385-111">If you need to use a proxy server</span></span>

<span data-ttu-id="12385-112">有些組織無法針對流量忽略 proxy商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="12385-112">Some organizations have no option to bypass a proxy for Skype for Business traffic.</span></span> <span data-ttu-id="12385-113">如果是這種情況，您必須記住上述問題。</span><span class="sxs-lookup"><span data-stu-id="12385-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="12385-114">Microsoft 也強烈建議您：</span><span class="sxs-lookup"><span data-stu-id="12385-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="12385-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="12385-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="12385-116">使用直接 UDP 路由</span><span class="sxs-lookup"><span data-stu-id="12385-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="12385-117">允許 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="12385-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="12385-118">遵循我們的網路指導方針中的其他建議：</span><span class="sxs-lookup"><span data-stu-id="12385-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="12385-119">線上媒體質量與網路連線商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="12385-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="12385-120">優化您的網路以商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="12385-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="12385-121">遵循此指引應能將潛在問題降到最低。</span><span class="sxs-lookup"><span data-stu-id="12385-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12385-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="12385-122">Related topics</span></span>

[<span data-ttu-id="12385-123">優化您的網路以商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="12385-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
