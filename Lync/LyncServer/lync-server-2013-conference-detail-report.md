---
title: Lync Server 2013：會議詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1c2a25105aec6cdf6d21193038f90ea852c5b3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526030"
---
# <a name="conference-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的會議詳細資料包告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

「會議詳細資料報告」可提供參與會議之使用者的詳細資訊。例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將使用者與會議連線的端點使用者代理程式之類的資訊。您也可以查看使用者在每個會議中的角色 (例如，簡報者或是出席者)。更重要的是，您可以更快速地查看哪些使用者已順利加入並完成會議，而哪些使用者無法順利加入並完成會議。

<div>

## <a name="accessing-the-conference-detail-report"></a>存取會議詳細資料報告

您可從下列報告來存取會議詳細資料報告：

  - [Lync Server 2013 (中的通話許可控制報告](lync-server-2013-call-admission-control-report.md)，按一下會議的詳細資料度量) 

  - [在 [Lync Server 2013 (中](lync-server-2013-failure-list-report.md)，按一下 [會議] 度量，以 [失敗清單] 報告) 

  - [Lync Server 2013 (中的使用者活動報告](lync-server-2013-user-activity-report.md)，請按一下會議 URI 度量) 

您可以從 [會議詳細資料包告] 中，按一下 [診斷報告] (詳細資料) 指標， [以存取 Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md) 。

</div>

<div>

## <a name="filters"></a>篩選

無。您無法篩選會議詳細資料報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出會議詳細資料報告的「會議資訊」區段中所提供的資訊。

### <a name="conference-information-metrics"></a>會議資訊計量

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
<td><p><strong>會議 URI</strong></p></td>
<td></td>
<td><p>指派給會議的 URI。例如：</p>
<p>sip： kmyer@litwareinc .com; gruu; 不透明 = 應用程式：會議： focus：識別碼： drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>集區 FQDN</strong></p></td>
<td></td>
<td><p>工作階段所涉及的登錄器集區或 Edge Server 的完整網域名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>開始時間</strong></p></td>
<td></td>
<td><p>會議開始的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td></td>
<td><p>召開會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td></td>
<td><p>會議結束的日期與時間。</p></td>
</tr>
</tbody>
</table>


下表列出會議詳細資料報告的「會議參與區段」中所提供的資訊。

### <a name="conference-participation-metrics"></a>會議參與計量

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
<td><p><strong>使用者</strong></p></td>
<td></td>
<td><p>參與會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td></td>
<td><p>會議參與者所扮演的角色 (例如，簡報者)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連線能力</strong></p></td>
<td></td>
<td><p>參與者的網路連線 (一般來說是從內部或從外部)。</p></td>
</tr>
<tr class="even">
<td><p>加入時間</p></td>
<td></td>
<td><p>參與者加入會議的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>離開時間</strong></p></td>
<td></td>
<td><p>參與者離開會議的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者代理程式</strong></p></td>
<td></td>
<td><p>參與者端點所使用的軟體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷報告</strong></p></td>
<td></td>
<td><p>可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</p></td>
</tr>
</tbody>
</table>


下表列出會議詳細資料包告之 [會議形式] 區段中所提供的資訊。

### <a name="conference-modalities-metrics"></a>會議形式計量

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
<td><p><strong>使用者</strong></p></td>
<td></td>
<td><p>參與會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入時間</strong></p></td>
<td></td>
<td><p>參與者加入會議的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>離開時間</strong></p></td>
<td></td>
<td><p>參與者離開會議的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議伺服器 URI</strong></p></td>
<td></td>
<td><p>會議中所使用之會議伺服器的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷報告</strong></p></td>
<td></td>
<td><p>可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

