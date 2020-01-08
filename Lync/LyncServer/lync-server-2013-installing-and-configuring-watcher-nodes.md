---
title: Lync Server 2013：安裝及設定觀察程式節點
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="6a553-102">在 Lync Server 2013 中安裝及設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="6a553-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a553-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6a553-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6a553-104">[觀察程式]*節點*是定期執行 Lync Server 綜合交易的電腦。</span><span class="sxs-lookup"><span data-stu-id="6a553-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="6a553-105">*綜合交易*是 Windows PowerShell Cmdlet，可驗證重要的最終使用者案例，例如登入系統的能力，或 exchange 立即訊息的功能，如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="6a553-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="6a553-106">在 Lync Server 2013 中，System Center Operations Manager 可以執行下表所示的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="6a553-107">資料表中有三種不同的綜合交易類型：</span><span class="sxs-lookup"><span data-stu-id="6a553-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="6a553-108">**預設值**。</span><span class="sxs-lookup"><span data-stu-id="6a553-108">**Default**.</span></span> <span data-ttu-id="6a553-109">這些是觀察程式節點預設會執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="6a553-110">當您建立新的 [觀察程式] 節點時，您可以選擇指定該節點要執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="6a553-111">（這是**新的 CsWatcherNodeConfiguration** Cmdlet 所使用的測試參數的用途）。如果您在建立觀察程式節點時不使用測試參數，就會自動執行所有預設的綜合交易，且不會執行任何非預設的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="6a553-112">這表示，系統會將觀察程式節點設定為執行測試 CsAddressBookService 測試，但不會將其設定為執行測試 CsExumConnectivity 測試。</span><span class="sxs-lookup"><span data-stu-id="6a553-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="6a553-113">**非預設值**。</span><span class="sxs-lookup"><span data-stu-id="6a553-113">**Non-default**.</span></span> <span data-ttu-id="6a553-114">正如名稱所示，非預設的綜合交易是測試觀察程式節點預設不會執行。</span><span class="sxs-lookup"><span data-stu-id="6a553-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="6a553-115">不過，可以啟用觀察程式節點來執行任何非預設的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="6a553-116">您可以在建立觀察程式節點（使用**新的 CsWatcherNodeConfiguration** Cmdlet），或在此後的任何時間執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6a553-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="6a553-117">許多非預設的綜合交易需要額外的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="6a553-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="6a553-118">如需詳細資訊，請參閱[Lync Server 2013 中的綜合交易的特殊設定指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="6a553-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="6a553-119">**延伸**。</span><span class="sxs-lookup"><span data-stu-id="6a553-119">**Extended**.</span></span> <span data-ttu-id="6a553-120">[延伸測試] 是一種特殊類型的非預設綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="6a553-121">與其他綜合交易不同，延長式測試可以在每一階段執行多次。</span><span class="sxs-lookup"><span data-stu-id="6a553-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="6a553-122">在驗證諸如多個公用交換電話網絡（PSTN）語音路由的資源時，這個功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="6a553-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="6a553-123">只要將延伸測試的多個實例新增至觀察程式節點，即可進行設定。</span><span class="sxs-lookup"><span data-stu-id="6a553-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="6a553-124">如需將其他綜合交易新增至觀察程式節點的程式詳細資訊，請參閱[在 Lync Server 2013 中管理觀察程式節點](lync-server-2013-managing-watcher-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="6a553-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="6a553-125">您可以使用 Lync Server 管理命令介面來移除來自觀察程式節點的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6a553-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="6a553-126">可供觀察程式節點使用的綜合交易，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6a553-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a553-127">Cmdlet 名稱（測試名稱）</span><span class="sxs-lookup"><span data-stu-id="6a553-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="6a553-128">描述</span><span class="sxs-lookup"><span data-stu-id="6a553-128">Description</span></span></th>
<th><span data-ttu-id="6a553-129">綜合交易類型</span><span class="sxs-lookup"><span data-stu-id="6a553-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a553-130">Test-CsAddressBookService （ABS）</span><span class="sxs-lookup"><span data-stu-id="6a553-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="6a553-131">確認使用者可以查詢不在連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6a553-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="6a553-132">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-133">CsAddressBookWebQuery （ABWQ）</span><span class="sxs-lookup"><span data-stu-id="6a553-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="6a553-134">確認使用者可以透過 HTTP 找不在連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6a553-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="6a553-135">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-136">Test CsIM （IM）</span><span class="sxs-lookup"><span data-stu-id="6a553-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="6a553-137">確認使用者可以傳送對等立即訊息。</span><span class="sxs-lookup"><span data-stu-id="6a553-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="6a553-138">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-139">CsP2PAV （P2PAV）</span><span class="sxs-lookup"><span data-stu-id="6a553-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="6a553-140">確認使用者可以進行對等音訊通話（僅限通知）。</span><span class="sxs-lookup"><span data-stu-id="6a553-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="6a553-141">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-142">CsPresence （目前狀態）</span><span class="sxs-lookup"><span data-stu-id="6a553-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="6a553-143">確認使用者能夠查看其他使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="6a553-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="6a553-144">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-145">Test CsRegistration （註冊）</span><span class="sxs-lookup"><span data-stu-id="6a553-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="6a553-146">確認使用者可以登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="6a553-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="6a553-147">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-148">CsAudioConferencingProvider （ACP）</span><span class="sxs-lookup"><span data-stu-id="6a553-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="6a553-149">不會用於 Lync Server 2013 的內部部署版本</span><span class="sxs-lookup"><span data-stu-id="6a553-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="6a553-150">延伸</span><span class="sxs-lookup"><span data-stu-id="6a553-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-151">CsPstnPeerToPeerCall （PSTN）</span><span class="sxs-lookup"><span data-stu-id="6a553-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="6a553-152">確認使用者可以與企業外部的人員（PSTN 號碼）撥打電話和接聽來電。</span><span class="sxs-lookup"><span data-stu-id="6a553-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="6a553-153">非預設，延伸</span><span class="sxs-lookup"><span data-stu-id="6a553-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-154">CsAVConference （AvConference）</span><span class="sxs-lookup"><span data-stu-id="6a553-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="6a553-155">確認使用者可以建立並參與音訊/視訊會議。</span><span class="sxs-lookup"><span data-stu-id="6a553-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="6a553-156">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-157">CsAVEdgeConnectivity （AVEdgeConnectivity）</span><span class="sxs-lookup"><span data-stu-id="6a553-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="6a553-158">確認 A/V 邊緣伺服器能夠接受對等通話和電話會議的連線。</span><span class="sxs-lookup"><span data-stu-id="6a553-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="6a553-159">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-160">CsDataConference （DataConference）</span><span class="sxs-lookup"><span data-stu-id="6a553-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="6a553-161">確認使用者可以參與資料共同作業會議，包括白板和投票等活動的線上會議。</span><span class="sxs-lookup"><span data-stu-id="6a553-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="6a553-162">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-163">CsExumConnectivity （ExumConnectivity）</span><span class="sxs-lookup"><span data-stu-id="6a553-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="6a553-164">確認使用者可以連線到 Exchange 整合通訊（UM）。</span><span class="sxs-lookup"><span data-stu-id="6a553-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="6a553-165">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-166">CsGroupIM （GroupIM）</span><span class="sxs-lookup"><span data-stu-id="6a553-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="6a553-167">確認使用者可以在會議中傳送立即訊息，並與三人或多位人員一起參與立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="6a553-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="6a553-168">設置</span><span class="sxs-lookup"><span data-stu-id="6a553-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-169">Test-CsGroupIM – TestJoinLauncher （JoinLauncher）</span><span class="sxs-lookup"><span data-stu-id="6a553-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="6a553-170">確認使用者可以透過網址連結來建立及加入排程會議。</span><span class="sxs-lookup"><span data-stu-id="6a553-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="6a553-171">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-172">CsMCXP2PIM （MCXP2PIM）</span><span class="sxs-lookup"><span data-stu-id="6a553-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="6a553-173">確認行動裝置使用者可以註冊並傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="6a553-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="6a553-174">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-175">CsPersistentChatMessage （PersistentChatMessage）</span><span class="sxs-lookup"><span data-stu-id="6a553-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="6a553-176">確認使用者可以使用持續聊天服務來交換郵件。</span><span class="sxs-lookup"><span data-stu-id="6a553-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="6a553-177">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-178">CsUnifiedContactStore （UnifiedContactStore）</span><span class="sxs-lookup"><span data-stu-id="6a553-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="6a553-179">確認使用者的連絡人可以透過整合連絡人存放區存取。</span><span class="sxs-lookup"><span data-stu-id="6a553-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="6a553-180">「整合連絡人存放區」提供一種方式，讓使用者可以使用 Lync 2013、Outlook 和/或 Outlook Web Access 來維護一組可存取的連絡人。</span><span class="sxs-lookup"><span data-stu-id="6a553-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="6a553-181">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-182">CsXmppIM （XmppIM）</span><span class="sxs-lookup"><span data-stu-id="6a553-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="6a553-183">確認立即訊息可透過 XMPP （可擴展訊息和目前狀態通訊協定）閘道傳送。</span><span class="sxs-lookup"><span data-stu-id="6a553-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="6a553-184">非預設值</span><span class="sxs-lookup"><span data-stu-id="6a553-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6a553-185">您不需要安裝觀察程式節點，就能使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="6a553-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="6a553-186">如果您沒有安裝這些節點，您仍然可以在問題發生時，從 Lync Server 2013 元件取得即時通知。</span><span class="sxs-lookup"><span data-stu-id="6a553-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="6a553-187">（元件和使用者管理套件不使用觀察程式節點）。不過，如果您想要使用主動監視管理套件監視端對端案例，則需要觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="6a553-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a553-188">系統管理員也可以手動執行綜合交易，而不需要使用或安裝，Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="6a553-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="6a553-189">如需各種 Test-Cs Cmdlet 的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 Cmdlet 索引</A>。</span><span class="sxs-lookup"><span data-stu-id="6a553-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="6a553-190">根據您的部署規模而定，綜合交易可能會使用大量的電腦記憶體和處理器時間。</span><span class="sxs-lookup"><span data-stu-id="6a553-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="6a553-191">基於這個原因，我們建議您使用專用電腦做為觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="6a553-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="6a553-192">例如，您不應該將前端伺服器設定為充當觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="6a553-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="6a553-193">觀察程式節點應該符合下列硬體規格：</span><span class="sxs-lookup"><span data-stu-id="6a553-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a553-194">舊版 Microsoft Lync Server 2010 觀察程式節點無法與 Lync Server 2013 觀察程式節點在同一部電腦上 collocated。</span><span class="sxs-lookup"><span data-stu-id="6a553-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="6a553-195">這是因為 Lync Server 2010 和 Lync Server 2013 的核心系統檔案無法安裝在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="6a553-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="6a553-196">不過，Lync Server 2013 觀察程式節點可以同時監視 Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="6a553-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="6a553-197">這兩個產品版本都支援預設的綜合交易記錄。</span><span class="sxs-lookup"><span data-stu-id="6a553-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="6a553-198">Lync Server 2013 觀察程式節點可以在企業內部或外部部署，以協助驗證：</span><span class="sxs-lookup"><span data-stu-id="6a553-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="6a553-199">企業內部使用者的 [池連線]。</span><span class="sxs-lookup"><span data-stu-id="6a553-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="6a553-200">針對在企業外部工作的遠端使用者，透過周邊網路進行連線。</span><span class="sxs-lookup"><span data-stu-id="6a553-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="6a553-201">連接至分支機搆裝置。</span><span class="sxs-lookup"><span data-stu-id="6a553-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="6a553-202">企業和周邊網路中的 Lync Server 2010 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="6a553-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="6a553-203">企業內部和外部都提供不同的驗證選項，可協助簡化管理。</span><span class="sxs-lookup"><span data-stu-id="6a553-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="6a553-204">如需詳細資訊，請參閱[將觀察程式節點設定為在 Lync Server 2013 中執行綜合交易](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="6a553-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="6a553-205">若要將電腦設定為充當觀察者節點，您必須在安裝 System Center Operations Manager 並匯入 Lync Server 2013 管理套件後完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="6a553-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="6a553-206">在您安裝 Lync Server 2013 core 檔案和 System Center 代理程式檔案之前，您也應該確定觀察程式節點電腦符合安裝 Lync Server 2013 的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="6a553-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="6a553-207">此外，觀察程式節點電腦也應該安裝下列專案：</span><span class="sxs-lookup"><span data-stu-id="6a553-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a553-208">硬體元件</span><span class="sxs-lookup"><span data-stu-id="6a553-208">Hardware component</span></span></th>
<th><span data-ttu-id="6a553-209">最低需求</span><span class="sxs-lookup"><span data-stu-id="6a553-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a553-210">CPU</span><span class="sxs-lookup"><span data-stu-id="6a553-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="6a553-211">下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6a553-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6a553-212">64-位處理器、四核、2.33 GHz 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6a553-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="6a553-213">64位雙路處理器、雙核、2.33 GHz 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6a553-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a553-214">儲存體</span><span class="sxs-lookup"><span data-stu-id="6a553-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="6a553-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="6a553-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a553-216">網路作業系統</span><span class="sxs-lookup"><span data-stu-id="6a553-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a553-217">1個網路介面卡 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="6a553-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="6a553-218">Windows Server 2008 R2、Windows Server 2012 或</span><span class="sxs-lookup"><span data-stu-id="6a553-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="6a553-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6a553-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="6a553-220">.NET Framework 4.5 的完整版本。</span><span class="sxs-lookup"><span data-stu-id="6a553-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="6a553-221">Windows 身分識別基礎。</span><span class="sxs-lookup"><span data-stu-id="6a553-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="6a553-222">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="6a553-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6a553-223">只要符合所有這些先決條件，您就可以透過下列方式設定觀察程式節點：</span><span class="sxs-lookup"><span data-stu-id="6a553-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="6a553-224">在觀察程式節點電腦上安裝 Lync Server 2013 core 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a553-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="6a553-225">在觀察程式節點電腦上安裝 System Center Operations Manager 代理程式。</span><span class="sxs-lookup"><span data-stu-id="6a553-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="6a553-226">執行 Watchernode 的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="6a553-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="6a553-227">使用**CsWatcherNodeConfiguration** Cmdlet 來設定要由觀察程式節點使用的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="6a553-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

