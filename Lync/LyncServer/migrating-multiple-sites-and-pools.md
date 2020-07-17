---
title: 移轉多個網站與集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="fa80a-102">移轉多個網站與集區</span><span class="sxs-lookup"><span data-stu-id="fa80a-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa80a-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fa80a-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fa80a-104">Lync Server 2013 支援多個網站和多個集區的部署。</span><span class="sxs-lookup"><span data-stu-id="fa80a-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="fa80a-105">將多個集區從 Lync Server 2010 遷移至 Lync Server 2013 的程式需要下列考慮：</span><span class="sxs-lookup"><span data-stu-id="fa80a-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="fa80a-106">部署 Lync Server 2013 試驗集區之後，您必須定義將要移至 Lync Server 2013 集區的試驗使用者子集，以及驗證使用者功能的方法。</span><span class="sxs-lookup"><span data-stu-id="fa80a-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="fa80a-107">例如，將使用者移至試驗集區後，請確認使用者的會議原則已移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fa80a-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="fa80a-108">在試驗集區中部署 Edge Server 之後，您需要驗證外部使用者是否可以與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="fa80a-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="fa80a-109">將同盟路由從 Lync Server 2010 Edge server 轉換至試驗 Lync Server 2013 Edge server 之後，您需要驗證同盟使用者是否可以與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="fa80a-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="fa80a-110">移動所有使用者與非使用者的連絡人物件之後，您必須驗證 Lync Server 2010 集區是否為空。</span><span class="sxs-lookup"><span data-stu-id="fa80a-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="fa80a-111">在確認 Lync Server 2010 集區是空的之後，即可停用該集區。</span><span class="sxs-lookup"><span data-stu-id="fa80a-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="fa80a-112">如需如何停用舊版 Lync Server 2010 集區和伺服器的詳細資訊，請參閱[階段8：解除委任舊版](phase-8-decommission-legacy-pools.md)集區。</span><span class="sxs-lookup"><span data-stu-id="fa80a-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

