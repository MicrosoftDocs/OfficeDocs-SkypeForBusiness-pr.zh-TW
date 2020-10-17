---
title: Lync Server 2013 規劃
description: Lync Server 2013 規劃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning
ms:assetid: 6398cd91-8773-41bc-9b66-725d65ba9d66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398447(v=OCS.15)
ms:contentKeyID: 48184302
ms.date: 12/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4468300195760e7e994087875b5f49489828d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563969"
---
# <a name="planning-for-lync-server-2013"></a><span data-ttu-id="fcfb9-103">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcfb9-103">Planning for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcfb9-104">_**主題上次修改日期：** 2014-12-09_</span><span class="sxs-lookup"><span data-stu-id="fcfb9-104">_**Topic Last Modified:** 2014-12-09_</span></span>

<span data-ttu-id="fcfb9-105">本節中的主題說明如何規劃 Lync Server 的成功部署。</span><span class="sxs-lookup"><span data-stu-id="fcfb9-105">The topics in this section describe how to plan for a successful Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fcfb9-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="fcfb9-106">In This Section</span></span>

  - [<span data-ttu-id="fcfb9-107">Lync Server 2013 的組織規劃</span><span class="sxs-lookup"><span data-stu-id="fcfb9-107">Organization planning for Lync Server 2013</span></span>](lync-server-2013-planning-for-your-organization.md)

  - [<span data-ttu-id="fcfb9-108">決定 Lync Server 2013 的基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="fcfb9-108">Determining your infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-determining-your-infrastructure-requirements.md)

  - [<span data-ttu-id="fcfb9-109">Lync Server 2013 的網路規劃</span><span class="sxs-lookup"><span data-stu-id="fcfb9-109">Network planning for Lync Server 2013</span></span>](lync-server-2013-network-planning.md)

  - [<span data-ttu-id="fcfb9-110">Lync Server 2013 的容量規劃</span><span class="sxs-lookup"><span data-stu-id="fcfb9-110">Capacity planning for Lync Server 2013</span></span>](lync-server-2013-capacity-planning.md)

  - [<span data-ttu-id="fcfb9-111">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="fcfb9-111">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="fcfb9-112">在 Lync Server 2013 中規劃可管理性和虛擬化</span><span class="sxs-lookup"><span data-stu-id="fcfb9-112">Planning for manageability and virtualization in Lync Server 2013</span></span>](lync-server-2013-planning-for-manageability-and-virtualization.md)

  - [<span data-ttu-id="fcfb9-113">在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態</span><span class="sxs-lookup"><span data-stu-id="fcfb9-113">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

  - [<span data-ttu-id="fcfb9-114">在 Lync Server 2013 中規劃會議</span><span class="sxs-lookup"><span data-stu-id="fcfb9-114">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)

  - [<span data-ttu-id="fcfb9-115">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="fcfb9-115">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)

  - [<span data-ttu-id="fcfb9-116">在 Lync Server 2013 中規劃 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fcfb9-116">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)

  - [<span data-ttu-id="fcfb9-117">在 Lync Server 2013 中規劃監控</span><span class="sxs-lookup"><span data-stu-id="fcfb9-117">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)

  - [<span data-ttu-id="fcfb9-118">在 Lync Server 2013 中規劃封存</span><span class="sxs-lookup"><span data-stu-id="fcfb9-118">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)

  - [<span data-ttu-id="fcfb9-119">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="fcfb9-119">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)

  - [<span data-ttu-id="fcfb9-120">規劃 Exchange Server 與 Lync Server 2013 的整合</span><span class="sxs-lookup"><span data-stu-id="fcfb9-120">Planning for Exchange Server integration with Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-server-integration.md)

  - [<span data-ttu-id="fcfb9-121">在 Lync Server 2013 中規劃用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="fcfb9-121">Planning for clients and devices in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients-and-devices.md)

  - [<span data-ttu-id="fcfb9-122">在 Lync Server 2013 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="fcfb9-122">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

  - [<span data-ttu-id="fcfb9-123">在 Lync Server 2013 中規劃行動性</span><span class="sxs-lookup"><span data-stu-id="fcfb9-123">Planning for mobility in Lync Server 2013</span></span>](lync-server-2013-planning-for-mobility.md)

  - [<span data-ttu-id="fcfb9-124">Lync Server 2013 中的安全性規劃</span><span class="sxs-lookup"><span data-stu-id="fcfb9-124">Planning for security in Lync Server 2013</span></span>](lync-server-2013-planning-for-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

