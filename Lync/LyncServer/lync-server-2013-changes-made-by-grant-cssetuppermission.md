---
title: Lync Server 2013：由授與授權所做的變更 CsSetupPermission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>在 Lync Server 2013 中由 Grant CsSetupPermission 所做的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

若要委派設定，您可以為特定 Active Directory 組織單位（OU）授予 RTCUniversalServerAdmins 通用群組的許可權，讓該 OU 中的 RTCUniversalServerAdmins 群組成員在指定的中安裝 Lync Server 2013。網域，而不是 [網域管理員] 群組的成員。

CsSetupPermission Cmdlet 會**授**與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所示：

### <a name="permissions-granted-to-objects-in-the-ou"></a>在 OU 中授與物件的許可權

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>許可權適用于：</th>
<th>已授與許可權：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Read servicePrincipalName</p></li>
<li><p>撰寫 servicePrincipalName</p></li>
<li><p>刪除樹</p></li>
<li><p>複製目錄變更</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>後代 serviceConnectionPoint 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>讀取權限</p></li>
<li><p>寫入權限</p></li>
<li><p>建立子系</p></li>
<li><p>刪除子系</p></li>
<li><p>清單內容</p></li>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-伺服器物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-WebComponents 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-MCU 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-MediationServer 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-ApplicationServer 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-ConnectionPoint 物件</p></td>
<td><p>特殊存取：</p>
<ul>
<li><p>Write 屬性</p></li>
<li><p>Read 屬性</p></li>
<li><p>刪除樹</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>後代電腦物件</p></td>
<td><p>用於 serviceConnectionPoint 的特殊存取：</p>
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

