---
title: 新增 Edge Server NAT IP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。 IP 位址必須可公開路由傳送。 這是必要的，因為您已在此嚮導的 [選取功能] 頁面上，選取 [此 Edge 集區的外部 IP 位址是由 NAT 轉譯] 選項。
ms.openlocfilehash: cf5cb61dce8d71e97ba3977e241df4480c30a403
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119812"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="7c8f9-105">新增 Edge Server NAT IP</span><span class="sxs-lookup"><span data-stu-id="7c8f9-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="7c8f9-106">公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="7c8f9-107">IP 位址必須可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="7c8f9-108">這是必要的，因為您已在此嚮導的 [**選取功能**] 頁面上，選取 [**此 Edge 集區的外部 IP 位址是由 NAT 轉譯**] 選項。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="7c8f9-109">網路位址轉譯 (NAT) 會在私人網路 (上啟用用戶端或伺服器。例如，192.168.0.0 範圍) ，可與透過公用網際網路網路的遠端網路上的系統進行通訊。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="7c8f9-110">NAT 的運作方式是使用外部介面上的單一公用 IP 位址，並將內部 IP 位址與一個公用 IP 位址產生關聯。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="7c8f9-111">NAT 對應會將內部位址對應至外部公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="7c8f9-112">遠端系統只會看到來源的公用位址。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="7c8f9-113">遠端系統會回應來源，而且來源會參照 NAT 對應，以決定回應應傳回的內部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="7c8f9-114">您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="7c8f9-115">如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的＜[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)＞。</span><span class="sxs-lookup"><span data-stu-id="7c8f9-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Edge Server Deployment documentation.</span></span>