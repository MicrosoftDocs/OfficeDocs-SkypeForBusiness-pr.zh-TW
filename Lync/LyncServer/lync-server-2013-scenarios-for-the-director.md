---
title: Lync Server 2013： Director 的案例
description: Lync Server 2013： Director 的案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45c611fbe680ba55fb148c08fed26d96a848507e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578999"
---
# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="9480f-103">Lync Server 2013 中的 Director 案例</span><span class="sxs-lookup"><span data-stu-id="9480f-103">Scenarios for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9480f-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9480f-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9480f-105">Director 是執行 Microsoft Lync Server 2013 通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="9480f-105">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="9480f-106">Director 也會主控類似前端伺服器的 web 服務，並會驗證 web 票證要求並提供其他服務。</span><span class="sxs-lookup"><span data-stu-id="9480f-106">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9480f-107">如果您要部署 Director，必須透過反向 proxy 和前端伺服器的 web 服務，從外部發佈 Director web 服務。</span><span class="sxs-lookup"><span data-stu-id="9480f-107">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="9480f-108">下列主題描述可能的 Director 拓撲的規劃程式。</span><span class="sxs-lookup"><span data-stu-id="9480f-108">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9480f-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9480f-109">In This Section</span></span>

  - [<span data-ttu-id="9480f-110">Lync Server 2013 中的 Director 概述</span><span class="sxs-lookup"><span data-stu-id="9480f-110">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="9480f-111">Lync Server 2013 中的 Director 所需的元件</span><span class="sxs-lookup"><span data-stu-id="9480f-111">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="9480f-112">Lync Server 2013 中 Director 的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="9480f-112">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="9480f-113">Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="9480f-113">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="9480f-114">Lync Server 2013 中的調整式 Director 集區</span><span class="sxs-lookup"><span data-stu-id="9480f-114">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9480f-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9480f-115">See Also</span></span>


[<span data-ttu-id="9480f-116">Lync Server 2013 中支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="9480f-116">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="9480f-117">Lync Server 2013 的伺服器硬體平臺</span><span class="sxs-lookup"><span data-stu-id="9480f-117">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

