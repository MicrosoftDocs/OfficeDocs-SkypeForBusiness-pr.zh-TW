---
title: 舊版合併
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: '[Web 會議外部 FQDN] 允許外部使用者加入內部會議。 請輸入舊有 Edge Server 之 Web 會議外部介面的完整網域名稱 (FQDN)。'
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805703"
---
# <a name="legacy-merge"></a><span data-ttu-id="2560a-104">舊版合併</span><span class="sxs-lookup"><span data-stu-id="2560a-104">Legacy Merge</span></span>

<span data-ttu-id="2560a-p102">[Web 會議外部 FQDN] 允許外部使用者加入內部會議。請輸入舊有 Edge Server 之 Web 會議外部介面的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2560a-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="2560a-p103">[外部 Web 會議外部連接埠] 值 443 為針對會議用戶端所預設的傳輸控制通訊協定 (TCP) 工作階段初始通訊協定 (SIP) 連接埠。如果系統未使用預設值，請更新 [外部 Web 會議外部連接埠] 的值。</span><span class="sxs-lookup"><span data-stu-id="2560a-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="2560a-109">如果您打算使用這部 Edge Server 進行同盟，則選取 [此 Edge 集區是用於同盟和公用 IM 連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2560a-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="2560a-110">如果您已部署多部 Edge Server，當中只有一部會啟用同盟功能。</span><span class="sxs-lookup"><span data-stu-id="2560a-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="2560a-111">如果您並未勾選此方塊，而是決定稍後再啟用同盟，則您必須再次執行 [拓撲產生器合併精靈] 並發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="2560a-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="2560a-112">如需詳細資訊，請參閱＜[Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="2560a-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


