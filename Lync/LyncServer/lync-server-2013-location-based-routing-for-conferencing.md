---
title: 電話撥入會議的 [Lync Server 2013： 位置型路由
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
ms.openlocfilehash: 58bc253427e26c63d97610f5958ae26287fd42e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9764b-102">Lync Server 2013 中的會議位置型路由</span><span class="sxs-lookup"><span data-stu-id="9764b-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9764b-103">_**上次修改主題：** 2013年-07-31_</span><span class="sxs-lookup"><span data-stu-id="9764b-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="9764b-104">位置型的路由可讓您可以限制的 VoIP 端點與位置的呼叫方為基礎的 PSTN 端點之間的通話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="9764b-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="9764b-105">與累計更新 2 的 Lync Server 2013 中，您可以強制執行位置型的路由規則在 Lync 會議 （亦即會議） 來防止 PSTN 的免付費電話略過。</span><span class="sxs-lookup"><span data-stu-id="9764b-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="9764b-106">應用程式監視作用中的會議，並強制執行的位置型路由限制根據使用者參與的位置。</span><span class="sxs-lookup"><span data-stu-id="9764b-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="9764b-107">位置型路由會議應用程式此外啟用位置型路由限制諮詢轉接涉及 PSTN 端點的強制執行。</span><span class="sxs-lookup"><span data-stu-id="9764b-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9764b-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9764b-108">In This Section</span></span>

  - [<span data-ttu-id="9764b-109">Lync Server 2013 中的會議位置型路由的概觀</span><span class="sxs-lookup"><span data-stu-id="9764b-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="9764b-110">位置型路由及 Lync Server 2013 中的諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="9764b-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="9764b-111">Lync Server 2013 中的會議位置型路由的需求</span><span class="sxs-lookup"><span data-stu-id="9764b-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="9764b-112">Lync Server 2013 中的會議位置型路由的組態</span><span class="sxs-lookup"><span data-stu-id="9764b-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

