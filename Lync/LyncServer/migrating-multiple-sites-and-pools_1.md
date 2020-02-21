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
ms.openlocfilehash: 9ed975a35c49bc5379a5cc2daf22bda729cbceee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>移轉多個網站與集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-08-26_

Lync Server 2013 支援多站台和多重集區的部署。 移轉多個集區從 Office Communications Server 2007 R2 至 Lync Server 2013 的程序需要下列考量：

1.  部署 Lync Server 2013 試驗集區之後, 您要定義將驗證功能的使用者移至 Lync Server 2013 集區] 和方法的試驗使用者子集。

2.  部署試驗集區中 Edge Server 之後，您需要驗證外部使用者能夠與 Lync Server 2013 集區通訊。

3.  從 Office Communications Server 2007 R2 Edge Server 同盟的路由至試驗的 Lync Server 2013 Edge Server 轉換之後，您需要驗證同盟的使用者能夠與 Lync Server 2013 集區通訊。

4.  移動所有使用者與非使用者的連絡人物件之後，您需要驗證 Office Communications Server 2007 R2 集區是空的。

5.  確認 Office Communications Server 2007 R2 集區空的之後, 您可以停用之集區。
    
    如需如何停用舊版 Office Communications Server 2007 R2 集區及伺服器的詳細資訊，請參閱[階段 10： 解除委任舊版站台](phase-10-decommission-legacy-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

