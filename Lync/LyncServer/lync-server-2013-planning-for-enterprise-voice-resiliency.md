---
title: Lync Server 2013：規劃企業語音復原
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
ms.openlocfilehash: 7b8b35871b740bd6d52d741922a3dcea9b7b60b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="041c6-102">在 Lync Server 2013 中規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="041c6-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="041c6-103">_**主題上次修改日期：** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="041c6-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="041c6-104">語音復原指的是，如果承載 Lync Server 2013 的中央網站無法使用（無論是透過廣域網路（WAN）故障或其他原因），使用者可以繼續撥打及接聽來電。</span><span class="sxs-lookup"><span data-stu-id="041c6-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="041c6-105">如果中央網站發生故障，企業語音服務必須透過無縫的容錯移轉到備份網站，繼續不間斷執行。</span><span class="sxs-lookup"><span data-stu-id="041c6-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="041c6-106">發生 WAN 故障時，必須將分支網站通話重新導向到本機 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="041c6-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="041c6-107">本節討論在發生中央網站或 WAN 失敗時，語音復原的規劃。</span><span class="sxs-lookup"><span data-stu-id="041c6-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="041c6-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="041c6-108">In This Section</span></span>

  - [<span data-ttu-id="041c6-109">在 Lync Server 2013 中規劃中央網站語音回復性</span><span class="sxs-lookup"><span data-stu-id="041c6-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="041c6-110">在 Lync Server 2013 中規劃分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="041c6-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

