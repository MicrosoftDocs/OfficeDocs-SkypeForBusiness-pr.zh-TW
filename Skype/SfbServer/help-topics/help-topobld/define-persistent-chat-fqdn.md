---
title: 定義常設聊天室 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 您可以使用 [定義新的持久性聊天池] 嚮導來建立新的持久聊天伺服器或持久聊天伺服器池。 請選取 [多部電腦集區] 或 [單一電腦集區]。 如果選取 [單一電腦集區] 並在稍後需要多部電腦集區，則必須移除單一電腦集區，再定義多部電腦集區。
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193762"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="c5823-105">定義常設聊天室 FQDN</span><span class="sxs-lookup"><span data-stu-id="c5823-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="c5823-106">您可以使用 [**定義新的持久性聊天池**] 嚮導來建立新的持久聊天伺服器或持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="c5823-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="c5823-107">請選取 [多部電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5823-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="c5823-108">如果選取 [單一電腦集區] 並在稍後需要多部電腦集區，則必須移除單一電腦集區，再定義多部電腦集區。</span><span class="sxs-lookup"><span data-stu-id="c5823-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="c5823-109">您也必須為持續聊天伺服器或持久聊天伺服器池定義一個**池 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="c5823-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="c5823-110">單一電腦集區的集區完整網域名稱 (FQDN) 必須與構成單一伺服器集區之電腦的 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="c5823-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="c5823-111">若是多部電腦集區，FQDN 必須是您選擇代表此多部電腦集區的名稱，並由主機 A (如果使用 IPv6，則為 AAAA) 記錄在 DNS 中定義。</span><span class="sxs-lookup"><span data-stu-id="c5823-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c5823-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5823-112">See also</span></span>

[<span data-ttu-id="c5823-113">在商務用 Skype Server 2015 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c5823-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="c5823-114">在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="c5823-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
