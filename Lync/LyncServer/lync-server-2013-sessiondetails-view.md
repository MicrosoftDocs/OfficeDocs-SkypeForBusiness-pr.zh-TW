---
title: Lync Server 2013： SessionDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510060"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a>Lync Server 2013 中的 SessionDetails 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

SessionDetails view 儲存點對點工作階段的資訊，這可能是 VoIP-VoIP 電話、兩方 IM 會話或其他類型的會話。 此視圖已引進于 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表格中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>第一個邀請要求的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>啟動會話之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>加入會話之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>啟動會話之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>加入會話之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>啟動會話之使用者的租使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>加入會話之使用者的租使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td><p>啟動會話之使用者的端點唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td><p>加入會話之使用者的端點唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>工作階段結束時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>啟動會話之使用者所傳送的訊息數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>加入會話之使用者所傳送的訊息數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>啟動會話之使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>啟動會話之使用者所使用的用戶端。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>啟動會話之使用者所使用的用戶端類別名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>加入會話之使用者所使用的用戶端版本</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>加入會話之使用者所使用的用戶端。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>加入會話之使用者所使用的用戶端類別名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>會話目標使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>會話之目標使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>代表啟動工作階段之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>代表啟動工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>代表啟動工作階段之使用者的租用戶。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>引用工作階段之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>引用工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>引用工作階段之使用者的租用戶。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>Varchar (775) </p></td>
<td><p>SIP 對話方塊識別碼。 格式為：</p>
<p>dialog; 從-標籤; to-標記</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>唯一</p></td>
<td><p>用於關聯多個會話的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話所取代之對話方塊的時間。 與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別工作階段的 ID 號碼。 與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>Varchar (775) </p></td>
<td><p>工作階段取代的 SIP 對話方塊識別碼。 格式為：</p>
<p>dialog; 從-標籤; to-標記</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>從 SIP 標頭捕獲的診斷識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>會話的內容類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>擷取工作階段適用之資料的前端伺服器 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>擷取工作階段適用之資料的集區 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>啟動會話之使用者所使用的 Edge server FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>啟動會話之使用者所使用的 Edge server FQDN</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>位</p></td>
<td><p>會指出啟動會話的使用者是否從內部網路登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>位</p></td>
<td><p>會指出加入會話的使用者是否從內部網路登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>會話的呼叫優先順序。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>會指出啟動會話之使用者的屬性。 以下為允許的屬性定義：</p>
<p>0x01 - 與桌上電話整合</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>會指出啟動會話之使用者的屬性。 以下為允許的屬性定義：</p>
<p>0x01 - 與桌上電話整合</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>指出通話屬性。以下為允許的屬性定義：</p>
<p>0x01 - 重試工作階段 1</p>
<p>0x02-代理程式代表回應群組所撥打的通話</p></td>
</tr>
<tr class="even">
<td><p><strong>位置</strong></p></td>
<td><p>Varchar (max) </p></td>
<td><p>緊急電話的位置。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

