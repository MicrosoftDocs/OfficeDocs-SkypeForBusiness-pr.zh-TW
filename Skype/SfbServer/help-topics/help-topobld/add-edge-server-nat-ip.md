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
ms.openlocfilehash: 42972caf9254eb4a7382b6f7066d2c781403616f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815213"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="3407a-105">新增 Edge Server NAT IP</span><span class="sxs-lookup"><span data-stu-id="3407a-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="3407a-106">公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3407a-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="3407a-107">IP 位址必須可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="3407a-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="3407a-108">這是必要的，因為您已在此嚮導的 [**選取功能**] 頁面上，選取 [**此 Edge 集區的外部 IP 位址是由 NAT 轉譯**] 選項。</span><span class="sxs-lookup"><span data-stu-id="3407a-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="3407a-109">網路位址轉譯 (NAT) 會在私人網路 (上啟用用戶端或伺服器。例如，192.168.0.0 範圍) ，可與透過公用網際網路網路的遠端網路上的系統進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3407a-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="3407a-110">NAT 的運作方式是使用外部介面上的單一公用 IP 位址，並將內部 IP 位址與一個公用 IP 位址產生關聯。</span><span class="sxs-lookup"><span data-stu-id="3407a-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="3407a-111">NAT 對應會將內部位址對應至外部公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3407a-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="3407a-112">遠端系統只會看到來源的公用位址。</span><span class="sxs-lookup"><span data-stu-id="3407a-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="3407a-113">遠端系統會回應來源，而且來源會參照 NAT 對應，以決定回應應傳回的內部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3407a-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="3407a-114">您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。</span><span class="sxs-lookup"><span data-stu-id="3407a-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="3407a-115">如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的＜[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="3407a-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


