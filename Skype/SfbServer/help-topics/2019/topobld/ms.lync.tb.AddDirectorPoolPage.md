---
title: 新增 Director 集區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定義 Director 集區 FQDN，請選取要包含在負載平衡集區中的兩個或多個 Director 或單一電腦集區的多部電腦集區。 您也必須輸入要用來連接 Director 集區的完整功能變數名稱 (FQDN) 或單一 Director 的 FQDN。 針對 Director 電腦的集區，這會是網域名稱系統 (DNS) 專案，以供硬體負載平衡器的虛擬 IP 或 DNS 負載平衡的共用 DNS 專案使用。
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807753"
---
# <a name="add-director-pool"></a><span data-ttu-id="ef117-105">新增 Director 集區</span><span class="sxs-lookup"><span data-stu-id="ef117-105">Add Director Pool</span></span>
 
<span data-ttu-id="ef117-106">若要 **定義 Director 集區 FQDN**，請選取要包含在負載平衡集區中的兩個或多個 Director 或 **單一電腦集** 區的 **多部電腦集** 區。</span><span class="sxs-lookup"><span data-stu-id="ef117-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="ef117-107">您也必須輸入要用來連接 Director 集區的完整功能變數名稱 (FQDN) 或單一 Director 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef117-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="ef117-108">針對 Director 電腦的集區，這會是網域名稱系統 (DNS) 專案，以供硬體負載平衡器的虛擬 IP 或 DNS 負載平衡的共用 DNS 專案使用。</span><span class="sxs-lookup"><span data-stu-id="ef117-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="ef117-109">如果您打算未來實作 Director 集區，請選取 [多部電腦集區]。</span><span class="sxs-lookup"><span data-stu-id="ef117-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="ef117-110">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef117-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="ef117-111">當您準備好將更多電腦新增至集區之後，您必須再次執行拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導設定新的 Director 集區成員。</span><span class="sxs-lookup"><span data-stu-id="ef117-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="ef117-112">您也必須新增集區成員至集區的適當負載平衡器、網域名稱系統 (DNS) 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="ef117-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="ef117-113">在許多情況下，您會同時具有兩種負載平衡系統。</span><span class="sxs-lookup"><span data-stu-id="ef117-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="ef117-114">請務必將新成員伺服器同時新增到這兩種系統。</span><span class="sxs-lookup"><span data-stu-id="ef117-114">Be sure that you are adding the new member server to both.</span></span> 
  

