---
title: Lync Server 2013：媒體旁路模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="b63d7-102">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="b63d7-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b63d7-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b63d7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b63d7-104">您必須針對每個獨立 PSTN 幹線設定全域旁路的媒體。</span><span class="sxs-lookup"><span data-stu-id="b63d7-104">You must configure media bypass both globally and for each individual PSTN trunk.</span></span> <span data-ttu-id="b63d7-105">若要全域啟用媒體，您有兩種選擇：**總是略過**並**使用網站和區域資訊**。</span><span class="sxs-lookup"><span data-stu-id="b63d7-105">When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="b63d7-106">如名稱所示，[**永遠避開**] 表示所有 PSTN 呼叫都會嘗試略過。</span><span class="sxs-lookup"><span data-stu-id="b63d7-106">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls.</span></span> <span data-ttu-id="b63d7-107">**Always 旁路**適用于不需要啟用呼叫許可控制的部署，也不需要指定有關何時嘗試媒體旁路的詳細配置資訊。</span><span class="sxs-lookup"><span data-stu-id="b63d7-107">**Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass.</span></span> <span data-ttu-id="b63d7-108">此外，在用戶端與 PSTN 閘道之間有完全連線的情況下，也會使用 [**永遠略過**]。</span><span class="sxs-lookup"><span data-stu-id="b63d7-108">Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways.</span></span> <span data-ttu-id="b63d7-109">在這個設定中，所有子網都會對應到一個，而且只有一個旁路 ID 是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="b63d7-109">In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="b63d7-110">使用**網站和區域資訊**時，會使用與網站和區域設定關聯的旁路識別碼來進行略過決策。</span><span class="sxs-lookup"><span data-stu-id="b63d7-110">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision.</span></span> <span data-ttu-id="b63d7-111">這項設定可讓您靈活地針對大多數常見拓撲設定略過，因為它不僅支援與通話許可控制（CAC）的互動，也能讓您更精細地控制。</span><span class="sxs-lookup"><span data-stu-id="b63d7-111">This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC).</span></span> <span data-ttu-id="b63d7-112">系統會嘗試自動指派旁路識別碼來減輕您的任務，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b63d7-112">The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="b63d7-113">系統會自動為每個區域指派單一唯一的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="b63d7-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="b63d7-114">在沒有頻寬限制的情況下，通過 WAN 連結連線至某個區域的任何網站，都會繼承與該區域相同的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="b63d7-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="b63d7-115">在具有有限頻寬的 WAN 連結上，與區域相關聯的網站會指派不同于該區域的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="b63d7-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="b63d7-116">與每個網站相關聯的子網會繼承該網站的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="b63d7-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b63d7-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="b63d7-117">See Also</span></span>


[<span data-ttu-id="b63d7-118">Lync Server 2013 中的媒體旁路概覽</span><span class="sxs-lookup"><span data-stu-id="b63d7-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="b63d7-119">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="b63d7-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="b63d7-120">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="b63d7-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

