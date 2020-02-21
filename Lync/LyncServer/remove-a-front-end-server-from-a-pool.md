---
title: 從集區移除前端伺服器
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
ms.openlocfilehash: 2e9cd348d6a96009e92dfa8a3ef50dae39eb013d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="166b6-102">從集區移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="166b6-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="166b6-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="166b6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="166b6-104">Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能存在於做為獨立的電腦。</span><span class="sxs-lookup"><span data-stu-id="166b6-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="166b6-105">它必須定義為前端集區，即使有只有單一電腦集區中。</span><span class="sxs-lookup"><span data-stu-id="166b6-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="166b6-106">本主題會引導您完成程序移除現有前端集區中的個別前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="166b6-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="166b6-107">如果前端伺服器集區中的最後一部伺服器，或如果您要完全移除集區，請參閱[移除前端集區或 Standard Edition server](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="166b6-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="166b6-108">沒有需要移除個別前端伺服器，然後再移除前端集區。</span><span class="sxs-lookup"><span data-stu-id="166b6-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="166b6-109">當您移除集區時，即會移除每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="166b6-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="166b6-110">從集區移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="166b6-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="166b6-111">開啟 Lync Server 2013 前端伺服器]，再開啟拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="166b6-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="166b6-112">瀏覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="166b6-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="166b6-113">依序展開 [ **Enterprise Edition 前端集區]**，依序展開 [前端集區與前端伺服器，您想要移除，以滑鼠右鍵按一下您要移除以前端伺服器，然後按一下 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="166b6-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

