---
title: Lync Server 2013：ConferenceSessionDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceSessionDetails 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
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
<td><p>會話要求的時間;與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會議會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>與此會話相關的焦點會議 URI。 如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。 此 URI 是以焦點為基礎的會議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>區分週期性會議實例的識別碼。 每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>與此會話相關的會議服務器會議 URI。 如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。 此 URI 是會議服務器的會議 URI。 針對焦點會議會話，此欄會是 null。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>在會議會話中，有一個使用者的識別碼。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>識別端點實例的 GUID。 例如，如果某個使用者使用相同的帳戶登入不同的電腦，則每個電腦將會有不同的端點 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>表示呼叫者代表者的使用者識別碼。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的使用者識別碼。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>會議使用者使用的用戶端版本。 如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>會議服務器所使用的用戶端版本。 如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外</p></td>
<td><p>[識別碼] 編號，找出目前會話所取代的對話方塊。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>識別會話的識別碼編號。 與<strong>ReplacesDialogIdTime</strong>搭配使用，可唯一識別此會話所取代的會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>指示會議服務器是否已啟動會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>表示會議服務器是否已結束會話。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>使用者是否已從內部登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會話初始通訊協定（SIP）回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從 SIP 標頭捕獲的診斷 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>此會話所用的前端伺服器 ID。 如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>捕獲會話的池 ID。 如需詳細資訊，請參閱<a href="lync-server-2013-pools-table.md">Lync Server 2013 中</a>的 [pool] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>通話使用的中繼伺服器。 如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>通話使用的閘道。 如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>通話使用的邊緣伺服器。 如需詳細資訊，請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中</a>的 [EdgeServers] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>會話中使用的內容類型。 如需詳細資訊，請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中</a>的 [主控] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一次 SIP 回應的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
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
<td><p>外</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 的 UriTypes 資料表中</a>包含 MCU URI 類型值。 此欄位可用來改善查詢效能。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>指示使用者屬性的位組。 下列屬性定義如下所示：</p>
<ul>
<li><p>與桌面手機整合-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>指明通話屬性的位組。 下列屬性定義如下所示：</p>
<ul>
<li><p>重試會話-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*在大部分的會話中，SessionIdSeq 將會有1的值。 如果多個會話的開始時間完全相同，則 SessionIdSeq 會是1，另一個會是2，依此類推。

</div>

<span> </span>

</div>

</div>

</div>

