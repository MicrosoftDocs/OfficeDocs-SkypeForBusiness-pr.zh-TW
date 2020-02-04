---
title: 新增 Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 若要將 Edge Server 或 Edge Server 集區納入拓撲設計，您必須為要部署 Edge Server 或 Edge Server 集區的伺服器指定完整網域名稱 (FQDN)。 在發佈包括 Edge 伺服器或 Edge 伺服器池以及安裝商務用 Skype Server 的拓撲之前，您應該已完成部署外部使用者存取的所有先決條件。 如需這些必要條件的詳細資訊，請參閱部署文件中的〈Preparing for Installation of Servers in the Perimeter Network〉。
ms.openlocfilehash: 3433f5dac67d0e02fb8e8552e205092a51082cc6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698338"
---
# <a name="add-edge-server"></a><span data-ttu-id="cd331-105">新增 Edge Server</span><span class="sxs-lookup"><span data-stu-id="cd331-105">Add Edge Server</span></span>

<span data-ttu-id="cd331-106">若要將 Edge Server 或 Edge Server 集區納入拓撲設計，您必須為要部署 Edge Server 或 Edge Server 集區的伺服器指定完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="cd331-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="cd331-107">在發佈包括 Edge 伺服器或 Edge 伺服器池以及安裝商務用 Skype Server 的拓撲之前，您應該已完成部署外部使用者存取的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="cd331-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="cd331-108">如需這些必要條件的詳細資訊，請參閱部署文件中的〈[Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="cd331-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd331-p103">您指定的名稱必須與伺服器上設定的電腦名稱相同。根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。拓撲產生器會使用 FQDN，而非簡稱。您必須為即將部署為 Edge Server 或 Edge Server 集區 (但不加入網域) 的電腦，設定其名稱的網域名稱系統 (DNS) 尾碼。</span><span class="sxs-lookup"><span data-stu-id="cd331-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span>

> [!TIP]
> <span data-ttu-id="cd331-113">如果您打算未來實作 Edge Server 集區，則選取 [多部電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd331-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="cd331-114">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cd331-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="cd331-115">當您準備好要在池中新增更多電腦之後，您必須重新建立拓撲建立器，才能定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的 Edge 伺服器池成員。</span><span class="sxs-lookup"><span data-stu-id="cd331-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="cd331-116">您也必須新增集區成員至集區的適當負載平衡器、DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="cd331-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="cd331-117">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="cd331-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="cd331-118">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="cd331-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="cd331-119">請務必將新成員伺服器新增到適當的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="cd331-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span>

<span data-ttu-id="cd331-p105">您可以在部署初始拓撲時，或部署初始拓撲之後，新增外部使用者存取的支援。如需新增 Edge Server 或 Edge Server 集區至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="cd331-p105">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology. For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


