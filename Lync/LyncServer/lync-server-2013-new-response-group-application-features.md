---
title: Lync Server 2013： 新的回應群組應用程式的功能
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
ms.openlocfilehash: f2538c6698875a0a96ce4e7dc7a46aa7cb9ed8e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="2728b-102">Lync Server 2013 中的新回應群組應用程式功能</span><span class="sxs-lookup"><span data-stu-id="2728b-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2728b-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="2728b-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="2728b-104">「回應群組」應用程式可讓您基於特殊目的將來電轉接和保留給指定人員，例如客戶服務、內部服務台或部門的一般電話支援。</span><span class="sxs-lookup"><span data-stu-id="2728b-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="2728b-105">下列回應群組應用程式的功能是 Lync Server 2013 的新增功能：</span><span class="sxs-lookup"><span data-stu-id="2728b-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="2728b-106">**管理員角色**</span><span class="sxs-lookup"><span data-stu-id="2728b-106">**Manager role**</span></span>
    
    <span data-ttu-id="2728b-107">Lync Server 2013 引進新的回應群組管理員角色。</span><span class="sxs-lookup"><span data-stu-id="2728b-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="2728b-108">現在有兩種管理角色的回應群組： 回應群組管理員及回應群組管理員。</span><span class="sxs-lookup"><span data-stu-id="2728b-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="2728b-109">雖然回應群組管理員仍然可以設定任何回應群組的任何項目，管理員可以設定僅限特定項目，僅適用於其所擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="2728b-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="2728b-110">系統管理模型中的這項改進功能有利於回應群組的延展性，特別適用於大型部署案例。</span><span class="sxs-lookup"><span data-stu-id="2728b-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="2728b-111">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="2728b-111">**High availability**</span></span>
    
    <span data-ttu-id="2728b-112">整體設定與 Lync Server 2013 的高可用性的部署的一部分，會啟用回應群組應用程式，在 SQL Server 鏡像，表單中的高可用性支援。</span><span class="sxs-lookup"><span data-stu-id="2728b-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="2728b-113">如果您設定高可性且遺失與主要後端伺服器的連線，回應群組功能便不會因為使用鏡像的後端伺服器而受到影響。</span><span class="sxs-lookup"><span data-stu-id="2728b-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="2728b-114">支援 SQL Server 鏡像的回應群組應用程式不能個別啟用或設定的整體的 Lync Server 2013 的高可用性設定以外。</span><span class="sxs-lookup"><span data-stu-id="2728b-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="2728b-115">**災害復原**</span><span class="sxs-lookup"><span data-stu-id="2728b-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="2728b-116">災害復原支援回應群組應用程式已啟用的設定資料庫和部署配對前端集區，屬於整體的 Lync Server 2013 災害復原設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="2728b-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="2728b-117">此外，回應群組匯入與匯出 Cmdlet 支援對備份集區的容錯移轉程序和對主要集區或新集區的容錯回復程序。</span><span class="sxs-lookup"><span data-stu-id="2728b-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="2728b-118">如果主要集區中發生中斷，回應群組即會容錯移轉至備份集區，然後在中斷回復之後容錯回復至主要集區或新集區。</span><span class="sxs-lookup"><span data-stu-id="2728b-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2728b-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2728b-119">See Also</span></span>


[<span data-ttu-id="2728b-120">規劃 Lync Server 2013 中的回應群組</span><span class="sxs-lookup"><span data-stu-id="2728b-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

