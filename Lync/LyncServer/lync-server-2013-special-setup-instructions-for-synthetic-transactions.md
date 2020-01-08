---
title: Lync Server 2013：綜合交易的特殊設定指示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="e90a9-102">Lync Server 2013 中的綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="e90a9-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e90a9-103">_**主題上次修改日期：** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="e90a9-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="e90a9-104">大多數的綜合交易可以在觀察程式節點上自行執行，也就是說，只要綜合交易已新增至 [觀察程式節點設定]，觀察程式節點就可以在其測試階段中開始使用綜合交易。</span><span class="sxs-lookup"><span data-stu-id="e90a9-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="e90a9-105">不過，所有的綜合交易都不是如此。</span><span class="sxs-lookup"><span data-stu-id="e90a9-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="e90a9-106">例外狀況：需要特殊設定指示的綜合交易，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="e90a9-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="e90a9-107">處理伺服器逾時錯誤</span><span class="sxs-lookup"><span data-stu-id="e90a9-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="e90a9-108">在某些情況下，您可能會發現綜合交易失敗發生伺服器逾時錯誤（錯誤碼504）。</span><span class="sxs-lookup"><span data-stu-id="e90a9-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="e90a9-109">這些錯誤通常是由防火牆問題所造成。</span><span class="sxs-lookup"><span data-stu-id="e90a9-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="e90a9-110">當執行綜合交易時，該事務會在 MonitoringHost 處理常式下執行;接著，MonitoringHost 會啟動 PowerShell .exe 程式的實例。</span><span class="sxs-lookup"><span data-stu-id="e90a9-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="e90a9-111">如果您的防火牆封鎖 MonitoringHost 或 ngen.exe，則綜合交易將會失敗，並會產生504錯誤。</span><span class="sxs-lookup"><span data-stu-id="e90a9-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="e90a9-112">若要解決此問題，您應該在本機電腦上手動建立 MonitoringHost 和 ngen.exe 的入站防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="e90a9-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="e90a9-113">這可以透過 Windows 防火牆或協力廠商的本機防火牆軟體來完成，這要視伺服器預先設定的設定而定。</span><span class="sxs-lookup"><span data-stu-id="e90a9-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="e90a9-114">如果您是在綜合交易主機電腦和您嘗試監視的 Lync 伺服器之間使用網路防火牆裝置，您應該將主機視為用戶端電腦，並[在 Lync Server 2013 中觀察內部伺服器的埠和通訊協定的](lync-server-2013-ports-and-protocols-for-internal-servers.md)所有防火牆埠需求。</span><span class="sxs-lookup"><span data-stu-id="e90a9-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="e90a9-115">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="e90a9-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-116">如果您的系統監控程式節點電腦位於周邊網路之外，則您可能無法執行資料會議綜合交易，除非您首先停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e90a9-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="e90a9-117">若要停用此服務的 proxy 設定，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="e90a9-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="e90a9-118">在觀察程式節點電腦上，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="e90a9-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e90a9-119">在主控台視窗中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e90a9-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="e90a9-120">下列訊息會出現在命令視窗中：</span><span class="sxs-lookup"><span data-stu-id="e90a9-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="e90a9-121">此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e90a9-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="e90a9-122">Exchange 整合訊息合成交易</span><span class="sxs-lookup"><span data-stu-id="e90a9-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-123">Exchange 整合通訊（UM）綜合交易會確認測試使用者可以連線至位於 Exchange 中的語音信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="e90a9-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="e90a9-124">這些測試使用者將需要使用語音信箱帳戶預先設定，才能使用 Exchange UM 測試。</span><span class="sxs-lookup"><span data-stu-id="e90a9-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="e90a9-125">持續聊天綜合交易</span><span class="sxs-lookup"><span data-stu-id="e90a9-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-126">若要使用持續性聊天綜合交易，系統管理員必須先建立一個通道，然後給予測試使用者使用該通道的許可權。</span><span class="sxs-lookup"><span data-stu-id="e90a9-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="e90a9-127">[Test CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) Cmdlet 可用來適當地設定這些測試使用者：</span><span class="sxs-lookup"><span data-stu-id="e90a9-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="e90a9-128">此設定任務必須從企業內部執行：</span><span class="sxs-lookup"><span data-stu-id="e90a9-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="e90a9-129">如果從 nonserver 電腦執行，則執行 Cmdlet 的使用者必須是以角色為基礎的存取控制（RBAC）的 PersistentChatAdministrators 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="e90a9-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="e90a9-130">如果從伺服器本身執行，執行 Cmdlet 的使用者應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e90a9-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="e90a9-131">在上述命令中，會包含 Setup 參數並將其設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="e90a9-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="e90a9-132">如果您包含 Setup 參數，CsPersistentChatMessage 將會建立一個特殊的持續聊天室，並將該會議室填入測試使用者。</span><span class="sxs-lookup"><span data-stu-id="e90a9-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="e90a9-133">這有助於確保實際有聊天室可供測試之用。</span><span class="sxs-lookup"><span data-stu-id="e90a9-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="e90a9-134">請注意，只能從前端伺服器執行 Setup 參數。</span><span class="sxs-lookup"><span data-stu-id="e90a9-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="e90a9-135">只有系統管理員才能刪除由測試 CsPersistentChatMessage 所建立的聊天室。</span><span class="sxs-lookup"><span data-stu-id="e90a9-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="e90a9-136">PSTN 對等呼叫綜合交易記錄</span><span class="sxs-lookup"><span data-stu-id="e90a9-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-137">[Test CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)綜合交易會確認透過公用交換電話網絡（PSTN）來撥打和接聽通話的功能。</span><span class="sxs-lookup"><span data-stu-id="e90a9-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="e90a9-138">若要執行此綜合交易，系統管理員必須設定：</span><span class="sxs-lookup"><span data-stu-id="e90a9-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="e90a9-139">針對企業語音啟用的兩個測試使用者（來電者和接收人）。</span><span class="sxs-lookup"><span data-stu-id="e90a9-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="e90a9-140">針對每個使用者帳戶直接撥打（已有）號碼。</span><span class="sxs-lookup"><span data-stu-id="e90a9-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="e90a9-141">語音原則和語音路由，可以呼叫接收器的號碼來到達 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e90a9-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="e90a9-142">可接受呼叫的 PSTN 閘道，以及根據所撥打的號碼，將呼叫傳送到收件者的主池中的媒介。</span><span class="sxs-lookup"><span data-stu-id="e90a9-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="e90a9-143">整合連絡人商店綜合交易</span><span class="sxs-lookup"><span data-stu-id="e90a9-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-144">[整合連絡人商店] 綜合交易記錄會確認 Lync Server 2013 可以代表使用者從 Microsoft Exchange Server 2013 取得連絡人。</span><span class="sxs-lookup"><span data-stu-id="e90a9-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="e90a9-145">若要使用這個綜合交易，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="e90a9-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="e90a9-146">[在 lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)，必須在 lync server 2013 和 Exchange 2013 之間設定。</span><span class="sxs-lookup"><span data-stu-id="e90a9-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="e90a9-147">測試使用者必須具備有效的 Exchange 2013 信箱。</span><span class="sxs-lookup"><span data-stu-id="e90a9-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="e90a9-148">在符合這些條件之後，系統管理員可以執行下列命令，以驗證擁有 SIP 位址 kenmyer@litwareinc.com 的使用者可以從整合連絡人存放區中取得連絡人：</span><span class="sxs-lookup"><span data-stu-id="e90a9-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="e90a9-149">請注意，在前面的命令中使用的 Setup 參數。</span><span class="sxs-lookup"><span data-stu-id="e90a9-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="e90a9-150">如果執行 CsUnifiedContactStore 時包含 Setup 參數，則指定使用者的連絡人（在此案例中為 sip:kenmyer@litwareinc.com）將會移至 [整合連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="e90a9-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="e90a9-151">（當然，如果使用者的連絡人已在 [整合連絡人] 存放區中，則不需要移動它們。）Setup 參數通常只會使用一次（第一次執行測試 CsUnifiedContactStore），而且只應與測試使用者搭配使用;也就是說，使用者帳戶永遠不會登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e90a9-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="e90a9-152">當您的測試使用者已遷移至 [整合連絡人存放區] 之後，您可以在不使用 Setup 參數的情況下呼叫 Test CsUnifiedContactStore，以驗證使用者的連絡人是否可以檢索。</span><span class="sxs-lookup"><span data-stu-id="e90a9-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="e90a9-153">XMPP 綜合交易記錄</span><span class="sxs-lookup"><span data-stu-id="e90a9-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="e90a9-154">XMPP （可擴展訊息和目前狀態通訊協定） IM 綜合交易需要使用一或多個聯盟網域來設定 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="e90a9-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="e90a9-155">若要啟用 XMPP 綜合交易，必須在可路由的 XMPP 網域中，以使用者帳戶提供 XmppTestReceiverMailAddress 參數。</span><span class="sxs-lookup"><span data-stu-id="e90a9-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="e90a9-156">例如：</span><span class="sxs-lookup"><span data-stu-id="e90a9-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="e90a9-157">在這個範例中，Lync Server 2013 規則必須存在，以將 litwareinc.com 的訊息路由至 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="e90a9-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

