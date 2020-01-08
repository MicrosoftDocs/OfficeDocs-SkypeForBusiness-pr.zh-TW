---
title: Lync Server 2013：新回應群組應用程式功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="15743-102">Lync Server 2013 中的新回應群組應用程式功能</span><span class="sxs-lookup"><span data-stu-id="15743-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15743-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="15743-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="15743-104">透過回應群組應用程式，您可以將來電傳送給指定的人員，以進行特殊用途（例如客戶服務、內部技術支援人員或部門的一般電話支援）。</span><span class="sxs-lookup"><span data-stu-id="15743-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="15743-105">下列回應群組應用程式功能是 Lync Server 2013 中的新功能：</span><span class="sxs-lookup"><span data-stu-id="15743-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="15743-106">**管理員角色**</span><span class="sxs-lookup"><span data-stu-id="15743-106">**Manager role**</span></span>
    
    <span data-ttu-id="15743-107">Lync Server 2013 引入了新的 [回應群組管理員] 角色。</span><span class="sxs-lookup"><span data-stu-id="15743-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="15743-108">現在，回應群組有兩個管理角色： [回應群組管理員] 和 [回應群組管理員]。</span><span class="sxs-lookup"><span data-stu-id="15743-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="15743-109">雖然回應群組管理員仍可為任何回應群組設定任何元素，但管理員只能針對其擁有的回應群組設定特定元素。</span><span class="sxs-lookup"><span data-stu-id="15743-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="15743-110">管理模型的這項改進帶來了回應群組的伸縮性，特別是大型部署案例。</span><span class="sxs-lookup"><span data-stu-id="15743-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="15743-111">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="15743-111">**High availability**</span></span>
    
    <span data-ttu-id="15743-112">回應群組應用程式的高可用性支援（以 SQL Server 鏡像的形式），是在 Lync Server 2013 的整體設定和部署的整體配置和部署中啟用。</span><span class="sxs-lookup"><span data-stu-id="15743-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="15743-113">如果您設定高可用性，且失去主要後端伺服器的連線，回應群組功能不會受到利用鏡像後端伺服器的影響。</span><span class="sxs-lookup"><span data-stu-id="15743-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="15743-114">在整個 Lync Server 2013 高可用性設定之外，無法個別啟用或設定回應群組應用程式的 SQL Server 鏡像支援。</span><span class="sxs-lookup"><span data-stu-id="15743-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="15743-115">**災害復原**</span><span class="sxs-lookup"><span data-stu-id="15743-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="15743-116">已啟用回應群組應用程式的災害復原支援，這是整個 Lync Server 2013 災害復原設定中的設定與部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="15743-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="15743-117">此外，回應群組的匯入及匯出 Cmdlet 支援將容錯移轉程式加入到主要池或新的池中。</span><span class="sxs-lookup"><span data-stu-id="15743-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="15743-118">如果主要池中出現停機，回應群組可以容錯移轉至備份池，然後在中斷結束時回到主要池或新的池中。</span><span class="sxs-lookup"><span data-stu-id="15743-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15743-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="15743-119">See Also</span></span>


[<span data-ttu-id="15743-120">在 Lync Server 2013 中規劃回應群組</span><span class="sxs-lookup"><span data-stu-id="15743-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

