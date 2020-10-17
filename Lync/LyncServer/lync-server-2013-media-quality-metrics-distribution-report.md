---
title: Lync Server 2013：媒體質量計量散佈報告
description: Lync Server 2013：媒體質量計量散佈報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548149"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體質量計量散佈報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

媒體質量計量散佈報告可讓您查看顯示品質狀況（如抖動或封包遺失）之分配值的圖形。 例如，假設您的使用者總共撥打了10次通話;這10個通話會報告下列往返時間：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通話號碼</th>
<th>往返時間 (毫秒) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>第</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>個</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


這些往返時間的平均值是500毫秒 (5000 除以 10) 。 500毫秒是極大的往返時間;因此，您可能會相信，網路擁塞發生嚴重問題。  (長的往返時間通常是超載網路的結果。 ) 

當然，在現實中，90% 的來電已有極好的來回行程時間;您只會有一個會使整體結果歪斜的錯誤通話。 如果您只查看平均往返時間，您可能會跳到錯誤的結論。

媒體質量計量散佈報告可讓您透過顯示指定指標 (例如來回行程時間) ，來協助您避免跳到錯誤結論。 這兩個圖形可協助您明確您有九個非常好的呼叫和一個極壞的通話。 無可否認，您可能仍要進一步調查此呼叫;不過，10個通話中的九個事實很不錯，這表示沒有理由對您的網路進行任何重大的變更，至少此時間不是這麼。

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以搭配媒體質量計量散佈報告使用的篩選器。

### <a name="media-quality-metrics-distribution-report-filters"></a>媒體質量計量散佈報告篩選器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>X 軸的最小值</strong></p></td>
<td><p>要在圖形的 X 軸上顯示的最低值。</p></td>
</tr>
<tr class="even">
<td><p><strong>X 軸的最大值</strong></p></td>
<td><p>要在圖形的 X 軸上顯示的最高值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>內部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

