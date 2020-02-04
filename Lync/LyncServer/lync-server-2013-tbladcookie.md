---
title: Lync Server 2013：tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>Lync Server 2013 中的 tblADCookie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-25_

tblADCookie 包含目前的輕型目錄存取通訊協定（LDAP）同步處理 cookie。

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>受監視之網域的主要 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>Nvarchar （255）</p></td>
<td><p>用於 Active Directory 網域服務同步處理之目前網網域控制站的完整功能變數名稱（FQDN）。有資訊值。</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image （二進位）</p></td>
<td><p>Active Directory 同步處理 cookie。</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>含有資料列更新時間的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>[時間]，直到列鎖定變更為止。 這是軟體互鎖機制的一部分，可確保一次只有其中一個聊天服務進行 Active Directory 同步處理。</p></td>
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
<th>欄（s）</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>PrinGuid 表格中的 [查閱] 外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

