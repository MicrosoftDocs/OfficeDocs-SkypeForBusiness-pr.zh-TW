---
title: Lync Server 2013： PSTN 會議摘要報告
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
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 會議摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在 Microsoft Lync Server 2013 中，PSTN 會議是一個會議，其中至少有一個參與者使用 PSTN （公開交換電話網絡）電話撥入音訊部分。 （PSTN 手機是「有線電話、」手機或任何其他不使用語音 over IP 的電話）。雖然在監視報告中稱為 PSTN 會議，但這些會議可能更常見，也稱為撥入式會議。

PSTN 會議摘要報告提供貴組織中所有 PSTN 會議的相關資訊（也就是至少有一個撥入使用者的所有會議）。 此報告包含有關 PSTN 會議總數、參與這些會議的人數總數，以及最重要的電話撥入使用者總數（總 PSTN 參與者統計值）的相關資訊。

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>存取 PSTN 會議摘要報告

PSTN 會議摘要報告只能從 [監控報告] 首頁進行存取。 此報告未連結至任何其他報表。 請注意，您無法取得 PSTN 會議的詳細呼叫資訊，因為個別端點負責提交此資訊。 PSTN 手機無法追蹤或提交通話詳細資訊。

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>充分利用 PSTN 會議摘要報告

若要判斷包含撥入使用者的所有會議的百分比，請比較 PSTN 會議總量與在[Lync Server 2013 的 [會議摘要] 報告中](lync-server-2013-conference-summary-report.md)找到的總會議度量值。

如果您沒有看到許多您可能會看到的 PSTN 會議，請記住，組織允許撥入使用者的會議的能力取決於已指派給使用者的會議原則：您的使用者數只有幾個使用者可以保留 PSTN-ZA&PLATFORM 會議您顯然會看到很少的 PSTN 會議。 您可以透過在 Lync Server 管理命令介面中執行下列命令，快速確認您的會議原則（如果有的話）允許使用者排程 PSTN 會議：

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

這樣會傳回如下所示的資料：

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

這樣會傳回如下所示的資料：

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，PSTN 會議摘要報告可讓您選擇資料的分組方式。 在這種情況下，會議會依小時、日、周或月進行分組。

下表列出您可搭配 PSTN 會議摘要報告使用的篩選準則。

### <a name="pstn-conference-summary-report-filters"></a>PSTN 會議摘要報告篩選器

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
<li><p>每月（最多可以顯示12個月）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 PSTN 會議摘要報告中的資訊。

### <a name="pstn-conference-summary-report-metrics"></a>PSTN 會議摘要報告度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>工資</strong></p>
<p><strong>日常</strong></p>
<p><strong>周更新</strong></p>
<p><strong>次</strong></p></td>
<td><p>否</p></td>
<td><p>指出選取的時間間隔。 在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</p></td>
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
<td><p><strong>A/V 會議紀要總計</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/視訊會議的總時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 會議參與者紀要總計</strong></p></td>
<td><p>否</p></td>
<td><p>音訊/視覺參與者的總時間。 例如，如果一個參與者在 A/V 會議中花費了五分鐘，而另一個參與者在同一筆會議中花費了三分鐘，則總的 A/V 會議參與者時間會是八分鐘。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>撥入會議且允許撥入存取的使用者總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PSTN 參與者通話總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>撥入使用者所花費的會議時間總量。 例如，如果一個撥入參與者在會議中花了五分鐘的時間，而另一個參與者在同一個會議中花費了三分鐘，則 PSTN 參與者時間總會是八分鐘。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一的會議召集人</strong></p></td>
<td><p>否</p></td>
<td><p>組織至少有一部允許撥入存取的會議的使用者總數。 組織多個會議的使用者會算作一個唯一的召集人，就像只組織單一會議的使用者。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

