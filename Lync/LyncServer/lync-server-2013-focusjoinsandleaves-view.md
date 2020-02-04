---
title: Lync Server 2013： FocusJoinsAndLeaves view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Lync Server 2013 中的 [FocusJoinsAndLeaves] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[FocusJoinsAndLeaves] 視圖儲存有關加入會議的資訊，並留下一個會議的資訊。 每個會議都會在每次使用者加入並離開會議時所撰寫的記錄在這個視圖中顯示。 此視圖已在 Microsoft Lync Server 2013 中推出。


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
<td><p>會議實例的時間。 與 SessionIdSeq 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別會議實例的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>已捕獲會議加入/離開資訊之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已捕獲會議加入/離開資訊之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已捕獲會議加入/離開資訊之使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>已捕獲會議加入/離開資訊之使用者的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已捕獲會議加入/離開資訊的使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>已捕獲會議加入/離開資訊的使用者所使用的用戶端。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>已捕獲會議加入/離開資訊之使用者所使用之用戶端類別的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>稍微</p></td>
<td><p>代表使用者是否為內部使用者的位。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>如果使用者是同時在多部電腦或裝置上登入，則 UserInstance 會用來唯一識別使用者/裝置組合。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>Varchar （775）</p></td>
<td><p>會話的 SIP 對話方塊識別碼。 格式為：對話方塊; 從標籤; 到標籤。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>使用者加入會議的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>使用者離開會議的時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>使用者在會議中的角色，例如 [簡報者] 或 [出席者]。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

