---
title: 定義常設聊天室 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 您可以使用 [定義新的持久聊天集區] 嚮導來建立新的 Persistent Chat Server 或 Persistent Chat Server 集區。 選取 [多部電腦集區] 或 [單一電腦集區]。 如果您選取單一電腦集區，後來需要多部電腦集區，則必須移除單一電腦集區，然後再定義多部電腦集區。
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818443"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="f2245-105">定義常設聊天室 FQDN</span><span class="sxs-lookup"><span data-stu-id="f2245-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="f2245-106">您可以使用 [ **定義新的持久聊天集** 區] 嚮導來建立新的 Persistent chat Server 或 Persistent chat server 集區。</span><span class="sxs-lookup"><span data-stu-id="f2245-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="f2245-107">選取 [ **多部電腦集** 區] 或 [ **單一電腦集** 區]。</span><span class="sxs-lookup"><span data-stu-id="f2245-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="f2245-108">如果您選取單一電腦集區，後來需要多部電腦集區，則必須移除單一電腦集區，然後再定義多部電腦集區。</span><span class="sxs-lookup"><span data-stu-id="f2245-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="f2245-109">您也必須定義 Persistent Chat Server 或 Persistent Chat Server 集區的 **集區 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="f2245-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="f2245-110">單一電腦集區的集區完整功能變數名稱 (FQDN) 必須與組成單一伺服器集區之電腦的 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="f2245-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="f2245-111">如果是多部電腦集區，FQDN 必須是您選擇用來代表此多部電腦集區的名稱，而且會由主機 A (和 AAAA （如果 IPv6) record）加以定義。</span><span class="sxs-lookup"><span data-stu-id="f2245-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2245-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f2245-112">See also</span></span>

[<span data-ttu-id="f2245-113">在商務用 Skype Server 2015 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="f2245-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="f2245-114">將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲</span><span class="sxs-lookup"><span data-stu-id="f2245-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
