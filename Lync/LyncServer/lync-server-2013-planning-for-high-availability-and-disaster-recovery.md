---
title: Lync Server 2013： 規劃高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ba7e58f29bb4e54972804fbe338c2e1345e91e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ccc6f-102">規劃 Lync Server 2013 中的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="ccc6f-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc6f-103">_**上次修改主題：** 2013年-10-31_</span><span class="sxs-lookup"><span data-stu-id="ccc6f-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="ccc6f-104">Lync Server 2010，如同在 Lync Server 2013 中的多數伺服器角色的主要高可用性配置根據經由共用伺服器備援。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="ccc6f-105">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="ccc6f-106">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="ccc6f-107">Lync Server 2013 會將新的前端集區的災害復原措施新增到兩個資料中心提供的服務接續萬一有一整個集區或網站移往下引入一部伺服器的地理位置不同。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="ccc6f-108">Lync Server 2013 也增強後端伺服器高可用性，可支援後端資料庫的同步 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="ccc6f-109">本節說明這些主要高可用性和災害復原功能，另外也會說明您可以針對其他伺服器角色的高可用性和災害復原採取哪些步驟。</span><span class="sxs-lookup"><span data-stu-id="ccc6f-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ccc6f-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="ccc6f-110">In This Section</span></span>

  - [<span data-ttu-id="ccc6f-111">Lync Server 2013 中的結束集區嚴重損壞修復的前端</span><span class="sxs-lookup"><span data-stu-id="ccc6f-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="ccc6f-112">Lync Server 2013 中的 edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="ccc6f-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="ccc6f-113">規劃 Lync Server 2013 中的企業語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="ccc6f-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="ccc6f-114">Lync Server 2013 的災害復原的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="ccc6f-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="ccc6f-115">針對 Lync Server 2013 中的高可用性和災害復原設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="ccc6f-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="ccc6f-116">Lync Server 2010 都會網站恢復</span><span class="sxs-lookup"><span data-stu-id="ccc6f-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

