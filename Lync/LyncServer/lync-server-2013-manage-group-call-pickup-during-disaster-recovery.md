---
title: Lync Server 2013：管理在災害復原期間進行挑選的群組呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 的災害復原期間管理群組呼叫挑選

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

當前端池由於未計畫的事件而無法使用時，服務就會失敗轉移至備份池。 在容錯移轉至備份池期間，使用者會被重新導向至備份池，且處於復原模式。 在復原模式中，使用者無法挑選其他使用者的通話，或由其他使用者接聽來電。 當容錯移轉完成時，使用者可以再次使用群組呼叫拾取。

在回切至主要池期間，使用者會被重新導向到主要池，且再次處於復原模式。 [群組呼叫] 功能無法使用，直到使用者不在復原模式為止。

本節討論災害復原期間群組通話拾取的一些考慮，同時也說明使用者體驗。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>在災害復原期間進行群組呼叫挑選的考慮

在災害復原期間，已重新導向至備份池的使用者，如果是作為容錯移轉程式的一部分，則會使用在備份池中為呼叫挑選群組編號執行的通話駐留應用程式。 因此，在災害復原期間對群組呼叫挑選的支援，必須在主要池和備份池中部署並啟用呼叫駐留應用程式。

在備份池完成容錯移轉程式後，必須將 [通話駐留軌道] 表格中的群組呼叫挑選編號範圍重新導向至備份池。 在回切處理常式完成後，必須將數位範圍重新導向到主要池。 若要重新導向群組呼叫範圍，請使用**CsCallParkOrbit** Cmdlet。

如果您使用不同的完整功能變數名稱（FQDN）部署新的池來取代主要池，您必須將與主要池相關聯的所有群組呼叫拾取號碼範圍重新指派給新的池的 FQDN。 若要將數位範圍重新指派給新的池中，您可以使用**CsCallParkOrbit** Cmdlet。 如需**CsCallParkOrbit** Cmdlet 的詳細資訊，請參閱[設定 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>在池失敗期間的群組呼叫裝貨體驗

下表摘要列出透過災難復原階段的群組通話體驗。

### <a name="user-experience-during-disaster-recovery"></a>災害復原期間的使用者體驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通話狀態</th>
<th>容錯移轉至備份池</th>
<th>回切至主要池</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新的通話</p></td>
<td><p><strong>在容錯移轉處理期間：</strong></p>
<ul>
<li><p>使用者處於復原模式時無法使用群組呼叫挑選</p></li>
</ul>
<p><strong>容錯移轉完成後：</strong></p>
<ul>
<li><p>當使用者離開復原，且群組呼叫挑選號碼範圍被重新導向至備份池時，可以使用群組通話裝貨</p></li>
</ul></td>
<td><p><strong>在回切進程期間：</strong></p>
<ul>
<li><p>使用者處於復原模式時無法使用群組呼叫挑選</p></li>
</ul>
<p><strong>回切完成後：</strong></p>
<ul>
<li><p>當使用者不能復原且群組呼叫挑選號碼範圍被重新導向到主要池時，可以使用群組通話裝貨</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>在群組呼叫分揀佇列中通話</p></td>
<td><p><strong>在容錯移轉處理期間：</strong></p>
<ul>
<li><p>無法透過群組呼叫挑選來應答佇列中的通話。</p></li>
</ul>
<p><strong>容錯移轉完成後：</strong></p>
<ul>
<li><p>此狀態中沒有通話</p></li>
</ul></td>
<td><p><strong>在回切進程期間：</strong></p>
<ul>
<li><p>無法透過群組呼叫挑選來應答佇列中的通話。</p></li>
</ul>
<p><strong>回切完成後：</strong></p>
<ul>
<li><p>無法透過群組呼叫挑選來應答佇列中的通話。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>已建立通話</p></td>
<td><p><strong>在容錯移轉處理期間：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul>
<p><strong>容錯移轉完成後：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul></td>
<td><p><strong>在回切進程期間：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul>
<p><strong>回切完成後：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

