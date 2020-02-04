---
title: Lync Server 2013：變更與前端集區相關聯的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736ed552a51182102310f4e10eb28472b251eb22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="5dcbb-102">在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="5dcbb-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dcbb-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5dcbb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5dcbb-104">如果邊緣池向下移動，但位於相同網站的前端池仍在執行，則您必須將前端池設定為在不同的網站上使用 Edge 池，直到失敗的邊緣池已復原為止。</span><span class="sxs-lookup"><span data-stu-id="5dcbb-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="5dcbb-105">變更與前端池相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="5dcbb-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="5dcbb-106">在 [拓撲建立器] 中，流覽至您需要變更的前端池名稱。</span><span class="sxs-lookup"><span data-stu-id="5dcbb-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="5dcbb-107">以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5dcbb-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5dcbb-108">在 [**關聯**性] 區段的 [**關聯邊緣池（適用于媒體元件）**] 底下，使用下拉式方塊來選取您要與此前端池建立關聯的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="5dcbb-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="5dcbb-109">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5dcbb-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5dcbb-110">請參閱</span><span class="sxs-lookup"><span data-stu-id="5dcbb-110">See Also</span></span>


[<span data-ttu-id="5dcbb-111">Lync Server 2013 中的 Edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="5dcbb-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

