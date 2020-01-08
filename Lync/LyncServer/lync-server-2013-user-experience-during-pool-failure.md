---
title: 在池失敗期間使用 Lync Server 2013 的使用者體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="9e471-102">Lync Server 2013 中的池失敗期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9e471-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e471-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9e471-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9e471-104">如果某個池已失敗，則受影響的池的所有使用者都會遭到強制登出，然後登入備份區。</span><span class="sxs-lookup"><span data-stu-id="9e471-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="9e471-105">您可以在短時間內登入備份池的使用者可能處於復原模式。</span><span class="sxs-lookup"><span data-stu-id="9e471-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="9e471-106">在復原模式中，使用者無法執行會導致 Lync 伺服器上的持久變更（例如新增連絡人）的工作。</span><span class="sxs-lookup"><span data-stu-id="9e471-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="9e471-107">當容錯移轉完成後，所有使用者都可以從備份池中取得所有服務。</span><span class="sxs-lookup"><span data-stu-id="9e471-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="9e471-108">使用者在池失敗時所擁有的任何會話都會中斷，而且使用者必須在容錯移轉之後重新建立這些會話，才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="9e471-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="9e471-109">在容錯移轉或回切期間，不會 rehomed 使用者。</span><span class="sxs-lookup"><span data-stu-id="9e471-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="9e471-110">駐留在失敗的池中的使用者，會暫時由備份池提供服務。</span><span class="sxs-lookup"><span data-stu-id="9e471-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="9e471-111">當主池已還原時，系統管理員可以將這些使用者以其原始的主文件庫提供服務，以進行容錯回復。</span><span class="sxs-lookup"><span data-stu-id="9e471-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="9e471-112">注意：在 Lync 2013 中，位置資訊服務器資料庫不會複製到備份池中。</span><span class="sxs-lookup"><span data-stu-id="9e471-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="9e471-113">針對最佳做法，系統管理員應該定期備份 IIS 資料庫，並在容錯移轉後使用最新的備份複本來還原備份池中的 .LIS 資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e471-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="9e471-114">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9e471-114">User Experience During Failover</span></span>

<span data-ttu-id="9e471-115">當使用者位於失敗的池中時，使用者就會登出。使用者參與的任何點對點工作階段都會終止，就像是由該使用者組織的會議一樣。</span><span class="sxs-lookup"><span data-stu-id="9e471-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="9e471-116">使用者無法再次登入，直到註冊機復原計時器過期，或由管理員啟動容錯移轉程式（依哪一項操作）。</span><span class="sxs-lookup"><span data-stu-id="9e471-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="9e471-117">當使用者重新登入時，他們會登入備份池中。</span><span class="sxs-lookup"><span data-stu-id="9e471-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="9e471-118">如果他們在容錯移轉完成之前登入，則在容錯移轉完成之前，它們將處於復原模式。</span><span class="sxs-lookup"><span data-stu-id="9e471-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="9e471-119">只有使用者可以建立新的會話，或重新建立先前的會話。</span><span class="sxs-lookup"><span data-stu-id="9e471-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="9e471-120">在回切期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9e471-120">User Experience During Failback</span></span>

<span data-ttu-id="9e471-121">當受影響的使用者登入備份池中，且使用者在回切期間仍保持登入狀態且正常運作時，可能會發生池容錯回復。</span><span class="sxs-lookup"><span data-stu-id="9e471-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="9e471-122">請注意，容錯回復程式需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="9e471-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="9e471-123">針對參考，對於20000使用者，預期會需要最多60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="9e471-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="9e471-124">下表顯示更多關於 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端在回切期間和之後如何受到影響的詳細資料，以及其他池中的使用者如何在發生故障的池中的使用者之間查看和互動。</span><span class="sxs-lookup"><span data-stu-id="9e471-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="9e471-125">使用 Microsoft Office Communicator 2007 R2 用戶端的使用者無法登入，直到頂層池完全失敗。）</span><span class="sxs-lookup"><span data-stu-id="9e471-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="9e471-126">*受影響的使用者*會參照任何從主池中失敗且由備份池提供服務的使用者。</span><span class="sxs-lookup"><span data-stu-id="9e471-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="9e471-127">根據定義，任何原先駐留在備份池中的使用者，都不是受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="9e471-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="9e471-128">在回切期間，池中受影響使用者的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9e471-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e471-129">使用者狀態或任務</span><span class="sxs-lookup"><span data-stu-id="9e471-129">User state or task</span></span></th>
<th><span data-ttu-id="9e471-130">在回切期間</span><span class="sxs-lookup"><span data-stu-id="9e471-130">During failback</span></span></th>
<th><span data-ttu-id="9e471-131">在回切完成後</span><span class="sxs-lookup"><span data-stu-id="9e471-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e471-132">使用者已登入的使用者狀態</span><span class="sxs-lookup"><span data-stu-id="9e471-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="9e471-133">使用者保持登入並聯機至備份池。</span><span class="sxs-lookup"><span data-stu-id="9e471-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="9e471-134">在某個時間點，使用者將會在復原模式中登出並重新登入原始的主文件庫。</span><span class="sxs-lookup"><span data-stu-id="9e471-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-135">使用者保持登入狀態，並進入一般模式。</span><span class="sxs-lookup"><span data-stu-id="9e471-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-136">登入的新使用者</span><span class="sxs-lookup"><span data-stu-id="9e471-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="9e471-137">使用者可以以復原模式登入主池中。</span><span class="sxs-lookup"><span data-stu-id="9e471-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-138">使用者可以在標準模式中登入原始的主版池。</span><span class="sxs-lookup"><span data-stu-id="9e471-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e471-139">依受影響的使用者組織的日常會議</span><span class="sxs-lookup"><span data-stu-id="9e471-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="9e471-140">所有的會議形式都是終止的。</span><span class="sxs-lookup"><span data-stu-id="9e471-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="9e471-141">隨即會顯示 [重新加入] 按鈕，但使用者無法在受影響的使用者處於復原模式時重新加入。</span><span class="sxs-lookup"><span data-stu-id="9e471-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-142">所有形式現在都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="9e471-142">All modalities now work.</span></span> <span data-ttu-id="9e471-143">每個參與者都需要按一下才能重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="9e471-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-144">依未受影響的使用者組織的日常會議</span><span class="sxs-lookup"><span data-stu-id="9e471-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="9e471-145">會議持續且受影響的使用者可以繼續參與會議。</span><span class="sxs-lookup"><span data-stu-id="9e471-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="9e471-146">受影響的使用者會受到其在復原模式中所能執行的動作限制。</span><span class="sxs-lookup"><span data-stu-id="9e471-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-147">會議持續進行，而且受影響的使用者可在使用者結束復原模式之後，繼續進行會議，且所有形式都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="9e471-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e471-148">排程或修改排程的會議，建立臨時會議</span><span class="sxs-lookup"><span data-stu-id="9e471-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="9e471-149">使用者處於復原模式時無法進行。</span><span class="sxs-lookup"><span data-stu-id="9e471-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-150">適用于所有形式。</span><span class="sxs-lookup"><span data-stu-id="9e471-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-151">同一個池中的其他使用者所看到的目前狀態</span><span class="sxs-lookup"><span data-stu-id="9e471-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="9e471-152">使用者在復原模式期間登入備份池時，目前狀態為未知。</span><span class="sxs-lookup"><span data-stu-id="9e471-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9e471-153">顯示使用者設定的最後一個目前狀態狀態，目前狀態變更現在會得到反映。</span><span class="sxs-lookup"><span data-stu-id="9e471-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e471-154">連絡人清單和通訊錄服務的可用性</span><span class="sxs-lookup"><span data-stu-id="9e471-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="9e471-155">無法使用</span><span class="sxs-lookup"><span data-stu-id="9e471-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="9e471-156">離線</span><span class="sxs-lookup"><span data-stu-id="9e471-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-157">所有點對點工作階段與形式</span><span class="sxs-lookup"><span data-stu-id="9e471-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="9e471-158">離線</span><span class="sxs-lookup"><span data-stu-id="9e471-158">Available</span></span></p></td>
<td><p><span data-ttu-id="9e471-159">離線</span><span class="sxs-lookup"><span data-stu-id="9e471-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="9e471-160">使用者在另一個池的回切期間駐留在未受影響的池中的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9e471-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e471-161">使用者任務</span><span class="sxs-lookup"><span data-stu-id="9e471-161">User task</span></span></th>
<th><span data-ttu-id="9e471-162">在回切期間</span><span class="sxs-lookup"><span data-stu-id="9e471-162">During failback</span></span></th>
<th><span data-ttu-id="9e471-163">在回切完成後</span><span class="sxs-lookup"><span data-stu-id="9e471-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e471-164">查看受影響使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="9e471-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="9e471-165">顯示受影響使用者所設定的最後一個目前狀態。</span><span class="sxs-lookup"><span data-stu-id="9e471-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="9e471-166">工作日.</span><span class="sxs-lookup"><span data-stu-id="9e471-166">Working.</span></span> <span data-ttu-id="9e471-167">未受影響的使用者會看到受影響使用者所做的更新。</span><span class="sxs-lookup"><span data-stu-id="9e471-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-168">依受影響的使用者組織的日常會議</span><span class="sxs-lookup"><span data-stu-id="9e471-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="9e471-169">所有的會議形式都是終止的。</span><span class="sxs-lookup"><span data-stu-id="9e471-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="9e471-170">所有形式現在都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="9e471-170">All modalities now work.</span></span> <span data-ttu-id="9e471-171">每個參與者都需要按一下才能重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="9e471-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e471-172">依未受影響的使用者組織的日常會議</span><span class="sxs-lookup"><span data-stu-id="9e471-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="9e471-173">會議持續進行，而且受影響的使用者可以繼續參與會議，且所有形式都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="9e471-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="9e471-174">會議持續進行，而且受影響的使用者可以繼續參與會議，且所有形式都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="9e471-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e471-175">所有點對點工作階段與形式</span><span class="sxs-lookup"><span data-stu-id="9e471-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="9e471-176">離線</span><span class="sxs-lookup"><span data-stu-id="9e471-176">Available</span></span></p></td>
<td><p><span data-ttu-id="9e471-177">離線</span><span class="sxs-lookup"><span data-stu-id="9e471-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

