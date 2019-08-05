---
title: 主管 (規劃工具)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 控制器是執行商務用 Skype Server 2015 通訊軟體的伺服器, 可驗證使用者要求, 但不會家用任何使用者帳戶。
ms.openlocfilehash: a551e2568b814f1811ebc84a8d187c8554cc1542
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191098"
---
# <a name="director-planning-tool"></a><span data-ttu-id="403d8-103">主管 (規劃工具)</span><span class="sxs-lookup"><span data-stu-id="403d8-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="403d8-104">控制器是執行商務用 Skype Server 2015 通訊軟體的伺服器, 可驗證使用者要求, 但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="403d8-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="403d8-105">這個角色是選擇性的, 您可以選擇在下列兩種案例中部署控制器:</span><span class="sxs-lookup"><span data-stu-id="403d8-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="403d8-106">如果您透過部署邊緣伺服器來啟用外部使用者存取, 您也應該部署控制器。</span><span class="sxs-lookup"><span data-stu-id="403d8-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="403d8-107">在這種情況下, 控制器會驗證外部使用者, 然後將通信量傳送到內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="403d8-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="403d8-108">當使用 Director 驗證外部使用者時, 它會從執行這些使用者驗證的負荷, 來免除前端池伺服器。</span><span class="sxs-lookup"><span data-stu-id="403d8-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="403d8-109">它也可協助將內部前端池與惡意流量 (例如拒絕服務攻擊) 隔離。</span><span class="sxs-lookup"><span data-stu-id="403d8-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="403d8-110">如果網路充斥在這種攻擊中的無效外部通信量, 此流量將結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="403d8-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="403d8-111">如果您是在中央網站部署多個前端池, 您可以在該網站上新增 Director, 以簡化驗證要求並改善效能。</span><span class="sxs-lookup"><span data-stu-id="403d8-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="403d8-112">在這種情況下, 所有要求都會先移至 Director, 然後將它們路由到正確的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="403d8-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

