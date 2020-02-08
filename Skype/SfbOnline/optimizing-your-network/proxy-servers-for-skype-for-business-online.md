---
title: Teams 或商務用 Skype Online 的 Proxy 伺服器
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
description: 本文提供在商務用 Skype 中使用 proxy 伺服器的相關資訊。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863746"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="b2576-103">商務用 Skype Online 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="b2576-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="b2576-104">本文提供有關在商務用 Skype 中使用 proxy 伺服器的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b2576-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="b2576-105">建議您不要使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="b2576-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="b2576-106">如果是來自 proxy 的商務用 Skype 流量，Microsoft 建議您回避 proxy。</span><span class="sxs-lookup"><span data-stu-id="b2576-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="b2576-107">Proxy 不會讓商務用 Skype 更加安全，因為通訊已加密。</span><span class="sxs-lookup"><span data-stu-id="b2576-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="b2576-108">而且擁有 proxy 可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="b2576-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="b2576-109">效能相關問題可透過延遲與資料包遺失來引進環境。</span><span class="sxs-lookup"><span data-stu-id="b2576-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="b2576-110">這類問題將導致在這些團隊或商務用 Skype 案例中使用音訊和影片的負面體驗，因為即時資料流非常重要。</span><span class="sxs-lookup"><span data-stu-id="b2576-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="b2576-111">如果您需要使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="b2576-111">If you need to use a proxy server</span></span>

<span data-ttu-id="b2576-112">有些組織沒有任何選項可讓商務用 Skype 流量略過 proxy。</span><span class="sxs-lookup"><span data-stu-id="b2576-112">Some organizations have no option to bypass a proxy for Skype for Business traffic.</span></span> <span data-ttu-id="b2576-113">如果是這種情況，上述問題必須牢記在前面。</span><span class="sxs-lookup"><span data-stu-id="b2576-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="b2576-114">Microsoft 也強烈建議：</span><span class="sxs-lookup"><span data-stu-id="b2576-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="b2576-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="b2576-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="b2576-116">使用直接的以 UDP 為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="b2576-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="b2576-117">允許 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="b2576-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="b2576-118">遵循我們的網路指導方針中的其他建議：</span><span class="sxs-lookup"><span data-stu-id="b2576-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="b2576-119">商務用 Skype Online 中的媒體質量和網路連線效能</span><span class="sxs-lookup"><span data-stu-id="b2576-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="b2576-120">針對商務用 Skype Online 優化您的網路</span><span class="sxs-lookup"><span data-stu-id="b2576-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="b2576-121">遵循此指導方針應該將潛在問題降至最低。</span><span class="sxs-lookup"><span data-stu-id="b2576-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b2576-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2576-122">Related topics</span></span>

[<span data-ttu-id="b2576-123">針對商務用 Skype Online 優化您的網路</span><span class="sxs-lookup"><span data-stu-id="b2576-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 