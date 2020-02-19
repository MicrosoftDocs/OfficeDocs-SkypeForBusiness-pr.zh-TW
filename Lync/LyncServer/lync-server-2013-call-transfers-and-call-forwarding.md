---
title: Lync Server 2013： 來電轉接和來電轉接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2d258b5820c95b346c76fb5ee7e47e9749c617
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>來電轉接和 Lync Server 2013 中來電轉接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

如果包含 PSTN 端點，位置型路由會分析 calle 端點及傳送或轉寄給 （亦即傳輸/順向目標） 通話的結束點的位置。 位置型路由會決定在呼叫是否應該轉接或轉寄根據這兩個端點的位置。

下表說明的案例中使用 PSTN 端點，呼叫 Lync 使用者與 Lync 使用者將轉接至另一位 Lync 使用者的呼叫。 未經的端點的網路站台位置，根據位置型路由會影響路由的來電轉接或轉寄。

### <a name="initiating-call-transfer-or-forward"></a>起始通話轉接或轉寄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者初始化通話轉接/轉寄</th>
<th>目標端點位於相同的網路網站，以初始化來電轉接或順向使用者</th>
<th>目標端點以初始化來電轉接或順向使用者位於不同的網路網站</th>
<th>目標端點無法辨識的網路站台或網路網站中未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>轉接通話] 或 [允許傳輸</p></td>
<td><p>轉接通話] 或 [不允許轉接</p></td>
<td><p>轉接通話] 或 [不允許轉接</p></td>
</tr>
</tbody>
</table>

  

例如： 與 PSTN 端點的呼叫中的 Lync 使用者將在相同的網路站台的另一位 Lync 使用者通話轉接。 在此情況下，允許通話轉接。

下表說明的另一位 Lync 使用者，在呼叫 Lync 使用者的案例，並有一位使用者轉接至 PSTN 端點的呼叫。 視呼叫會轉接至表格詳細資料如何之使用者的位置而定位置型路由會影響通話。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>來電轉接或轉接至 PSTN 端點

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫傳輸/順向端點目標</th>
<th>Lync 使用者在相同的網路網站</th>
<th>Lync 使用者在不同的網路網站</th>
<th>不明的網路站台或未啟用位置型路由的網路網站中的一或兩個 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>轉接通話] 或 [傳送的使用者的網站語音路由原則所允許的轉接</p></td>
<td><p>轉接通話] 或 [傳送的使用者的網站語音路由原則所允許的轉接</p></td>
<td><p>轉接通話] 或 [只能透過主幹傳送的使用者的語音原則允許傳輸未啟用位置型的路由</p></td>
</tr>
</tbody>
</table>

  
例如： Lync 使用者的呼叫中具有相同的網路站台中的另一位 Lync 使用者轉接至 PSTN 端點的呼叫，並允許來電轉接。

<div>

## <a name="see-also"></a>另請參閱


[依位置路由 Lync Server 2013 中的案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

