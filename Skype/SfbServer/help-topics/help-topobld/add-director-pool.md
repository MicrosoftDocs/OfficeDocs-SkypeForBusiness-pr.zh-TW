---
title: 新增 Director 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: 若要定義控制器池 FQDN，請選取多個電腦池，其中包含負載平衡池中的兩個或多個控制器，或是單一電腦池。 您也必須輸入要用來連線到主管池或單一控制器 FQDN 的完整功能變數名稱（FQDN）。 對於控制器電腦池，這會是硬體負載平衡器之虛擬 IP 的網域名稱系統（DNS）專案，或是 DNS 負載平衡的共用 DNS 專案。
ms.openlocfilehash: 150975cedf09c19acac1afffab25f5becf053fe3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698568"
---
# <a name="add-director-pool"></a><span data-ttu-id="c83b8-105">新增 Director 集區</span><span class="sxs-lookup"><span data-stu-id="c83b8-105">Add Director Pool</span></span>
 
<span data-ttu-id="c83b8-106">若要**定義控制器池 FQDN**，請選取**多個電腦池**，其中包含負載平衡池中的兩個或多個控制器，或是**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="c83b8-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="c83b8-107">您也必須輸入要用來連線到主管池或單一控制器 FQDN 的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c83b8-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="c83b8-108">對於控制器電腦池，這會是硬體負載平衡器之虛擬 IP 的網域名稱系統（DNS）專案，或是 DNS 負載平衡的共用 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="c83b8-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="c83b8-109">如果您打算在將來實施控制器池，請選取 [**多個電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="c83b8-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="c83b8-110">即使某個池已定義為兩個以上的負載平衡電腦，您也可以建立單一電腦池，並為單一電腦建立一個池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c83b8-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="c83b8-111">當您準備好要稍後再新增更多電腦至池中時，您必須再次執行拓撲建立器，以定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的控制器池成員。</span><span class="sxs-lookup"><span data-stu-id="c83b8-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c83b8-112">您也必須將新的池成員新增到該池的適當負載平衡器、[網域名稱系統（DNS）負載平衡] 或 [硬體負載平衡器]。</span><span class="sxs-lookup"><span data-stu-id="c83b8-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="c83b8-113">在許多情況下，系統會同時進行兩個負載平衡系統。</span><span class="sxs-lookup"><span data-stu-id="c83b8-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="c83b8-114">請確定您要將新的成員伺服器新增到兩者中。</span><span class="sxs-lookup"><span data-stu-id="c83b8-114">Be sure that you are adding the new member server to both.</span></span> 
  

