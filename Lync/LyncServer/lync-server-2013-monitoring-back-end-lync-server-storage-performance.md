---
title: Lync Server 2013：監視後端 Lync 伺服器儲存效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>監視後端 Lync Server 2013 儲存效能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-02_

Lync Server 2013 後端資料庫是 Lync Server 2013 部署中非常重要的部分。 我們建議您持續監視資料庫及各個事務記錄，以協助確定 Lync Server 2013 後端執行效果最佳。

下表列出應監視的效能計數器，以瞭解儲存效能的相關資訊。 必須先決定這些計數器的比較基準值（系統是其正常負載預期載入），以瞭解系統負載壓力時的效能變更。

### <a name="performance-counters-to-be-monitored"></a>要監視的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>效能計數器</th>
<th>比較基準閾值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>事務/秒（RTC）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>事務/秒（rtcdyn）</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>事務/秒（tempdb）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>記錄刷新/秒（RTC）</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>記錄刷新/秒（rtcdyn）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>記錄刷新/秒（tempdb）</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁片傳輸/秒（讀取 + 寫入）-RTC 資料庫</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁片傳輸/秒-RTC 記錄</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁片傳輸/sec-rtcdyn db</p></td>
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

