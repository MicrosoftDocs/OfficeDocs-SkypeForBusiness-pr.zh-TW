---
title: 舊版合併
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: 網路會議外部 FQDN 允許外部使用者加入內部部署會議。 輸入舊版 Edge 伺服器的網路會議外部介面的完整功能變數名稱（FQDN）。
ms.openlocfilehash: 1f2a1e9ca3d3ca20b7b0fe6832a0e394d7fac5ce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688336"
---
# <a name="legacy-merge"></a><span data-ttu-id="63710-104">舊版合併</span><span class="sxs-lookup"><span data-stu-id="63710-104">Legacy Merge</span></span>

<span data-ttu-id="63710-105">**網路會議外部 FQDN**允許外部使用者加入內部部署會議。</span><span class="sxs-lookup"><span data-stu-id="63710-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="63710-106">輸入舊版 Edge 伺服器的網路會議外部介面的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="63710-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="63710-107">[**外部 Web 會議外部埠**值**443** ] 是為會議用戶端設定的預設傳輸控制通訊協定（SIP）埠。</span><span class="sxs-lookup"><span data-stu-id="63710-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="63710-108">如果未使用預設值，請更新 [**外部 Web 會議外部埠**] 值。</span><span class="sxs-lookup"><span data-stu-id="63710-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="63710-109">如果您打算將此 Edge 伺服器用於同盟，請選取 [**此 edge 池用於同盟與公用 IM**連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="63710-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="63710-110">如果您部署了多個 Edge 伺服器，則只有其中一個是針對同盟啟用。</span><span class="sxs-lookup"><span data-stu-id="63710-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="63710-111">如果您不選取此方塊，且稍後決定要啟用同盟，您必須再次執行 [拓撲建立器合併] 嚮導，以及發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="63710-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="63710-112">如需詳細資訊，請參閱[階段4：合併拓撲](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63710-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


