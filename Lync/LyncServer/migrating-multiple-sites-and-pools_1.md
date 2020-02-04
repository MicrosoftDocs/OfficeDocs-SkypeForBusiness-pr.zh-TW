---
title: 移轉多個網站與集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ff9164dcd824d6b836577b04783954cb81b067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>移轉多個網站與集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-26_

Lync Server 2013 支援多網站和多池部署。 從 Office 通訊伺服器 2007 R2 將多個池遷移到 Lync Server 2013 的程式需要下列考慮：

1.  部署 Lync Server 2013 試驗池之後，您必須定義將會移至 Lync Server 2013 池的試驗使用者子集，以及驗證使用者功能的方法。

2.  在試驗池中部署邊緣伺服器之後，您必須驗證外部使用者可以與 Lync Server 2013 池進行通訊。

3.  將 Office 通訊伺服器 2007 R2 Edge 伺服器的聯盟路由轉換為試驗 Lync Server 2013 Edge 伺服器之後，您必須驗證聯盟使用者是否可以與 Lync Server 2013 池通訊。

4.  移動所有使用者和非使用者連絡人物件之後，您必須確認 Office 通訊伺服器 2007 R2 池是空的。

5.  確認 Office 通訊伺服器 2007 R2 池為空白之後，您就可以將該池停用。
    
    如需如何停用舊版 Office 通訊伺服器 2007 R2 池和伺服器的詳細資料，請參閱[階段10：解除舊版網站](phase-10-decommission-legacy-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

