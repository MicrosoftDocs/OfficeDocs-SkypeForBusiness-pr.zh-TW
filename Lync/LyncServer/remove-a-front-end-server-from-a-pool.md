---
title: 從集區中移除前端伺服器
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
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>從集區中移除前端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能以獨立電腦的形式存在。 它必須定義為前端池，即使池中只有一個電腦。

本主題將引導您完成從現有的前端池移除個別前端伺服器的程式。 如果前端伺服器是池中的最後一個伺服器，或如果您要徹底移除該資源池，請參閱[移除前端池或標準版伺服器](remove-front-end-pool-or-standard-edition-server.md)。 移除前端池前，不需要移除個別的前端伺服器。 移除該池後，就會移除每個前端伺服器。

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>從池中移除前端伺服器

1.  開啟 Lync Server 2013 前端伺服器，然後開啟 [拓撲建立器]。

2.  流覽至 Lync Server 2010 節點。

3.  展開 [**企業版前端池**]，展開要移除之前端伺服器的 [前端] 池，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

