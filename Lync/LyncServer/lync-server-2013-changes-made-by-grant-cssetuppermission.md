---
title: 'Lync Server 2013: Grant-cssetuppermission 所做的變更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Grant-cssetuppermission Lync Server 2013 中所做的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-20 個_

若要委派設定，您可以授與權限的 RTCUniversalServerAdmins 萬用群組特定 Active Directory 組織單位 (OU)，讓該 OU 中指定之安裝 Lync Server 2013 中的 RTCUniversalServerAdmins 群組成員不需要以 Domain Admins 群組成員的網域。

**Grant-cssetuppermission** cmdlet 授與下表中所指定 OU 上的 RTCUniversalServerAdmins 群組權限：

### <a name="permissions-granted-to-objects-in-the-ou"></a>OU 中的物件授與權限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要套用權限：</th>
<th>授與的權限為：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>讀取 servicePrincipalName</p></li>
<li><p>寫入 servicePrincipalName</p></li>
<li><p>刪除樹狀目錄</p></li>
<li><p>「 複寫目錄變更</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子系 serviceConnectionPoint 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>讀取權限</p></li>
<li><p>寫入權限</p></li>
<li><p>建立子項</p></li>
<li><p>刪除子項</p></li>
<li><p>列出內容</p></li>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子系 Msrtcsip-server 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子系 Msrtcsip-webcomponents 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子系 MSRTCSIP-MCU 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子系 Msrtcsip-mediationserver 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子系 Msrtcsip-applicationserver 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子系 Msrtcsip-connectionpoint 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>寫入屬性</p></li>
<li><p>讀取屬性</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子系 Computer 物件</p></td>
<td><p>ServiceConnectionPoint 的特殊存取權：</p>
<ul>
<li><p>建立子物件</p></li>
<li><p>刪除子物件</p></li>
<li><p>刪除樹狀目錄</p></li>
</ul>
<p>公用資訊的特殊存取權：</p>
<ul>
<li><p>讀取屬性</p></li>
</ul>
<p>DNS 主機名稱的特殊存取權：</p>
<ul>
<li><p>讀取屬性</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

