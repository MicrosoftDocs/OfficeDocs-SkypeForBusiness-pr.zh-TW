---
title: Lync Server 2013：會議摘要子報表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Lync Server 2013 中的會議摘要子報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

[會議摘要] 子報表提供失敗會議會話的整體視圖。 這些失敗的會話會透過會話類型進一步細分：焦點會話與 MCU 會話。

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出可與會議摘要子報表搭配使用的篩選。

### <a name="conference-summary-subreport-filters"></a>會議摘要子報表篩選

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
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出會議摘要子報表中提供的資訊。

### <a name="conference-summary-subreport-metrics"></a>會議摘要子報表度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>已舉行的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>會議會話總數。 單一會議可以有多個會話;例如，會議可能同時包含焦點會話和 MCU 會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總體會話失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>所有失敗的會議所占的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦點會話</strong></p></td>
<td><p>否</p></td>
<td><p>焦點會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦點失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的焦點會話百分比。</p></td>
</tr>
<tr class="even">
<td><p>MCU 會話</p></td>
<td><p>否</p></td>
<td><p>MCU 會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 MCU 會話百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用模態的 MCU 會話</strong></p></td>
<td><p>否</p></td>
<td><p>MCU 會話總數，依模態分組（例如 IM 會議）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>依模態的失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 MCU 會話百分比，依模態分組（例如 IM 會議）。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

