---
title: Lync Server 2013：媒體旁路模式
description: Lync Server 2013：媒體旁路模式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577899"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="57eb8-103">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="57eb8-103">Media bypass modes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57eb8-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="57eb8-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="57eb8-p101">您必須設定全域媒體旁路，並針對每個個別 PSTN 主幹設定媒體旁路。啟用全域媒體旁路時，有兩個選項：**[永遠略過]** 和 **[使用站台和區域資訊]**。</span><span class="sxs-lookup"><span data-stu-id="57eb8-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="57eb8-107">顧名思義， **Always 旁路** 表示所有 PSTN 通話都會嘗試略過。</span><span class="sxs-lookup"><span data-stu-id="57eb8-107">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls.</span></span> <span data-ttu-id="57eb8-108">**Always 旁路** 用於無需啟用通話許可控制的部署，也不需要指定有關何時嘗試媒體旁路的詳細設定資訊。</span><span class="sxs-lookup"><span data-stu-id="57eb8-108">**Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass.</span></span> <span data-ttu-id="57eb8-109">此外，當用戶端與 PSTN 閘道之間有完全連線時，就會使用 **Always 略過** 。</span><span class="sxs-lookup"><span data-stu-id="57eb8-109">Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways.</span></span> <span data-ttu-id="57eb8-110">在此設定中，所有子網都會對應至其中一個，而不是由系統所計算的一個旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57eb8-110">In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="57eb8-111">使用 **網站與地區資訊**時，與網站與地區設定相關聯的旁路識別碼是用來進行旁路決定。</span><span class="sxs-lookup"><span data-stu-id="57eb8-111">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision.</span></span> <span data-ttu-id="57eb8-112">這項設定可讓您靈活地為大多數常見拓撲設定旁路，因為它可讓您在略過時進行精細的控制，也就是以通話許可控制來支援互動 (CAC) 。</span><span class="sxs-lookup"><span data-stu-id="57eb8-112">This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC).</span></span> <span data-ttu-id="57eb8-113">系統會嘗試自動依下列方式指派旁路 IDs，以簡化您的工作。</span><span class="sxs-lookup"><span data-stu-id="57eb8-113">The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="57eb8-114">系統會自動為每個地區指派單一的唯一旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57eb8-114">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="57eb8-115">透過 WAN 連結連線至區域的任何網站，只要沒有頻寬限制，就會繼承該地區的相同旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57eb8-115">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="57eb8-116">在具有限制頻寬的 WAN 連結上，與區域相關聯的網站會被指派不同于該地區的回避識別碼。</span><span class="sxs-lookup"><span data-stu-id="57eb8-116">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="57eb8-117">與每個網站相關聯的子網會繼承該網站的旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57eb8-117">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="57eb8-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="57eb8-118">See Also</span></span>


[<span data-ttu-id="57eb8-119">Lync Server 2013 中的媒體旁路概述</span><span class="sxs-lookup"><span data-stu-id="57eb8-119">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="57eb8-120">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="57eb8-120">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="57eb8-121">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="57eb8-121">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

