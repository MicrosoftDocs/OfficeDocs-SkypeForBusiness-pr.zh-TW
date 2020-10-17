---
title: Lync Server 2013： PSTN 會議摘要報告
description: Lync Server 2013： PSTN 會議摘要報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bc468e494577c229562a1cb7cfddaf839f946f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562769"
---
# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 會議摘要報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在 Microsoft Lync Server 2013 中，PSTN 會議是指至少有一個參與者透過使用 PSTN (公用交換電話網路) 電話，撥打音訊部分的任何會議。  (PSTN 電話是 "室內電話"、"蜂窩電話] 或任何其他未利用 Voice over IP 的電話。 ) 雖然在監控報告中稱為 PSTN 會議，但這些會議甚至可能更常見，稱為電話撥入式會議。

PSTN 會議摘要報告提供您組織中所有 PSTN 會議的相關資訊 (也就是說，所有具有至少一個撥入式使用者) 的會議。 此報告包含有關 PSTN 會議總數、參與這些會議的人員總數，以及最重要的電話撥入式使用者總數 (全部 PSTN 參與者度量) 中的相關資訊。

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>存取 PSTN 會議摘要報告

PSTN 會議摘要報告只可從監控報告首頁進行存取。 此報告未連結至任何其他報告。 請注意，您無法為 PSTN 會議檢索詳細的呼叫資訊，因為個別端點負責提交此資訊。 PSTN 電話不具備追蹤或送出通話詳細資訊的能力。

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 會議摘要報告的最佳用法

若要決定所有包含撥入使用者之會議的百分比，請將「PSTN 會議總數」度量值與 [Lync Server 2013 中「會議摘要」報告](lync-server-2013-conference-summary-report.md)上的 [會議總數] 度量值進行比較。

如果您看不到許多 PSTN 會議，如您可能會看到，請記住組織允許撥入使用者之會議的功能，取決於已指派給使用者的會議原則：如果允許很少的使用者持有 PSTN 會議，您顯然會看到極少的 PSTN 會議。 若有任何) 允許使用者在 Lync Server 管理命令介面中執行下列命令，您可以快速驗證 (的哪一種會議原則：

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

該命令將傳回類似下列的資料：

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

該命令將傳回類似下列的資料：

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，PSTN 會議摘要報告可讓您選擇資料的分組方式。 在此情況下，會依小時、天、周或月群組會議。

下表列出您可以搭配 PSTN 會議摘要報告使用的篩選器。

### <a name="pstn-conference-summary-report-filters"></a>PSTN 會議摘要報告篩選器

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 PSTN 會議摘要報告中的資訊。

### <a name="pstn-conference-summary-report-metrics"></a>PSTN 會議摘要報告計量

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
<td><p><strong>每小時</strong></p>
<p><strong>每日</strong></p>
<p><strong>每週</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示所選的時間間隔。在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。例如，若您使用 [每日] 間隔並按一下 7/7/2012，將會顯示該日期之使用者登錄活動的每小時明細。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>允許撥入存取的會議總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>參與允許撥入存取之會議的人員總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 會議總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/視訊會議的總時數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 會議參與者總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/視頻參與者的總時數。 例如，如果一個參與者在 A/V 會議中花了五分鐘，另一個參與者在同一部會議中花三分鐘的時間，則會議參與者時間的總數 A/V 會是8分鐘。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>撥打至允許撥入存取之會議的總使用者人數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PSTN 參與者分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>撥號使用者所花費的會議時間總量。 例如，如果一個撥入式參與者在會議中花了五分鐘的時間，另一個參與者在同一部會議中花三分鐘的時間，則 PSTN 參與者時間總量會是8分鐘。</p></td>
</tr>
<tr class="even">
<td><p><strong>獨特的會議召集人</strong></p></td>
<td><p>否</p></td>
<td><p>組織至少一部允許撥入存取之會議的總使用者人數。 召集過多次會議的使用者計為一個專屬召集人，就像只召集過一次會議的使用者一樣。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

