---
title: 建立前端與 Edge 的關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。 當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。 您也可以啟用同盟使用者的支援，其可包含對特定公用立即訊息 (IM) 連線提供者 (（如 Windows Live) ）和匿名使用者支援等使用者的支援。
ms.openlocfilehash: cc804ed9a21b81ce0315664bcb1b3530e8087584
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217754"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="8bff3-105">建立前端與 Edge 的關聯</span><span class="sxs-lookup"><span data-stu-id="8bff3-105">Associate Front End With Edge</span></span>

<span data-ttu-id="8bff3-106">每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="8bff3-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="8bff3-107">當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。</span><span class="sxs-lookup"><span data-stu-id="8bff3-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="8bff3-108">您也可以啟用同盟使用者的支援，其可包含對特定公用立即訊息 (IM) 連線提供者 (（如 Windows Live) ）和匿名使用者支援等使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="8bff3-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="8bff3-109">如果使用不超過 Edge Server 的容量，則網站上的所有集區和多個中央網站的集區可以使用同一個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="8bff3-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="8bff3-110">如需監控的詳細資訊 (包括規模調整在內)，請參閱＜規劃＞文件中的[規劃外部使用者存取](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8bff3-110">For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="8bff3-111">如需設計拓撲來支援外部使用者存取的詳細資訊，請參閱＜部署＞文件中的[定義您的 Edge 拓撲](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8bff3-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


