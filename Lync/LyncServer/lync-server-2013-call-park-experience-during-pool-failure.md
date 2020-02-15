---
title: 集區失敗期間的 Lync Server 2013： 通話駐留經驗
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
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Lync Server 2013 的集區失敗期間的通話駐留經驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-10_

前端集區由於意外事件無法使用時，已駐留但尚未擷取通話中斷連線。 容錯移轉期間至備份集區，使用者會重新導向至備份集區，且處於恢復能力模式。 在恢復能力模式時，使用者無法駐留通話，但他們可以撥打電話保留並將他們轉接。 完成容錯移轉時，呼叫一次可駐留及擷取像平常一樣。 容錯回復期間，使用者無法駐留通話，除非經過退出恢復能力模式。

嚴重損壞復原期間已重新導向至備份集區一部分的容錯移轉程序的使用者會使用備份集區中部署通話駐留應用程式。 因此，會重新導向至備份集區的使用者會使用所設定的通話駐留設定的備份集區的通話駐留應用程式。

下表摘要說明透過災難復原階段的通話駐留經驗。

### <a name="user-experience-during-disaster-recovery"></a>嚴重損壞復原期間的使用者經驗

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫狀態</th>
<th>發生中斷時</th>
<th>容錯移轉期間</th>
<th>容錯回復期間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>尚未駐留通話</p></td>
<td><p>通話保持連線，但無法駐留通話。</p></td>
<td><ul>
<li><p>容錯移轉期間，當使用者處於復原模式，但可以保留與轉接無法駐留通話。</p></li>
<li><p>完成容錯移轉時，可以駐留與擷取通話。</p></li>
</ul></td>
<td><ul>
<li><p>容錯回復期間，當使用者處於復原模式，但可以保留與轉接無法駐留通話。</p></li>
<li><p>完成容錯回復時，可以駐留與擷取通話。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>通話已駐留，但尚未擷取</p></td>
<td><p>通話已中斷。</p></td>
<td><p>沒有通話處於此狀態。</p></td>
<td><p>通話保持駐留。</p></td>
</tr>
<tr class="odd">
<td><p>已擷取通話</p></td>
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

