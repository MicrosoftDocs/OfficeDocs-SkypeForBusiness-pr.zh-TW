---
title: Lync Server 2013：Director 案例
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
ms.openlocfilehash: ac7c5a262f5323f28ff089766cab1f4d65e30757
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="a8d20-102">Lync Server 2013 中的 Director 案例</span><span class="sxs-lookup"><span data-stu-id="a8d20-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d20-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a8d20-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a8d20-104">Director 是執行 Microsoft Lync Server 2013 通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a8d20-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="a8d20-105">控制器也會託管與前端伺服器類似的 web 服務，並會驗證 web 票證要求並提供其他服務。</span><span class="sxs-lookup"><span data-stu-id="a8d20-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a8d20-106">如果您要部署控制器，您必須透過反向 proxy 以及前端伺服器的 web 服務，在外部發佈控制器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="a8d20-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="a8d20-107">下列主題說明可能的控制器拓撲的規劃程式。</span><span class="sxs-lookup"><span data-stu-id="a8d20-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8d20-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="a8d20-108">In This Section</span></span>

  - [<span data-ttu-id="a8d20-109">Lync Server 2013 中的 Director 概觀</span><span class="sxs-lookup"><span data-stu-id="a8d20-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="a8d20-110">Lync Server 2013 中 Director 的必要元件</span><span class="sxs-lookup"><span data-stu-id="a8d20-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="a8d20-111">Lync Server 2013 中 Director 的軟硬體需求</span><span class="sxs-lookup"><span data-stu-id="a8d20-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="a8d20-112">Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="a8d20-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="a8d20-113">Lync Server 2013 中的調整式 Director 集區</span><span class="sxs-lookup"><span data-stu-id="a8d20-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8d20-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="a8d20-114">See Also</span></span>


[<span data-ttu-id="a8d20-115">Lync Server 2013 中支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="a8d20-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="a8d20-116">Lync Server 2013 的伺服器硬體平台</span><span class="sxs-lookup"><span data-stu-id="a8d20-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

