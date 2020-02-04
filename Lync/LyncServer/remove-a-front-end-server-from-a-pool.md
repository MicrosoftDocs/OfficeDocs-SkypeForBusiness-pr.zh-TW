---
title: 從集區中移除前端伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="13bd1-102">從集區中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="13bd1-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13bd1-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="13bd1-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="13bd1-104">Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能以獨立電腦的形式存在。</span><span class="sxs-lookup"><span data-stu-id="13bd1-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="13bd1-105">它必須定義為前端池，即使池中只有一個電腦。</span><span class="sxs-lookup"><span data-stu-id="13bd1-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="13bd1-106">本主題將引導您完成從現有的前端池移除個別前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="13bd1-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="13bd1-107">如果前端伺服器是池中的最後一個伺服器，或如果您要徹底移除該資源池，請參閱[移除前端池或標準版伺服器](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="13bd1-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="13bd1-108">移除前端池前，不需要移除個別的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="13bd1-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="13bd1-109">移除該池後，就會移除每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="13bd1-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="13bd1-110">從池中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="13bd1-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="13bd1-111">開啟 Lync Server 2013 前端伺服器，然後開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="13bd1-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="13bd1-112">流覽至 Lync Server 2010 節點。</span><span class="sxs-lookup"><span data-stu-id="13bd1-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="13bd1-113">展開 [**企業版前端池**]，展開要移除之前端伺服器的 [前端] 池，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="13bd1-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

