---
title: Lync Server 2013： ConferenceSessionDetails 表格
description: Lync Server 2013： ConferenceSessionDetails 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566779"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceSessionDetails 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話要求的時間;與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議會話。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要，外部</p></td>
<td><p>用來識別工作階段的識別碼。 與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議會話。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>與此會話相關的聚焦會議 URI。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。 此 URI 是以焦點為基礎的會議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>可區分週期性會議的執行個體的識別碼。 每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>與此會話相關的會議服務器會議 URI。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。 此 URI 是以會議服務器為基礎的會議 URI。 若為 Focus 會議會話，此欄將會是 null。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議會話中某位使用者的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>識別端點實例的 GUID。 例如，如果一個使用者使用相同的帳戶登入不同的機器，則每一部機器都會有不同的端點識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>指出來電者所代表之使用者的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>轉接此通話之使用者的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議使用者使用的用戶端版本。 如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議服務器所使用的用戶端版本。 如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Foreign</p></td>
<td><p>用來識別目前工作階段所取代之對話的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用來識別工作階段的識別碼。 其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>會指出會議服務器是否已啟動會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>表示會話是否由會議服務器結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>使用者是否從內部登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會話初始通訊協定 (SIP) 回應程式碼加入會話邀請。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從 SIP 標頭擷取而來的診斷識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用於此工作階段之前端伺服器的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>擷取工作階段所在集區的識別碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>通話所使用的轉送伺服器。 如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>通話所使用的閘道。 如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>通話所使用的 Edge Server。 如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>工作階段中所使用的內容類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一個 INVITE 要求的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一次 SIP 回應的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>會話結束的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>Foreign</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 的 UriTypes 表格中</a>包含 MCU URI 類型值。 此欄位是用來改善查詢效能。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>會指出使用者屬性的位組。 下列是屬性的定義：</p>
<ul>
<li><p>與桌面電話-1 整合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>指出通話屬性的位元設定。下列是屬性的定義：</p>
<ul>
<li><p>重新嘗試的會話-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* 對於大部分的會話，SessionIdSeq 的值會是1。 如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。

</div>

<span> </span>

</div>

</div>

</div>

