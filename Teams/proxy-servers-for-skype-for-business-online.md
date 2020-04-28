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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有關在 Microsoft 團隊或商務用 Skype 中使用 proxy 伺服器的資訊。
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905675"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="82d90-103">Teams 或商務用 Skype Online 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="82d90-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="82d90-104">本文提供有關將 proxy 伺服器與團隊或商務用 Skype 結合使用的指導方針。</span><span class="sxs-lookup"><span data-stu-id="82d90-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="82d90-105">建議您不要使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="82d90-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="82d90-106">如果是來自 proxy 的小組或商務用 Skype 流量，Microsoft 建議您回避 proxy。</span><span class="sxs-lookup"><span data-stu-id="82d90-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="82d90-107">Proxy 不會讓小組或商務用 Skype 更加安全，因為通訊已經過加密。</span><span class="sxs-lookup"><span data-stu-id="82d90-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="82d90-108">而且擁有 proxy 可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="82d90-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="82d90-109">效能相關問題可透過延遲與資料包遺失來引進環境。</span><span class="sxs-lookup"><span data-stu-id="82d90-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="82d90-110">這類問題將導致在這些團隊或商務用 Skype 案例中使用音訊和影片的負面體驗，因為即時資料流非常重要。</span><span class="sxs-lookup"><span data-stu-id="82d90-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="82d90-111">如果您需要使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="82d90-111">If you need to use a proxy server</span></span>

<span data-ttu-id="82d90-112">有些組織沒有任何選項可讓小組或商務用 Skype 流量略過。</span><span class="sxs-lookup"><span data-stu-id="82d90-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="82d90-113">如果是這種情況，上述問題必須牢記在前面。</span><span class="sxs-lookup"><span data-stu-id="82d90-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="82d90-114">Microsoft 也強烈建議：</span><span class="sxs-lookup"><span data-stu-id="82d90-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="82d90-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="82d90-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="82d90-116">使用直接的以 UDP 為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="82d90-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="82d90-117">允許 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="82d90-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="82d90-118">遵循我們的網路指導方針中的其他建議：[針對團隊準備貴組織的網路](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="82d90-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="82d90-119">遵循此指導方針應該將潛在問題降至最低。</span><span class="sxs-lookup"><span data-stu-id="82d90-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="82d90-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="82d90-120">Related topics</span></span>

[<span data-ttu-id="82d90-121">Office 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="82d90-121">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="82d90-122">針對 Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="82d90-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
