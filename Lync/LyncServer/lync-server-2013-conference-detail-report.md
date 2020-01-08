---
title: Lync Server 2013：會議詳細資料包表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的會議詳細資料包表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

[會議詳細資料] 報告提供參與會議之所有使用者的詳細資訊。 例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將該使用者連線到會議的端點使用者代理程式。 您也可以在每個會議中查看使用者角色的資訊（例如，簡報者或出席者）。 最重要的是，您會快速看到哪些使用者成功加入並完成會議，哪些使用者無法順利加入並完成會議。

<div>

## <a name="accessing-the-conference-detail-report"></a>存取會議詳細資料包表

您可以從下列報表存取會議詳細資料包告：

  - [Lync Server 2013 中的呼叫許可控制報告](lync-server-2013-call-admission-control-report.md)（按一下會議的詳細資料）

  - [Lync Server 2013 中的 [失敗清單] 報告](lync-server-2013-failure-list-report.md)（按一下會議躍點數）

  - [Lync Server 2013 中的使用者活動報告](lync-server-2013-user-activity-report.md)（按一下會議 URI 躍點數）

在 [會議詳細資料] 報告中，您可以按一下診斷報告（詳細資料）度量，[以存取 Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)。

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法在會議詳細資料包表中篩選。

</div>

<div>

## <a name="metrics"></a>指標

下表列出在會議詳細資料包表的 [會議資訊] 區段中提供的資訊。

### <a name="conference-information-metrics"></a>會議資訊度量單位

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
<td><p><strong>會議 URI</strong></p></td>
<td></td>
<td><p>指派給會議的 URI。 例如：</p>
<p>sip： kmyer@litwareinc .com; gruu; 不透明 = 應用程式：會議：焦點： id： drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>池 FQDN</strong></p></td>
<td></td>
<td><p>會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>開始時間</strong></p></td>
<td></td>
<td><p>會議開始的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td></td>
<td><p>組織會議的使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td></td>
<td><p>會議結束的日期和時間。</p></td>
</tr>
</tbody>
</table>


下表列出會議詳細資料包表之會議參與區段中提供的資訊。

### <a name="conference-participation-metrics"></a>會議參與指標

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
<td><p><strong>使用者</strong></p></td>
<td></td>
<td><p>參與會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>角色</strong></p></td>
<td></td>
<td><p>會議參與者所扮演的角色（例如，簡報者）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連通</strong></p></td>
<td></td>
<td><p>參與者的網路連線（通常是內部或外部的網路連線）。</p></td>
</tr>
<tr class="even">
<td><p>加入時間</p></td>
<td></td>
<td><p>參與者加入會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>休假時間</strong></p></td>
<td></td>
<td><p>參與者離開會議的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者代理程式</strong></p></td>
<td></td>
<td><p>參與者終點所使用之軟體的識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷報告</strong></p></td>
<td></td>
<td><p>提供診斷及疑難排解資訊。 包括 SIP 回應代碼、診斷標頭、會議加入時間，以及失敗會話的診斷 Id。</p></td>
</tr>
</tbody>
</table>


下表列出在會議詳細資料包表的 [會議形式] 區段中提供的資訊。

### <a name="conference-modalities-metrics"></a>會議形式度量單位

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
<td><p><strong>使用者</strong></p></td>
<td></td>
<td><p>參與會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入時間</strong></p></td>
<td></td>
<td><p>參與者加入會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>休假時間</strong></p></td>
<td></td>
<td><p>參與者離開會議的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議服務器 URI</strong></p></td>
<td></td>
<td><p>在會議中使用的會議服務器 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷報告</strong></p></td>
<td></td>
<td><p>提供診斷及疑難排解資訊。 包括 SIP 回應代碼、診斷標頭、會議加入時間，以及失敗會話的診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

