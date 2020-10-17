---
title: Lync Server 2013：監控後端 Lync Server 儲存效能
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
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531950"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>監視後端 Lync Server 2013 儲存效能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-02_

Lync Server 2013 後端資料庫是 Lync Server 2013 部署中非常重要的部分。 我們建議您不斷監控資料庫和各自的交易記錄，以協助確保 Lync Server 2013 後端的執行效果最佳。

下表識別應監控的效能計數器，以瞭解儲存效能的相關資訊。 當系統處於其正常的負載) 時，必須先判斷這些計數器的比較基準值，以瞭解系統負載壓力下的效能變更時 (。

### <a name="performance-counters-to-be-monitored"></a>要監視的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>效能計數器</th>
<th>基準閾值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒交易 (RTC) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每秒交易 (rtcdyn) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每秒交易 (tempdb) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p> (RTC) 的記錄檔刷新次數/秒</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>記錄檔刷新次數/秒 (rtcdyn) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>記錄檔刷新次數/秒 (tempdb) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁片傳輸/秒 (讀取 + 寫入) RTC db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁片傳輸/秒-RTC 記錄</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁片傳輸/秒-rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁片傳輸/秒-rtcdyn 記錄</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

