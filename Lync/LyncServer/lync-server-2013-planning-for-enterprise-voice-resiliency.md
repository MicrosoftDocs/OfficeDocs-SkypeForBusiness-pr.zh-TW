---
title: Lync Server 2013：規劃企業語音恢復功能
description: Lync Server 2013：規劃企業語音恢復功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adcf09b87264666924a16543a1b21e8e3cae39f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567259"
---
# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="0be0f-103">在 Lync Server 2013 中規劃 Enterprise Voice 韌性</span><span class="sxs-lookup"><span data-stu-id="0be0f-103">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0be0f-104">_**主題上次修改日期：** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="0be0f-104">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="0be0f-105">語音恢復指的是，如果主控 Lync Server 2013 的中央網站無法使用（不論是透過廣域網路絡 (WAN) 故障或其他原因），則使用者可以繼續撥打和接聽電話的能力。</span><span class="sxs-lookup"><span data-stu-id="0be0f-105">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="0be0f-106">若中央網站失敗，Enterprise Voice 服務必須透過無縫容錯移轉至備份網站而繼續中斷。</span><span class="sxs-lookup"><span data-stu-id="0be0f-106">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="0be0f-107">在 WAN 失敗的情況下，必須將分支網站來電重新導向至本機 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0be0f-107">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="0be0f-108">本節討論在中央網站或 WAN 失敗的情況時，如何規劃語音彈性。</span><span class="sxs-lookup"><span data-stu-id="0be0f-108">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0be0f-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0be0f-109">In This Section</span></span>

  - [<span data-ttu-id="0be0f-110">在 Lync Server 2013 中規劃中央網站語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="0be0f-110">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="0be0f-111">在 Lync Server 2013 中規劃分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="0be0f-111">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

