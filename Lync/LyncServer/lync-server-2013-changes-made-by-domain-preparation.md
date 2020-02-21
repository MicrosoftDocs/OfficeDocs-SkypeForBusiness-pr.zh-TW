---
title: Lync Server 2013： 網域準備所進行的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013 中的網域準備所進行的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010年-10-18_

下表列出網域準備作業會建立在網域根目錄存取控制項目 (Ace)。 除非另有說明，是繼承而來的所有 Ace。

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>新增到網域根目錄的 Ace

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal UserReadOnly 群組</th>
<th>RTCUniversal ServerReadOnly 群組</th>
<th>RTCUniversal UserAdmins</th>
<th>RTCHSUniversal 服務</th>
<th>驗證使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>讀取容器 （非繼承的）</p></td>
<td><p><strong>是</strong></p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>讀取使用者 User-account-restrictions 帳戶限制</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>讀取使用者 Personal-information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>讀取使用者 General-information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>讀取使用者 Public-information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>讀取使用者屬性集 Rtcusersearchproperty-set</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
</tr>
<tr class="odd">
<td><p>讀取使用者屬性集 RTCPropertySet</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>寫入使用者屬性 Proxy-addresses</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>寫入使用者屬性集 Rtcusersearchproperty-set</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>寫入使用者屬性集 RTCPropertySet</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>讀取屬性 DS-複寫的 Get-變更的所有 Active Directory 物件</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>無</p></td>
</tr>
</tbody>
</table>


下表列出網域準備會在三個內建容器中建立之 Ace： 使用者、 電腦和網域控制站。 除非另有說明，是繼承而來的所有 Ace。

### <a name="aces-added-to-built-in-containers"></a>新增到內建容器的 Ace

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal UserReadOnly 群組</th>
<th>RTCUniversal ServerReadOnly 群組</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>讀取容器 （非繼承的）</p></td>
<td><p><strong>是</strong></p></td>
<td><p><strong>是</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

