---
title: Lync Server 2013： 新的災害復原和高可用性功能
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
ms.openlocfilehash: 366b58f05e8567659dc630042494f1ede25cf338
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="47c9f-102">新的災害復原和 Lync Server 2013 中的高可用性功能</span><span class="sxs-lookup"><span data-stu-id="47c9f-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47c9f-103">_**主題上次修改日期：** 2012年-09-20 個_</span><span class="sxs-lookup"><span data-stu-id="47c9f-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="47c9f-104">如同 Lync Server 2010、 Lync Server 2013 的主要高可用性 (HA) 配置根據經由共用伺服器備援。</span><span class="sxs-lookup"><span data-stu-id="47c9f-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="47c9f-105">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="47c9f-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="47c9f-106">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="47c9f-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="47c9f-107">Lync Server 2013 新增新的災害復原措施如此可讓您位於兩個資料中心的配對前端集區。</span><span class="sxs-lookup"><span data-stu-id="47c9f-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="47c9f-108">如果配對的集區中有一個故障，系統管理員可以將使用者從該集區容錯移轉至配對中的另一個集區，以便繼續提供服務。</span><span class="sxs-lookup"><span data-stu-id="47c9f-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="47c9f-109">這項功能不需要昂貴的網路或硬體解決方案，例如存放網路或共用磁碟。</span><span class="sxs-lookup"><span data-stu-id="47c9f-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="47c9f-110">Lync Server 2013 也會新增後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="47c9f-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="47c9f-111">這是選用的拓樸您部署兩個後端伺服器的前端集區]，並設定同步 SQL 鏡像在後端伺服器上執行的所有 Lync 資料庫。</span><span class="sxs-lookup"><span data-stu-id="47c9f-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="47c9f-112">您可以選擇是否要部署鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="47c9f-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="47c9f-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="47c9f-113">See Also</span></span>


[<span data-ttu-id="47c9f-114">規劃 Lync Server 2013 中的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="47c9f-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

