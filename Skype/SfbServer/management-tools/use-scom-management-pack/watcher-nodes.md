---
title: 安裝和設定觀察程式節點
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 摘要：針對商務用 Skype Server 合成事務安裝及設定觀察程式節點。
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816092"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="b94e2-103">安裝和設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="b94e2-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="b94e2-104">**摘要：** 針對商務用 Skype Server 合成事務安裝及設定觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="b94e2-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="b94e2-105">[觀察程式] 節點是定期執行商務用 Skype Server 綜合交易的電腦。</span><span class="sxs-lookup"><span data-stu-id="b94e2-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="b94e2-106">綜合交易是 Windows PowerShell Cmdlet，可驗證主要的使用者案例，例如登入或 exchange 立即訊息的功能是否如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="b94e2-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="b94e2-107">如果是商務用 Skype Server 2015，系統中心作業管理員可以執行下表所示的綜合交易，包括三個綜合交易類型：</span><span class="sxs-lookup"><span data-stu-id="b94e2-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="b94e2-108">**預設值**觀察程式節點預設會執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b94e2-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="b94e2-109">當您建立新的 [觀察程式] 節點時，您可以指定該節點要執行的綜合交易記錄。</span><span class="sxs-lookup"><span data-stu-id="b94e2-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="b94e2-110">（這是新的 CsWatcherNodeConfiguration Cmdlet 所使用的測試參數的用途）。如果您在建立觀察程式節點時不使用測試參數，就會自動執行所有預設的綜合交易，且不會執行任何非預設的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b94e2-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="b94e2-111">例如，這表示會將觀察程式節點設定為執行測試 CsAddressBookService 測試，但不會將其設定為執行測試 CsExumConnectivity 測試。</span><span class="sxs-lookup"><span data-stu-id="b94e2-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="b94e2-112">**非預設值**測試觀察程式節點預設不會執行。</span><span class="sxs-lookup"><span data-stu-id="b94e2-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="b94e2-113">（如需詳細資訊，請參閱預設類型的描述）。不過，可以啟用觀察程式節點來執行任何非預設的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b94e2-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="b94e2-114">您可以在建立觀察程式節點（使用 New-CsWatcherNodeConfiguration Cmdlet），或在已建立觀察程式節點之後的任何時間執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b94e2-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="b94e2-115">請注意，許多非預設的綜合交易需要額外的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="b94e2-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="b94e2-116">如需這些步驟的詳細資訊，請參閱[綜合交易的特殊設定指示](test-users-and-settings.md#special_synthetictrans)。</span><span class="sxs-lookup"><span data-stu-id="b94e2-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="b94e2-117">**延伸**非預設綜合交易的特殊類型。</span><span class="sxs-lookup"><span data-stu-id="b94e2-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="b94e2-118">與其他綜合交易不同，延長式測試可以在每一階段執行多次。</span><span class="sxs-lookup"><span data-stu-id="b94e2-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="b94e2-119">這在驗證行為（例如針對某個池的多個公用交換電話網絡（PSTN）語音路由）時很有用。</span><span class="sxs-lookup"><span data-stu-id="b94e2-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="b94e2-120">您只需將延伸測試的多個實例新增至觀察程式節點，就能進行這項設定。</span><span class="sxs-lookup"><span data-stu-id="b94e2-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="b94e2-121">如需有關新增其他綜合交易至觀察程式節點之程式的詳細資料，請參閱[設定觀察程式節點以執行綜合交易](watcher-nodes.md#enable_synthetic_trans)處理。</span><span class="sxs-lookup"><span data-stu-id="b94e2-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="b94e2-122">您也可以使用商務用 Skype Server Management Shell 來移除來自觀察程式節點的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b94e2-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="b94e2-123">可供觀察程式節點使用的綜合交易，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="b94e2-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="b94e2-124">**Cmdlet 名稱（測試名稱）**</span><span class="sxs-lookup"><span data-stu-id="b94e2-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="b94e2-125">**說明**</span><span class="sxs-lookup"><span data-stu-id="b94e2-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b94e2-126">Test-CsAddressBookService （ABS）</span><span class="sxs-lookup"><span data-stu-id="b94e2-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="b94e2-127">確認使用者可以查詢不在連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="b94e2-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="b94e2-128">CsAddressBookWebQuery （ABWQ）</span><span class="sxs-lookup"><span data-stu-id="b94e2-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="b94e2-129">確認使用者可以透過 HTTP 找不在連絡人清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="b94e2-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="b94e2-130">CsAVConference （AvConference）</span><span class="sxs-lookup"><span data-stu-id="b94e2-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="b94e2-131">確認使用者可以建立並參與音訊/視訊會議。</span><span class="sxs-lookup"><span data-stu-id="b94e2-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="b94e2-132">測試 CsGroupIM （IM 會議）</span><span class="sxs-lookup"><span data-stu-id="b94e2-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="b94e2-133">確認使用者可以在會議中傳送立即訊息，並與三人或多位人員一起參與立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="b94e2-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="b94e2-134">Test CsIM （P2P IM）</span><span class="sxs-lookup"><span data-stu-id="b94e2-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="b94e2-135">確認使用者可以傳送對等立即訊息。</span><span class="sxs-lookup"><span data-stu-id="b94e2-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="b94e2-136">CsP2PAV （P2PAV）</span><span class="sxs-lookup"><span data-stu-id="b94e2-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="b94e2-137">確認使用者可以進行對等音訊通話（僅限通知）。</span><span class="sxs-lookup"><span data-stu-id="b94e2-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="b94e2-138">CsPresence （目前狀態）</span><span class="sxs-lookup"><span data-stu-id="b94e2-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="b94e2-139">確認使用者能夠查看其他使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b94e2-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="b94e2-140">Test CsRegistration （註冊）</span><span class="sxs-lookup"><span data-stu-id="b94e2-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="b94e2-141">確認使用者可以登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="b94e2-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="b94e2-142">CsPstnPeerToPeerCall （PSTN）</span><span class="sxs-lookup"><span data-stu-id="b94e2-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="b94e2-143">確認使用者可以與企業外部的人員（PSTN 號碼）撥打電話和接聽來電。</span><span class="sxs-lookup"><span data-stu-id="b94e2-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="b94e2-144">CsASConference （ASConference）</span><span class="sxs-lookup"><span data-stu-id="b94e2-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="b94e2-145">確認使用者可以建立並參與應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="b94e2-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="b94e2-146">CsAVEdgeConnectivity （AVEdgeConnectivity）</span><span class="sxs-lookup"><span data-stu-id="b94e2-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="b94e2-147">確認音訊視頻邊緣伺服器能夠接受對等通話和電話會議的連線。</span><span class="sxs-lookup"><span data-stu-id="b94e2-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="b94e2-148">CsDataConference （DataConference）</span><span class="sxs-lookup"><span data-stu-id="b94e2-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="b94e2-149">確認使用者可以參與資料共同作業會議（包括白板和投票等活動的線上會議）。</span><span class="sxs-lookup"><span data-stu-id="b94e2-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="b94e2-150">CsDialinConferencing （DialinConferencing）</span><span class="sxs-lookup"><span data-stu-id="b94e2-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="b94e2-151">確認使用者可以撥打電話號碼加入會議。</span><span class="sxs-lookup"><span data-stu-id="b94e2-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="b94e2-152">CsDialinConferencing （DialinConferencing）</span><span class="sxs-lookup"><span data-stu-id="b94e2-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="b94e2-153">確認使用者可以撥打電話號碼加入會議。</span><span class="sxs-lookup"><span data-stu-id="b94e2-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="b94e2-154">CsExumConnectivity （ExumConnectivity）</span><span class="sxs-lookup"><span data-stu-id="b94e2-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="b94e2-155">確認使用者可以連線到 Exchange 整合通訊（UM）。</span><span class="sxs-lookup"><span data-stu-id="b94e2-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="b94e2-156">Test-CsGroupIM-TestJoinLauncher （JoinLauncher）</span><span class="sxs-lookup"><span data-stu-id="b94e2-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="b94e2-157">確認使用者可以建立並加入排程的會議（透過網址連結）。</span><span class="sxs-lookup"><span data-stu-id="b94e2-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="b94e2-158">CsMCXP2PIM （MCXP2PIM）</span><span class="sxs-lookup"><span data-stu-id="b94e2-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="b94e2-159">確認行動裝置使用者可以註冊並傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="b94e2-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="b94e2-160">CsP2PVideoInteropServerSipTrunkAV （P2PVideoInteropServerSipTrunkAV）</span><span class="sxs-lookup"><span data-stu-id="b94e2-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="b94e2-161">確認影片互通性伺服器已啟動，而且可以在視頻 SIP 主幹上處理傳入的連線。</span><span class="sxs-lookup"><span data-stu-id="b94e2-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="b94e2-162">**注意：** 商務用 Skype Server 2019 已不再提供舊版行動用戶端的 MCX 支援。</span><span class="sxs-lookup"><span data-stu-id="b94e2-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="b94e2-163">CsPersistentChatMessage （PersistentChatMessage）</span><span class="sxs-lookup"><span data-stu-id="b94e2-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="b94e2-164">確認使用者可以使用持續聊天服務來交換郵件。</span><span class="sxs-lookup"><span data-stu-id="b94e2-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="b94e2-165">CsUcwaConference （UcwaConference）</span><span class="sxs-lookup"><span data-stu-id="b94e2-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="b94e2-166">確認使用者可以透過網路加入會議。</span><span class="sxs-lookup"><span data-stu-id="b94e2-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="b94e2-167">CsUnifiedContactStore （UnifiedContactStore）</span><span class="sxs-lookup"><span data-stu-id="b94e2-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="b94e2-168">確認使用者的連絡人可以透過整合連絡人存放區存取。</span><span class="sxs-lookup"><span data-stu-id="b94e2-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="b94e2-169">「整合連絡人存放區」提供一種方式，讓使用者可以使用商務用 Skype Server 2015、Outlook 訊息與共同作業用戶端及/或 Outlook Web Access，來維護一組可存取的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b94e2-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="b94e2-170">CsXmppIM （XmppIM）</span><span class="sxs-lookup"><span data-stu-id="b94e2-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="b94e2-171">確認立即訊息可透過可擴展訊息和目前狀態通訊協定（XMPP）閘道傳送。</span><span class="sxs-lookup"><span data-stu-id="b94e2-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="b94e2-172">XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="b94e2-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="b94e2-173">您不需要安裝觀察程式節點，就能使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="b94e2-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="b94e2-174">如果您沒有安裝這些節點，您仍然可以在問題發生時，從商務用 Skype Server 2015 元件取得即時通知。</span><span class="sxs-lookup"><span data-stu-id="b94e2-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="b94e2-175">（元件和使用者管理套件不使用觀察程式節點）。不過，如果您想要使用主動監視管理套件監視端對端案例，則需要觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="b94e2-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b94e2-176">系統管理員也可以手動執行綜合交易，而不需使用或安裝 Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="b94e2-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="b94e2-177">根據商務用 Skype Server 部署的大小而定，綜合交易可以使用大量的電腦記憶體和處理器時間。</span><span class="sxs-lookup"><span data-stu-id="b94e2-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="b94e2-178">因此，建議您使用專用電腦做為觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="b94e2-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="b94e2-179">例如，您不應該將商務用 Skype Server 前端伺服器設定為充當觀察者節點。</span><span class="sxs-lookup"><span data-stu-id="b94e2-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="b94e2-180">觀察程式節點應該符合商務用 Skype Server 拓朴中任何其他電腦的基本硬體需求。</span><span class="sxs-lookup"><span data-stu-id="b94e2-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b94e2-181">舊版 Lync Server 2013 觀察程式節點無法在與商務用 Skype Server 2015 觀察程式節點相同的電腦上 collocated，因為 Lync Server 2013 和商務用 Skype Server 2015 的核心系統檔案無法安裝在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="b94e2-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="b94e2-182">不過，商務用 Skype Server 2015 觀察程式節點可以同時監視商務用 Skype Server 2015 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b94e2-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="b94e2-183">這兩個產品版本都支援預設的綜合交易記錄。</span><span class="sxs-lookup"><span data-stu-id="b94e2-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="b94e2-184">Lync Server 2013 觀察程式節點可以部署在企業內部或外部，以協助驗證：</span><span class="sxs-lookup"><span data-stu-id="b94e2-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="b94e2-185">企業內部使用者的 [池連線]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="b94e2-186">在企業外部工作的遠端使用者的周邊網路的連線能力。</span><span class="sxs-lookup"><span data-stu-id="b94e2-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="b94e2-187">連接至分支機搆裝置。</span><span class="sxs-lookup"><span data-stu-id="b94e2-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="b94e2-188">企業和周邊網路中的 Lync Server 2013 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="b94e2-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="b94e2-189">為了協助簡化管理，在企業內部和外部都可以使用不同的驗證選項。</span><span class="sxs-lookup"><span data-stu-id="b94e2-189">To help simplify administration, different authentication options are available for inside and outside of the enterprise.</span></span> <span data-ttu-id="b94e2-190">如需詳細資訊，請參閱[設定觀察程式節點以執行綜合交易](watcher-nodes.md#enable_synthetic_trans)。</span><span class="sxs-lookup"><span data-stu-id="b94e2-190">For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="b94e2-191">若要將電腦設定為充當觀察者節點，您必須先完成下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="b94e2-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="b94e2-192">安裝 System Center Operations Manager，然後匯入商務用 Skype Server 2015 管理套件。</span><span class="sxs-lookup"><span data-stu-id="b94e2-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="b94e2-193">您也必須先確認觀察程式節點電腦符合安裝商務用 Skype Server 2015 的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="b94e2-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="b94e2-194">在觀察程式節點電腦上安裝下列專案：</span><span class="sxs-lookup"><span data-stu-id="b94e2-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="b94e2-195">完整版的 .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="b94e2-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="b94e2-196">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="b94e2-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="b94e2-197">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="b94e2-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="b94e2-198">在符合先決條件之後，您可以依照下列步驟來設定觀察程式節點：</span><span class="sxs-lookup"><span data-stu-id="b94e2-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="b94e2-199">在觀察程式節點電腦上安裝商務用 Skype Server 2015 核心檔案。</span><span class="sxs-lookup"><span data-stu-id="b94e2-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="b94e2-200">在觀察程式節點電腦上安裝 System Center Operations Manager 代理程式。</span><span class="sxs-lookup"><span data-stu-id="b94e2-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="b94e2-201">執行 Watchernode 的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="b94e2-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="b94e2-202">使用**CsWatcherNodeConfiguration** Cmdlet 來設定要供觀察程式節點使用的測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b94e2-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="b94e2-203">安裝商務用 Skype Server 2015 核心檔案和 RTCLocal 資料庫</span><span class="sxs-lookup"><span data-stu-id="b94e2-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="b94e2-204">若要在電腦上安裝商務用 Skype Server 2015 核心檔案，請完成下列程式。</span><span class="sxs-lookup"><span data-stu-id="b94e2-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="b94e2-205">當您安裝核心檔案時，系統會自動安裝 RTCLocal 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b94e2-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="b94e2-206">請注意，您不需要在觀察程式節點上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b94e2-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="b94e2-207">SQL Server Express 將會自動安裝。</span><span class="sxs-lookup"><span data-stu-id="b94e2-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="b94e2-208">若要安裝商務用 Skype Server 2015 core 檔案和 RTCLocal 資料庫：</span><span class="sxs-lookup"><span data-stu-id="b94e2-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="b94e2-209">在觀察程式節點電腦上，按一下 [開始]，按一下 [所有程式]，按一下 [附件]，以滑鼠右鍵按一下命令提示字元，然後按一下 [以系統管理員身分執行]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="b94e2-210">在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="b94e2-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="b94e2-211">請務必輸入商務用 Skype Server 設定檔案的適當路徑： D:\Setup.exe/BootstrapLocalMgmtTo 驗證已成功安裝核心商務用 Skype server 元件，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [商務用**skype server 2015**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="b94e2-212">在商務用 Skype Server Management Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="b94e2-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="b94e2-213">第一次執行此命令時，不會傳回任何資料，因為您尚未設定任何觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="b94e2-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="b94e2-214">如果命令執行時不會傳回錯誤，您可以假設商務用 Skype Server 設定已順利完成。</span><span class="sxs-lookup"><span data-stu-id="b94e2-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="b94e2-215">如果您的系統監控程式節點電腦位於您的周邊網路內，您可以執行下列命令來驗證商務用 Skype Server 2015 的安裝：</span><span class="sxs-lookup"><span data-stu-id="b94e2-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="b94e2-216">根據您在組織中設定使用的 PIN 原則數目，CsPinPolicyYou 將會收到類似以下內容的資訊：</span><span class="sxs-lookup"><span data-stu-id="b94e2-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="b94e2-217">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b94e2-217">Identity : Global</span></span>
  
<span data-ttu-id="b94e2-218">說明</span><span class="sxs-lookup"><span data-stu-id="b94e2-218">Description :</span></span>
  
<span data-ttu-id="b94e2-219">MinPasswordLength：5</span><span class="sxs-lookup"><span data-stu-id="b94e2-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="b94e2-220">PINHistoryCount：0</span><span class="sxs-lookup"><span data-stu-id="b94e2-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="b94e2-221">AllowCommonPatterns： False</span><span class="sxs-lookup"><span data-stu-id="b94e2-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="b94e2-222">PINLifetime：0</span><span class="sxs-lookup"><span data-stu-id="b94e2-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="b94e2-223">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="b94e2-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="b94e2-224">如果您看到 PIN 原則的相關資訊，說明已成功安裝核心元件。</span><span class="sxs-lookup"><span data-stu-id="b94e2-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="b94e2-225">在觀察程式節點上安裝 Operation Manager 代理檔案</span><span class="sxs-lookup"><span data-stu-id="b94e2-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="b94e2-226">與商務用 Skype Server 設定類似，對於報告元件警示，商務用 Skype Server 2015 觀察程式節點需要安裝 System Center Operations Manager 代理檔案。</span><span class="sxs-lookup"><span data-stu-id="b94e2-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="b94e2-227">這可讓綜合交易執行，並將警示報告給 System Center Operations Manager 根管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="b94e2-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="b94e2-228">若要安裝代理程式檔案，請按照[設定要監視之商務用 Skype Server 電腦](configure-computers-to-monitor.md)中所列的程式進行。</span><span class="sxs-lookup"><span data-stu-id="b94e2-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="b94e2-229">設定觀察程式節點以執行綜合交易</span><span class="sxs-lookup"><span data-stu-id="b94e2-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="b94e2-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="b94e2-230"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="b94e2-231">安裝 System Center Operations Manager 代理檔案之後，您必須設定 [觀察程式] 節點本身。</span><span class="sxs-lookup"><span data-stu-id="b94e2-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="b94e2-232">您執行這項動作所採取的步驟會因您的觀察程式節點電腦是在周邊網路內或周邊網路以外的情況而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b94e2-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="b94e2-233">當您設定 [觀察程式] 節點時，您也必須選擇該節點要採用的驗證方法類型。</span><span class="sxs-lookup"><span data-stu-id="b94e2-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="b94e2-234">商務用 Skype Server 2015 可讓您選擇兩種驗證方法的其中一種：信任的伺服器或認證驗證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="b94e2-235">下表顯示這兩種方法之間的差異：</span><span class="sxs-lookup"><span data-stu-id="b94e2-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="b94e2-236">**說明**</span><span class="sxs-lookup"><span data-stu-id="b94e2-236">**Description**</span></span>|<span data-ttu-id="b94e2-237">**支援的位置**</span><span class="sxs-lookup"><span data-stu-id="b94e2-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b94e2-238">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="b94e2-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="b94e2-239">使用憑證來類比內部伺服器並略過驗證難題。</span><span class="sxs-lookup"><span data-stu-id="b94e2-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="b94e2-240">適用于喜歡管理單一憑證的系統管理員，而不是每個觀察程式節點上的許多使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="b94e2-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="b94e2-241">在企業內。</span><span class="sxs-lookup"><span data-stu-id="b94e2-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="b94e2-242">使用這個方法，觀察程式節點必須與受監視的池位於同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="b94e2-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="b94e2-243">如果觀察程式節點和池位於不同的網域中，請改用認證驗證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="b94e2-244">Negotiate</span><span class="sxs-lookup"><span data-stu-id="b94e2-244">Negotiate</span></span>  <br/> |<span data-ttu-id="b94e2-245">在每個觀察程式節點上安全地儲存在 Windows 認證管理器中的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b94e2-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="b94e2-246">這個模式需要更多的密碼管理，但是企業外部之觀察程式節點的唯一選項。</span><span class="sxs-lookup"><span data-stu-id="b94e2-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="b94e2-247">這些觀察程式節點無法被視為受信任的端點以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="b94e2-248">在企業外部。</span><span class="sxs-lookup"><span data-stu-id="b94e2-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="b94e2-249">在企業內。</span><span class="sxs-lookup"><span data-stu-id="b94e2-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="b94e2-250">將觀察程式節點設定為使用信任的伺服器驗證</span><span class="sxs-lookup"><span data-stu-id="b94e2-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="b94e2-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="b94e2-251"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="b94e2-252">如果您的 [觀察程式] 節點電腦位於周邊網路內，使用受信任的伺服器驗證，可維護單一憑證，而不是使用大量的使用者帳戶密碼，以大大減少管理工作。</span><span class="sxs-lookup"><span data-stu-id="b94e2-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="b94e2-253">若要設定信任的伺服器驗證，您必須先建立信任的應用程式池來託管觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="b94e2-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="b94e2-254">在您建立受信任的應用程式池之後，您必須接著在該觀察程式節點上設定綜合交易，以執行為信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b94e2-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b94e2-255">受信任的應用程式是以商務用 Skype Server 2015 （不是產品內建元件）的方式提供受信任狀態的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b94e2-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="b94e2-256">[受信任的狀態] 表示應用程式在每次執行時不會受到驗證的挑戰。</span><span class="sxs-lookup"><span data-stu-id="b94e2-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="b94e2-257">若要建立信任的應用程式池，請開啟商務用 Skype Server 管理命令介面，並執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="b94e2-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="b94e2-258">如需上述命令中參數的詳細資訊，請從商務用 Skype Server Management Shell 提示輸入以下內容：</span><span class="sxs-lookup"><span data-stu-id="b94e2-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="b94e2-259">建立受信任的應用程式池之後，您就可以使用**新的 CsTrustedApplication** Cmdlet 和類似以下的命令，將 [觀察程式] 節點電腦設定為以受信任的應用程式執行綜合交易：</span><span class="sxs-lookup"><span data-stu-id="b94e2-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="b94e2-260">完成這個命令並建立受信任的應用程式後，您必須執行**Enable CsTopology** Cmdlet，以確保變更生效：</span><span class="sxs-lookup"><span data-stu-id="b94e2-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="b94e2-261">觀察程式節點電腦帳戶必須能夠查詢 CMS，以尋找某些綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b94e2-261">The watcher node computer account requires the ability to query CMS for some synthetic transactions.</span></span> <span data-ttu-id="b94e2-262">若要允許這項功能，請將觀察程式節點的電腦帳戶新增至 RTCUniversalReadOnlyAdmins 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b94e2-262">To allow this ability, add the computer account of the watcher node to the RTCUniversalReadOnlyAdmins security group.</span></span> <span data-ttu-id="b94e2-263">發生廣告複製之後，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b94e2-263">Once AD replication has occurred, restart the computer.</span></span>
  
<span data-ttu-id="b94e2-264">若要確認是否已建立新的受信任應用程式，請在商務用 Skype Server Management Shell 提示中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="b94e2-264">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="b94e2-265">在 [觀察程式] 節點上設定預設憑證</span><span class="sxs-lookup"><span data-stu-id="b94e2-265">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="b94e2-266"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="b94e2-266"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="b94e2-267">使用 TrustedServer 驗證的每個觀察程式節點，都必須有使用商務用 Skype Server 部署嚮導指派的預設憑證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-267">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="b94e2-268">若要指派預設憑證：</span><span class="sxs-lookup"><span data-stu-id="b94e2-268">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="b94e2-269">按一下 [開始]，按一下 [所有程式]，按一下 [商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server 部署嚮導]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-269">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="b94e2-270">在商務用 Skype Server 部署嚮導中，按一下 [安裝或更新商務用 Skype Server System]，然後按一下標題要求、安裝或指派憑證底下的 [執行]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-270">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b94e2-271">如果停用 [執行] 按鈕，您可能需要先按一下 [安裝本機設定儲存區] 下的 [執行]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-271">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="b94e2-272">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="b94e2-272">Do one of the following:</span></span>
  
- <span data-ttu-id="b94e2-273">如果您已有可用作預設憑證的憑證，請按一下 [證書] 嚮導中的 [預設]，然後按一下 [指派]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-273">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign.</span></span> <span data-ttu-id="b94e2-274">遵循 [證書指派] 嚮導中的步驟，將該憑證指派給您。</span><span class="sxs-lookup"><span data-stu-id="b94e2-274">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="b94e2-275">如果您需要要求使用預設憑證的憑證，請按一下 [要求]，然後依照 [證書申請] 嚮導中的步驟要求認證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-275">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="b94e2-276">如果您使用的是 Web 服務器憑證的預設值，您會取得可指派為預設憑證的憑證。</span><span class="sxs-lookup"><span data-stu-id="b94e2-276">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="b94e2-277">安裝和設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="b94e2-277">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="b94e2-278"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="b94e2-278"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="b94e2-279">重新開機觀察程式節點電腦並設定憑證之後，您必須執行檔案 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="b94e2-279">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="b94e2-280">（您必須在同時安裝 Operations Manager 代理程式和商務用 Skype Server 2015 核心元件的任何電腦上執行 Watchernode。）</span><span class="sxs-lookup"><span data-stu-id="b94e2-280">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="b94e2-281">若要安裝和設定觀察程式節點：</span><span class="sxs-lookup"><span data-stu-id="b94e2-281">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="b94e2-282">按一下 [開始]，按一下 [所有程式]，按一下 [商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server Management Shell]，即可開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b94e2-282">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="b94e2-283">在管理命令介面中，輸入下列命令，然後按 ENTER （請確定並指定您 Watchernode 複本的實際路徑）：</span><span class="sxs-lookup"><span data-stu-id="b94e2-283">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="b94e2-284">您也可以從命令視窗執行 Watchernode n。</span><span class="sxs-lookup"><span data-stu-id="b94e2-284">You can also run Watchernode.msi n from a command window.</span></span> <span data-ttu-id="b94e2-285">若要開啟命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-285">To open a command window, click Start, right-click Command Prompt, and then click Run as administrator.</span></span> <span data-ttu-id="b94e2-286">當命令視窗開啟時，請輸入與上述步驟2所示的相同命令。</span><span class="sxs-lookup"><span data-stu-id="b94e2-286">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b94e2-287">在上述命令中，名稱/值對驗證 = TrustedServer 是區分大小寫的。</span><span class="sxs-lookup"><span data-stu-id="b94e2-287">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="b94e2-288">必須完全按照所示輸入。</span><span class="sxs-lookup"><span data-stu-id="b94e2-288">It must be typed exactly as shown.</span></span> <span data-ttu-id="b94e2-289">例如，這個命令會因為不使用正確的字母大小寫而失敗：</span><span class="sxs-lookup"><span data-stu-id="b94e2-289">For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="b94e2-290">TrustedServer 模式只能與位於周邊網路內的電腦搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b94e2-290">TrustedServer mode can be used only with computers that lie inside the perimeter network.</span></span> <span data-ttu-id="b94e2-291">當觀察程式節點以 TrustedServer 模式執行時，系統管理員不需要維護電腦上的測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="b94e2-291">When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="b94e2-292">將觀察程式節點設定為使用 Negotiate</span><span class="sxs-lookup"><span data-stu-id="b94e2-292">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="b94e2-293"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="b94e2-293"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="b94e2-294">如果您的觀察程式節點電腦位於周邊網路之外，您必須遵循稍有不同的程式，才能設定該觀察程式節點執行綜合交易：尤其是，您不應該建立信任的應用程式池或信任的專案應用程式.</span><span class="sxs-lookup"><span data-stu-id="b94e2-294">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application.</span></span> <span data-ttu-id="b94e2-295">這表示您將需要完成後續兩項工作。</span><span class="sxs-lookup"><span data-stu-id="b94e2-295">That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="b94e2-296">更新 RTC 本機唯讀系統管理員群組中的成員資格</span><span class="sxs-lookup"><span data-stu-id="b94e2-296">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="b94e2-297">如果您的 [觀察程式] 節點位於周邊網路之外，您必須在 [觀察程式] 節點上完成下列程式，將 [網路服務] 帳戶新增到 [觀察程式] 節點電腦上的 RTC 本機唯讀系統管理員群組：</span><span class="sxs-lookup"><span data-stu-id="b94e2-297">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="b94e2-298">按一下 [開始]，以滑鼠右鍵按一下 [電腦]，然後按一下 [管理]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-298">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="b94e2-299">在 [伺服器管理員] 中，展開 [設定]，展開 [本機使用者和群組]，然後按一下 [群組]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-299">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="b94e2-300">在 [群組] 窗格中，按兩下 [RTC 局部唯讀管理員]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-300">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="b94e2-301">在 [RTC 本機唯讀系統管理員屬性] 對話方塊中，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-301">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="b94e2-302">在 [選取使用者、電腦、服務帳戶或群組] 對話方塊中，按一下 [位置]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-302">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="b94e2-303">在 [位置] 對話方塊中，選取 [觀察程式] 節點電腦的名稱，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-303">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="b94e2-304">在 [輸入要選取的物件名稱] 方塊中，輸入 [網路服務]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-304">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="b94e2-305">在 [RTC 本機唯讀系統管理員屬性] 對話方塊中，按一下 [確定]，然後關閉 [伺服器管理員]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-305">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="b94e2-306">重新開機觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="b94e2-306">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="b94e2-307">安裝觀察程式節點設定檔</span><span class="sxs-lookup"><span data-stu-id="b94e2-307">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="b94e2-308">下一步是執行檔案 Watchernode：</span><span class="sxs-lookup"><span data-stu-id="b94e2-308">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="b94e2-309">開啟 Microsoft 商務用 Skype Server 2015 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b94e2-309">Open the Microsoft Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="b94e2-310">按一下 [開始]，按一下 [所有程式]，按一下 [Microsoft 商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server Management Shell]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-310">Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="b94e2-311">在商務用 Skype Server 管理命令介面中，輸入下列命令，然後按 ENTER （請務必指定您 Watchernode 複本的實際路徑）：</span><span class="sxs-lookup"><span data-stu-id="b94e2-311">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="b94e2-312">如先前所述，Watchernode 也可以從命令視窗執行。</span><span class="sxs-lookup"><span data-stu-id="b94e2-312">As mentioned previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="b94e2-313">若要開啟命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下 [**命令提示**字元]，然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="b94e2-313">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="b94e2-314">當命令視窗開啟時，請輸入與上述步驟2所示的相同命令。</span><span class="sxs-lookup"><span data-stu-id="b94e2-314">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="b94e2-315">當無法將觀察程式節點設定為受信任的應用程式池時，就會使用 [協商] 模式。</span><span class="sxs-lookup"><span data-stu-id="b94e2-315">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="b94e2-316">在此模式中，系統管理員必須在 [觀察程式] 節點上管理測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="b94e2-316">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

