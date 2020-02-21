---
title: Lync Server 2013： 最大失敗報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Lync Server 2013 中的最大失敗報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

Top Failures 報告列出最常發生的失敗及其在一段時間後的趨勢。

  - **診斷 ID**。附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)。診斷 ID 可以在疑難排解通話相關錯誤時提供實用的資訊。

  - **回應碼**。 回應碼適用於 SIP 通訊工作階段來回應 SIP 要求。 例如，假設 Ken 邀請將要求傳送至為 Pilar Ackerman （也就是假設 Ken Myer 呼叫為 Pilar Ackerman）。 如果 Pilar 接聽，其電話將傳送給您知道有回答 Pilar Ken 的電話，讓回應碼 200 (OK)。 最大失敗報告只包含已傳送回應通話失敗; 回應碼Lync Server 不會不追蹤的發出的通話過程中的所有回應碼。

資訊回報內容不僅有發生失敗的工作階段總數，還有因失敗受到影響的使用者總數。

<div>

## <a name="accessing-the-top-failures-report"></a>存取最大失敗報告

可以從監視報告首頁存取最大失敗報告。 按一下 [Reported 工作階段計量，將帶您前往[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>善用最大失敗報告

在某方面而言，最大失敗報告顯得十分特別：此報告最多能讓您一次篩選 5 個診斷 ID (通常一次只能篩選一個項目，例如一個使用者 SIP 位址)。若要篩選多個診斷 ID，只要在「診斷 ID」方塊中輸入各個 ID，並以逗號區隔即可 (也可以在每個逗號後面留下空格)。例如：

1011, 2412, 1033, 52116, 1008

完成後，只會顯示回報五個診斷 ID 中至少有一個 ID 的失敗通話。

如果您將滑鼠移到回應碼時會看到工具提示，說明有問題的回應代碼所代表的涵義。例如將滑鼠移到回應碼 486，會看到此訊息：

此處非常忙碌。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，「最大失敗報告」可讓您依據活動類型之類的項目 (對等工作階段或會議工作階段)，或是依失敗工作階段隨附的 SIP 回應碼，篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。

下表列出您可以用於最大失敗報告的篩選器。

### <a name="top-failures-report-filters"></a>最大失敗報告篩選器

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
<td><p><strong>活動類型</strong></p></td>
<td><p>活動的類型。請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>端對端</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>目前唯一可用的選項是 [全部]<strong></strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>類別</strong></p></td>
<td><p>遇到的失敗類型。請選取下列其中一項：</p>
<ul>
<li><p>預期及未預期的失敗</p></li>
<li><p>未預期的失敗</p></li>
</ul>
<p>&quot;預期失敗&quot;是預期會發生的失敗。 例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。 &quot;未預期的失敗&quot;是在項目會顯示為否則狀況良好的系統，就會發生的失敗。 例如，當發話者處於保留狀態時，不應掛斷通話。 當發生此狀況時，會將其標幟為未預期的失敗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>會議失敗時所傳送的 SIP 回應碼。請輸入完整的回應碼，例如：</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出前幾名失敗報告提供的資訊。

### <a name="top-failures-report-metrics"></a>最大失敗報告計量

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
<td><p><strong>Rank</strong></p></td>
<td><p>是</p></td>
<td><p>依據所報告之工作階段數的相對排名。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告的工作階段</strong></p></td>
<td><p>是</p></td>
<td><p>依據診斷識別碼及 SIP 回應碼的失敗工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>受影響的使用者</strong></p></td>
<td><p>是</p></td>
<td><p>受失敗工作階段影響的使用者總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>失敗資訊</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的詳細資訊，包括診斷識別碼、SIP 回應碼，以及工作階段為什麼失敗的說明。</p></td>
</tr>
<tr class="odd">
<td><p><strong>過去的趨勢</strong></p></td>
<td><p>否</p></td>
<td><p>一段時間的失敗工作階段圖表。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

