---
title: Lync Server 2013： SessionDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Lync Server 2013 中的 [SessionDetails] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

SessionDetails view 會儲存點對點工作階段的相關資訊，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 資料表中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>啟動會話之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>加入會話的使用者 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>加入會話之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>啟動會話之使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>加入會話之使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>啟動會話之使用者之端點的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>加入會話之使用者之端點的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話的結束時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>啟動會話的使用者所傳送的訊息數目。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>加入會話的使用者所傳送的訊息數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話的使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>啟動會話的使用者所使用的用戶端。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>啟動會話之使用者所使用之用戶端類別的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>加入會話的使用者所使用的用戶端版本</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>加入會話的使用者所使用的用戶端。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>加入會話之使用者所使用之用戶端類別的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>會話目標使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>會話的目標使用者 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>代表其啟動會話的使用者 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話所代表之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>代表啟動會話的使用者租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>參照會話之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>參照會話之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>參照會話之使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>Varchar （775）</p></td>
<td><p>SIP 對話方塊識別碼。 格式為：</p>
<p>對話方塊; 從標籤; 到標籤</p></td>
</tr>
<tr class="even">
<td><p><strong>Id</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>用於關聯多個會話的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話所取代的對話方塊時間。 與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別會話的識別碼編號。 與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>Varchar （775）</p></td>
<td><p>[SIP] 對話方塊識別碼，該會話會取代。 格式為：</p>
<p>對話方塊; 從標籤; 到標籤</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>第一次邀請訊息的回復時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>從 SIP 標頭捕獲的診斷 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>會話的內容類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>捕獲會話資料的前端伺服器 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>捕獲會話資料之池的 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話之使用者所使用的邊緣伺服器 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話之使用者所使用的邊緣伺服器 FQDN</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>稍微</p></td>
<td><p>指出啟動會話的使用者是否已從內部網路登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>稍微</p></td>
<td><p>指出加入會話的使用者是否已從內部網路登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>會話的呼叫優先順序。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>指出啟動會話之使用者的屬性。 允許下列屬性定義：</p>
<p>0x01-與桌面電話整合</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>指出啟動會話之使用者的屬性。 允許下列屬性定義：</p>
<p>0x01-與桌面電話整合</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>指出通話屬性。 允許下列屬性定義：</p>
<p>0x01-重新嘗試會話</p>
<p>0x02-代理代表回應群組所做的通話</p></td>
</tr>
<tr class="even">
<td><p><strong>位置</strong></p></td>
<td><p>Varchar （max）</p></td>
<td><p>緊急通話的位置。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

