---
title: Lync Server 2013： 對等活動摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的對等活動摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

對等活動摘要報告提供您對等通訊工作階段的整體] 檢視。 端對端工作階段通常涉及僅由兩個使用者，且不需要使用 Lync Server 會議服務。 相較之下，會議通常包括兩個以上的使用者，以及需要使用 Microsoft Lync Server 2013 會議服務。 會議活動報告在 Conference Summary Report。

對等活動摘要報告可協助您回答下列問題：

  - 我的使用者傳送多少對等立即訊息平日？

  - 是否有任何我的使用者實際運用的 Lync Server 應用程式共用和檔案傳輸功能？

  - 使用者有抱怨，網路似乎速度很慢在特定一天的時間。 幾分鐘的時間是在專供端對端音訊和視訊工作階段期間的時段？

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>存取對等活動摘要報告

您從監視報告首頁存取對等活動摘要報告。 您可以按一下下列計量之一，以開啟[Lync Server 2013 中的對等 IM 報告](lync-server-2013-peer-to-peer-im-report.md)：

  - 對等 IM 工作階段總數

  - 對等 IM 訊息總數

同樣地，您可以按一下下列其中一個指標開啟對等語音和視訊報告：

  - 對等音訊工作階段總數

  - 對等音訊工作階段分鐘總數

  - 對等音訊工作階段總數

  - 對等音訊工作階段分鐘總數

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>對等活動摘要報告的最佳用法

底部的對等活動摘要報告中，您會發現總計的對等 IM 工作階段總數和對等 IM 訊息總數等量值。 這會提供報表的內文中找到的詳細資訊的快速摘要。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。 例如，對等活動摘要報告可讓您選擇分組資料的方式。 在此情況下，活動依據小時、 日、 週或月。

下表列出您可以使用對等活動摘要報告的篩選器。

### <a name="peer-to-peer-activity-summary-report-filters"></a>對等活動摘要報告篩選器

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
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/13</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/13</p>
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
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。 例如，如果您選取 [每日的間隔時間與開始日期是 7/17/12012 和結束日期的 2/28/2012年，資料會顯示天 8/7/12012 上午 12:00 到 9/7/12012 12:00 AM （也就是 31 天的資料總數）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出對等活動摘要報告中提供的資訊。

### <a name="peer-to-peer-activity-summary-report-metrics"></a>對等活動摘要報告計量

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
<td><p><strong>每小時</strong></p>
<p><strong>每日</strong></p>
<p><strong>每週</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指出在篩選工具列上所選取的時間間隔。 在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。 例如，如果您正在使用的每日時間間隔，因此您按一下 [7/17/12012，您看到使用者註冊活動每小時分解該日期。</p></td>
</tr>
<tr class="even">
<td><p><strong>端對端工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>端對端工作階段總數，不論工作階段類型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等 IM 工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等立即訊息 (IM) 工作階段總數。 當您按一下此項目時，報告會顯示您對等 IM 報告針對選取的時段。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等 IM 訊息總數</strong></p></td>
<td><p>否</p></td>
<td><p>傳送端對端工作階段中的立即訊息總數。 當您按一下此項目時，報告會顯示您對等 IM 報告針對選取的時段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等音訊工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊通話總數。 當您按一下此欄位中，報告會顯示 「 對等語音和視訊報告所選時段。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等音訊工作階段分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊工作階段中所花費的時間總數。 當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均對等音訊工作階段分鐘</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊工作階段中所花費的平均時間量。 計算除以總計音訊工作階段時間依音訊工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等視訊工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>端對端視訊通話總數。 請注意視訊工作階段也視為音訊工作階段： 每個視訊工作階段視為一個視訊工作階段和一個音訊工作階段。 當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等視訊工作階段分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視訊工作階段中所花費的時間總數。 當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均對等視訊工作階段分鐘</strong></p></td>
<td><p>否</p></td>
<td><p>對等視訊工作階段中所花費的平均時間量。 計算除以總計視訊工作階段時間依視訊工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總數的端對端檔案傳輸工作階段</strong></p></td>
<td><p>否</p></td>
<td><p>包含檔案傳輸之對等工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>總端對端應用程式共用工作階段</strong></p></td>
<td><p>否</p></td>
<td><p>包含應用程式共用之對等工作階段總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

