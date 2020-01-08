---
title: Lync Server 2013：集區失敗期間的通話駐留體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>集區失敗期間使用 Lync Server 2013 的通話駐留體驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

當前端池由於未計畫的事件而無法使用時，已暫停但尚未檢索的通話會中斷連線。 在容錯移轉至備份池期間，使用者會被重新導向至備份池，且處於復原模式。 在復原模式中，使用者不能停止通話，但可以保留通話並加以轉移。 當容錯移轉完成後，就可以再次停用和檢索通話。 在回切期間，使用者不能停止呼叫，直到他們不在復原模式為止。

在災害復原期間，已重新導向至備份池的使用者，如果是作為容錯移轉程式的一部分，則會使用在備份池中部署的通話駐留應用程式。 因此，重新導向至備份池的使用者，請使用針對備份池中的通話駐留應用程式所設定的通話駐留設定。

下表摘要列出災害復原階段的通話寄存體驗。

### <a name="user-experience-during-disaster-recovery"></a>災害復原期間的使用者體驗

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
<th>當停機時間</th>
<th>在容錯移轉期間</th>
<th>在回切期間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通話尚未停用</p></td>
<td><p>通話仍保持連線，但無法停用。</p></td>
<td><ul>
<li><p>在容錯移轉期間，不能在使用者處於復原模式時停用通話，但可以保留並傳送。</p></li>
<li><p>當容錯移轉完成時，可以停用或檢索通話。</p></li>
</ul></td>
<td><ul>
<li><p>在回切期間，不能在使用者處於復原模式時停用通話，但可以保留並傳送。</p></li>
<li><p>當回切完成時，可以停用或檢索通話。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>呼叫已暫停，但尚未檢索</p></td>
<td><p>通話已中斷連線。</p></td>
<td><p>此狀態中沒有通話。</p></td>
<td><p>通話仍保持停用。</p></td>
</tr>
<tr class="odd">
<td><p>已檢索到 [寄存通話]</p></td>
<td><p>通話仍保持連線。</p></td>
<td><p>通話仍保持連線。</p></td>
<td><p>通話仍保持連線。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

