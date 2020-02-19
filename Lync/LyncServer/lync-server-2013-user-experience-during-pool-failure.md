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
ms.openlocfilehash: 65d33dad39527f64ba7b96ae6d75f8d6e11a2f04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="49ef6-102">Lync Server 2013 中的集區失敗期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="49ef6-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ef6-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="49ef6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="49ef6-104">如果集區容錯移轉，受影響的集區上的所有使用者都要都強制登出並重新登入備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="49ef6-105">短暫期間登入備份集區的使用者可能會在恢復模式中。</span><span class="sxs-lookup"><span data-stu-id="49ef6-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="49ef6-106">在恢復模式中，使用者將無法執行工作所造成的持續性的變更在 Lync 伺服器上，例如新增連絡人。</span><span class="sxs-lookup"><span data-stu-id="49ef6-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="49ef6-107">容錯移轉完成後，所有使用者可以從備份集區都取得所有服務。</span><span class="sxs-lookup"><span data-stu-id="49ef6-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="49ef6-108">任何的使用者具有時之集區失敗的工作階段都會中斷，而使用者必須重新建立這些繼續的容錯移轉後的工作階段。</span><span class="sxs-lookup"><span data-stu-id="49ef6-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="49ef6-109">使用者不會重新放置在容錯移轉或容錯回復期間。</span><span class="sxs-lookup"><span data-stu-id="49ef6-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="49ef6-110">位於失敗的集區的使用者將暫時受到服務，由備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="49ef6-111">還原主集區時，系統管理員可以容錯回復到其原始主集區由這些使用者。</span><span class="sxs-lookup"><span data-stu-id="49ef6-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="49ef6-112">附註在 Lync 2013 中，位置資訊伺服器資料庫不會複寫至備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="49ef6-113">最佳作法是，管理員應定期備份 LIS 資料庫，並使用最新的備份複本還原 LIS 資料庫在備份集區容錯移轉後。</span><span class="sxs-lookup"><span data-stu-id="49ef6-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="49ef6-114">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="49ef6-114">User Experience During Failover</span></span>

<span data-ttu-id="49ef6-115">失敗的集區中的使用者時，在使用者登出。使用者已參與任何端對端工作階段終止，因為該使用者召集的會議。</span><span class="sxs-lookup"><span data-stu-id="49ef6-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="49ef6-116">使用者無法登入，直到登錄器恢復計時器到期或系統管理員初始化容錯移轉程序，準。</span><span class="sxs-lookup"><span data-stu-id="49ef6-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="49ef6-117">當使用者登入時，他們將登入備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="49ef6-118">如果他們登入容錯移轉完成之前，他們會處於恢復能力模式容錯移轉完成之前。</span><span class="sxs-lookup"><span data-stu-id="49ef6-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="49ef6-119">僅限使用者則可以建立新的工作階段，或重新建立先前工作階段。</span><span class="sxs-lookup"><span data-stu-id="49ef6-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="49ef6-120">容錯回復期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="49ef6-120">User Experience During Failback</span></span>

<span data-ttu-id="49ef6-121">在受影響的使用者登入備份集區]，並登入並使用容錯回復期間的使用者仍會保留，就會發生集區容錯回復。</span><span class="sxs-lookup"><span data-stu-id="49ef6-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="49ef6-122">請注意，容錯回復程序需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="49ef6-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="49ef6-123">僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="49ef6-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="49ef6-124">下表顯示使用者與 Lync 2013 用戶端或 Microsoft Lync 2010 用戶端會有何影響期間和之後容錯回復，也如何其他集區中的使用者查看並與人員回失敗的集區中的使用者互動的詳細。</span><span class="sxs-lookup"><span data-stu-id="49ef6-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="49ef6-125">使用 Microsoft Office Communicator 2007 R2 用戶端使用者無法登入前端集區完全失敗回直到。）</span><span class="sxs-lookup"><span data-stu-id="49ef6-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="49ef6-126">*受影響使用者*的字詞指的是任何使用者都已從主集區容錯移轉和所服務的備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="49ef6-127">根據定義，任何使用者原本裝載於備份集區不是受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="49ef6-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="49ef6-128">在 [容錯回復集區中受影響使用者的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="49ef6-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49ef6-129">使用者狀態或工作</span><span class="sxs-lookup"><span data-stu-id="49ef6-129">User state or task</span></span></th>
<th><span data-ttu-id="49ef6-130">容錯回復期間</span><span class="sxs-lookup"><span data-stu-id="49ef6-130">During failback</span></span></th>
<th><span data-ttu-id="49ef6-131">容錯回復完成之後</span><span class="sxs-lookup"><span data-stu-id="49ef6-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-132">使用者已登入的使用者狀態</span><span class="sxs-lookup"><span data-stu-id="49ef6-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="49ef6-133">使用者保持登入，並連線至備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="49ef6-134">有些時候使用者將會被登出並重新登入原始主集區，在恢復模式中。</span><span class="sxs-lookup"><span data-stu-id="49ef6-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-135">使用者維持登入狀態並進入一般模式。</span><span class="sxs-lookup"><span data-stu-id="49ef6-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-136">新使用者登入</span><span class="sxs-lookup"><span data-stu-id="49ef6-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="49ef6-137">使用者可以登入恢復能力模式中的主集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-138">使用者可以登入原始主集區，以一般模式。</span><span class="sxs-lookup"><span data-stu-id="49ef6-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-139">受影響使用者召集的進行中會議</span><span class="sxs-lookup"><span data-stu-id="49ef6-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="49ef6-140">會終止所有形式的會議。</span><span class="sxs-lookup"><span data-stu-id="49ef6-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="49ef6-141">重新加入] 按鈕會出現，但受影響的使用者處於恢復能力模式時，可以重新加入任何使用者。</span><span class="sxs-lookup"><span data-stu-id="49ef6-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-142">所有形式即能立即運作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-142">All modalities now work.</span></span> <span data-ttu-id="49ef6-143">每位參與者需要按一下 [重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="49ef6-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-144">不受影響使用者召集的進行中會議</span><span class="sxs-lookup"><span data-stu-id="49ef6-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="49ef6-145">會議會繼續執行，並受影響使用者能停留在會議中。</span><span class="sxs-lookup"><span data-stu-id="49ef6-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="49ef6-146">受影響的使用者只有他可以在恢復模式中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-147">會議持續進行，而受影響的使用者能停留在會議中，所有形式皆可運作後使用者退出恢復能力模式。</span><span class="sxs-lookup"><span data-stu-id="49ef6-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-148">排程或修改已排程的會議，建立臨機操作會議</span><span class="sxs-lookup"><span data-stu-id="49ef6-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="49ef6-149">可能無法在使用者處於恢復能力模式。</span><span class="sxs-lookup"><span data-stu-id="49ef6-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-150">適用於所有形式的。</span><span class="sxs-lookup"><span data-stu-id="49ef6-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-151">相同集區中其他使用者所看到的目前狀態</span><span class="sxs-lookup"><span data-stu-id="49ef6-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="49ef6-152">目前狀態為不明同時使用者會恢復能力模式期間登入備份集區。</span><span class="sxs-lookup"><span data-stu-id="49ef6-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-153">顯示最後一個目前狀態設定的使用者和目前狀態變更會立即反映。</span><span class="sxs-lookup"><span data-stu-id="49ef6-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-154">連絡人清單與通訊錄服務可用性</span><span class="sxs-lookup"><span data-stu-id="49ef6-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="49ef6-155">不適用</span><span class="sxs-lookup"><span data-stu-id="49ef6-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="49ef6-156">可以使用</span><span class="sxs-lookup"><span data-stu-id="49ef6-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-157">所有端對端工作階段與形式</span><span class="sxs-lookup"><span data-stu-id="49ef6-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="49ef6-158">可以使用</span><span class="sxs-lookup"><span data-stu-id="49ef6-158">Available</span></span></p></td>
<td><p><span data-ttu-id="49ef6-159">可以使用</span><span class="sxs-lookup"><span data-stu-id="49ef6-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="49ef6-160">使用者的使用者經驗位於另一個集區容錯回復期間不會受到影響的集區</span><span class="sxs-lookup"><span data-stu-id="49ef6-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49ef6-161">使用者工作</span><span class="sxs-lookup"><span data-stu-id="49ef6-161">User task</span></span></th>
<th><span data-ttu-id="49ef6-162">容錯回復期間</span><span class="sxs-lookup"><span data-stu-id="49ef6-162">During failback</span></span></th>
<th><span data-ttu-id="49ef6-163">容錯回復完成之後</span><span class="sxs-lookup"><span data-stu-id="49ef6-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-164">檢視受影響使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="49ef6-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="49ef6-165">顯示受影響使用者所設定的最後一個目前狀態。</span><span class="sxs-lookup"><span data-stu-id="49ef6-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-166">運作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-166">Working.</span></span> <span data-ttu-id="49ef6-167">不會受到影響的使用者會看到受影響的使用者所做的更新。</span><span class="sxs-lookup"><span data-stu-id="49ef6-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-168">受影響使用者召集的進行中會議</span><span class="sxs-lookup"><span data-stu-id="49ef6-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="49ef6-169">會終止所有形式的會議。</span><span class="sxs-lookup"><span data-stu-id="49ef6-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-170">所有形式即能立即運作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-170">All modalities now work.</span></span> <span data-ttu-id="49ef6-171">每位參與者需要按一下 [重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="49ef6-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ef6-172">不受影響使用者召集的進行中會議</span><span class="sxs-lookup"><span data-stu-id="49ef6-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="49ef6-173">會議持續進行，並受影響的使用者能停留在會議中，所有形式皆可運作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="49ef6-174">會議持續進行，並受影響的使用者能停留在會議中，所有形式皆可運作。</span><span class="sxs-lookup"><span data-stu-id="49ef6-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ef6-175">所有端對端工作階段與形式</span><span class="sxs-lookup"><span data-stu-id="49ef6-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="49ef6-176">可以使用</span><span class="sxs-lookup"><span data-stu-id="49ef6-176">Available</span></span></p></td>
<td><p><span data-ttu-id="49ef6-177">可以使用</span><span class="sxs-lookup"><span data-stu-id="49ef6-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

