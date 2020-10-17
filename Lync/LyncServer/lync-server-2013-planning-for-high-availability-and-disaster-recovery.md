---
title: Lync Server 2013：規劃高可用性和嚴重損壞修復
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
ms.openlocfilehash: 7a44a3b5f83814bf4d4b975dc8f9d548661294e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522110"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="919f4-102">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="919f4-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="919f4-103">_**主題上次修改日期：** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="919f4-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="919f4-104">就像在 Lync Server 2010 中，Lync Server 2013 中的大部分伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。</span><span class="sxs-lookup"><span data-stu-id="919f4-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="919f4-105">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="919f4-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="919f4-106">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="919f4-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="919f4-107">Lync Server 2013 新增前端集區的新的嚴重損壞修復方法，方法是將伺服器的地理 dispersement 引入兩個資料中心，以在整個集區或網站中斷時，提供服務的連續執行。</span><span class="sxs-lookup"><span data-stu-id="919f4-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="919f4-108">Lync Server 2013 也可支援後端資料庫的同步 SQL 鏡像，增強後端伺服器的高可用性。</span><span class="sxs-lookup"><span data-stu-id="919f4-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="919f4-109">本節說明這些主要高可用性和災害復原功能，另外也會說明您可以針對其他伺服器角色的高可用性和災害復原採取哪些步驟。</span><span class="sxs-lookup"><span data-stu-id="919f4-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="919f4-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="919f4-110">In This Section</span></span>

  - [<span data-ttu-id="919f4-111">Lync Server 2013 中的前端集區嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="919f4-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="919f4-112">Lync Server 2013 中的 Edge Server 災難性修復</span><span class="sxs-lookup"><span data-stu-id="919f4-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="919f4-113">在 Lync Server 2013 中規劃 Enterprise Voice 韌性</span><span class="sxs-lookup"><span data-stu-id="919f4-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="919f4-114">Lync Server 2013 中的「災難修復」的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="919f4-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="919f4-115">在 Lync Server 2013 中設定持久聊天伺服器以取得高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="919f4-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="919f4-116">Lync Server 2010 大都市網站恢復功能</span><span class="sxs-lookup"><span data-stu-id="919f4-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

