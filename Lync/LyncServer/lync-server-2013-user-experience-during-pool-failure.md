---
title: 集區失敗期間的 Lync Server 2013 使用者經驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63bef718af5664c18ccedca7482e4ca0a0a7f95e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Lync Server 2013 中的集區失敗期間的使用者經驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

如果集區容錯移轉，受影響的集區上的所有使用者都要都強制登出並重新登入備份集區。 短暫期間登入備份集區的使用者可能會在恢復模式中。 在恢復模式中，使用者將無法執行工作所造成的持續性的變更在 Lync 伺服器上，例如新增連絡人。 容錯移轉完成後，所有使用者可以從備份集區都取得所有服務。

任何的使用者具有時之集區失敗的工作階段都會中斷，而使用者必須重新建立這些繼續的容錯移轉後的工作階段。

使用者不會重新放置在容錯移轉或容錯回復期間。 位於失敗的集區的使用者將暫時受到服務，由備份集區。 還原主集區時，系統管理員可以容錯回復到其原始主集區由這些使用者。

附註在 Lync 2013 中，位置資訊伺服器資料庫不會複寫至備份集區。 最佳作法是，管理員應定期備份 LIS 資料庫，並使用最新的備份複本還原 LIS 資料庫在備份集區容錯移轉後。

<div>

## <a name="user-experience-during-failover"></a>容錯移轉期間的使用者體驗

失敗的集區中的使用者時，在使用者登出。使用者已參與任何端對端工作階段終止，因為該使用者召集的會議。 使用者無法登入，直到登錄器恢復計時器到期或系統管理員初始化容錯移轉程序，準。 當使用者登入時，他們將登入備份集區。 如果他們登入容錯移轉完成之前，他們會處於恢復能力模式容錯移轉完成之前。 僅限使用者則可以建立新的工作階段，或重新建立先前工作階段。

</div>

<div>

## <a name="user-experience-during-failback"></a>容錯回復期間的使用者體驗

在受影響的使用者登入備份集區]，並登入並使用容錯回復期間的使用者仍會保留，就會發生集區容錯回復。 請注意，容錯回復程序需要數分鐘才能完成。僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。

下表顯示使用者與 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端會有何影響期間和之後容錯回復，也如何其他集區中的使用者查看並與人員回失敗的集區中的使用者互動的詳細。 使用 Microsoft Office Communicator 2007 R2 用戶端使用者無法登入前端集區完全失敗回直到。）

*受影響使用者*的字詞指的是任何使用者都已從主集區容錯移轉和所服務的備份集區。 根據定義，任何使用者原本裝載於備份集區不是受影響的使用者。

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>在 [容錯回復集區中受影響使用者的使用者經驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者狀態或工作</th>
<th>容錯回復期間</th>
<th>容錯回復完成之後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者已登入的使用者狀態</p></td>
<td><p>使用者保持登入，並連線至備份集區。 有些時候使用者將會被登出並重新登入原始主集區，在恢復模式中。</p></td>
<td><p>使用者維持登入狀態並進入一般模式。</p></td>
</tr>
<tr class="even">
<td><p>新使用者登入</p></td>
<td><p>使用者可以登入恢復能力模式中的主集區。</p></td>
<td><p>使用者可以登入原始主集區，以一般模式。</p></td>
</tr>
<tr class="odd">
<td><p>受影響使用者召集的進行中會議</p></td>
<td><p>會終止所有形式的會議。 重新加入] 按鈕會出現，但受影響的使用者處於恢復能力模式時，可以重新加入任何使用者。</p></td>
<td><p>所有形式即能立即運作。 每位參與者需要按一下 [重新加入會議。</p></td>
</tr>
<tr class="even">
<td><p>不受影響使用者召集的進行中會議</p></td>
<td><p>會議會繼續執行，並受影響使用者能停留在會議中。 受影響的使用者只有他可以在恢復模式中執行的動作。</p></td>
<td><p>會議持續進行，而受影響的使用者能停留在會議中，所有形式皆可運作後使用者退出恢復能力模式。</p></td>
</tr>
<tr class="odd">
<td><p>排程或修改已排程的會議，建立臨機操作會議</p></td>
<td><p>可能無法在使用者處於恢復能力模式。</p></td>
<td><p>適用於所有形式的。</p></td>
</tr>
<tr class="even">
<td><p>相同集區中其他使用者所看到的目前狀態</p></td>
<td><p>目前狀態為不明同時使用者會恢復能力模式期間登入備份集區。</p></td>
<td><p>顯示最後一個目前狀態設定的使用者和目前狀態變更會立即反映。</p></td>
</tr>
<tr class="odd">
<td><p>連絡人清單與通訊錄服務可用性</p></td>
<td><p>不適用</p></td>
<td><p>可以使用</p></td>
</tr>
<tr class="even">
<td><p>所有端對端工作階段與形式</p></td>
<td><p>可以使用</p></td>
<td><p>可以使用</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>使用者的使用者經驗位於另一個集區容錯回復期間不會受到影響的集區

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者工作</th>
<th>容錯回復期間</th>
<th>容錯回復完成之後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>檢視受影響使用者的目前狀態</p></td>
<td><p>顯示受影響使用者所設定的最後一個目前狀態。</p></td>
<td><p>運作。 不會受到影響的使用者會看到受影響的使用者所做的更新。</p></td>
</tr>
<tr class="even">
<td><p>受影響使用者召集的進行中會議</p></td>
<td><p>會終止所有形式的會議。</p></td>
<td><p>所有形式即能立即運作。 每位參與者需要按一下 [重新加入會議。</p></td>
</tr>
<tr class="odd">
<td><p>不受影響使用者召集的進行中會議</p></td>
<td><p>會議持續進行，並受影響的使用者能停留在會議中，所有形式皆可運作。</p></td>
<td><p>會議持續進行，並受影響的使用者能停留在會議中，所有形式皆可運作。</p></td>
</tr>
<tr class="even">
<td><p>所有端對端工作階段與形式</p></td>
<td><p>可以使用</p></td>
<td><p>可以使用</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

