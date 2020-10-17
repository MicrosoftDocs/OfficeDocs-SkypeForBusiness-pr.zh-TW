---
title: Lync Server 2013：變更與前端集區相關聯的 Edge 集區
description: Lync Server 2013：變更與前端集區相關聯的 Edge 集區。
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
ms.openlocfilehash: ab22ba35420341e291d51a1ff012459840e63a56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543569"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="c7c5e-103">在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c7c5e-103">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7c5e-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c7c5e-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c7c5e-105">如果 Edge 集區失效但相同網站上的前端集區仍在執行，您將需要設定前端集區來使用其他網站上的 Edge 集區，直到失敗的 Edge 集區還原為止。</span><span class="sxs-lookup"><span data-stu-id="c7c5e-105">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="c7c5e-106">變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c7c5e-106">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="c7c5e-107">在拓撲產生器中，瀏覽至您需要變更的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="c7c5e-107">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="c7c5e-108">以滑鼠右鍵按一下集區，然後按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="c7c5e-108">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c7c5e-109">在 **[關聯]** 區段的 **[關聯 Edge 集區 (適用於媒體元件)]** 下方，使用下拉式方塊來選取您要與此前端集區產生關聯的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c7c5e-109">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="c7c5e-110">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7c5e-110">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7c5e-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7c5e-111">See Also</span></span>


[<span data-ttu-id="c7c5e-112">Lync Server 2013 中的 Edge Server 災難性修復</span><span class="sxs-lookup"><span data-stu-id="c7c5e-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

