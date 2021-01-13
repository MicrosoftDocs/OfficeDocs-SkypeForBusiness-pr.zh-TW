---
title: 新增 A/V MCU 集區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 中央網站裡，沒有配置音訊/視訊會議服務的所有 Enterprise Edition 前端伺服器，可以使用相同的獨立式 A/V 會議集區。針對每個 A/V 會議集區，您必須指定集區的完整網域名稱 (FQDN)，以及它是否將只有單一 A/V 會議伺服器，還是多個負載平衡的 A/V 會議伺服器。
ms.openlocfilehash: f0bfa6155320a23467545be19de290a3f1df19dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812023"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="bf452-104">新增 A/V MCU 集區</span><span class="sxs-lookup"><span data-stu-id="bf452-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="bf452-p102">中央網站裡，沒有配置音訊/視訊會議服務的所有 Enterprise Edition 前端伺服器，可以使用相同的獨立式 A/V 會議集區。針對每個 A/V 會議集區，您必須指定集區的完整網域名稱 (FQDN)，以及它是否將只有單一 A/V 會議伺服器，還是多個負載平衡的 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="bf452-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bf452-p103">您無法將單一伺服器的集區轉換成多伺服器的集區。如果您後來決定組織需要多伺服器的集區，必須刪除單一伺服器的集區，然後新增多伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="bf452-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="bf452-109">如果您打算未來實作 A/V 會議集區，請選取 [多部電腦集區]。</span><span class="sxs-lookup"><span data-stu-id="bf452-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="bf452-110">即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bf452-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="bf452-111">當您準備好將更多電腦新增至集區之後，您必須重新建立拓撲產生器，以定義新的集區成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導設定新的 A/V 會議集區成員。</span><span class="sxs-lookup"><span data-stu-id="bf452-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="bf452-112">A/V 會議伺服器集區是獨一無二的，它們不需要負載平衡器便能建立集區。</span><span class="sxs-lookup"><span data-stu-id="bf452-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="bf452-113">A/V 會議集區內部即具有負載平衡，不需要使用額外的硬體。</span><span class="sxs-lookup"><span data-stu-id="bf452-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

