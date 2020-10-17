---
title: Lync Server 2013：會議的 Location-Based 路由
description: Lync Server 2013：會議的 Location-Based 路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554849"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="32747-103">在 Lync Server 2013 中為會議 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="32747-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32747-104">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="32747-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="32747-105">Location-Based 路由可讓您根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。</span><span class="sxs-lookup"><span data-stu-id="32747-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="32747-106">使用 Lync Server 2013 的累計更新2，可在 Lync 會議上強制執行 Location-Based 的路由規則 (也就是說，可) 防止 PSTN 免付費旁路的會議。</span><span class="sxs-lookup"><span data-stu-id="32747-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="32747-107">應用程式會監視作用中的會議，並根據參與的使用者位置，強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="32747-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="32747-108">Location-Based 路由會議應用程式，此外也可強制執行 Location-Based 路由限制，以進行涉及 PSTN 端點的諮詢式轉接。</span><span class="sxs-lookup"><span data-stu-id="32747-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="32747-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="32747-109">In This Section</span></span>

  - [<span data-ttu-id="32747-110">在 Lync Server 2013 中 Location-Based 用於會議之路由的概述</span><span class="sxs-lookup"><span data-stu-id="32747-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="32747-111">Lync Server 2013 中的位置基礎路由和顧問式來電轉接</span><span class="sxs-lookup"><span data-stu-id="32747-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="32747-112">在 Lync Server 2013 中 Location-Based 路由進行會議的需求</span><span class="sxs-lookup"><span data-stu-id="32747-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="32747-113">在 Lync Server 2013 中設定會議的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="32747-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

