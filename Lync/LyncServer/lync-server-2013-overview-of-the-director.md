---
title: Lync Server 2013：Director 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="d44d1-102">Lync Server 2013 中的 Director 概觀</span><span class="sxs-lookup"><span data-stu-id="d44d1-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d44d1-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d44d1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d44d1-104">Director 是執行 Lync Server 2013 的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d44d1-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="d44d1-105">您也可以選擇在下列兩種案例中部署主管：</span><span class="sxs-lookup"><span data-stu-id="d44d1-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="d44d1-106">如果您透過部署邊緣伺服器來啟用外部使用者存取，您也應該部署控制器。</span><span class="sxs-lookup"><span data-stu-id="d44d1-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="d44d1-107">在這種情況下，控制器會驗證外部使用者，然後將通信量傳送到內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="d44d1-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="d44d1-108">當使用 Director 驗證外部使用者時，它會從執行這些使用者驗證的負荷，來免除前端池伺服器。</span><span class="sxs-lookup"><span data-stu-id="d44d1-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="d44d1-109">它也可協助將內部前端池與惡意流量（例如拒絕服務攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="d44d1-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="d44d1-110">如果網路充斥在這種攻擊中的無效外部通信量，此流量將結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="d44d1-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="d44d1-111">如果您是在中央網站部署多個前端池，您可以在該網站上新增 Director，以簡化驗證要求並改善效能。</span><span class="sxs-lookup"><span data-stu-id="d44d1-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="d44d1-112">在這種情況下，所有要求都會先移至 Director，然後將它們路由到正確的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="d44d1-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

