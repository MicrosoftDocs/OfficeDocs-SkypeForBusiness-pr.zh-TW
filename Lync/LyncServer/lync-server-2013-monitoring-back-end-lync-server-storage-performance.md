---
title: Lync Server 2013： 監控端 Lync Server 儲存體效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4ab62bdbb9b33a7c64014433dfd4f950a6298
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>監視後端 Lync Server 2013 儲存體效能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-02_

Lync Server 2013 後端資料庫是非常重要的 Lync Server 2013 部署的一部分。 我們建議您持續監控資料庫和各自的交易記錄，以協助確定 Lync Server 2013 back end 最佳狀態執行。

下表列出應監視以了解儲存效能的相關資訊的效能計數器。 這些計數器的基準值必須判斷第一次 （當系統在其正常負載） 若要了解效能變更，當負荷系統。

### <a name="performance-counters-to-be-monitored"></a>要監視的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>效能計數器</th>
<th>[比較基準臨界值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>交易/秒 (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>交易/秒 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>交易/秒 (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>記錄清除/秒 (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>記錄清除/秒 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>記錄清除/秒 (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁碟傳輸/秒 （讀取 + 寫入）-RTC db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁碟傳輸/秒-RTC 記錄檔</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁碟傳輸/秒-rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁碟傳輸/秒-rtcdyn 記錄檔</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

