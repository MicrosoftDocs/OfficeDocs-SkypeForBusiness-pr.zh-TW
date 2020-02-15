---
title: Lync Server 2013： 綜合交易的特殊設定指示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="56889-102">Lync Server 2013 中的綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="56889-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56889-103">_**主題上次修改日期：** 2015 年 11-16_</span><span class="sxs-lookup"><span data-stu-id="56889-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="56889-p101">在現有的監看員節點上可執行大多數綜合交易；也就是說，一旦將綜合交易新增至監看員節點組態設定，監看員節點就可在其測試通過期間開始使用綜合交易。不過，並非所有綜合交易皆如此。需要特殊設定指示的綜合交易就是例外， 我們會在後續章節中討論。</span><span class="sxs-lookup"><span data-stu-id="56889-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="56889-107">因應伺服器逾時錯誤</span><span class="sxs-lookup"><span data-stu-id="56889-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="56889-108">在某些情況下您可能會發現您的綜合交易的失敗伺服器逾時錯誤 （錯誤代碼 504）。</span><span class="sxs-lookup"><span data-stu-id="56889-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="56889-109">這些錯誤通常是因為防火牆問題。</span><span class="sxs-lookup"><span data-stu-id="56889-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="56889-110">綜合交易執行時下 MonitoringHost.exe 程序; 執行交易接著，MonitoringHost.exe 啟動 PowerShell.exe 程序的執行個體。</span><span class="sxs-lookup"><span data-stu-id="56889-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="56889-111">如果您的防火牆封鎖 MonitoringHost.exe 或 PowerShell.exe 綜合交易會失敗，並將會產生 504 錯誤。</span><span class="sxs-lookup"><span data-stu-id="56889-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="56889-112">若要解決此問題，您應該手動輸入的防火牆規則 MonitoringHost.exe 和 PowerShell.exe 上建立本機電腦。</span><span class="sxs-lookup"><span data-stu-id="56889-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="56889-113">這可以透過 Windows 防火牆或協力廠商本機防火牆軟體，視您的伺服器預先存在的組態而定。</span><span class="sxs-lookup"><span data-stu-id="56889-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="56889-114">如果您正在使用綜合交易主機機器與您在嘗試監視 Lync 伺服器之間的網路防火牆裝置，您應該視為主應用程式的用戶端電腦與觀察者[連接埠和通訊協定適用於 Lync Server 2013 中的內部伺服器](lync-server-2013-ports-and-protocols-for-internal-servers.md)的所有防火牆連接埠需求。</span><span class="sxs-lookup"><span data-stu-id="56889-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="56889-115">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="56889-116">如果您的監看員節點電腦位於周邊網路外，您可能不會是能夠執行資料會議綜合交易，除非您先停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="56889-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="56889-117">若要停用此服務的 Proxy 設定，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="56889-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="56889-118">在監看員節點電腦上，按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**、 以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="56889-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="56889-119">在主控台視窗中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="56889-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="56889-120">下列訊息會出現在命令視窗中：</span><span class="sxs-lookup"><span data-stu-id="56889-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="56889-121">此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="56889-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="56889-122">Exchange 整合通訊綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="56889-123">Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者可連線的帳戶位於 Exchange 中的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="56889-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="56889-124">需使用語音信箱帳戶預先設定這些測試使用者之後，他們才可使用 Exchange UM 測試。</span><span class="sxs-lookup"><span data-stu-id="56889-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="56889-125">常設聊天室綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="56889-126">若要使用的常設聊天室的綜合交易，系統管理員必須先建立通道，並使用它的使用者權限授與測試。</span><span class="sxs-lookup"><span data-stu-id="56889-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="56889-127">[Test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet 可用於適當地設定這些測試使用者：</span><span class="sxs-lookup"><span data-stu-id="56889-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="56889-128">必須從企業內部執行此設定工作：</span><span class="sxs-lookup"><span data-stu-id="56889-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="56889-129">如果從非伺服器電腦執行，則執行 Cmdlet 的使用者須為角色型存取控制 (RBAC) 的 PersistentChatAdministrators 角色成員。</span><span class="sxs-lookup"><span data-stu-id="56889-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="56889-130">如果從伺服器本身執行，則執行 Cmdlet 的使用者應為 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="56889-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="56889-131">在上述命令中，已包含設定參數並設為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="56889-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="56889-132">如果您包含的安裝程式參數，Test-cspersistentchatmessage 會建立特殊的常設聊天室會議室，並填入該測試使用者的會議室。</span><span class="sxs-lookup"><span data-stu-id="56889-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="56889-133">這樣可確保確實有聊天室可供測試之用。</span><span class="sxs-lookup"><span data-stu-id="56889-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="56889-134">請注意，只能從前端伺服器應執行 Setup 參數。</span><span class="sxs-lookup"><span data-stu-id="56889-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="56889-135">Test-CsPersistentChatMessage 建立的聊天室僅可由系統管理員刪除。</span><span class="sxs-lookup"><span data-stu-id="56889-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="56889-136">PSTN 對等通話綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="56889-137">[Test-cspstnpeertopeercall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)綜合交易會驗證撥出及接聽透過公用交換的電話網路 (PSTN) 通話的能力。</span><span class="sxs-lookup"><span data-stu-id="56889-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="56889-138">若要執行此綜合交易，系統管理員必須進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="56889-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="56889-139">兩名測試使用者 （發話者和收件者） 啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="56889-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="56889-140">每個使用者帳戶的直接內部撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="56889-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="56889-141">語音原則和語音路由可讓撥打至受話者號碼的通話到達 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="56889-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="56889-142">接受通話的 PSTN 閘道，與依據撥打的號碼將通話路由傳送回受話者主集區的媒體。</span><span class="sxs-lookup"><span data-stu-id="56889-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="56889-143">整合連絡人存放區綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="56889-144">整合連絡人存放區綜合交易會驗證 Lync Server 2013 是能夠從 Microsoft Exchange Server 2013 中擷取代表使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="56889-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="56889-145">若要使用此綜合交易，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="56889-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="56889-146">[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)必須設定 Lync Server 2013 和 Exchange 2013 之間。</span><span class="sxs-lookup"><span data-stu-id="56889-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="56889-147">測試使用者必須具備有效的 Exchange 2013 信箱。</span><span class="sxs-lookup"><span data-stu-id="56889-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="56889-148">在符合這些條件後，系統管理員可執行下列命令，以確定 SIP 位址為 kenmyer@litwareinc.com 的使用者，可從整合連絡人存放區擷取其連絡人：</span><span class="sxs-lookup"><span data-stu-id="56889-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="56889-149">請注意在上述命令中使用 Setup 參數使用。</span><span class="sxs-lookup"><span data-stu-id="56889-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="56889-150">如果 Setup 參數時，包含執行 Test-csunifiedcontactstore 然後指定的使用者的連絡人 (在此情況下，sip:kenmyer@litwareinc.com) 將會移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="56889-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="56889-151">（當然，如果使用者的連絡人已經整合連絡人存放區中然後他們沒有要移動。）Setup 參數通常只有一次 （第一次執行 Test-csunifiedcontactstore），並只應使用的測試使用者;亦即，將不會實際登入 Lync Server 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="56889-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="56889-152">測試使用者已移轉至整合連絡人存放區之後，您可以確認，可以透過呼叫 Test-csunifiedcontactstore 沒有 Setup 參數來擷取使用者的連絡人：</span><span class="sxs-lookup"><span data-stu-id="56889-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="56889-153">XMPP 綜合交易</span><span class="sxs-lookup"><span data-stu-id="56889-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="56889-154">使用 XMPP (Extensible Messaging and Presence Protocol，可延伸訊息和目前狀態通訊協定) IM 綜合交易時，需配合一或多個同盟網域來設定 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="56889-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="56889-155">若要啟用 XMPP 綜合交易，須在可路由的 XMPP 網域提供 XmppTestReceiverMailAddress 參數和使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="56889-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="56889-156">例如：</span><span class="sxs-lookup"><span data-stu-id="56889-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="56889-157">在這個範例中，Lync Server 2013 規則必須存在，才可將郵件路由傳送至 XMPP 閘道 litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="56889-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

