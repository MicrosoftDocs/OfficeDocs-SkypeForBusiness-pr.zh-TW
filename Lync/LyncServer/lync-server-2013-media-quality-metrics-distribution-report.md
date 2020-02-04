---
title: Lync Server 2013：媒體質量度量值分佈報告
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
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體質量度量分佈報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

媒體質量度量分佈報告可讓您查看顯示品質統計資料（例如抖動或資料包遺失）的分配值的圖形。 例如，假設您的使用者總共撥打10個通話;這10個通話會報告下列往返時間：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通話號碼</th>
<th>往返時間（毫秒）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>500</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>utf-7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>型</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>第</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


這些往返時間的平均值是500毫秒（5000除以10）。 500毫秒是相當大的往返時間;因此，您可能會相信您的網路擁塞存在嚴重問題。 （較長的往返時間通常是超載網路的結果）。

當然，事實上，90% 的通話時間有極好的往返行程;您只會有一個不正確的呼叫會將整體結果扭曲。 如果您只看看平均往返時間，可能會跳到一個非常錯誤的結論。

媒體質量度量分佈報告可讓您透過顯示指定指標的圖形化分佈（例如往返行程時間），協助您避免跳躍到錯誤的結論。 這些圖形可以讓您清楚，看看有九個好用的通話，還有一個非常糟糕的通話。 無可否認，您可能仍想要進一步調查該通話;不過，10個通話中有九不只是為了讓您的網路受到任何重大變更，至少不需要您在這個時間點。

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出您可搭配媒體質量規格分佈報告使用的篩選。

### <a name="media-quality-metrics-distribution-report-filters"></a>媒體質量度量分佈報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期/時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>X 軸中的最小值</strong></p></td>
<td><p>要在圖表的 X 軸上顯示的最小值。</p></td>
</tr>
<tr class="even">
<td><p><strong>X 軸中的最大值</strong></p></td>
<td><p>要在圖表的 X 軸上顯示的最高值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Access 類型</strong></p></td>
<td><p>指出撥打電話時，用戶端是否已登入內部網路或外部網路。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>內部</p></li>
<li><p>外來</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>點對點</strong></p></td>
<td><p>指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出撥打電話時，用戶端連線到的網路類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
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

