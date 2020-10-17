---
title: Lync Server 2013：會議的 Location-Based 路由
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
ms.openlocfilehash: 03e216e80b50bd7b2d5c0515700c4f1cd7260f22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513800"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9ca03-102">在 Lync Server 2013 中為會議 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="9ca03-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca03-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="9ca03-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="9ca03-104">Location-Based 路由可讓您根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。</span><span class="sxs-lookup"><span data-stu-id="9ca03-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="9ca03-105">使用 Lync Server 2013 的累計更新2，可在 Lync 會議上強制執行 Location-Based 的路由規則 (也就是說，可) 防止 PSTN 免付費旁路的會議。</span><span class="sxs-lookup"><span data-stu-id="9ca03-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="9ca03-106">應用程式會監視作用中的會議，並根據參與的使用者位置，強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="9ca03-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="9ca03-107">Location-Based 路由會議應用程式，此外也可強制執行 Location-Based 路由限制，以進行涉及 PSTN 端點的諮詢式轉接。</span><span class="sxs-lookup"><span data-stu-id="9ca03-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9ca03-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9ca03-108">In This Section</span></span>

  - [<span data-ttu-id="9ca03-109">在 Lync Server 2013 中 Location-Based 用於會議之路由的概述</span><span class="sxs-lookup"><span data-stu-id="9ca03-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="9ca03-110">Lync Server 2013 中的位置基礎路由和顧問式來電轉接</span><span class="sxs-lookup"><span data-stu-id="9ca03-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="9ca03-111">在 Lync Server 2013 中 Location-Based 路由進行會議的需求</span><span class="sxs-lookup"><span data-stu-id="9ca03-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="9ca03-112">在 Lync Server 2013 中設定會議的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="9ca03-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

