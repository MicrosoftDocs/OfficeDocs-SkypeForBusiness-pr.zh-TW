---
title: Lync Server 2013：安裝及設定監視程式節點
description: Lync Server 2013：安裝及設定監視程式節點。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573999"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="19ff5-103">在 Lync Server 2013 中安裝及設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="19ff5-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19ff5-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="19ff5-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="19ff5-105">*觀察程式節點* 是定期執行 Lync Server 綜合交易的電腦。</span><span class="sxs-lookup"><span data-stu-id="19ff5-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="19ff5-106">*綜合交易* 是 Windows PowerShell Cmdlet，用來驗證重要的使用者案例，例如登入系統的功能，或 exchange 立即訊息的功能會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="19ff5-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="19ff5-107">對於 Lync Server 2013，System Center Operations Manager 可以執行下表所示的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="19ff5-108">表中顯示三種不同綜合交易類型：</span><span class="sxs-lookup"><span data-stu-id="19ff5-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="19ff5-109">**預設值**。</span><span class="sxs-lookup"><span data-stu-id="19ff5-109">**Default**.</span></span> <span data-ttu-id="19ff5-110">這些是監看員節點預設會執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="19ff5-111">建立新的監看員節點時，可以選擇指定節點會執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="19ff5-112"> (**New-CsWatcherNodeConfiguration** 指令程式所使用之測試參數的目的。 ) 如果在建立監看員節點時未使用 [測試] 參數，它會自動執行所有預設的綜合交易，而且不會執行任何非預設的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="19ff5-113">舉例而言，這表示監看員節點會設定執行 Test-CsAddressBookService 測試，但是不會設定執行 Test-CsExumConnectivity 測試。</span><span class="sxs-lookup"><span data-stu-id="19ff5-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="19ff5-114">**非預設值**。</span><span class="sxs-lookup"><span data-stu-id="19ff5-114">**Non-default**.</span></span> <span data-ttu-id="19ff5-115">如名稱所指，非預設綜合交易為監看員節點依預設不會執行的測試。</span><span class="sxs-lookup"><span data-stu-id="19ff5-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="19ff5-116">不過，可以啟用監看員節點來執行任何非預設綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="19ff5-117">您可以在建立監看員節點時 (透過使用 **New-CsWatcherNodeConfiguration** Cmdlet)，或在建立後的任何時點進行啟用。</span><span class="sxs-lookup"><span data-stu-id="19ff5-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="19ff5-118">許多非預設綜合交易需要額外的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="19ff5-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="19ff5-119">如需詳細資訊，請參閱 [Lync Server 2013 中的綜合交易的特殊安裝指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="19ff5-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="19ff5-120">**擴充**。</span><span class="sxs-lookup"><span data-stu-id="19ff5-120">**Extended**.</span></span> <span data-ttu-id="19ff5-121">延伸測試為非預設綜合交易的特別類型。</span><span class="sxs-lookup"><span data-stu-id="19ff5-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="19ff5-122">與其他綜合交易不同的是，延伸測試在每個行程中可以執行多次。</span><span class="sxs-lookup"><span data-stu-id="19ff5-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="19ff5-123">在驗證如集區的多重公用電話交換網路 (PSTN) 語音路由時，這就非常有用。</span><span class="sxs-lookup"><span data-stu-id="19ff5-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="19ff5-124">只要在監看員節點中新增延伸測試的多個執行個體，即可設定。</span><span class="sxs-lookup"><span data-stu-id="19ff5-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="19ff5-125">如需將其他綜合交易新增至監看員節點程式的詳細資訊，請參閱 [管理 Lync Server 2013 中的](lync-server-2013-managing-watcher-nodes.md)監看員節點。</span><span class="sxs-lookup"><span data-stu-id="19ff5-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="19ff5-126">您可以使用 Lync Server 管理命令介面，從監看員節點中移除綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="19ff5-127">監看員節點可用的綜合交易包括下列：</span><span class="sxs-lookup"><span data-stu-id="19ff5-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19ff5-128">Cmdlet 名稱 (測試名稱)</span><span class="sxs-lookup"><span data-stu-id="19ff5-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="19ff5-129">描述</span><span class="sxs-lookup"><span data-stu-id="19ff5-129">Description</span></span></th>
<th><span data-ttu-id="19ff5-130">綜合交易類型</span><span class="sxs-lookup"><span data-stu-id="19ff5-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="19ff5-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-132">確認使用者可以查詢不在其連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="19ff5-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-133">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="19ff5-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-135">確認使用者可以透過 HTTP 查詢不在其連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="19ff5-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-136">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="19ff5-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-138">確認使用者可以傳送對等立即訊息。</span><span class="sxs-lookup"><span data-stu-id="19ff5-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-139">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-140">Test-CsP2PAV (P2PAV) </span><span class="sxs-lookup"><span data-stu-id="19ff5-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-141">確認使用者可以撥出對等音訊通話 (僅訊號)。</span><span class="sxs-lookup"><span data-stu-id="19ff5-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="19ff5-142">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-143">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="19ff5-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-144">確認使用者可以檢視其他使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="19ff5-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-145">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-146">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="19ff5-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-147">確認使用者可以登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="19ff5-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-148">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="19ff5-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-150">不會搭配 Lync Server 2013 的內部部署版本使用</span><span class="sxs-lookup"><span data-stu-id="19ff5-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="19ff5-151">延伸</span><span class="sxs-lookup"><span data-stu-id="19ff5-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="19ff5-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-153">確認使用者可以對企業外人員 (PSTN 號碼) 撥出及接聽通話。</span><span class="sxs-lookup"><span data-stu-id="19ff5-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="19ff5-154">非預設、延伸</span><span class="sxs-lookup"><span data-stu-id="19ff5-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-155">Test-CsAVConference (AvConference) </span><span class="sxs-lookup"><span data-stu-id="19ff5-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-156">確認使用者可以建立並參與音訊/視訊會議。</span><span class="sxs-lookup"><span data-stu-id="19ff5-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-157">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity) </span><span class="sxs-lookup"><span data-stu-id="19ff5-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-159">確認 A/V Edge Server 可以接受對等通話及電話會議的連線。</span><span class="sxs-lookup"><span data-stu-id="19ff5-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-160">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-161">Test-CsDataConference (DataConference) </span><span class="sxs-lookup"><span data-stu-id="19ff5-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-162">確認使用者可以參與資料共同作業會議 (包含如白板及投票等活動的線上會議)。</span><span class="sxs-lookup"><span data-stu-id="19ff5-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-163">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-164">Test-CsExumConnectivity (ExumConnectivity) </span><span class="sxs-lookup"><span data-stu-id="19ff5-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-165">確認使用者可以連線至 Exchange 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="19ff5-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="19ff5-166">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-167">Test-CsGroupIM (GroupIM) </span><span class="sxs-lookup"><span data-stu-id="19ff5-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-168">確認使用者可以在會議中傳送立即訊息，並參與有三位或更多位人員的立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="19ff5-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-169">預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-170">Test-CsGroupIM – TestJoinLauncher (JoinLauncher) </span><span class="sxs-lookup"><span data-stu-id="19ff5-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-171">確認使用者可以透過網址連結建立並加入排程會議。</span><span class="sxs-lookup"><span data-stu-id="19ff5-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-172">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-173">Test-CsMCXP2PIM (MCXP2PIM) </span><span class="sxs-lookup"><span data-stu-id="19ff5-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-174">確認行動裝置使用者可以註冊並傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="19ff5-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-175">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-176">Test-CsPersistentChatMessage (PersistentChatMessage) </span><span class="sxs-lookup"><span data-stu-id="19ff5-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-177">確認使用者可以使用 Persistent Chat service 來交換郵件。</span><span class="sxs-lookup"><span data-stu-id="19ff5-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-178">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-179">Test-CsUnifiedContactStore (UnifiedContactStore) </span><span class="sxs-lookup"><span data-stu-id="19ff5-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-180">確認可以透過整合連絡人存放區來存取使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="19ff5-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="19ff5-181">整合連絡人存放區提供一種方法，讓使用者維護一組可使用 Lync 2013、Outlook 和/或 Outlook Web Access 存取的連絡人。</span><span class="sxs-lookup"><span data-stu-id="19ff5-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-182">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-183">Test-CsXmppIM (XmppIM) </span><span class="sxs-lookup"><span data-stu-id="19ff5-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="19ff5-184">確認立即訊息可以跨 XMPP (Extensible Messaging and Presence Protocol) 閘道傳送。</span><span class="sxs-lookup"><span data-stu-id="19ff5-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="19ff5-185">非預設</span><span class="sxs-lookup"><span data-stu-id="19ff5-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="19ff5-186">您不需要安裝觀察程式節點，即可使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="19ff5-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="19ff5-187">如果您未安裝這些節點，您仍然可以在發生問題時，從 Lync Server 2013 元件取得即時提醒。</span><span class="sxs-lookup"><span data-stu-id="19ff5-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="19ff5-188"> (元件和 User Management Pack 不會使用觀察器節點。 ) 不過，如果您想要使用作用中的監控管理元件來監視端對端案例，則必須要有觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="19ff5-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ff5-189">系統管理員也不需要使用或安裝 Operations Manager，就可以手動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="19ff5-190">如需各種 Test-Cs Cmdlet 的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 Cmdlet 索引</A>。</span><span class="sxs-lookup"><span data-stu-id="19ff5-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="19ff5-191">視部署大小而定，綜合交易可能會使用大量電腦記憶體及處理器時間。</span><span class="sxs-lookup"><span data-stu-id="19ff5-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="19ff5-192">因此，建議您使用專用電腦作為監看員節點。</span><span class="sxs-lookup"><span data-stu-id="19ff5-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="19ff5-193">例如，您不應將前端伺服器設定為充當監看員節點。</span><span class="sxs-lookup"><span data-stu-id="19ff5-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="19ff5-194">觀察程式節點應該符合下列硬體規格：</span><span class="sxs-lookup"><span data-stu-id="19ff5-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ff5-195">舊版 Microsoft Lync Server 2010 監看員節點無法在具有 Lync Server 2013 觀察者節點的同一部電腦上組合。</span><span class="sxs-lookup"><span data-stu-id="19ff5-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="19ff5-196">這是因為 Lync Server 2010 和 Lync Server 2013 的核心系統檔無法安裝在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="19ff5-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="19ff5-197">不過，Lync Server 2013 觀察程式節點可以同時監視 Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="19ff5-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="19ff5-198">兩個產品版本都支援預設綜合交易。</span><span class="sxs-lookup"><span data-stu-id="19ff5-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="19ff5-199">Lync Server 2013 觀察程式節點可能會部署在企業內部或外部，以協助確認：</span><span class="sxs-lookup"><span data-stu-id="19ff5-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="19ff5-200">企業內使用者對集區的連線。</span><span class="sxs-lookup"><span data-stu-id="19ff5-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="19ff5-201">於企業外工作的遠端使用者透過周邊網路的連線。</span><span class="sxs-lookup"><span data-stu-id="19ff5-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="19ff5-202">對分公司設備的連線。</span><span class="sxs-lookup"><span data-stu-id="19ff5-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="19ff5-203">企業內和周邊網路中的 Lync Server 2010 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="19ff5-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="19ff5-204">對於簡化管理，企業內外有不同的驗證選項。</span><span class="sxs-lookup"><span data-stu-id="19ff5-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="19ff5-205">如需詳細資訊，請參閱設定 [監視節點以在 Lync Server 2013 中執行綜合交易](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="19ff5-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="19ff5-206">若要將電腦設定為監視節點，您必須在安裝 System Center Operations Manager 並匯入 Lync Server 2013 管理套件之後，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="19ff5-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="19ff5-207">在您安裝 Lync Server 2013 核心檔案與 System Center agent 檔案之前，您也應該確定觀察程式節點電腦符合安裝 Lync Server 2013 的所有必要條件。</span><span class="sxs-lookup"><span data-stu-id="19ff5-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="19ff5-208">此外，監看員節點電腦還應該安裝下列項目：</span><span class="sxs-lookup"><span data-stu-id="19ff5-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19ff5-209">硬體元件</span><span class="sxs-lookup"><span data-stu-id="19ff5-209">Hardware component</span></span></th>
<th><span data-ttu-id="19ff5-210">基本需求</span><span class="sxs-lookup"><span data-stu-id="19ff5-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-211">CPU</span><span class="sxs-lookup"><span data-stu-id="19ff5-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="19ff5-212">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="19ff5-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="19ff5-213">64位處理器、四核心2.33GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="19ff5-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="19ff5-214">64位2路處理器、雙核2.33GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="19ff5-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff5-215">記憶體</span><span class="sxs-lookup"><span data-stu-id="19ff5-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="19ff5-216">8 GB</span><span class="sxs-lookup"><span data-stu-id="19ff5-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff5-217">網路作業系統</span><span class="sxs-lookup"><span data-stu-id="19ff5-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="19ff5-218">1個網路介面卡 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="19ff5-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="19ff5-219">Windows Server 2008 R2、Windows Server 2012 或</span><span class="sxs-lookup"><span data-stu-id="19ff5-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="19ff5-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="19ff5-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="19ff5-221">.NET Framework 4.5 的完整版本。</span><span class="sxs-lookup"><span data-stu-id="19ff5-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="19ff5-222">Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="19ff5-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="19ff5-223">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="19ff5-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="19ff5-224">一旦符合所有這些必要條件，就可以執行下列動作來設定監看員節點：</span><span class="sxs-lookup"><span data-stu-id="19ff5-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="19ff5-225">在監看員節點電腦上安裝 Lync Server 2013 核心檔案。</span><span class="sxs-lookup"><span data-stu-id="19ff5-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="19ff5-226">在監看員節點電腦上安裝 System Center Operations Manager 代理程式。</span><span class="sxs-lookup"><span data-stu-id="19ff5-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="19ff5-227">執行 Watchernode.msi 可執行檔。</span><span class="sxs-lookup"><span data-stu-id="19ff5-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="19ff5-228">使用 **CsWatcherNodeConfiguration** Cmdlet 設定監看員節點要使用的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="19ff5-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

