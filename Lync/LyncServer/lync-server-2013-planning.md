---
title: Lync Server 2013 規劃
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
ms.openlocfilehash: e77603edea8accdfb34cb180f0f216ce07afdbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513410"
---
# <a name="planning-for-lync-server-2013"></a><span data-ttu-id="16dae-102">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16dae-102">Planning for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16dae-103">_**主題上次修改日期：** 2014-12-09_</span><span class="sxs-lookup"><span data-stu-id="16dae-103">_**Topic Last Modified:** 2014-12-09_</span></span>

<span data-ttu-id="16dae-104">本節中的主題說明如何規劃 Lync Server 的成功部署。</span><span class="sxs-lookup"><span data-stu-id="16dae-104">The topics in this section describe how to plan for a successful Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16dae-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="16dae-105">In This Section</span></span>

  - [<span data-ttu-id="16dae-106">Lync Server 2013 的組織規劃</span><span class="sxs-lookup"><span data-stu-id="16dae-106">Organization planning for Lync Server 2013</span></span>](lync-server-2013-planning-for-your-organization.md)

  - [<span data-ttu-id="16dae-107">決定 Lync Server 2013 的基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="16dae-107">Determining your infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-determining-your-infrastructure-requirements.md)

  - [<span data-ttu-id="16dae-108">Lync Server 2013 的網路規劃</span><span class="sxs-lookup"><span data-stu-id="16dae-108">Network planning for Lync Server 2013</span></span>](lync-server-2013-network-planning.md)

  - [<span data-ttu-id="16dae-109">Lync Server 2013 的容量規劃</span><span class="sxs-lookup"><span data-stu-id="16dae-109">Capacity planning for Lync Server 2013</span></span>](lync-server-2013-capacity-planning.md)

  - [<span data-ttu-id="16dae-110">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="16dae-110">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="16dae-111">在 Lync Server 2013 中規劃可管理性和虛擬化</span><span class="sxs-lookup"><span data-stu-id="16dae-111">Planning for manageability and virtualization in Lync Server 2013</span></span>](lync-server-2013-planning-for-manageability-and-virtualization.md)

  - [<span data-ttu-id="16dae-112">在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態</span><span class="sxs-lookup"><span data-stu-id="16dae-112">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

  - [<span data-ttu-id="16dae-113">在 Lync Server 2013 中規劃會議</span><span class="sxs-lookup"><span data-stu-id="16dae-113">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)

  - [<span data-ttu-id="16dae-114">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="16dae-114">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)

  - [<span data-ttu-id="16dae-115">在 Lync Server 2013 中規劃 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="16dae-115">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)

  - [<span data-ttu-id="16dae-116">在 Lync Server 2013 中規劃監控</span><span class="sxs-lookup"><span data-stu-id="16dae-116">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)

  - [<span data-ttu-id="16dae-117">在 Lync Server 2013 中規劃封存</span><span class="sxs-lookup"><span data-stu-id="16dae-117">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)

  - [<span data-ttu-id="16dae-118">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="16dae-118">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)

  - [<span data-ttu-id="16dae-119">規劃 Exchange Server 與 Lync Server 2013 的整合</span><span class="sxs-lookup"><span data-stu-id="16dae-119">Planning for Exchange Server integration with Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-server-integration.md)

  - [<span data-ttu-id="16dae-120">在 Lync Server 2013 中規劃用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="16dae-120">Planning for clients and devices in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients-and-devices.md)

  - [<span data-ttu-id="16dae-121">在 Lync Server 2013 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="16dae-121">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

  - [<span data-ttu-id="16dae-122">在 Lync Server 2013 中規劃行動性</span><span class="sxs-lookup"><span data-stu-id="16dae-122">Planning for mobility in Lync Server 2013</span></span>](lync-server-2013-planning-for-mobility.md)

  - [<span data-ttu-id="16dae-123">Lync Server 2013 中的安全性規劃</span><span class="sxs-lookup"><span data-stu-id="16dae-123">Planning for security in Lync Server 2013</span></span>](lync-server-2013-planning-for-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

