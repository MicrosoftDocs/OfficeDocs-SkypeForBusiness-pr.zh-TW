---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 中的 tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblNode 受管理的 Lync Server 2013 控制台和系統管理指令程式中會包含物件樹狀目錄 （含有類別或聊天室節點）。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>類型	</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>節點識別碼</p></td>
<td><p>int，非 null</p></td>
<td><p>節點識別碼 （唯一號碼）。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID，非 null</p></td>
<td><p>節點 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>父代的節點識別碼。 根節點 （以識別碼 1) 會包含本身作為父也。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>位元，非 null</p></td>
<td><p>如果該節點是類別，則為 true。</p>
<p>如果該節點是聊天室，則為 false。</p></td>
</tr>
<tr class="odd">
<td><p>節點</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>節點名稱。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>節點描述。</p></td>
</tr>
<tr class="odd">
<td><p>邀請</p></td>
<td><p>位元</p></td>
<td><p>對於類別：</p>
<ul>
<li><p>如果啟用 invite，則為 true。</p></li>
<li><p>若關閉 invite，則為 false。</p></li>
</ul>
<p>對於會議室：</p>
<ul>
<li><p>若關閉 invite，則為 false （覆寫父系類別）。</p></li>
<li><p>如果從父系類別繼承的設定 invite，則為 null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>登入</p></td>
<td><p>位元</p></td>
<td><p>對於類別：</p>
<ul>
<li><p>如果聊天記錄，則為 true。</p></li>
<li><p>如果聊天歷程記錄已關閉，則為 false。</p></li>
</ul>
<p>對於會議室：</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>位元</p></td>
<td><p>對於類別：</p>
<ul>
<li><p>如果允許檔案上傳，則為 true。</p></li>
<li><p>如果不允許檔案上傳，則為 false。</p></li>
</ul>
<p>對於會議室：</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>停用</p></td>
<td><p>位元，非 null</p></td>
<td><p>如果已停用聊天室，則為 true。 僅適用於聊天室。 (False 類別)。</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>smallint，非 null</p></td>
<td><p>行為 （在 EnumValue 表格中查閱）：</p>
<ul>
<li><p>4： 一般 （一般聊天室）。</p></li>
<li><p>5： 視聽中心 （視聽中心聊天室，只有簡報者可以參與）。</p></li>
</ul>
<p>僅適用於聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint，非 null</p></td>
<td><p>可見度 （在 EnumValue 表格中查閱）：</p>
<ul>
<li><p>2： 私用</p></li>
<li><p>3： 範圍</p></li>
<li><p>6： 開啟</p></li>
</ul>
<p>僅適用於聊天室。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>增益集的 GUID 如果增益集是此聊天室相關聯。 （類別不需要增益集。）</p>
<p>增益集的資訊會在 SiopWhiteList 表格中查閱。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>建立此節點之主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>節點建立的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>最近一次更新此節點之主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>最近一次此節點更新的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>最新清除作業 （移除從 tblScopedPrincipal 表格的範圍，以及從 tblPrincipalRole 表格角色），此節點會受到影響的時間。 這會使用聊天服務的內部快取更新機制。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>索引鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>節點識別碼</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>在 tblEnumValue.valueID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>在 tblEnumValue.valueID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>在 tblNode.nodeID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>在 tblSiopWhiteList.siopId 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

