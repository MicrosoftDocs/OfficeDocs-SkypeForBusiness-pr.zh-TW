---
title: Lync Server 2013 集區失敗期間的使用者經驗
description: Lync Server 2013 集區失敗期間的使用者經驗。
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
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569789"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Lync Server 2013 的集區失敗期間的使用者經驗

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

如果集區容錯移轉，則受影響集區的所有使用者都會強制登出，然後登入備份組區。 對於登入備份組區的簡短使用者，其可能是以復原模式進行。 在復原模式中，使用者無法執行會導致 Lync Server 持續變更的任務，例如新增連絡人。 容錯移轉完成後，所有使用者都可以從備份組區取得所有服務。

當集區失敗時，使用者所擁有的任何會話都會中斷，使用者必須在容錯移轉之後重新建立這些會話，以繼續進行。

容錯移轉或回復時，使用者不會 rehomed。 裝載于集區的集區失敗的使用者會暫時為備份組區提供服務。 當您還原主集區時，系統管理員可以使用其原始的主集區來回應這些使用者。

附注在 Lync 2013 中，位置資訊服務器資料庫不會複製到備份組區。 為了獲得最佳作法，管理員應該定期備份 .LIS 資料庫，並使用最新的備份副本，在容錯移轉後，將備份組區中的 IIS 資料庫還原。

<div>

## <a name="user-experience-during-failover"></a>容錯移轉期間的使用者體驗

當使用者處於失敗的集區時，使用者就會登出。使用者參與的任何點對點工作階段都會終止，就像是該使用者所組織的會議。 使用者無法登入，直到註冊機恢復計時器到期，或系統管理員啟動容錯移轉程式為止（從前面開始）。 當使用者重新登入時，他們會登入備份組區。 如果在容錯移轉完成之前登入，則會在容錯移轉完成之前以復原模式進行登入。 只有使用者才能建立新的會話或重新建立先前的會話。

</div>

<div>

## <a name="user-experience-during-failback"></a>容錯回復期間的使用者體驗

當受影響的使用者登入備份組區，且該使用者在回切期間仍保持登入和運作狀態時，便會發生集區回復。 請注意，容錯回復程序需要數分鐘才能完成。僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。

下表顯示如何在回切後和之後，如何影響具有 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端之使用者的詳細資訊，也會顯示其他集區中的使用者如何在容錯回復的集區中查看和與使用者互動。 當前端集區完全失敗後，使用 Microsoft Office Communicator 2007 R2 用戶端的使用者無法登入。 ) 

*受影響的使用者*是指從主集區容錯移轉且由備份組區服務之任何使用者。 根據定義，任何原本位於備份組區的使用者，都不是受影響的使用者。

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>容錯回復集區中受影響使用者的使用者經驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者狀態或任務</th>
<th>回復期間</th>
<th>回復完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者的使用者狀態已登入</p></td>
<td><p>使用者保持登入並聯機至備份組區。 在某些情況下，使用者會以復原模式登入原始的主集區，並以復原模式重新登入。</p></td>
<td><p>使用者保持登入狀態，並且進入一般模式。</p></td>
</tr>
<tr class="even">
<td><p>新使用者登入</p></td>
<td><p>使用者可以以復原模式登入主集區。</p></td>
<td><p>使用者可以採用一般模式登入原始的主集區。</p></td>
</tr>
<tr class="odd">
<td><p>受影響使用者所組織的現行會議</p></td>
<td><p>所有會議形式都會終止。 [重新加入] 按鈕將會出現，但在受影響的使用者處於復原模式時，使用者無法重新加入按鈕。</p></td>
<td><p>所有形式現在均可運作。 每個參與者都需要按一下以重新加入會議。</p></td>
</tr>
<tr class="even">
<td><p>由不受影響的使用者組織的現行會議</p></td>
<td><p>會議持續和受影響的使用者可以保留在會議中。 受影響的使用者限制為以復原模式來執行的動作。</p></td>
<td><p>會議繼續進行，且受影響的使用者可以保留在會議中，而且在使用者結束復原模式後，所有形式都會運作。</p></td>
</tr>
<tr class="odd">
<td><p>排程或修改排程的會議，建立即席會議</p></td>
<td><p>當使用者處於復原模式時，不可能。</p></td>
<td><p>適用于所有形式。</p></td>
</tr>
<tr class="even">
<td><p>相同集區中的其他使用者看到的狀態</p></td>
<td><p>當使用者在復原模式期間登入備份組區時，目前狀態不明。</p></td>
<td><p>顯示使用者設定的最後一個目前狀態，而且現在會反映目前狀態變更。</p></td>
</tr>
<tr class="odd">
<td><p>連絡人清單和通訊錄服務可用性</p></td>
<td><p>不適用</p></td>
<td><p>可以使用</p></td>
</tr>
<tr class="even">
<td><p>所有點對點工作階段和形式</p></td>
<td><p>可以使用</p></td>
<td><p>可以使用</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>使用者在另一個集區的回切期間位於未受影響的集區中的使用者經驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者工作</th>
<th>回復期間</th>
<th>回復完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>查看受影響使用者的目前狀態</p></td>
<td><p>顯示受影響使用者設定的最後一個目前狀態。</p></td>
<td><p>工作。 不受影響的使用者會看到受影響使用者所做的更新。</p></td>
</tr>
<tr class="even">
<td><p>受影響使用者所組織的現行會議</p></td>
<td><p>所有會議形式都會終止。</p></td>
<td><p>所有形式現在均可運作。 每個參與者都需要按一下以重新加入會議。</p></td>
</tr>
<tr class="odd">
<td><p>由不受影響的使用者組織的現行會議</p></td>
<td><p>會議繼續進行，而受影響的使用者可以保留在會議中，而且所有的形式都會運作。</p></td>
<td><p>會議繼續進行，而受影響的使用者可以保留在會議中，而且所有的形式都會運作。</p></td>
</tr>
<tr class="even">
<td><p>所有點對點工作階段和形式</p></td>
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

