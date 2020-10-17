---
title: Lync Server 2013： Grant-CsSetupPermission 所做的變更
description: Lync Server 2013： Grant-CsSetupPermission 所做的變更。
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
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543599"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013 中 Grant-CsSetupPermission 所做的變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

若要委派設定，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 OU 中 RTCUniversalServerAdmins 群組的成員，以在指定的網域中安裝 Lync Server 2013，而不是 Domain Admins 群組的成員。

**Grant-CsSetupPermission** Cmdlet 會授與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所指定：

### <a name="permissions-granted-to-objects-in-the-ou"></a>授與 OU 中物件的許可權

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>許可權適用于：</th>
<th>授與的許可權：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>讀取 servicePrincipalName</p></li>
<li><p>寫入 servicePrincipalName</p></li>
<li><p>刪除樹</p></li>
<li><p>複製目錄變更</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 serviceConnectionPoint 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>讀取權限</p></li>
<li><p>寫入權限</p></li>
<li><p>建立子項</p></li>
<li><p>刪除子項</p></li>
<li><p>清單內容</p></li>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-Server 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-WebComponents 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-MCU 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-MediationServer 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-ApplicationServer 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-ConnectionPoint 物件</p></td>
<td><p>特殊存取權：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代電腦物件</p></td>
<td><p>ServiceConnectionPoint 的特殊存取權：</p>
<ul>
<li><p>建立子物件</p></li>
<li><p>刪除子物件</p></li>
<li><p>刪除樹</p></li>
</ul>
<p>公用資訊的特殊存取權：</p>
<ul>
<li><p>Read 屬性</p></li>
</ul>
<p>DNS 主機名稱的特殊存取權：</p>
<ul>
<li><p>Read 屬性</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

