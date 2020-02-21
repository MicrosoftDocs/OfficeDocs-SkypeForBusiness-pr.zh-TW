---
title: Lync Server 2013： 會議診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb475db2d1a12dcfc2b95dbf4711191767b18236
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的會議診斷報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

會議診斷報告提供的成功和失敗的所有會議工作階段的相關資訊。 請注意，Microsoft Lync Server 區別不同種類的失敗：

  - **預期的失敗**。 預期的失敗通常是指技術上預期會有的失敗。 例如，假設有人啟動會議，但是任何人都可以加入之前掛斷。 技術上而言，是失敗： 會議已啟動，但不是會完成。 不過，這是您預期會發生失敗： 如果召集人取消會議，任何人都可以加入接著您應該不會完成該會議之前。

  - **未預期的失敗**。 未預期的錯誤正如其名稱所指：在不同的情況下，所發生的未預期錯誤。 例如，假設會議可能不會佔用，因為無法擷取召集人的會議原則。 這是未預期的錯誤： 所有之後，您應該一律能夠擷取使用者的會議原則。

請注意，「成功」、「預期的失敗」及「未預期的失敗」計量的總和不一定等於「工作階段總數」計量。 例如，您可能會看到在報表中的下列值：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>成功</th>
<th>預期的失敗</th>
<th>未預期的失敗</th>
<th>工作階段總數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


如果您新增 2024 + 469 + 16 您收到 2,509 工作階段總計和尚未，工作階段總數] 欄位會顯示 2,521 工作階段總數。 「 缺少 」 12 工作階段是系統找不到分類為成功或失敗的工作階段。 有時會這種情況時的協力廠商產品引進新的診斷程式碼是不太熟悉監控伺服器。 若發生此情況，使用該產品撥打電話後回報該診斷碼，可能無法歸類為「成功」、「預期的失敗」或「未預期的失敗」。

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>存取會議診斷報告

從監視報告首頁存取會議診斷報告。 您可以按一下下列計量之一來存取[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)：

  - 未預期失敗次數

  - 預期失敗次數

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>會議診斷報告的最佳用法

會議診斷報告包含一系列的圖形。 每個圖所示的資料行是實際的超連結。 如果您按一下欄時，您將向下切入[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)期間與該會議類型。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，會議診斷報告可讓您篩選上為正在進行的會議 （例如，基於 Focus 的會議） 或會議中使用的 Edge 伺服器類型等項目。 您也可以選擇資料的分組方式。 在此情況下，會議分組小時、 日、 週或月。

下表列出您可以搭配會議診斷報告的篩選器。

### <a name="conference-diagnostic-report-filters"></a>會議診斷報告篩選器

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
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會議工作階段</strong></p></td>
<td><p>指出會議工作階段的類型。 請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>焦點工作階段</p></li>
<li><p>所有 MCU 工作階段</p></li>
<li><p>IM 會議</p></li>
<li><p>應用程式共用</p></li>
<li><p>A/V 會議</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出會議工作階段的每一種會議診斷報告所提供的資訊。

### <a name="conference-diagnostic-report-metrics"></a>會議診斷報告計量

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>成功次數</strong></p></td>
<td><p>否</p></td>
<td><p>成功的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>成功百分比</strong></p></td>
<td><p>否</p></td>
<td><p>完成但有重大問題的會議的百分比。 計算方式是將成功次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>預期失敗次數</strong></p></td>
<td><p>否</p></td>
<td><p>會議總數：&quot;預期失敗&quot;發生。</p>
<p>預期的失敗是指預期會發生的失敗。例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>預期失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>發生預期的錯誤的會議的百分比。 計算方式是將預期失敗次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>未預期失敗次數</strong></p></td>
<td><p>否</p></td>
<td><p>會議總數：&quot;未預期的失敗&quot;發生。</p>
<p>未預期的失敗是指起因於系統不健全的失敗。例如，當發話者處於保留狀態時，不應掛斷通話。當發生此狀況時，會將其標幟為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>未預期失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>發生意外的錯誤的會議的百分比。 計算方式是將未預期失敗次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>會議，包括成功的會議、 失敗的會議 （預期的失敗與未預期的失敗），以及未分類的會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

