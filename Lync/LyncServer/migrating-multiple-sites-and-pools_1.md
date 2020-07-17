---
title: 移轉多個網站與集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efbad7107109096a5f17d82912353e6f8a1a14a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="7d617-102">移轉多個網站與集區</span><span class="sxs-lookup"><span data-stu-id="7d617-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d617-103">_**主題上次修改日期：** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="7d617-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="7d617-104">Lync Server 2013 支援多個網站和多個集區的部署。</span><span class="sxs-lookup"><span data-stu-id="7d617-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="7d617-105">將多個集區從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013 的程式需要下列考慮：</span><span class="sxs-lookup"><span data-stu-id="7d617-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="7d617-106">部署 Lync Server 2013 試驗集區之後，您必須定義將要移至 Lync Server 2013 集區的試驗使用者子集，以及驗證使用者功能的方法。</span><span class="sxs-lookup"><span data-stu-id="7d617-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="7d617-107">在試驗集區中部署 Edge Server 之後，您需要驗證外部使用者是否可以與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="7d617-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="7d617-108">將 Office 通訊伺服器 2007 R2 Edge Server 的同盟路由轉換至試驗 Lync Server 2013 Edge server 之後，您需要驗證同盟使用者是否可以與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="7d617-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="7d617-109">移動所有使用者與非使用者的連絡人物件之後，您必須驗證 Office 通訊伺服器 2007 R2 集區是空的。</span><span class="sxs-lookup"><span data-stu-id="7d617-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="7d617-110">確認 Office 通訊伺服器 2007 R2 集區是空的之後，即可停用該集區。</span><span class="sxs-lookup"><span data-stu-id="7d617-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="7d617-111">如需如何停用舊版 Office 通訊伺服器 2007 R2 集區和伺服器的詳細資訊，請參閱第[10 階段：解除委任舊版網站](phase-10-decommission-legacy-site.md)。</span><span class="sxs-lookup"><span data-stu-id="7d617-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

