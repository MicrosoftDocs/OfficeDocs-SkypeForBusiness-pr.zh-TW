---
title: 新增 Edge Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 若要將 Edge Server 或 Edge Server 集區併入拓撲設計，您必須指定要部署 Edge Server 或 Edge Server 集區之伺服器的完整功能變數名稱 (FQDN) 。 在發佈包含 Edge Server 或 Edge Server 集區的拓撲，並安裝商務用 Skype 伺服器之前，您必須完成部署外部使用者存取的所有必要條件。 如需這些必要條件的詳細資訊，請參閱部署檔中的在周邊網路中安裝伺服器的準備。
ms.openlocfilehash: fb5fc4f34531da9bae4585d5a6140fdfe5837735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803593"
---
# <a name="add-edge-server"></a><span data-ttu-id="61c0e-105">新增 Edge Server</span><span class="sxs-lookup"><span data-stu-id="61c0e-105">Add Edge Server</span></span>

<span data-ttu-id="61c0e-106">若要將 Edge Server 或 Edge Server 集區併入拓撲設計，您必須指定要部署 Edge Server 或 Edge Server 集區之伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="61c0e-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="61c0e-107">在發佈包含 Edge Server 或 Edge Server 集區的拓撲，並安裝商務用 Skype 伺服器之前，您必須完成部署外部使用者存取的所有必要條件。</span><span class="sxs-lookup"><span data-stu-id="61c0e-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="61c0e-108">如需這些必要條件的詳細資訊，請參閱部署檔中的在 [周邊網路中安裝伺服器的準備](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="61c0e-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61c0e-109">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="61c0e-109">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="61c0e-110">根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="61c0e-110">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="61c0e-111">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="61c0e-111">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="61c0e-112">您必須在要部署為 Edge Server 或 Edge Server 集區的網域名稱系統 (DNS) 尾碼（未加入網域的電腦）設定網域名稱系統。</span><span class="sxs-lookup"><span data-stu-id="61c0e-112">You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span>

> [!TIP]
> <span data-ttu-id="61c0e-113">如果您想要在未來實施 Edge Server 集區，請選取 [ **多部電腦集** 區]。</span><span class="sxs-lookup"><span data-stu-id="61c0e-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="61c0e-114">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="61c0e-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="61c0e-115">當您準備好將更多電腦新增至集區之後，您必須重新建立拓撲產生器，以定義新的集區成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導設定新的 Edge Server 集區成員。</span><span class="sxs-lookup"><span data-stu-id="61c0e-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="61c0e-116">您也必須新增集區成員至集區的適當負載平衡器、DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="61c0e-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="61c0e-117">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="61c0e-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="61c0e-118">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="61c0e-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="61c0e-119">確定您要將新的成員伺服器加入適當的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="61c0e-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span>

<span data-ttu-id="61c0e-120">您可以在部署初始拓撲時，或在部署初始拓撲之後，新增對外部使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="61c0e-120">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology.</span></span> <span data-ttu-id="61c0e-121">如需將 Edge Servers 或 Edge Server 集區新增至現有拓撲的詳細資訊，請參閱 Edge Server 部署檔中的 [定義 Edge 拓撲](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="61c0e-121">For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


