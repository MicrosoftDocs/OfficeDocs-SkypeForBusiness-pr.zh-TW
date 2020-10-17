---
title: Lync Server 2013：執行 ABC 前端集區容錯移轉
description: Lync Server 2013：執行 ABC 前端集區容錯移轉。
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
ms.openlocfilehash: 0c1aa7a18bc1f1126bcb942a0b3a21283637dcb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557219"
---
# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="e8b1f-103">在 Lync Server 2013 中執行 ABC 前端集區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="e8b1f-103">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8b1f-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e8b1f-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e8b1f-105">本節中的兩個主題將說明在 Lync Server 2013 中執行 ABC 集區容錯移轉的程式，其中有成對的 Lync Server 前端集區 A 和 B，而集區 A 將無法復原。</span><span class="sxs-lookup"><span data-stu-id="e8b1f-105">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="e8b1f-106">使用此程式，您可以建立新的前端集區 C，並使用新的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="e8b1f-106">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e8b1f-107">集區 C 是由失敗集區 A 的資訊所構造。此程式還包括將集區 B 和 C 結合在一起。</span><span class="sxs-lookup"><span data-stu-id="e8b1f-107">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="e8b1f-108">Lync Server 2013 中的 ABC 集區容錯移轉的備份必要條件</span><span class="sxs-lookup"><span data-stu-id="e8b1f-108">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="e8b1f-109">Lync Server 2013 中的前端集區 ABC 容錯移轉程式</span><span class="sxs-lookup"><span data-stu-id="e8b1f-109">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

