---
title: Lync Server 2013： 對等語音和視訊報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974f403f65b494964affc4fbdc4880820ecb2db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>對等語音和視訊報告在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

對等語音和視訊報告提供詳細的外觀在一段指定的時間 （例如，每小時的通話） 或每日的電話語音和視訊通話的通訊。 報告也會提供您檢視所有語音和視訊通話進行，或都檢視僅成功或失敗通話的選項。 報告顯示通話的資訊分為下列群組：

  - 每個集區的通話

  - 每一種通話類型 (例如，要撥打至 PSTN 網路內的人員的 Lync 電話與 Lync 通話 Lync) 的通話

  - 每個存取類型 （內部網路與外部網路登入的使用者登入的使用者） 的通話

  - 每個中繼伺服器的呼叫

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>若要存取對等語音和視訊報告

您可以存取對等語音和視訊報告只能透過開啟對等活動摘要報告，然後按一下下列計量之一：

  - 對等音訊工作階段總數

  - 對等音訊分鐘總數

  - 對等視訊工作階段總數

  - 端對端視訊分鐘總數

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>若要充分運用對等語音和視訊報告

有多種方式對等語音和視訊報告，您可以篩選。 不過，這些篩選選項預設為隱藏從檢視。 若要檢視您可以使用的篩選選項，請按一下 [報表] 視窗右上角的 [**顯示/隱藏參數**] 按鈕。

</div>

<div>

## <a name="filters"></a>篩選

篩選提供方法，讓您傳回更準確地目標的資料集，或以不同方式檢視資料。 下表列出您可以使用 「 對等語音和視訊報告的篩選器。

### <a name="peer-to-peer-voice-and-video-report-filters"></a>對等語音和視訊報告篩選器

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
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 下午 1:00</p>
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
<td><p><strong>媒體類型</strong></p></td>
<td><p>會指出媒體工作階段中所使用的類型。 選取下列其中一項：</p>
<ul>
<li><p>兩者都要</p></li>
<li><p>音訊</p></li>
<li><p>影片</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>通話處理</strong></p></td>
<td><p>會指出成功或失敗的工作階段。 請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>通話成功</p></li>
<li><p>失敗的通話</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>報告依據</strong></p></td>
<td><p>指定報告中所要使用的值。請選取下列其中一項：</p>
<ul>
<li><p>工作階段計數</p></li>
<li><p>通話分鐘數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>對等語音及視訊活動的集區的計量

下表列出對等語音和視訊報告 」 中每個集區所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>對等語音及視訊活動的集區的計量

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
<td><p>登錄器集區或 Edge Server 用於通話的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>在呼叫發生日期和時間期間。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音及視訊活動依通話類型的計量

下表列出對等語音和視訊報告 」 中每一種所進行之通話所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音及視訊活動依通話類型的計量

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
<td><p><strong>通話類型</strong></p></td>
<td><p>否</p></td>
<td><p>會指出所進行之通話的類型。 值可以是下列其中一項：</p>
<ul>
<li><p>UC 對 UC</p></li>
<li><p>UC 對 PSTN</p></li>
<li><p>PSTN-UC</p></li>
<li><p>PSTN 對 PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>在呼叫發生日期和時間期間。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>對等語音及視訊活動依存取類型的計量

下表列出每個網路存取類型對等語音和視訊報告 」 中所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>對等語音及視訊活動依存取類型的計量

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
<td><p><strong>活動類型</strong></p></td>
<td><p>否</p></td>
<td><p>會指出是否在用戶端已登入內部網路或外部網路時撥打電話。 一般來說，值都是下列其中之一：</p>
<ul>
<li><p>內部</p></li>
<li><p>External</p></li>
<li><p>混合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>在呼叫發生日期和時間期間。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>對等語音及視訊活動由中繼伺服器的計量

下表列出對等語音和視訊報告 」 中每一部中繼伺服器所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>對等語音及視訊活動由中繼伺服器的計量

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
<td><p><strong>中繼伺服器</strong></p></td>
<td><p>否</p></td>
<td><p>中繼伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>在呼叫發生日期和時間期間。</p></td>
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

