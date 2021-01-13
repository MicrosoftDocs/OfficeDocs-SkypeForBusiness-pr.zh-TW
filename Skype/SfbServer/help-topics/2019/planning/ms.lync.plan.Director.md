---
title: 'Director (規劃工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Director 是一部執行商務用 Skype 伺服器通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。
ms.openlocfilehash: 0c76fb5290715bb394b4c84ffadad3a2e9dd74db
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801093"
---
# <a name="director-planning-tool"></a><span data-ttu-id="b5b28-103">Director (規劃工具) </span><span class="sxs-lookup"><span data-stu-id="b5b28-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="b5b28-104">Director 是一部執行商務用 Skype 伺服器通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5b28-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="b5b28-105">這個角色是選用的，您可以選擇在下列兩個案例中部署 Director：</span><span class="sxs-lookup"><span data-stu-id="b5b28-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="b5b28-106">如果您透過部署 Edge Server 啟用外部使用者存取，您也應該部署 Director。</span><span class="sxs-lookup"><span data-stu-id="b5b28-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="b5b28-107">在此案例中，Director 會驗證外部使用者，然後將流量傳遞給內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5b28-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="b5b28-108">當 Director 用於驗證外部使用者時，它會從執行這些使用者驗證的開銷中免除前端集區伺服器的執行。</span><span class="sxs-lookup"><span data-stu-id="b5b28-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="b5b28-109">它也有助於將內部前端集區與惡意流量（如拒絕服務攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="b5b28-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="b5b28-110">如果網路在這類攻擊中以不正確外部流量淹沒，這項流量會結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="b5b28-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="b5b28-111">如果您在中央網站部署多個前端集區，只要將 Director 新增至該網站，您就可以簡化驗證要求並改善效能。</span><span class="sxs-lookup"><span data-stu-id="b5b28-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="b5b28-112">在此案例中，所有要求都會先移至 Director，然後再將其路由傳送到正確的前端集區。</span><span class="sxs-lookup"><span data-stu-id="b5b28-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

