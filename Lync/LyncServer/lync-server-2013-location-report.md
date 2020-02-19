---
title: Lync Server 2013： 位置報告
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
ms.openlocfilehash: 0afe9de5220c81985ad4efc0f9c27d5ab87c325a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a>Lync Server 2013 中的位置報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

位置報告提供有關通話品質計量依據網路位置資訊 (也就是由網路子網路)。 如果您的使用者遇到其通話的問題，這份報告可以協助您判斷如果這些問題時遇到的普遍，或者主要限於特定的網路區段。

<div>

## <a name="accessing-the-location-report"></a>存取位置報告

從監視報告首頁存取位置報告。 您可以按一下向下切入 Call List Report 下列計量之一：

  - [通話數

  - 通話不良百分比

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，位置報告可讓您篩選上為呼叫起源的所在位置，或是否通話中發生了在無線或有線的連線等項目。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配位置報告的篩選器。

### <a name="location-report-filters"></a>位置報告篩選器

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
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來電者位置</strong></p></td>
<td><p>撥打通話之使用者的 IP 子網路。 您只能選取<strong>[全部]</strong>表示所有子網路。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者位置</strong></p></td>
<td><p>接到電話之使用者的 IP 子網路。 您只能選取<strong>[全部]</strong>表示所有子網路。</p></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出位置報告中提供的資訊。

### <a name="location-report-metrics"></a>位置報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>呼叫者子網路</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 IP 子網路。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者子網路</strong></p></td>
<td><p>否</p></td>
<td><p>接到電話之使用者的 IP 子網路。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[通話數</strong></p></td>
<td><p>是</p></td>
<td><p>撥打的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>是</p></td>
<td><p>通話歸類為不良通話百分比。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="odd">
<td><p><strong>往返時間 （毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。 100 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>降低 (MOS)</strong></p></td>
<td><p>是</p></td>
<td><p>平均量平均意見分數 (MOS) 降低在通話期間發生。 為 [高] 的 5.0，降低值可介於 0.0 的低。 為 0.5 或更低的值代表可接受的效能下降。 在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</p>
<p>高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。 高降低的情形會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動</strong></p></td>
<td><p>是</p></td>
<td><p>偵測到之間 RTP 封包抵達的平均抖動值。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>是</p></td>
<td><p>之隱藏樣本總數總計的音訊樣本的平均比率。 （隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復延伸的比率</strong></p></td>
<td><p>是</p></td>
<td><p>範例總數總計的延伸音訊樣本的平均比率。 （延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復壓縮的比率</strong></p></td>
<td><p>是</p></td>
<td><p>範例總數的壓縮音訊樣本的平均比率。 （壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

