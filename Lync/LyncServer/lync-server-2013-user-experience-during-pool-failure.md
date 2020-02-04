---
title: 在池失敗期間使用 Lync Server 2013 的使用者體驗
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
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Lync Server 2013 中的池失敗期間的使用者體驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

如果某個池已失敗，則受影響的池的所有使用者都會遭到強制登出，然後登入備份區。 您可以在短時間內登入備份池的使用者可能處於復原模式。 在復原模式中，使用者無法執行會導致 Lync 伺服器上的持久變更（例如新增連絡人）的工作。 當容錯移轉完成後，所有使用者都可以從備份池中取得所有服務。

使用者在池失敗時所擁有的任何會話都會中斷，而且使用者必須在容錯移轉之後重新建立這些會話，才能繼續進行。

在容錯移轉或回切期間，不會 rehomed 使用者。 駐留在失敗的池中的使用者，會暫時由備份池提供服務。 當主池已還原時，系統管理員可以將這些使用者以其原始的主文件庫提供服務，以進行容錯回復。

注意：在 Lync 2013 中，位置資訊服務器資料庫不會複製到備份池中。 針對最佳做法，系統管理員應該定期備份 IIS 資料庫，並在容錯移轉後使用最新的備份複本來還原備份池中的 .LIS 資料庫。

<div>

## <a name="user-experience-during-failover"></a>容錯移轉期間的使用者體驗

當使用者位於失敗的池中時，使用者就會登出。使用者參與的任何點對點工作階段都會終止，就像是由該使用者組織的會議一樣。 使用者無法再次登入，直到註冊機復原計時器過期，或由管理員啟動容錯移轉程式（依哪一項操作）。 當使用者重新登入時，他們會登入備份池中。 如果他們在容錯移轉完成之前登入，則在容錯移轉完成之前，它們將處於復原模式。 只有使用者可以建立新的會話，或重新建立先前的會話。

</div>

<div>

## <a name="user-experience-during-failback"></a>在回切期間的使用者體驗

當受影響的使用者登入備份池中，且使用者在回切期間仍保持登入狀態且正常運作時，可能會發生池容錯回復。 請注意，容錯回復程式需要幾分鐘的時間才能完成。針對參考，對於20000使用者，預期會需要最多60分鐘的時間。

下表顯示更多關於 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端在回切期間和之後如何受到影響的詳細資料，以及其他池中的使用者如何在發生故障的池中的使用者之間查看和互動。 使用 Microsoft Office Communicator 2007 R2 用戶端的使用者無法登入，直到頂層池完全失敗。）

*受影響的使用者*會參照任何從主池中失敗且由備份池提供服務的使用者。 根據定義，任何原先駐留在備份池中的使用者，都不是受影響的使用者。

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>在回切期間，池中受影響使用者的使用者體驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者狀態或任務</th>
<th>在回切期間</th>
<th>在回切完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者已登入的使用者狀態</p></td>
<td><p>使用者保持登入並聯機至備份池。 在某個時間點，使用者將會在復原模式中登出並重新登入原始的主文件庫。</p></td>
<td><p>使用者保持登入狀態，並進入一般模式。</p></td>
</tr>
<tr class="even">
<td><p>登入的新使用者</p></td>
<td><p>使用者可以以復原模式登入主池中。</p></td>
<td><p>使用者可以在標準模式中登入原始的主版池。</p></td>
</tr>
<tr class="odd">
<td><p>依受影響的使用者組織的日常會議</p></td>
<td><p>所有的會議形式都是終止的。 隨即會顯示 [重新加入] 按鈕，但使用者無法在受影響的使用者處於復原模式時重新加入。</p></td>
<td><p>所有形式現在都能正常運作。 每個參與者都需要按一下才能重新加入會議。</p></td>
</tr>
<tr class="even">
<td><p>依未受影響的使用者組織的日常會議</p></td>
<td><p>會議持續且受影響的使用者可以繼續參與會議。 受影響的使用者會受到其在復原模式中所能執行的動作限制。</p></td>
<td><p>會議持續進行，而且受影響的使用者可在使用者結束復原模式之後，繼續進行會議，且所有形式都能正常運作。</p></td>
</tr>
<tr class="odd">
<td><p>排程或修改排程的會議，建立臨時會議</p></td>
<td><p>使用者處於復原模式時無法進行。</p></td>
<td><p>適用于所有形式。</p></td>
</tr>
<tr class="even">
<td><p>同一個池中的其他使用者所看到的目前狀態</p></td>
<td><p>使用者在復原模式期間登入備份池時，目前狀態為未知。</p></td>
<td><p>顯示使用者設定的最後一個目前狀態狀態，目前狀態變更現在會得到反映。</p></td>
</tr>
<tr class="odd">
<td><p>連絡人清單和通訊錄服務的可用性</p></td>
<td><p>無法使用</p></td>
<td><p>離線</p></td>
</tr>
<tr class="even">
<td><p>所有點對點工作階段與形式</p></td>
<td><p>離線</p></td>
<td><p>離線</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>使用者在另一個池的回切期間駐留在未受影響的池中的使用者體驗

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者任務</th>
<th>在回切期間</th>
<th>在回切完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>查看受影響使用者的目前狀態</p></td>
<td><p>顯示受影響使用者所設定的最後一個目前狀態。</p></td>
<td><p>工作日. 未受影響的使用者會看到受影響使用者所做的更新。</p></td>
</tr>
<tr class="even">
<td><p>依受影響的使用者組織的日常會議</p></td>
<td><p>所有的會議形式都是終止的。</p></td>
<td><p>所有形式現在都能正常運作。 每個參與者都需要按一下才能重新加入會議。</p></td>
</tr>
<tr class="odd">
<td><p>依未受影響的使用者組織的日常會議</p></td>
<td><p>會議持續進行，而且受影響的使用者可以繼續參與會議，且所有形式都能正常運作。</p></td>
<td><p>會議持續進行，而且受影響的使用者可以繼續參與會議，且所有形式都能正常運作。</p></td>
</tr>
<tr class="even">
<td><p>所有點對點工作階段與形式</p></td>
<td><p>離線</p></td>
<td><p>離線</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

