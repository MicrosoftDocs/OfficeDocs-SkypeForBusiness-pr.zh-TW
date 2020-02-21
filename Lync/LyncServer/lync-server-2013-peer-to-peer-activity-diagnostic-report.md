---
title: Lync Server 2013： 對等活動診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc7c6de27a4ccc9cd05777476ac4abc7d6fc9f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的對等活動診斷報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

對等活動診斷報告提供對等通訊工作階段成功與失敗的資訊。 請注意，Microsoft Lync Server 2013 區別不同種類的失敗：

  - **預期的失敗**。 預期的失敗通常是指技術上預期會有的失敗。 例如，假設您撥打電話給某人，但是該名人員不在辦公室，而無法接聽電話。 由於無人接聽電話，該通話在技術上會視為失敗。 相反地，這是未預期的失敗： Microsoft Lync Server 2013 中未預期接聽電話，如果您不是可用於接聽電話。 同樣地，如果您嘗試將立即訊息傳送給離線的使用者，或傳送給只登入到不支援立即訊息之電話的使用者，則會發生預期的失敗。

  - **未預期的失敗**。 未預期的錯誤正如其名稱所指：在不同的情況下，所發生的未預期錯誤。 例如，假設您呼叫某人且人員便可用於接聽通話;不過，當 Lync Server 2013 嘗試路由傳送您的電話語音信箱通話失敗，因為已中斷連線至 Exchange 整合通訊。 此即為未預期的錯誤：您預期通話一律會轉接到語音信箱。 一般而言，未預期的失敗是真正的失敗：這些失敗可能是無法透過教育使用者或類似措施加以補救的問題。

請注意，「成功」、「預期的失敗」及「未預期的失敗」計量的總和不一定等於「工作階段總數」計量。例如，在以上說明中，我們有下列值：


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


如果將 2024 + 469 + 16，則會得到工作階段總數 2,509，但是 [工作階段總數] 欄顯示工作階段總數為 2,521。 「遺失的」12 個工作階段是系統無法分類為成功或失敗的工作階段。 協力廠商產品引進新的診斷程式碼是不太熟悉 Lync Server 時，這會有時是這種情況。 若發生此情況，使用該產品撥打電話後回報該診斷碼，可能無法歸類為「成功」、「預期的失敗」或「未預期的失敗」。

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>存取對等活動診斷報告

對等診斷報告是透過監視報告首頁來存取。 您可以按一下下列計量之一來存取[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)：

  - 未預期失敗次數

  - 預期失敗次數

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>充分運用對等活動診斷報告

您可以透過一些方式來篩選對等活動診斷報告，但是預設無法檢視這些篩選選項。若要檢視可用的篩選選項，請按一下報告視窗右上角的 [顯示/隱藏參數] 按鈕。如此一來，即可使用篩選選項。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，對等活動診斷報告可以讓您依據工作階段形式等項目 (例如立即訊息、檔案傳輸或應用程式共用) 進行篩選。您也可以選擇資料的分組方式。在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配對等活動診斷報告的篩選器。

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>對等活動診斷報告篩選器

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
<td><p><strong>形式</strong></p></td>
<td><p>指出發生之通訊活動的類型。請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>立即訊息</p></li>
<li><p>檔案傳輸</p></li>
<li><p>應用程式共用</p></li>
<li><p>音訊</p></li>
<li><p>影片</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>計量 (每種形式)

下表列出對等活動診斷報告中針對每種形式所提供的資訊。

### <a name="metrics-per-modality"></a>計量 (每種形式)

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
<td><p>成功的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>成功百分比</strong></p></td>
<td><p>否</p></td>
<td><p>完成時具有重大問題的點對點工作階段百分比。計算方式是將成功次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>預期失敗次數</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數：&quot;預期失敗&quot;發生。</p>
<p>預期的失敗是指預期會發生的失敗。例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>預期失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>發生預期失敗的點對點工作階段百分比。計算方式是將預期失敗次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>未預期失敗次數</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數：&quot;未預期的失敗&quot;發生。</p>
<p>未預期的失敗是指起因於系統不健全的失敗。例如，當發話者處於保留狀態時，不應掛斷通話。當發生此狀況時，會將其標幟為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>未預期失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>發生未預期失敗的點對點工作階段百分比。計算方式是將未預期失敗次數除以工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

