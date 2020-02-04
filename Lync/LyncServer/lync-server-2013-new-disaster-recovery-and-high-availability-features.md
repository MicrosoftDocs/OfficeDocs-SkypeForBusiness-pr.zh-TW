---
title: Lync Server 2013：新的災害復原和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="8015c-102">Lync Server 2013 中新的災害復原和高可用性功能</span><span class="sxs-lookup"><span data-stu-id="8015c-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8015c-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="8015c-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="8015c-104">就像在 Lync Server 2010 中，Lync Server 2013 的主要高可用性（HA）配置是透過「池」以伺服器冗余為基礎。</span><span class="sxs-lookup"><span data-stu-id="8015c-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="8015c-105">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="8015c-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="8015c-106">這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="8015c-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="8015c-107">Lync Server 2013 可讓您對位於兩個資料中心的前端池進行配對，以新增災害復原量值。</span><span class="sxs-lookup"><span data-stu-id="8015c-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="8015c-108">如果其中一個配對的池向下，系統管理員可以將該池中的使用者容錯移轉至該組中的另一個池，以提供服務的延續。</span><span class="sxs-lookup"><span data-stu-id="8015c-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="8015c-109">此功能不需要昂貴的網路或硬體解決方案（例如儲存網路或共用磁片）。</span><span class="sxs-lookup"><span data-stu-id="8015c-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="8015c-110">Lync Server 2013 也會新增後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="8015c-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="8015c-111">這是一種選用拓朴，您可以在其中部署前端池的兩個後端伺服器，並針對在後端伺服器上執行的所有 Lync 資料庫，設定同步處理的 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="8015c-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="8015c-112">您可以選擇是否要為鏡像部署見證。</span><span class="sxs-lookup"><span data-stu-id="8015c-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8015c-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="8015c-113">See Also</span></span>


[<span data-ttu-id="8015c-114">在 Lync Server 2013 中規劃高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="8015c-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

