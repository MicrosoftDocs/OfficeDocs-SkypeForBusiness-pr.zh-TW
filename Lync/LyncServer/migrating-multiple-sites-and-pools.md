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
ms.openlocfilehash: 52e14cccb9856534ea9b7229fd020edc2ec21dba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="4505e-102">移轉多個網站與集區</span><span class="sxs-lookup"><span data-stu-id="4505e-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4505e-103">_**主題上次修改日期：** 2012年-09-17_</span><span class="sxs-lookup"><span data-stu-id="4505e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="4505e-104">Lync Server 2013 支援多站台和多重集區的部署。</span><span class="sxs-lookup"><span data-stu-id="4505e-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="4505e-105">從 Lync Server 2010 的多個集區移轉至 Lync Server 2013 的程序需要下列考量：</span><span class="sxs-lookup"><span data-stu-id="4505e-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="4505e-106">部署 Lync Server 2013 試驗集區之後, 您要定義將驗證功能的使用者移至 Lync Server 2013 集區] 和方法的試驗使用者子集。</span><span class="sxs-lookup"><span data-stu-id="4505e-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="4505e-107">例如之後將使用者移至試驗集區，, 請確認使用者的會議原則已移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4505e-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="4505e-108">部署試驗集區中 Edge Server 之後，您需要驗證外部使用者能夠與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="4505e-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="4505e-109">從 Lync Server 2010 Edge Server 同盟的路由至試驗的 Lync Server 2013 Edge Server 轉換之後，您需要驗證同盟的使用者能夠與 Lync Server 2013 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="4505e-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="4505e-110">移動所有使用者與非使用者的連絡人物件之後，您需要驗證的 Lync Server 2010 集區是空的。</span><span class="sxs-lookup"><span data-stu-id="4505e-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="4505e-111">確認 Lync Server 2010 集區空的之後, 您可以停用之集區。</span><span class="sxs-lookup"><span data-stu-id="4505e-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="4505e-112">如需如何停用舊版 Lync Server 2010 集區及伺服器的詳細資訊，請參閱[階段 8： 解除委任舊版的集區](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="4505e-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

