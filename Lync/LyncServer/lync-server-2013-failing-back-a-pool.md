---
title: Lync Server 2013：容錯回復集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ad8ee15d0242a5512284e00064dfe9b49c41c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522360"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中回復集區失敗

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在發生災難的集區重新連線後 (如此範例中的 Pool1)，請採取下列步驟將部署還原至正常運作狀態。

請注意，容錯回復程序需要數分鐘才能完成。僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。

1.  若要容錯回復原來位於 Pool1 而容錯移轉至 Pool2 的使用者，請鍵入下列 Cmdlet：
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

無需其他步驟。 如果您已對中央管理伺服器進行容錯移轉，您可以將它保留在 Pool2 中。

</div>

<span> </span>

</div>

</div>

</div>

