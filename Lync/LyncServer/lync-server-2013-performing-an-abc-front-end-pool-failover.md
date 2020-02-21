---
title: Lync Server 2013： 執行 ABC 前端集區容錯移轉
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebffd5b4e1b4cca1cb815f37f569aebd6a241ccd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="2d1c7-102">在 Lync Server 2013 中執行 ABC 前端集區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="2d1c7-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d1c7-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="2d1c7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2d1c7-104">本節中的兩個主題將說明在 Lync Server 2013 中，執行 ABC 集區容錯移轉程序有 A 和 B 的 Lync Server 前端集區配對且集區 A 變成無法復原。</span><span class="sxs-lookup"><span data-stu-id="2d1c7-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="2d1c7-105">您可使用此程序，以新的完整的網域名稱 (FQDN) 建立新的前端集區 C。</span><span class="sxs-lookup"><span data-stu-id="2d1c7-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2d1c7-106">集區 C 的建構會從失敗的集區 a 中的資訊此程序也包含一起配對集區 B 和 c。</span><span class="sxs-lookup"><span data-stu-id="2d1c7-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="2d1c7-107">Lync Server 2013 中的 ABC 集區容錯移轉備份先決條件</span><span class="sxs-lookup"><span data-stu-id="2d1c7-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="2d1c7-108">前端集區在 Lync Server 2013 中的 ABC 容錯移轉程序</span><span class="sxs-lookup"><span data-stu-id="2d1c7-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

