---
title: Lync Server 2013：集區失敗期間的通話駐留體驗
description: Lync Server 2013：集區失敗期間的通話駐留體驗。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565269"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>集區失敗期間的 Lync Server 2013 中的通話駐留體驗

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

當前端集區因未計畫的事件而變為無法使用時，已寄存但尚未找回的來電會中斷連線。 容錯移轉至備份組區時，會將使用者重新導向至備份組區，並以復原模式進行。 在復原模式中，使用者無法寄存通話，但是可以保留通話，並將其轉接。 容錯移轉完成之後，就可以再照常停用和找回通話。 在回切期間內，使用者將無法寄存通話，直到其無法恢復執行模式為止。

在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用部署于備份組區中的通話駐留應用程式。 因此，重新導向至備份組區的使用者，會使用針對備份組區中的通話駐留應用程式所設定的通話駐留設定。

下表摘要說明災難復原階段的通話駐留體驗。

### <a name="user-experience-during-disaster-recovery"></a>發生嚴重損壞修復的使用者經驗

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話狀態</th>
<th>當中斷發生時</th>
<th>容錯移轉期間</th>
<th>回復期間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>尚未寄存通話</p></td>
<td><p>通話保持連線，但無法寄存。</p></td>
<td><ul>
<li><p>在容錯移轉期間，使用者處於復原模式，無法駐留通話，但可保留與轉接通話。</p></li>
<li><p>容錯移轉完成時，可以寄存及取回通話。</p></li>
</ul></td>
<td><ul>
<li><p>在回復期間，使用者處於復原模式，無法駐留通話，但可保留與轉接通話。</p></li>
<li><p>當回切完成時，可以寄存及取回通話。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>通話已寄存，但尚未找回</p></td>
<td><p>通話中斷連線。</p></td>
<td><p>沒有處於此狀態的來電。</p></td>
<td><p>通話保持寄存狀態。</p></td>
</tr>
<tr class="odd">
<td><p>已找回寄存通話</p></td>
<td><p>通話保持連線。</p></td>
<td><p>通話保持連線。</p></td>
<td><p>通話保持連線。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

