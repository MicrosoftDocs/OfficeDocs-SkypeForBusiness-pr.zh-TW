---
title: 移轉多個網站與集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="5e089-102">移轉多個網站與集區</span><span class="sxs-lookup"><span data-stu-id="5e089-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e089-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="5e089-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="5e089-104">Lync Server 2013 支援多網站和多池部署。</span><span class="sxs-lookup"><span data-stu-id="5e089-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="5e089-105">從 Lync Server 2010 將多個池遷移至 Lync Server 2013 的程式需要下列考慮：</span><span class="sxs-lookup"><span data-stu-id="5e089-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="5e089-106">部署 Lync Server 2013 試驗池之後，您必須定義將會移至 Lync Server 2013 池的試驗使用者子集，以及驗證使用者功能的方法。</span><span class="sxs-lookup"><span data-stu-id="5e089-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="5e089-107">例如，將使用者移至 [試驗] 池之後，請確認使用者的會議原則已移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5e089-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="5e089-108">在試驗池中部署邊緣伺服器之後，您必須驗證外部使用者可以與 Lync Server 2013 池進行通訊。</span><span class="sxs-lookup"><span data-stu-id="5e089-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="5e089-109">將 Lync Server 2010 Edge 伺服器的同盟路由轉換為試驗 Lync Server 2013 Edge 伺服器之後，您必須驗證聯盟使用者可以與 Lync Server 2013 池進行通訊。</span><span class="sxs-lookup"><span data-stu-id="5e089-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="5e089-110">移動所有使用者和非使用者連絡人物件之後，您必須驗證 Lync Server 2010 池是否為空白。</span><span class="sxs-lookup"><span data-stu-id="5e089-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="5e089-111">驗證 Lync Server 2010 池為空白之後，您就可以將該池停用。</span><span class="sxs-lookup"><span data-stu-id="5e089-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="5e089-112">如需如何停用舊版 Lync Server 2010 池和伺服器的詳細資料，請參閱[階段8：解除舊版池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="5e089-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

