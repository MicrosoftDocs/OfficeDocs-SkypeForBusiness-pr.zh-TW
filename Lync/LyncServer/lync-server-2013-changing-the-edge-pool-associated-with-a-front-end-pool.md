---
title: Lync Server 2013： 變更與前端集區相關聯的 Edge 集區
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
ms.openlocfilehash: 73d28a6641df35ac1de29fb1f6668e628e8e0ec9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="171ad-102">變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="171ad-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="171ad-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="171ad-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="171ad-104">如果 Edge 集區失效但相同網站上的前端集區仍在執行，您將需要設定前端集區來使用其他網站上的 Edge 集區，直到失敗的 Edge 集區還原為止。</span><span class="sxs-lookup"><span data-stu-id="171ad-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="171ad-105">變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="171ad-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="171ad-106">在拓撲產生器中，瀏覽至您需要變更的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="171ad-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="171ad-107">以滑鼠右鍵按一下集區，然後按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="171ad-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="171ad-108">在 **[關聯]** 區段的 **[關聯 Edge 集區 (適用於媒體元件)]** 下方，使用下拉式方塊來選取您要與此前端集區產生關聯的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="171ad-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="171ad-109">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="171ad-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="171ad-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="171ad-110">See Also</span></span>


[<span data-ttu-id="171ad-111">Lync Server 2013 中的 edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="171ad-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

