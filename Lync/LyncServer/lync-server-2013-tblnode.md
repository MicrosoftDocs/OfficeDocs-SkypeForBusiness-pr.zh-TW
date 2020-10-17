---
title: Lync Server 2013： tblNode
description: Lync Server 2013： tblNode。
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
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547549"
---
# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 中的 tblNode

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblNode 包含類別或聊天室節點的物件樹 () Lync Server 2013 控制台和管理 Cmdlet 中的管理。

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
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int，非 null</p></td>
<td><p>節點識別碼 (唯一編號) 。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID，非 null</p></td>
<td><p>節點 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>父系的節點識別碼。 識別碼為 1) 的根節點 (也會將其本身包含為上層。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果節點為類別。</p>
<p>False 表示節點為聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
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
<td><p>位</p></td>
<td><p>類別：</p>
<ul>
<li><p>True 是表示如果邀請已開啟。</p></li>
<li><p>為 False，則邀請為關閉狀態。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>False 如果邀請已關 (會覆寫父類別) 。</p></li>
<li><p>如果 [邀請] 設定繼承自父系類別，則為 Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>登錄</p></td>
<td><p>位</p></td>
<td><p>類別：</p>
<ul>
<li><p>True 是表示如果聊天記錄開啟。</p></li>
<li><p>為 False，則聊天記錄為關閉狀態。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>空。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>位</p></td>
<td><p>類別：</p>
<ul>
<li><p>True 是表示如果允許檔案上傳。</p></li>
<li><p>False 表示不允許檔案上傳。</p></li>
</ul>
<p>會議室：</p>
<ul>
<li><p>空。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>禁用</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果停用聊天室。 僅適用于聊天室。  (類別為 False。 ) </p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>smallint，非 null</p></td>
<td><p>在 EnumValue table) 中查閱 (行為：</p>
<ul>
<li><p>4：正常 (一般聊天室) 。</p></li>
<li><p>5：視聽中心 (視聽中心聊天室，只有簡報者可以參與) 。</p></li>
</ul>
<p>僅適用于聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint，非 null</p></td>
<td><p>EnumValue table) 上查看的可見度 (：</p>
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
<td><p>Add-In GUID （如果增益集與此聊天室關聯）。  (類別沒有增益集。 ) </p>
<p>增益集資訊會在 SiopWhiteList 表格中進行查閱。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>建立此節點之主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>建立節點的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>進行此節點之最新更新之主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>此節點最新更新的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>最新的清除作業時間 (從影響此節點 tblPrincipalRole 表格) 移除 tblScopedPrincipal 資料表和角色中的範圍。 這是由聊天服務的內部快取更新機制使用。</p></td>
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
<td><p>nodeID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>行為</p></td>
<td><p>在 tblEnumValue.valueID 表格中查閱的外鍵。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>在 tblEnumValue.valueID 表格中查閱的外鍵。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>在 tblNode.nodeID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>在 tblSiopWhiteList.siopId 表格中查閱的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

