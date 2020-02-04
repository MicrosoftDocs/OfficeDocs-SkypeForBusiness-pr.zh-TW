---
title: Lync Server 2013：規劃高可用性和災害復原
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
ms.openlocfilehash: 79abf8b98252f3b05b899a9840e7a9c9a2e8096c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="fa38a-102">在 Lync Server 2013 中規劃高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="fa38a-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa38a-103">_**主題上次修改日期：** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="fa38a-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="fa38a-104">就像在 Lync Server 2010 中，Lync Server 2013 中大多數伺服器角色的主要高可用性配置都是透過「池」以伺服器冗余為基礎。</span><span class="sxs-lookup"><span data-stu-id="fa38a-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="fa38a-105">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="fa38a-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="fa38a-106">這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="fa38a-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="fa38a-107">Lync Server 2013 會將您的伺服器地理位置 dispersement 引入兩個資料中心，以提供服務的新災害復原方法，以在整個池或網站向下移動。</span><span class="sxs-lookup"><span data-stu-id="fa38a-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="fa38a-108">Lync Server 2013 也會針對後端資料庫支援同步 SQL 鏡像，改善後端伺服器的高可用性。</span><span class="sxs-lookup"><span data-stu-id="fa38a-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="fa38a-109">本節說明這些主要的高可用性和災難復原功能，同時也說明您可以針對其他伺服器角色採取的高可用性和災難復原步驟。</span><span class="sxs-lookup"><span data-stu-id="fa38a-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa38a-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="fa38a-110">In This Section</span></span>

  - [<span data-ttu-id="fa38a-111">Lync Server 2013 中的前端集區災害復原</span><span class="sxs-lookup"><span data-stu-id="fa38a-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="fa38a-112">Lync Server 2013 中的 Edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="fa38a-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="fa38a-113">在 Lync Server 2013 中規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="fa38a-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="fa38a-114">Lync Server 2013 中的災害復原通話管理功能</span><span class="sxs-lookup"><span data-stu-id="fa38a-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="fa38a-115">在 Lync Server 2013 中針對高可用性和災害復原設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="fa38a-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="fa38a-116">Lync Server 2010 都會區網站復原</span><span class="sxs-lookup"><span data-stu-id="fa38a-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

