---
title: 新增 Edge Server IP 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 可讓您為 Edge Server 和 Edge 集區的每個介面設定 IPv4 和 IPv6 位址。 若要這樣做，請執行下列動作：
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219788"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="91957-104">新增 Edge Server IP 選項</span><span class="sxs-lookup"><span data-stu-id="91957-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="91957-105">Microsoft Lync Server 2013 可讓您為 Edge Server 和 Edge 集區的每個介面設定 IPv4 和 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="91957-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="91957-106">若要這樣做，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="91957-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="91957-107">**在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="91957-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="91957-108">**在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="91957-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="91957-109">**在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="91957-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="91957-110">**在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="91957-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="91957-111">您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="91957-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="91957-112">您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯]\*\*\*\* 核取方塊，來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="91957-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="91957-113">NAT 支援。</span><span class="sxs-lookup"><span data-stu-id="91957-113">NAT support.</span></span> <span data-ttu-id="91957-114">當您使用硬體負載平衡時，不支援 [網路位址轉譯 (NAT) ]，所以如果您要部署具有硬體負載平衡的 Edge Server 集區，請勿選取 NAT 選項。</span><span class="sxs-lookup"><span data-stu-id="91957-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

