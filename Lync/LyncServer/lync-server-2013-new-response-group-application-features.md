---
title: Lync Server 2013：新的回應群組應用程式功能
description: Lync Server 2013：新的回應群組應用程式功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 191d3867758da427ade3470e78abfd417f6f00de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541959"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="85595-103">Lync Server 2013 中新的回應群組應用程式功能</span><span class="sxs-lookup"><span data-stu-id="85595-103">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85595-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="85595-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="85595-105">「回應群組」應用程式可讓您基於特殊目的將來電轉接和保留給指定人員，例如客戶服務、內部服務台或部門的一般電話支援。</span><span class="sxs-lookup"><span data-stu-id="85595-105">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="85595-106">下列回應群組應用程式功能是 Lync Server 2013 中的新功能：</span><span class="sxs-lookup"><span data-stu-id="85595-106">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="85595-107">**管理員角色**</span><span class="sxs-lookup"><span data-stu-id="85595-107">**Manager role**</span></span>
    
    <span data-ttu-id="85595-108">Lync Server 2013 引進新的回應群組管理員角色。</span><span class="sxs-lookup"><span data-stu-id="85595-108">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="85595-109">現在有兩個管理角色的回應群組：回應群組管理員和回應群組管理員。</span><span class="sxs-lookup"><span data-stu-id="85595-109">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="85595-110">當回應群組管理員仍可為任何回應群組設定任何元素時，管理員只可以設定特定元素，只適用于其擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="85595-110">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="85595-111">系統管理模型中的這項改進功能有利於回應群組的延展性，特別適用於大型部署案例。</span><span class="sxs-lookup"><span data-stu-id="85595-111">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="85595-112">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="85595-112">**High availability**</span></span>
    
    <span data-ttu-id="85595-113">以 SQL Server 鏡像的方式，回應群組應用程式的高可用性支援，是在 Lync Server 2013 的整體設定與部署的整體設定和部署中啟用的一部分。</span><span class="sxs-lookup"><span data-stu-id="85595-113">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="85595-114">如果您設定高可性且遺失與主要後端伺服器的連線，回應群組功能便不會因為使用鏡像的後端伺服器而受到影響。</span><span class="sxs-lookup"><span data-stu-id="85595-114">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="85595-115">無法在整體 Lync Server 2013 高可用性設定外，個別啟用或設定回應群組應用程式的 SQL Server 鏡像支援。</span><span class="sxs-lookup"><span data-stu-id="85595-115">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="85595-116">**災害復原**</span><span class="sxs-lookup"><span data-stu-id="85595-116">**Disaster recovery**</span></span>
    
    <span data-ttu-id="85595-117">在設定及部署成對的前端集區時（屬於整體 Lync Server 2013 災害復原設定的一部分），會啟用回應群組應用程式的嚴重損壞修復支援。</span><span class="sxs-lookup"><span data-stu-id="85595-117">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="85595-118">此外，回應群組匯入與匯出 Cmdlet 支援對備份集區的容錯移轉程序和對主要集區或新集區的容錯回復程序。</span><span class="sxs-lookup"><span data-stu-id="85595-118">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="85595-119">如果主要集區中發生中斷，回應群組即會容錯移轉至備份集區，然後在中斷回復之後容錯回復至主要集區或新集區。</span><span class="sxs-lookup"><span data-stu-id="85595-119">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85595-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85595-120">See Also</span></span>


[<span data-ttu-id="85595-121">在 Lync Server 2013 中規劃回應群組</span><span class="sxs-lookup"><span data-stu-id="85595-121">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

