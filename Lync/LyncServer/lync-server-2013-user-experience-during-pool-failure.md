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
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="af75f-103">Lync Server 2013 的集區失敗期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="af75f-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af75f-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="af75f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="af75f-105">如果集區容錯移轉，則受影響集區的所有使用者都會強制登出，然後登入備份組區。</span><span class="sxs-lookup"><span data-stu-id="af75f-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="af75f-106">對於登入備份組區的簡短使用者，其可能是以復原模式進行。</span><span class="sxs-lookup"><span data-stu-id="af75f-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="af75f-107">在復原模式中，使用者無法執行會導致 Lync Server 持續變更的任務，例如新增連絡人。</span><span class="sxs-lookup"><span data-stu-id="af75f-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="af75f-108">容錯移轉完成後，所有使用者都可以從備份組區取得所有服務。</span><span class="sxs-lookup"><span data-stu-id="af75f-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="af75f-109">當集區失敗時，使用者所擁有的任何會話都會中斷，使用者必須在容錯移轉之後重新建立這些會話，以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="af75f-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="af75f-110">容錯移轉或回復時，使用者不會 rehomed。</span><span class="sxs-lookup"><span data-stu-id="af75f-110">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="af75f-111">裝載于集區的集區失敗的使用者會暫時為備份組區提供服務。</span><span class="sxs-lookup"><span data-stu-id="af75f-111">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="af75f-112">當您還原主集區時，系統管理員可以使用其原始的主集區來回應這些使用者。</span><span class="sxs-lookup"><span data-stu-id="af75f-112">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="af75f-113">附注在 Lync 2013 中，位置資訊服務器資料庫不會複製到備份組區。</span><span class="sxs-lookup"><span data-stu-id="af75f-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="af75f-114">為了獲得最佳作法，管理員應該定期備份 .LIS 資料庫，並使用最新的備份副本，在容錯移轉後，將備份組區中的 IIS 資料庫還原。</span><span class="sxs-lookup"><span data-stu-id="af75f-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="af75f-115">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="af75f-115">User Experience During Failover</span></span>

<span data-ttu-id="af75f-116">當使用者處於失敗的集區時，使用者就會登出。使用者參與的任何點對點工作階段都會終止，就像是該使用者所組織的會議。</span><span class="sxs-lookup"><span data-stu-id="af75f-116">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="af75f-117">使用者無法登入，直到註冊機恢復計時器到期，或系統管理員啟動容錯移轉程式為止（從前面開始）。</span><span class="sxs-lookup"><span data-stu-id="af75f-117">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="af75f-118">當使用者重新登入時，他們會登入備份組區。</span><span class="sxs-lookup"><span data-stu-id="af75f-118">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="af75f-119">如果在容錯移轉完成之前登入，則會在容錯移轉完成之前以復原模式進行登入。</span><span class="sxs-lookup"><span data-stu-id="af75f-119">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="af75f-120">只有使用者才能建立新的會話或重新建立先前的會話。</span><span class="sxs-lookup"><span data-stu-id="af75f-120">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="af75f-121">容錯回復期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="af75f-121">User Experience During Failback</span></span>

<span data-ttu-id="af75f-122">當受影響的使用者登入備份組區，且該使用者在回切期間仍保持登入和運作狀態時，便會發生集區回復。</span><span class="sxs-lookup"><span data-stu-id="af75f-122">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="af75f-123">請注意，容錯回復程序需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="af75f-123">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="af75f-124">僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="af75f-124">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="af75f-125">下表顯示如何在回切後和之後，如何影響具有 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端之使用者的詳細資訊，也會顯示其他集區中的使用者如何在容錯回復的集區中查看和與使用者互動。</span><span class="sxs-lookup"><span data-stu-id="af75f-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="af75f-126">當前端集區完全失敗後，使用 Microsoft Office Communicator 2007 R2 用戶端的使用者無法登入。 ) </span><span class="sxs-lookup"><span data-stu-id="af75f-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="af75f-127">*受影響的使用者*是指從主集區容錯移轉且由備份組區服務之任何使用者。</span><span class="sxs-lookup"><span data-stu-id="af75f-127">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="af75f-128">根據定義，任何原本位於備份組區的使用者，都不是受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="af75f-128">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="af75f-129">容錯回復集區中受影響使用者的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="af75f-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af75f-130">使用者狀態或任務</span><span class="sxs-lookup"><span data-stu-id="af75f-130">User state or task</span></span></th>
<th><span data-ttu-id="af75f-131">回復期間</span><span class="sxs-lookup"><span data-stu-id="af75f-131">During failback</span></span></th>
<th><span data-ttu-id="af75f-132">回復完成後</span><span class="sxs-lookup"><span data-stu-id="af75f-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af75f-133">使用者的使用者狀態已登入</span><span class="sxs-lookup"><span data-stu-id="af75f-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="af75f-134">使用者保持登入並聯機至備份組區。</span><span class="sxs-lookup"><span data-stu-id="af75f-134">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="af75f-135">在某些情況下，使用者會以復原模式登入原始的主集區，並以復原模式重新登入。</span><span class="sxs-lookup"><span data-stu-id="af75f-135">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-136">使用者保持登入狀態，並且進入一般模式。</span><span class="sxs-lookup"><span data-stu-id="af75f-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-137">新使用者登入</span><span class="sxs-lookup"><span data-stu-id="af75f-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="af75f-138">使用者可以以復原模式登入主集區。</span><span class="sxs-lookup"><span data-stu-id="af75f-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-139">使用者可以採用一般模式登入原始的主集區。</span><span class="sxs-lookup"><span data-stu-id="af75f-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af75f-140">受影響使用者所組織的現行會議</span><span class="sxs-lookup"><span data-stu-id="af75f-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="af75f-141">所有會議形式都會終止。</span><span class="sxs-lookup"><span data-stu-id="af75f-141">All modalities of conference are terminated.</span></span> <span data-ttu-id="af75f-142">[重新加入] 按鈕將會出現，但在受影響的使用者處於復原模式時，使用者無法重新加入按鈕。</span><span class="sxs-lookup"><span data-stu-id="af75f-142">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-143">所有形式現在均可運作。</span><span class="sxs-lookup"><span data-stu-id="af75f-143">All modalities now work.</span></span> <span data-ttu-id="af75f-144">每個參與者都需要按一下以重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="af75f-144">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-145">由不受影響的使用者組織的現行會議</span><span class="sxs-lookup"><span data-stu-id="af75f-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="af75f-146">會議持續和受影響的使用者可以保留在會議中。</span><span class="sxs-lookup"><span data-stu-id="af75f-146">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="af75f-147">受影響的使用者限制為以復原模式來執行的動作。</span><span class="sxs-lookup"><span data-stu-id="af75f-147">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-148">會議繼續進行，且受影響的使用者可以保留在會議中，而且在使用者結束復原模式後，所有形式都會運作。</span><span class="sxs-lookup"><span data-stu-id="af75f-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af75f-149">排程或修改排程的會議，建立即席會議</span><span class="sxs-lookup"><span data-stu-id="af75f-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="af75f-150">當使用者處於復原模式時，不可能。</span><span class="sxs-lookup"><span data-stu-id="af75f-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-151">適用于所有形式。</span><span class="sxs-lookup"><span data-stu-id="af75f-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-152">相同集區中的其他使用者看到的狀態</span><span class="sxs-lookup"><span data-stu-id="af75f-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="af75f-153">當使用者在復原模式期間登入備份組區時，目前狀態不明。</span><span class="sxs-lookup"><span data-stu-id="af75f-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="af75f-154">顯示使用者設定的最後一個目前狀態，而且現在會反映目前狀態變更。</span><span class="sxs-lookup"><span data-stu-id="af75f-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af75f-155">連絡人清單和通訊錄服務可用性</span><span class="sxs-lookup"><span data-stu-id="af75f-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="af75f-156">不適用</span><span class="sxs-lookup"><span data-stu-id="af75f-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="af75f-157">可以使用</span><span class="sxs-lookup"><span data-stu-id="af75f-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-158">所有點對點工作階段和形式</span><span class="sxs-lookup"><span data-stu-id="af75f-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="af75f-159">可以使用</span><span class="sxs-lookup"><span data-stu-id="af75f-159">Available</span></span></p></td>
<td><p><span data-ttu-id="af75f-160">可以使用</span><span class="sxs-lookup"><span data-stu-id="af75f-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="af75f-161">使用者在另一個集區的回切期間位於未受影響的集區中的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="af75f-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af75f-162">使用者工作</span><span class="sxs-lookup"><span data-stu-id="af75f-162">User task</span></span></th>
<th><span data-ttu-id="af75f-163">回復期間</span><span class="sxs-lookup"><span data-stu-id="af75f-163">During failback</span></span></th>
<th><span data-ttu-id="af75f-164">回復完成後</span><span class="sxs-lookup"><span data-stu-id="af75f-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af75f-165">查看受影響使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="af75f-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="af75f-166">顯示受影響使用者設定的最後一個目前狀態。</span><span class="sxs-lookup"><span data-stu-id="af75f-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="af75f-167">工作。</span><span class="sxs-lookup"><span data-stu-id="af75f-167">Working.</span></span> <span data-ttu-id="af75f-168">不受影響的使用者會看到受影響使用者所做的更新。</span><span class="sxs-lookup"><span data-stu-id="af75f-168">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-169">受影響使用者所組織的現行會議</span><span class="sxs-lookup"><span data-stu-id="af75f-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="af75f-170">所有會議形式都會終止。</span><span class="sxs-lookup"><span data-stu-id="af75f-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="af75f-171">所有形式現在均可運作。</span><span class="sxs-lookup"><span data-stu-id="af75f-171">All modalities now work.</span></span> <span data-ttu-id="af75f-172">每個參與者都需要按一下以重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="af75f-172">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af75f-173">由不受影響的使用者組織的現行會議</span><span class="sxs-lookup"><span data-stu-id="af75f-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="af75f-174">會議繼續進行，而受影響的使用者可以保留在會議中，而且所有的形式都會運作。</span><span class="sxs-lookup"><span data-stu-id="af75f-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="af75f-175">會議繼續進行，而受影響的使用者可以保留在會議中，而且所有的形式都會運作。</span><span class="sxs-lookup"><span data-stu-id="af75f-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af75f-176">所有點對點工作階段和形式</span><span class="sxs-lookup"><span data-stu-id="af75f-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="af75f-177">可以使用</span><span class="sxs-lookup"><span data-stu-id="af75f-177">Available</span></span></p></td>
<td><p><span data-ttu-id="af75f-178">可以使用</span><span class="sxs-lookup"><span data-stu-id="af75f-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

