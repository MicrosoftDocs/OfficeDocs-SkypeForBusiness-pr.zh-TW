---
title: 'Lync Server 2013: ConferenceSessionDetails 表格'
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
ms.openlocfilehash: 3e991f6240d9c21815299a3ef169c5824cf5ef3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceSessionDetails 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

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
<th>主索引鍵 /</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>工作階段要求;<strong>SessionIdSeq</strong>搭配使用來唯一地識別會議工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要，外部</p></td>
<td><p>用來識別工作階段的識別碼。 搭配<strong>SessionIdTime</strong>用來唯一地識別會議工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>此工作階段相關焦點會議 URI。 請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。 此 URI 是基於 Focus 的會議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>可區分週期性會議的執行個體的識別碼。 每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議伺服器會議 URI 相關此工作階段。 請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。 此 URI 是會議伺服器型會議 URI。 焦點會議工作階段，此欄都是 null。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>在會議工作階段中的一位使用者的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>GUID，以識別端點的執行個體。 例如，如果不同的電腦，以相同的帳戶登入一位使用者，然後每一部機器會有不同的端點識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>指出來電者所代表之使用者的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>轉接此通話之使用者的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議使用者所使用的用戶端版本。 請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議伺服器所使用的用戶端版本。 請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Foreign</p></td>
<td><p>用來識別目前工作階段所取代之對話的識別碼。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用來識別工作階段的識別碼。 其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>會指出由會議伺服器是否啟動工作階段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>會指出是否工作階段結束透過會議伺服器。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>是否使用者登入從內部或不。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>工作階段初始通訊協定 (SIP) 工作階段邀請的回應碼。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
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
<td><p>用於此工作階段之前端伺服器的識別碼。 請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>擷取工作階段所在集區的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>中繼伺服器通話使用。 請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用通話的閘道。 請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用 Edge Server 通話。 請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>工作階段中所使用的內容類型。 請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a>如需詳細資訊。</p></td>
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
<td><p>第一個 SIP 回應的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>工作階段結束時的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Foreign</p></td>
<td><p>包含<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>MCU 的 URI 類型值。 提升查詢效能會使用此欄位。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>這表示使用者屬性的位元。 下列是屬性的定義：</p>
<ul>
<li><p>整合與桌上電話-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指出通話屬性的位元設定。下列是屬性的定義：</p>
<ul>
<li><p>重試工作階段-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*對於大多數的工作階段，SessionIdSeq 會有 1 的值。 如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。

</div>

<span> </span>

</div>

</div>

</div>

