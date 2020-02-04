---
title: 新增前端集區 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 指定您要建立的前端池的完整功能變數名稱（FQDN）。 發佈包含 [前端] 池的拓朴之後，您就無法變更該池的 FQDN。 如果您需要重新命名池，您必須先刪除該池，然後使用新的 FQDN 新增新的池中。
ms.openlocfilehash: 0d05455a1b57394eaf0b6b11c70d3a6e9d1f84ae
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689322"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="c7829-105">新增前端集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="c7829-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="c7829-106">指定您要建立的前端池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c7829-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="c7829-107">發佈包含 [前端] 池的拓朴之後，您就無法變更該池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c7829-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="c7829-108">如果您需要重新命名池，您必須先刪除該池，然後使用新的 FQDN 新增新的池中。</span><span class="sxs-lookup"><span data-stu-id="c7829-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="c7829-109">如果您打算在將來實施前端池，請選取 [**多個電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="c7829-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="c7829-110">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c7829-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="c7829-111">當您準備好要在池中新增更多電腦之後，您必須再次執行拓撲建立器，以定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的前端池成員。</span><span class="sxs-lookup"><span data-stu-id="c7829-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c7829-112">您也必須針對 pool、Domain Name System （DNS）負載平衡或硬體負載平衡器，將新的池成員新增至適當的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="c7829-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="c7829-113">在許多情況下，您可以同時進行兩個負載平衡系統。</span><span class="sxs-lookup"><span data-stu-id="c7829-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="c7829-114">請確定您要將新的成員伺服器新增到兩者中。</span><span class="sxs-lookup"><span data-stu-id="c7829-114">Be sure that you are adding the new member server to both.</span></span> 
  

