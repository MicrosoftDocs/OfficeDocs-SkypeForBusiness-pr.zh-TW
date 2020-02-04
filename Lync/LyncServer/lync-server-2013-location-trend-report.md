---
title: Lync Server 2013：位置趨勢報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f825a33eeb90817685c1694a5c6579110ffcd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a>Lync Server 2013 中的位置趨勢報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

[位置趨勢] 報告可提供網路位置的通話品質趨勢資訊。

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[位置趨勢] 報告可讓您篩選傳回的資料，例如存取類型（也就是間隔存取與外部存取）或有線/無線網路連線等專案。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、天或周分組。

下表列出可與 [位置趨勢] 報表搭配使用的篩選。

### <a name="location-trend-report-filters"></a>位置趨勢報表篩選

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
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列其中一項：</p>
<ul>
<li><p>每小時（最多可顯示25小時）</p></li>
<li><p>每天（最多可以顯示31天）</p></li>
<li><p>每週（最多可以顯示12周）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 1/1/2011] 和 [結束日期] 2/28/2011 的 [日間隔]，則會顯示 8/1/2011 12:00 AM 至 9/1/2011 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>Access 類型</strong></p></td>
<td><p>指出撥打電話時，用戶端是否已登入內部網路或外部網路。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>內部</p></li>
<li><p>外來</p></li>
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
<tr class="even">
<td><p><strong>點對點</strong></p></td>
<td><p>指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
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

