---
title: Lync Server 2013： 通話診斷摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ebd3da761fe9923f05c2ddd5dfced852b4b27e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Lync Server 2013 中通話診斷摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

通話診斷摘要報告提供失敗對等和會議工作階段的整體外觀。 報表顯示這兩種類型的工作階段，整體失敗率，並進一步依工作階段形式類型細分的失敗資訊：

  - 立即訊息

  - 應用程式共用

  - 檔案傳輸

  - 音訊

  - 影片

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>存取通話診斷摘要報告

從監視報告首頁存取通話診斷摘要報告。 您可以從 「 通話診斷摘要報告按一下失敗率計量報告的端對端工作階段摘要] 區段下存取[Lync Server 2013 中的對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)。 您也可以藉由按一下任何下列的會議計量存取[Lync Server 2013 中的會議診斷報告](lync-server-2013-conference-diagnostic-report.md)：

  - 整體工作階段失敗率

  - 焦點失敗率

  - MCU 失敗率

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>通話診斷摘要報告的最佳用法

通話診斷摘要報告包含比較 Microsoft Lync Server 2013 中使用各種形式的失敗率的圖形。 這些圖形中的資料行是實際不良率;例如，如果您按一下 [立即訊息] 欄中的端對端工作階段，您將向下切入[Lync Server 2013 中的對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)提供有關所有立即訊息工作階段通話診斷摘要報告中包含的其他詳細資料報告的執行個體。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，通話診斷摘要報告可讓您篩選上為 [登錄器集區等項目或工作階段中使用的 Edge 伺服器。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配通話診斷摘要報告的篩選器。

### <a name="call-diagnostic-summary-report-filters"></a>通話診斷摘要報告篩選器

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
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>端對端工作階段的計量

下表列出對等端對端工作階段 （也就是工作階段只有兩個參與者） 通話診斷摘要報告所提供的資訊。

### <a name="metrics-for-peer-to-peer-sessions"></a>端對端工作階段的計量

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
<td><p><strong>工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>端對端工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>端對端工作階段失敗百分比。 當您按一下此項目時，報告顯示對等活動診斷報告，會顯示失敗的對等工作階段的詳細的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

下表列出會議工作階段 （也就是參與者的工作階段三個或多個） 之通話診斷報告所提供的資訊。

### <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

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
<td><p><strong>會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>會議工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>整體工作階段失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>總會議工作階段失敗百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦點工作階段</strong></p></td>
<td><p>否</p></td>
<td><p>基於 Focus 的會議工作階段失敗總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦點失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>基於 Focus 的會議工作階段失敗百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 工作階段</strong></p></td>
<td><p>否</p></td>
<td><p>總數基於會議伺服器 （以前稱為 Multipoint Control Unit 或 MCU） 的失敗會議。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>基於會議伺服器的百分比 （以前稱為 Multipoint Control Unit 或 MCU） 的失敗會議。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

