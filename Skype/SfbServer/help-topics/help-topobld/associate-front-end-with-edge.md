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
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 每個前端集區都只能有一個相關聯的 Edge Server 或 Edge 集區。當您啟用網站的外部使用者存取時，您可以提供遠端使用者的支援。您也可以啟用同盟使用者的支援，包括特定公用立即訊息 (IM) 連線提供者 (例如 Windows Live) 的使用者支援，以及匿名使用者的支援。
ms.openlocfilehash: c68195607feea74f29048affaf12662b2682ad39
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684926"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="f8196-105">建立前端與 Edge 的關聯</span><span class="sxs-lookup"><span data-stu-id="f8196-105">Associate Front End With Edge</span></span>

<span data-ttu-id="f8196-p102">每個前端集區都只能有一個相關聯的 Edge Server 或 Edge 集區。當您啟用網站的外部使用者存取時，您可以提供遠端使用者的支援。您也可以啟用同盟使用者的支援，包括特定公用立即訊息 (IM) 連線提供者 (例如 Windows Live) 的使用者支援，以及匿名使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="f8196-p102">Each Front End pool can have only one Edge Server or Edge pool associated with it. When you enable external user access for a site, you can provide support for remote users. You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="f8196-p103">只要使用量不超出 Edge Server 的容量，一個網站的所有集區和多個中央網站的集區可以使用同一個 Edge Server。如需監控的詳細資訊 (包括規模調整在內)，請參閱規劃文件中的＜〈[Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)〉。如需設計拓撲來支援外部使用者存取的詳細資訊，請參閱部署文件中的〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="f8196-p103">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server. For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation. For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


