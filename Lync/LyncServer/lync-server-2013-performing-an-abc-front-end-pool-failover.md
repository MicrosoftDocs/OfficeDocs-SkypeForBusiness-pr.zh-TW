---
title: Lync Server 2013：執行 ABC 前端池容錯移轉
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
ms.openlocfilehash: 155d8224b80e614ac8609c007a16072e9d3a5c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="2723c-102">在 Lync Server 2013 中執行 ABC 前端池容錯移轉</span><span class="sxs-lookup"><span data-stu-id="2723c-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2723c-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2723c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2723c-104">本節中的兩個主題描述在 Lync Server 2013 中執行 ABC 池容錯移轉的程式，其中有成對的 Lync Server 前端池 A 和 B，而 A; 池 A 變為無法還原。</span><span class="sxs-lookup"><span data-stu-id="2723c-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="2723c-105">使用此程式，您可以使用新的完整功能變數名稱（FQDN）來建立新的前端池 C。</span><span class="sxs-lookup"><span data-stu-id="2723c-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2723c-106">Pool C 是由來自失敗的池 A 的資訊所構造。此程式也包括將同一個池 B 和 C 配對。</span><span class="sxs-lookup"><span data-stu-id="2723c-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="2723c-107">Lync Server 2013 中 ABC 池容錯移轉的備份先決條件</span><span class="sxs-lookup"><span data-stu-id="2723c-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="2723c-108">Lync Server 2013 中的前端集區 ABC 容錯移轉程序</span><span class="sxs-lookup"><span data-stu-id="2723c-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

