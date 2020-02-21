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
ms.openlocfilehash: f70d53e99c040d336ec99032b08db04f33f4de6e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013"></a><span data-ttu-id="3994b-102">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3994b-102">Planning for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3994b-103">_**上次修改主題：** 2014年-12-09_</span><span class="sxs-lookup"><span data-stu-id="3994b-103">_**Topic Last Modified:** 2014-12-09_</span></span>

<span data-ttu-id="3994b-104">本節中的主題說明如何規劃成功的 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="3994b-104">The topics in this section describe how to plan for a successful Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3994b-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3994b-105">In This Section</span></span>

  - [<span data-ttu-id="3994b-106">規劃 Lync Server 2013 的組織</span><span class="sxs-lookup"><span data-stu-id="3994b-106">Organization planning for Lync Server 2013</span></span>](lync-server-2013-planning-for-your-organization.md)

  - [<span data-ttu-id="3994b-107">決定針對 Lync Server 2013 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="3994b-107">Determining your infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-determining-your-infrastructure-requirements.md)

  - [<span data-ttu-id="3994b-108">規劃 Lync Server 2013 的網路</span><span class="sxs-lookup"><span data-stu-id="3994b-108">Network planning for Lync Server 2013</span></span>](lync-server-2013-network-planning.md)

  - [<span data-ttu-id="3994b-109">Lync Server 2013 的容量規劃</span><span class="sxs-lookup"><span data-stu-id="3994b-109">Capacity planning for Lync Server 2013</span></span>](lync-server-2013-capacity-planning.md)

  - [<span data-ttu-id="3994b-110">規劃 Lync Server 2013 中的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="3994b-110">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="3994b-111">規劃管理性與 Lync Server 2013 中的虛擬化</span><span class="sxs-lookup"><span data-stu-id="3994b-111">Planning for manageability and virtualization in Lync Server 2013</span></span>](lync-server-2013-planning-for-manageability-and-virtualization.md)

  - [<span data-ttu-id="3994b-112">規劃前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="3994b-112">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

  - [<span data-ttu-id="3994b-113">規劃 Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="3994b-113">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)

  - [<span data-ttu-id="3994b-114">規劃 Lync Server 2013 中的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="3994b-114">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)

  - [<span data-ttu-id="3994b-115">規劃 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3994b-115">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)

  - [<span data-ttu-id="3994b-116">規劃 Lync Server 2013 中監視</span><span class="sxs-lookup"><span data-stu-id="3994b-116">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)

  - [<span data-ttu-id="3994b-117">規劃 Lync Server 2013 中的封存</span><span class="sxs-lookup"><span data-stu-id="3994b-117">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)

  - [<span data-ttu-id="3994b-118">規劃 Lync Server 2013 中的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3994b-118">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)

  - [<span data-ttu-id="3994b-119">規劃 Exchange Server 與 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="3994b-119">Planning for Exchange Server integration with Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-server-integration.md)

  - [<span data-ttu-id="3994b-120">規劃用戶端和 Lync Server 2013 中的裝置</span><span class="sxs-lookup"><span data-stu-id="3994b-120">Planning for clients and devices in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients-and-devices.md)

  - [<span data-ttu-id="3994b-121">規劃 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="3994b-121">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

  - [<span data-ttu-id="3994b-122">Lync Server 2013 中的行動規劃</span><span class="sxs-lookup"><span data-stu-id="3994b-122">Planning for mobility in Lync Server 2013</span></span>](lync-server-2013-planning-for-mobility.md)

  - [<span data-ttu-id="3994b-123">Lync Server 2013 中的安全性規劃</span><span class="sxs-lookup"><span data-stu-id="3994b-123">Planning for security in Lync Server 2013</span></span>](lync-server-2013-planning-for-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

