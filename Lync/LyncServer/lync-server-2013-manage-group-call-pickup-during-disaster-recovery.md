---
title: Lync Server 2013：在嚴重損壞修復期間管理群組呼叫收取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d181570b55ce175a63ac1ac1f218ee99aec7a5a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534530"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中管理「在災難修復」期間收取的群組呼叫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

當前端集區因未計畫的事件而變為無法使用時，服務便會容錯移轉至備份組區。 容錯移轉至備份組區時，會將使用者重新導向至備份組區，並以復原模式進行。 在復原模式中，使用者無法挑選其他使用者的來電，或讓其他使用者接聽來電。 容錯移轉完成時，使用者可以再次使用群組呼叫收取。

在回切至主要集區時，會將使用者重新導向至主要集區，並以復原模式重新導向。 除非使用者在復原模式下，否則無法使用群組呼叫收取功能。

本節討論在嚴重損壞復原期間，群組呼叫收取的一些考慮，也說明使用者經驗。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>在嚴重損壞修復期間，群組呼叫收取的考慮

在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用在備份組區中為呼叫收取群組號碼執行的通話駐留應用程式。 因此，在嚴重損壞修復過程中支援群組呼叫收取，需要在主要集區和備份組區中部署及啟用通話駐留應用程式。

備份組區的容錯移轉程式完成後，必須將通話駐留軌道表格中的群組呼叫收取號碼範圍重新導向至備份組區。 當主要集區的回切處理常式完成後，必須重新導向主要集區的號碼範圍。 若要重新導向群組呼叫收取範圍，請使用 **get-cscallparkorbit** Cmdlet。

如果您使用不同的完整功能變數名稱來部署新集區 (FQDN) 取代主要集區，您必須將與主要集區相關聯的所有群組呼叫收取號碼範圍重新指派給新集區的 FQDN。 若要將號碼範圍重新指派給新的集區，您可以使用 **get-cscallparkorbit 指令程式** 。 如需 **get-cscallparkorbit** Cmdlet 的詳細資訊，請參閱 [set-get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>集區失敗期間的群組呼叫收取經驗

下表摘要說明透過嚴重損壞修復的群組呼叫收取經驗。

### <a name="user-experience-during-disaster-recovery"></a>發生嚴重損壞修復的使用者經驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通話狀態</th>
<th>容錯移轉至備份組區</th>
<th>回切至主要集區</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新通話</p></td>
<td><p><strong>容錯移轉過程中：</strong></p>
<ul>
<li><p>使用者在復原模式中無法使用群組呼叫收取</p></li>
</ul>
<p><strong>容錯移轉完成之後：</strong></p>
<ul>
<li><p>當使用者不在恢復能力和群組呼叫收取號碼範圍重新導向至備份組區時可用的群組通話收取</p></li>
</ul></td>
<td><p><strong>在回切過程中：</strong></p>
<ul>
<li><p>使用者在復原模式中無法使用群組呼叫收取</p></li>
</ul>
<p><strong>容錯回復完成後：</strong></p>
<ul>
<li><p>當使用者不在恢復能力和群組呼叫收取號碼範圍重新導向至主要集區時可用的群組通話收取</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>群組呼叫收取佇列中的通話</p></td>
<td><p><strong>容錯移轉過程中：</strong></p>
<ul>
<li><p>佇列中的通話無法透過群組叫用收取應答。</p></li>
</ul>
<p><strong>容錯移轉完成之後：</strong></p>
<ul>
<li><p>這種狀態沒有來電</p></li>
</ul></td>
<td><p><strong>在回切過程中：</strong></p>
<ul>
<li><p>佇列中的通話無法透過群組叫用收取應答。</p></li>
</ul>
<p><strong>容錯回復完成後：</strong></p>
<ul>
<li><p>佇列中的通話無法透過群組叫用收取應答。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>已建立通話</p></td>
<td><p><strong>容錯移轉過程中：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul>
<p><strong>容錯移轉完成之後：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul></td>
<td><p><strong>在回切過程中：</strong></p>
<ul>
<li><p>通話保持連線</p></li>
</ul>
<p><strong>容錯回復完成後：</strong></p>
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

