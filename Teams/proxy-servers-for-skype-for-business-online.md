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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有關在 Microsoft Teams 或商務用 Skype 中使用 Proxy 伺服器的資訊。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117721"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="bbc13-103">適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bbc13-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="bbc13-104">本文提供使用 Proxy 伺服器與 Teams 或商務用 Skype 的指南。</span><span class="sxs-lookup"><span data-stu-id="bbc13-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="bbc13-105">建議您不要使用 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bbc13-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="bbc13-106">當涉及 Teams 或商務用 Skype 流量超過代理時，Microsoft 建議忽略代理。</span><span class="sxs-lookup"><span data-stu-id="bbc13-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="bbc13-107">由於流量已加密，因此代理不會讓 Teams 或商務用 Skype 更安全。</span><span class="sxs-lookup"><span data-stu-id="bbc13-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="bbc13-108">而擁有 Proxy 可能會導致問題。</span><span class="sxs-lookup"><span data-stu-id="bbc13-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="bbc13-109">透過延遲和封包遺失，可能會將與績效相關的問題引入環境。</span><span class="sxs-lookup"><span data-stu-id="bbc13-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="bbc13-110">這類問題會導致 Teams 或商務用 Skype 案例的負面體驗，例如音訊和視像，即時資料流不可或缺。</span><span class="sxs-lookup"><span data-stu-id="bbc13-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="bbc13-111">如果您需要使用 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bbc13-111">If you need to use a proxy server</span></span>

<span data-ttu-id="bbc13-112">有些組織無法選擇忽略 Teams 或商務用 Skype 流量的 Proxy。</span><span class="sxs-lookup"><span data-stu-id="bbc13-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="bbc13-113">如果是這種情況，您必須記住上述問題。</span><span class="sxs-lookup"><span data-stu-id="bbc13-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="bbc13-114">Microsoft 也強烈建議您：</span><span class="sxs-lookup"><span data-stu-id="bbc13-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="bbc13-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="bbc13-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="bbc13-116">使用直接 UDP 路由</span><span class="sxs-lookup"><span data-stu-id="bbc13-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="bbc13-117">允許 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="bbc13-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="bbc13-118">遵循我們的網路指導方針中的其他建議：準備貴組織的 [Teams 網路](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="bbc13-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="bbc13-119">遵循此指南應能將潛在問題降到最低。</span><span class="sxs-lookup"><span data-stu-id="bbc13-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bbc13-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="bbc13-120">Related topics</span></span>

[<span data-ttu-id="bbc13-121">Microsoft 365 和 Office 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="bbc13-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="bbc13-122">針對 Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="bbc13-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)