---
title: Lync Server 2013：變更與前端集區相關聯的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

如果邊緣池向下移動，但位於相同網站的前端池仍在執行，則您必須將前端池設定為在不同的網站上使用 Edge 池，直到失敗的邊緣池已復原為止。

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>變更與前端池相關聯的邊緣池

1.  在 [拓撲建立器] 中，流覽至您需要變更的前端池名稱。

2.  以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。

3.  在 [**關聯**性] 區段的 [**關聯邊緣池（適用于媒體元件）**] 底下，使用下拉式方塊來選取您要與此前端池建立關聯的邊緣池。

4.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 Edge Server 災害復原](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

