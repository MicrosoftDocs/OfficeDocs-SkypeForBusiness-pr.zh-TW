---
title: 從集區中移除前端伺服器
description: 從集區移除前端伺服器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551299"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="82004-103">從集區中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="82004-103">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82004-104">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="82004-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="82004-105">Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能作為獨立電腦存在。</span><span class="sxs-lookup"><span data-stu-id="82004-105">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="82004-106">它必須定義為前端集區，即使集區中只有一部電腦也一樣。</span><span class="sxs-lookup"><span data-stu-id="82004-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="82004-107">本主題將引導您完成從現有前端集區移除個別前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="82004-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="82004-108">如果前端伺服器是集區中的最後一部伺服器，或您要完全移除集區，請參閱 [移除前端集區或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="82004-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="82004-109">移除前端集區之前，不需要先移除個別的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="82004-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="82004-110">當您移除集區時，會移除每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="82004-110">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="82004-111">從集區移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="82004-111">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="82004-112">開啟 Lync Server 2013 前端伺服器，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="82004-112">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="82004-113">流覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="82004-113">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="82004-114">展開 [ **Enterprise Edition 前端**集區]，展開要移除前端伺服器的前端集區，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="82004-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

