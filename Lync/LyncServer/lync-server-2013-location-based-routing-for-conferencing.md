---
title: Lync Server 2013：適用于會議的位置路由
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
ms.openlocfilehash: dffc6ee9beaabc4705ac47e643a3fb19e589a745
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="bc345-102">Lync Server 2013 中以位置為基礎的會議路由</span><span class="sxs-lookup"><span data-stu-id="bc345-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc345-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="bc345-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="bc345-104">以位置為基礎的路由可以根據通話中各方的位置，限制 VoIP 端點與 PSTN 端點之間的通話路由。</span><span class="sxs-lookup"><span data-stu-id="bc345-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="bc345-105">有了 Lync Server 2013 的累積更新2，就可以在 Lync 會議（亦即會議）上強制執行位置路由規則，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="bc345-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="bc345-106">應用程式會監視作用中的會議，並根據參與的使用者位置強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="bc345-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="bc345-107">以位置為基礎的路由會議應用程式可讓您將以位置為基礎的路由限制實施到涉及 PSTN 端點的顧問式轉移。</span><span class="sxs-lookup"><span data-stu-id="bc345-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc345-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="bc345-108">In This Section</span></span>

  - [<span data-ttu-id="bc345-109">在 Lync Server 2013 中針對會議位置路由的概覽</span><span class="sxs-lookup"><span data-stu-id="bc345-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="bc345-110">Lync Server 2013 中的位置路由與諮詢式來電轉接</span><span class="sxs-lookup"><span data-stu-id="bc345-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="bc345-111">Lync Server 2013 中針對位置路由的會議需求</span><span class="sxs-lookup"><span data-stu-id="bc345-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="bc345-112">Lync Server 2013 中以位置為基礎的路由會議設定</span><span class="sxs-lookup"><span data-stu-id="bc345-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

