---
title: Lync Server 2013：tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 中的 tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblNode 包含在 Lync Server 2013 [控制台] 和 [管理 Cmdlet] 中管理的物件樹狀結構（具有類別或聊天室節點）。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個</p></td>
<td><p>int，not null</p></td>
<td><p>節點識別碼（唯一編號）。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>節點 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>父級的節點識別碼。 根節點（含 ID 1）也會將它本身包含在父級中。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit、not null</p></td>
<td><p>如果節點是類別，則為 True。</p>
<p>如果該節點是聊天室，則為 False。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>節點名稱。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>[節點描述]。</p></td>
</tr>
<tr class="odd">
<td><p>參加</p></td>
<td><p>稍微</p></td>
<td><p>針對類別：</p>
<ul>
<li><p>如果邀請開啟，則為 True。</p></li>
<li><p>如果邀請關閉，則為 False。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>如果邀請關閉，則為 False （覆寫上層類別）。</p></li>
<li><p>如果 [邀請] 設定繼承自上層類別，則為 Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>註冊</p></td>
<td><p>稍微</p></td>
<td><p>針對類別：</p>
<ul>
<li><p>如果聊天記錄開啟，則為 True。</p></li>
<li><p>如果聊天記錄為關閉，則為 False。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>非.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>稍微</p></td>
<td><p>針對類別：</p>
<ul>
<li><p>如果允許檔案上傳，則為 True。</p></li>
<li><p>如果不允許檔案上傳，則為 False。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>非.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>禁止</p></td>
<td><p>bit、not null</p></td>
<td><p>如果停用聊天室，則為 True。 僅適用于聊天室。 （[類別] 為 False）。</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>Smallint，not null</p></td>
<td><p>行為（在 EnumValue 資料表中查閱）：</p>
<ul>
<li><p>4：標準（標準聊天室）。</p></li>
<li><p>5： Auditorium （Auditorium 聊天室，只有簡報者可以參與）。</p></li>
</ul>
<p>僅適用于聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>看見</p></td>
<td><p>Smallint，not null</p></td>
<td><p>可見度（在 EnumValue 表格上查閱）：</p>
<ul>
<li><p>2：私人</p></li>
<li><p>3：範圍</p></li>
<li><p>6：開啟</p></li>
</ul>
<p>僅適用于聊天室。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>增益集 GUID （如果增益集與此聊天室相關聯）。 （類別沒有增益集）。</p>
<p>增益集資訊是在 SiopWhiteList 表格中尋找。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int，not null</p></td>
<td><p>建立此節點之主體的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>Bigint，not null</p></td>
<td><p>節點建立的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int，not null</p></td>
<td><p>已執行此節點最新更新之主體的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>Bigint，not null</p></td>
<td><p>此節點最新更新的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>最新清除作業的時間（從 tblScopedPrincipal 資料表中移除作用中的範圍，以及從 tblPrincipalRole 資料表移除角色），這會影響這個節點。 這是由聊天服務的內部快取機制所使用。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="odd">
<td><p>看見</p></td>
<td><p>在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>在 tblNode 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>在 tblSiopWhiteList siopId 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

