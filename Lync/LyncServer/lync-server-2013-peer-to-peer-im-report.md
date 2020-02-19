---
title: Lync Server 2013： 對等 IM 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e2cf987c40279a4854b9fe776c1585247d24e55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013 中的對等 IM 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

對等 IM 報告會提供對等立即訊息 (IM) 工作階段的趨勢資訊 (依集區和驗證類型細分)。此報告可以顯示指定時段內 (例如，每天或每小時) 主控的工作階段總數，或者可以顯示該時段內傳送的立即訊息總數。

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>存取對等 IM 報告

您可以存取對等 IM 報告只能透過開啟[對等活動摘要報告在 Lync Server 2013 中](lync-server-2013-peer-to-peer-activity-summary-report.md)，再按一下下列計量之一：

  - 對等 IM 工作階段總數

  - 對等 IM 訊息總數

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>善加利用對等 IM 報告

依預設，對等 IM 報告會顯示每小時 (或每天，視您的設定而定) 的訊息計數。不過，您也可以選擇依每小時的工作階段來檢視那一天。若要執行這項作業，請按一下報告視窗右上角的 [隱藏/顯示參數]****，然後從 [報告者]**** 清單按一下 [工作階段計數]****。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。下表列出您可以搭配對等 IM 報告的篩選器。

### <a name="peer-to-peer-im-report-filters"></a>對等 IM 報告篩選器

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
<td><p>時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份查看，請輸入當週或該月內的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</p>
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
<td><p><strong>報告依據</strong></p></td>
<td><p>指定報告中所要使用的值。請選取下列其中一項：</p>
<ul>
<li><p>工作階段計數</p></li>
<li><p>訊息計數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>對等 IM 工作階段計量 (依集區)

下表列出對等 IM 報告提供的資訊。

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>對等 IM 工作階段計量 (依集區)

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
<td><p><strong>Pool</strong></p></td>
<td><p>否</p></td>
<td><p>登錄器集區或 Edge Server 的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段的執行日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>對等 IM 工作階段計量 (依驗證類型)

下表列出對等 IM 報告針對參與者在對等工作階段中使用之每項驗證類型所提供的資訊。

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>對等 IM 工作階段計量 (依驗證類型)

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
<td><p><strong>驗證類型</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段參與者所使用的驗證類型。一般來說，值都是下列其中之一：</p>
<ul>
<li><p>企業</p></li>
<li><p>同盟</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段的執行日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

