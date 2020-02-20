---
title: Lync Server 2013： 規劃 Enterprise Voice 彈性
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
ms.openlocfilehash: 16ca49b8548b60fce6adb723f5a4546ad1ff7388
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="8468d-102">規劃 Lync Server 2013 中的企業語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="8468d-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8468d-103">_**上次修改主題：** 2014年-10-17_</span><span class="sxs-lookup"><span data-stu-id="8468d-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="8468d-104">語音恢復能力指的是使用者能夠繼續了與接收的通話，如果中央網站的主應用程式 Lync Server 2013 變成無法使用，不論是透過廣域網路 (WAN) 失敗或其他原因的網路。</span><span class="sxs-lookup"><span data-stu-id="8468d-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="8468d-105">如果中央站台失敗，企業語音服務必須繼續不中斷地透過無縫的容錯移轉至備份網站。</span><span class="sxs-lookup"><span data-stu-id="8468d-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="8468d-106">WAN 故障時分支站台通話必須重新導向到本機的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="8468d-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="8468d-107">本章節將討論規劃中央網站或 WAN 故障時的語音恢復能力。</span><span class="sxs-lookup"><span data-stu-id="8468d-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8468d-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8468d-108">In This Section</span></span>

  - [<span data-ttu-id="8468d-109">規劃 Lync Server 2013 中的中央網站語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="8468d-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="8468d-110">規劃 Lync Server 2013 中的分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="8468d-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

