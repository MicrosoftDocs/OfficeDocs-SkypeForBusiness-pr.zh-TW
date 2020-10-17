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
ms.openlocfilehash: 8b71678b9fbd19cfd52c81976de0955ea39ce9e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500820"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Lync Server 2013 中的 FocusJoinsAndLeaves 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

FocusJoinsAndLeaves 檢視可儲存會議的加入和離開相關資訊。 每次有使用者加入和離開某場會議時，此檢視中的該場會議都會有一筆撰寫記錄來表示。 此視圖已引進于 Microsoft Lync Server 2013。


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
<td><p>會議執行個體的時間。 會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用於辨識執行個體的 ID 號碼。 會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>已擷取其加入/離開會議資訊之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已擷取其加入/離開會議資訊之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已擷取其加入/離開會議資訊之使用者的租用戶。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td><p>已擷取其加入/離開會議資訊之使用者的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已擷取其加入/離開會議資訊之使用者所用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>已擷取其加入/離開會議資訊之使用者所用的用戶端。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>已擷取其加入/離開會議資訊之使用者所用的用戶端類別名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>位</p></td>
<td><p>代表使用者是否為內部使用者的位元。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>若使用者同時登入多部電腦或裝置，會使用 UserInstance 專門識別使用者/裝置的組合。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>Varchar (775) </p></td>
<td><p>工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。</p></td>
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
<td><p>Nvarchar (256) </p></td>
<td><p>此使用者在會議中的角色，例如簡報者或是出席者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

