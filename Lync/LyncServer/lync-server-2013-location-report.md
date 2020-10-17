---
title: Lync Server 2013：位置報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e98107d4949a935cbef448e1a533bddb0f7c5dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513790"
---
# <a name="location-report-in-lync-server-2013"></a>Lync Server 2013 中的位置報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

位置報告提供依網路位置 (，也就是由網路子網) 分組之通話品質計量的相關資訊。 如果使用者遇到來電問題，此報告可協助您判斷這些問題是否受到廣泛使用，或是主要局限于指定的網段。

<div>

## <a name="accessing-the-location-report"></a>存取位置報告

您可以從監控報告首頁存取位置報告。 您可以按一下下列其中一項度量，向下流覽通話清單報告：

  - 通話數量

  - 通話百分比不佳

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，位置報告可讓您篩選出呼叫來源所在的位置，或是呼叫是否發生在無線或有線連線上。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配位置報告使用的篩選器。

### <a name="location-report-filters"></a>位置報表篩選

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
<td><p><strong>來電者位置</strong></p></td>
<td><p>撥打通話之使用者的 IP 子網。 您只可以選取 <strong>[全部]</strong> ，以表示所有子網。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者位置</strong></p></td>
<td><p>接收通話之使用者的 IP 子網。 您只可以選取 <strong>[全部]</strong> ，以表示所有子網。</p></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ol>
<li><p>一切</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<ol>
<li><p>一切</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出位置報告中提供的資訊。

### <a name="location-report-metrics"></a>位置報告度量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>來電者子網</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 IP 子網。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者子網</strong></p></td>
<td><p>否</p></td>
<td><p>接收通話之使用者的 IP 子網。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話數量</strong></p></td>
<td><p>是</p></td>
<td><p>發出的呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>是</p></td>
<td><p>分類為不良通話的通話百分比。 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來回行程 (毫秒) </strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。 在100毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>MOS) 降級 (</strong></p></td>
<td><p>是</p></td>
<td><p>通話期間 (MOS) 效能的平均平均觀點量。 降級值的範圍從低0.0 到高5.0。 值0.5 或更少代表可接受的降級。 在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。 高降級導致音訊失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 封包遺失的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>是</p></td>
<td><p>隱藏音訊樣本的平均比率與樣本總數總數。  (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復延伸比率</strong></p></td>
<td><p>是</p></td>
<td><p>延伸音訊樣本的平均比例與樣本總數總數。  (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復壓縮比例</strong></p></td>
<td><p>是</p></td>
<td><p>壓縮音訊樣本的平均比率與樣本總數。  (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

