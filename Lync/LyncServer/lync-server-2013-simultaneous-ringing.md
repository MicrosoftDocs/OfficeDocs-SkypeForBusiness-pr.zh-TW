---
title: Lync Server 2013： 同時響鈴
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c05122bb2d6f8f0c9b21aeb12c6e889e3f98750
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>同時響鈴的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

當受話的方具有已啟用同時響鈴時，位置型路由會分析的呼叫方的位置和受話方設定決定是否應路由傳送通話的端點。

下表說明設定與同時響鈴的使用者，同時響鈴的目標是相同的網路站台、 不同的網路網站，或無法辨識的網路網站的使用者。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>傳入 PSTN 通話</th>
<th>位於與受話者位於相同網路站台</th>
<th>位於比受話者的不同的網路網站</th>
<th>位於不明的網路站台或未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>允許的同時響鈴</p></td>
<td><p>不允許的同時響鈴</p></td>
<td><p>不允許的同時響鈴</p></td>
</tr>
</tbody>
</table>

  
下表說明從 Lync 使用者 （亦即 Lync 呼叫者） 的呼叫中相同的網路網站，在不同的網路網站中，或從不明的網路網站。 受話者已設定為同時響鈴目標 PSTN 端點 （亦即行動電話）。 在此案例中，位置型路由會決定是否在呼叫應被路由傳送至受話者的同時響鈴目標 (亦即 cellphone) 或不。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時響鈴目標</th>
<th>位於與受話者位於相同網路站台</th>
<th>位於比受話者的不同的網路網站</th>
<th>位於不明的網路站台或未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>透過發話者網站的語音路由原則所允許的同時響鈴</p></td>
<td><p>透過發話者網站的語音路由原則所允許的同時響鈴</p></td>
<td><p>發話者的語音原則未啟用位置型路由的主幹，透過允許的同時響鈴</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另請參閱


[依位置路由 Lync Server 2013 中的案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

