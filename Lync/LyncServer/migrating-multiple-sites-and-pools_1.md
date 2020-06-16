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

# <a name="migrating-multiple-sites-and-pools"></a>移轉多個網站與集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-26_

Lync Server 2013 支援多個網站和多個集區的部署。 將多個集區從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013 的程式需要下列考慮：

1.  部署 Lync Server 2013 試驗集區之後，您必須定義將要移至 Lync Server 2013 集區的試驗使用者子集，以及驗證使用者功能的方法。

2.  在試驗集區中部署 Edge Server 之後，您需要驗證外部使用者是否可以與 Lync Server 2013 集區通訊。

3.  將 Office 通訊伺服器 2007 R2 Edge Server 的同盟路由轉換至試驗 Lync Server 2013 Edge server 之後，您需要驗證同盟使用者是否可以與 Lync Server 2013 集區通訊。

4.  移動所有使用者與非使用者的連絡人物件之後，您必須驗證 Office 通訊伺服器 2007 R2 集區是空的。

5.  確認 Office 通訊伺服器 2007 R2 集區是空的之後，即可停用該集區。
    
    如需如何停用舊版 Office 通訊伺服器 2007 R2 集區和伺服器的詳細資訊，請參閱第[10 階段：解除委任舊版網站](phase-10-decommission-legacy-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

