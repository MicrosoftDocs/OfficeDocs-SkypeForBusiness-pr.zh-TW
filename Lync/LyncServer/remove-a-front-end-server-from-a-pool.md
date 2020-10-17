---
title: 從集區中移除前端伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cfcd96d0663ca977c83cc90b56bcafd9359a038
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500160"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>從集區中移除前端伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能作為獨立電腦存在。 它必須定義為前端集區，即使集區中只有一部電腦也一樣。

本主題將引導您完成從現有前端集區移除個別前端伺服器的程式。 如果前端伺服器是集區中的最後一部伺服器，或您要完全移除集區，請參閱 [移除前端集區或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。 移除前端集區之前，不需要先移除個別的前端伺服器。 當您移除集區時，會移除每個前端伺服器。

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>從集區移除前端伺服器

1.  開啟 Lync Server 2013 前端伺服器，開啟拓撲產生器。

2.  流覽至 [Lync Server 2010] 節點。

3.  展開 [ **Enterprise Edition 前端**集區]，展開要移除前端伺服器的前端集區，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [ **刪除**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

