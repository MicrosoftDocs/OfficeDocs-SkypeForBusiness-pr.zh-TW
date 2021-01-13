---
title: 新增前端集區 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 指定您正在建立之前端集區的完整網域名稱 (FQDN)。在發行包含前端集區的拓撲之後，便無法變更集區的 FQDN。如果需要將集區重新命名，必須刪除集區，再用新的 FQDN 新增集區。
ms.openlocfilehash: 7b0b14ab9b8cb450a80872cedf61e6f24da91dc2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811653"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="077ca-105">新增前端集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="077ca-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="077ca-p102">指定您正在建立之前端集區的完整網域名稱 (FQDN)。在發行包含前端集區的拓撲之後，便無法變更集區的 FQDN。如果需要將集區重新命名，必須刪除集區，再用新的 FQDN 新增集區。</span><span class="sxs-lookup"><span data-stu-id="077ca-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="077ca-109">如果您打算未來實作前端集區，請選取 **[多部電腦集區]**。</span><span class="sxs-lookup"><span data-stu-id="077ca-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="077ca-110">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="077ca-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="077ca-111">當您準備好將更多電腦新增至集區之後，您必須再次執行拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的前端集區成員。</span><span class="sxs-lookup"><span data-stu-id="077ca-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="077ca-112">您也必須新增集區成員至集區的適當負載平衡器、網域名稱系統 (DNS) 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="077ca-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="077ca-113">在許多情況下，您會同時具有兩種負載平衡系統。</span><span class="sxs-lookup"><span data-stu-id="077ca-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="077ca-114">請務必將新成員伺服器同時新增到這兩種系統。</span><span class="sxs-lookup"><span data-stu-id="077ca-114">Be sure that you are adding the new member server to both.</span></span> 
  

