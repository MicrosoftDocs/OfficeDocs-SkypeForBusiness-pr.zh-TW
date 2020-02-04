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
ms.openlocfilehash: 91e1dca7ffc210e9b44913f21846726f7a776912
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中容錯回復集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

當發生災難的池回到線上（也就是在這個範例中 Pool1）之後，請執行下列步驟，將您的部署還原為一般的工作狀態。

請注意，容錯回復程式需要幾分鐘的時間才能完成。針對參考，對於20000使用者，預期會需要最多60分鐘的時間。

1.  您可以輸入下列 Cmdlet，以容錯回復傳回 Pool1 且已容錯移轉至 Pool2 的使用者：
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

不需要其他步驟。 如果您未通過中央管理伺服器進行容錯移轉，您可以將它留在 Pool2 中。

</div>

<span> </span>

</div>

</div>

</div>

