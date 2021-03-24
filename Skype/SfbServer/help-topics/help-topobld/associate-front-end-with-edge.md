---
title: 建立前端與 Edge 的關聯
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
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。 當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。 您也可以啟用同盟使用者的支援，其可包含對特定公用立即訊息 (IM) 連線提供者 (（如 Windows Live) ）和匿名使用者支援等使用者的支援。
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103219"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="0d471-105">建立前端與 Edge 的關聯</span><span class="sxs-lookup"><span data-stu-id="0d471-105">Associate Front End With Edge</span></span>

<span data-ttu-id="0d471-106">每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="0d471-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="0d471-107">當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。</span><span class="sxs-lookup"><span data-stu-id="0d471-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="0d471-108">您也可以啟用同盟使用者的支援，其可包含對特定公用立即訊息 (IM) 連線提供者 (（如 Windows Live) ）和匿名使用者支援等使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="0d471-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="0d471-109">如果使用不超過 Edge Server 的容量，則網站上的所有集區和多個中央網站的集區可以使用同一個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="0d471-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="0d471-110">如需監控的詳細資訊 (包括規模調整在內)，請參閱＜規劃＞文件中的[規劃外部使用者存取](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)。</span><span class="sxs-lookup"><span data-stu-id="0d471-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="0d471-111">如需設計拓撲來支援外部使用者存取的詳細資訊，請參閱＜部署＞文件中的[定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="0d471-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>