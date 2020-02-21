---
title: 'Lync Server 2013: PSTN 會議摘要報告'
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
ms.openlocfilehash: 7b531d0e8d7d4fe5de6d1598cf557096ebff8a90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 中 PSTN 會議摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

Microsoft Lync Server 2013 中，在 PSTN 會議是在其中至少一名參與者撥入的音訊部分使用 PSTN （公用交換的電話網路） 電話任何會議。 (PSTN 電話是 「 室內電話 」，行動電話或任何其他這不會讓使用的 Voice over IP 電話。)雖然稱為監控報告中的 PSTN 會議，但這些會議也許更常稱為電話撥入式會議。

PSTN 會議摘要報告提供有關保留組織 （亦即，所有的會議有至少一個電話撥入式使用者） 中的所有 PSTN 會議資訊。 報告中包含的 PSTN 會議，參與那些會議中，和，也許，大部分的人員總數總數的相關資訊很重要，電話撥入式使用者 （總共 PSTN 參與者公制） 總數。

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>存取 PSTN 會議摘要報告

只能從監視報告首頁存取 PSTN 會議摘要報告。 這份報告未連結至任何其他報告。 請注意，您無法擷取詳細的通話資訊 PSTN 會議，部分因為個別端點負責送出此資訊。 PSTN 電話不能夠追蹤或送出通話詳細資訊。

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 會議摘要報告的最佳用法

若要判斷所有包含撥入式使用者之會議的百分比，比較的值與[Lync Server 2013 中的會議摘要報告](lync-server-2013-conference-summary-report.md)上找到的會議總數公制總 PSTN 會議計量。

如果看不到多個 PSTN 會議預期您可能必須以查看，請記住，組織可讓使用者撥入式會議的功能取決於已指派給使用者的會議原則： 如果很少的使用者可以保留 PSTN 很明顯地，您會看到極少 PSTN 會議的會議。 您可以快速驗證讓使用者執行從 Lync Server 管理命令介面中的下列命令來排定 PSTN 會議的會議原則 （如果有的話）：

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

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，PSTN 會議摘要報告可讓您選擇分組資料的方式。 在此情況下，會議分組小時、 日、 週或月。

下表列出您可以搭配 PSTN 會議摘要報告的篩選器。

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

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
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>說明</th>
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
<td><p>會議總數允許撥入存取。</p></td>
</tr>
<tr class="odd">
<td><p><strong>參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>參與允許撥入存取的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 會議總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/視訊會議時間總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 會議參與者總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/visual 參與者時間總數。 例如，如果一名參與者所花費的五分鐘在 A / V 會議，並另一位參與者所花費在同一場會議的總 A 3 分鐘 / V 會議參與者時間就是 8 分鐘的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>使用者撥打到允許撥入存取的會議總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PSTN 參與者分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>總數量所花費的撥入使用者的會議時間的詳細資訊。 例如，如果一個電話撥入式參與者所花費的會議中的五分鐘及其他參與者所花費在同一場會議中的三個分鐘，PSTN 參與者時間總計會是 8 分鐘的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一會議召集人</strong></p></td>
<td><p>否</p></td>
<td><p>組織允許撥入存取的至少一場會議的使用者總數。 召集過多次會議的使用者計為一個專屬召集人，就像只召集過一次會議的使用者一樣。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

