---
title: 設定監視器節點測試使用者和設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ecb6946bcbb7244ef3e5ef8504312063ab1bd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507520"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f67b1-102">在 Lync Server 2013 中設定監視節點測試使用者和設定設定</span><span class="sxs-lookup"><span data-stu-id="f67b1-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f67b1-103">_**主題上次修改日期：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="f67b1-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="f67b1-104">在設定將充當監視節點的電腦之後，您必須：</span><span class="sxs-lookup"><span data-stu-id="f67b1-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="f67b1-105">建立這些觀察器節點要使用的測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="f67b1-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="f67b1-106">如果您使用 Negotiate 驗證方法，您也必須使用 [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) Cmdlet 來啟用這些測試帳戶，以在監看員節點上使用。</span><span class="sxs-lookup"><span data-stu-id="f67b1-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="f67b1-107">更新監視節點的設定。</span><span class="sxs-lookup"><span data-stu-id="f67b1-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="f67b1-108">本節涵蓋：</span><span class="sxs-lookup"><span data-stu-id="f67b1-108">This section covers:</span></span>

  - <span data-ttu-id="f67b1-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f67b1-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="f67b1-110">使用預設的綜合交易，設定基本的監看員節點</span><span class="sxs-lookup"><span data-stu-id="f67b1-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="f67b1-111">設定擴充測試</span><span class="sxs-lookup"><span data-stu-id="f67b1-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="f67b1-112">新增及移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="f67b1-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="f67b1-113">查看及測試監視節點設定</span><span class="sxs-lookup"><span data-stu-id="f67b1-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="f67b1-114">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f67b1-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="f67b1-115">測試使用者不需要表示實際人員，但必須是有效的 Active Directory 網域服務帳戶;此外，必須對 Lync Server 2013 啟用這些帳戶，他們必須具有有效的 SIP 位址，而且應為 Enterprise Voice (啟用這些帳戶，才能使用 Test-CsPstnPeerToPeerCall 綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="f67b1-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="f67b1-116">如果您使用 TrustedServer 驗證方法，則您需要做的全部工作是確定這些帳戶都存在，且已依照這裡所指定的方式進行設定。</span><span class="sxs-lookup"><span data-stu-id="f67b1-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="f67b1-117">您應為每個要測試的集區至少指派三個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="f67b1-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="f67b1-118">如果您使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 和 Lync Server 管理命令介面，讓這些測試帳戶能夠搭配綜合交易。</span><span class="sxs-lookup"><span data-stu-id="f67b1-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="f67b1-119">您可以執行類似如下的命令來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f67b1-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="f67b1-120"> (這些命令會假設已建立三個 Active Directory 使用者帳戶，且已啟用這些帳戶的 Lync Server 2013。 ) ：</span><span class="sxs-lookup"><span data-stu-id="f67b1-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="f67b1-121">請注意，您不僅必須包含 SIP 位址，也必須包含使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="f67b1-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="f67b1-122">如果您未加入密碼 Set-CsTestUserCredential 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="f67b1-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="f67b1-123">您可以使用 \\ 如上所示的功能變數名稱使用者名稱格式指定使用者名稱，或使用 format user name@domain name; 例如：</span><span class="sxs-lookup"><span data-stu-id="f67b1-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="f67b1-124">若要確認已建立測試使用者認證，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="f67b1-125">針對每位使用者應傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f67b1-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="f67b1-126">使用預設的綜合交易，設定基本的監看員節點</span><span class="sxs-lookup"><span data-stu-id="f67b1-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="f67b1-127">在建立測試使用者之後，您可以使用類似下列的命令來建立監看員節點：</span><span class="sxs-lookup"><span data-stu-id="f67b1-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="f67b1-128">這個命令會建立新的監看員節點，使用預設設定，並執行預設的綜合交易集合。</span><span class="sxs-lookup"><span data-stu-id="f67b1-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="f67b1-129">新的監看員節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 及 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="f67b1-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="f67b1-130">如果監看員節點使用的是 TrustedServer 驗證，則三個測試帳戶可以是為 Active Directory 和 Lync Server 啟用的任何有效使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f67b1-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="f67b1-131">如果監看員節點使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 來啟用監看員節點的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f67b1-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="f67b1-132">設定擴充測試</span><span class="sxs-lookup"><span data-stu-id="f67b1-132">Configuring Extended Tests</span></span>

<span data-ttu-id="f67b1-133">如果您想要啟用公用交換電話網路 (PSTN 測試) ，它會驗證與公用交換電話網路的連線，您必須在設定監看員節點時執行一些其他設定。</span><span class="sxs-lookup"><span data-stu-id="f67b1-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="f67b1-134">首先，您必須將測試使用者與 PSTN 測試類型產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f67b1-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="f67b1-135">若要這麼做，請在 Lync Server 管理命令介面中執行類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="f67b1-136">請注意，此命令的結果必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="f67b1-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="f67b1-137">在此範例中，這是一個名為 $pstnTest 的變數。</span><span class="sxs-lookup"><span data-stu-id="f67b1-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="f67b1-138">此時，您可以使用 **New-CsWatcherNodeConfiguration** Cmdlet，將 $pstnTest) 中儲存的測試類型 (關聯至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="f67b1-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="f67b1-139">例如，下列命令會為集區 atl-cs-001.litwareinc.com 建立新的監看員節點設定，加入先前建立的三個測試使用者，也新增 PSTN 測試類型：</span><span class="sxs-lookup"><span data-stu-id="f67b1-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="f67b1-140">請注意，如果您尚未在監看員節點電腦上安裝 Lync Server 核心檔案和 RTCLocal 資料庫，上述命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f67b1-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="f67b1-141">若要測試多種語音原則，您必須使用 **New-CsExtendedTest** Cmdlet，為每個原則建立擴充測試。</span><span class="sxs-lookup"><span data-stu-id="f67b1-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="f67b1-142">指派給此測試的使用者應以所需的語音原則加以設定。</span><span class="sxs-lookup"><span data-stu-id="f67b1-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="f67b1-143">然後，您可以使用類似下列的命令，將延伸的測試傳遞至 **New-CsWatcherNodeConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f67b1-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="f67b1-144">如果不使用 [測試] 參數呼叫 New-CsWatcherNodeConfiguration，表示只有預設的綜合交易 (，且會為新的監看員節點啟用指定的延伸綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="f67b1-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="f67b1-145">這表示觀察程式節點會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="f67b1-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="f67b1-146">註冊</span><span class="sxs-lookup"><span data-stu-id="f67b1-146">Registration</span></span>

  - <span data-ttu-id="f67b1-147">我</span><span class="sxs-lookup"><span data-stu-id="f67b1-147">IM</span></span>

  - <span data-ttu-id="f67b1-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="f67b1-148">GroupIM</span></span>

  - <span data-ttu-id="f67b1-149">P2PAV (對等音訊/視頻會話) </span><span class="sxs-lookup"><span data-stu-id="f67b1-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="f67b1-150">AvConference (音訊/會議) </span><span class="sxs-lookup"><span data-stu-id="f67b1-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="f67b1-151">目前狀態</span><span class="sxs-lookup"><span data-stu-id="f67b1-151">Presence</span></span>

  - <span data-ttu-id="f67b1-152">ABS (通訊錄服務) </span><span class="sxs-lookup"><span data-stu-id="f67b1-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="f67b1-153">ABWQ (通訊錄 web 服務) </span><span class="sxs-lookup"><span data-stu-id="f67b1-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="f67b1-154">PSTN (PSTN 閘道通話，指定為延伸測試。</span><span class="sxs-lookup"><span data-stu-id="f67b1-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="f67b1-155">預設會停用 PSTN。</span><span class="sxs-lookup"><span data-stu-id="f67b1-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="f67b1-156">在此情況下會啟用測試，只是因為命令已使用 ExtendedTests 參數啟用 PSTN。 ) </span><span class="sxs-lookup"><span data-stu-id="f67b1-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="f67b1-157">這也意味著預設不會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="f67b1-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="f67b1-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="f67b1-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="f67b1-159">MCXP2PIM (行動裝置立即訊息) </span><span class="sxs-lookup"><span data-stu-id="f67b1-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="f67b1-160">ExumConnectivity (Exchange 整合通訊) </span><span class="sxs-lookup"><span data-stu-id="f67b1-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="f67b1-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="f67b1-161">JoinLauncher</span></span>

  - <span data-ttu-id="f67b1-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="f67b1-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="f67b1-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="f67b1-163">DataConference</span></span>

  - <span data-ttu-id="f67b1-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="f67b1-164">XmppIM</span></span>

  - <span data-ttu-id="f67b1-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="f67b1-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="f67b1-166">新增及移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="f67b1-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="f67b1-167">在設定了監看員節點之後，您可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來新增或移除節點中的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="f67b1-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="f67b1-168">例如，若要將 PersistentChatMessage 測試新增至監看員節點，請使用 Add 方法及類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="f67b1-169">若要新增多個測試，您可以使用逗號分隔測試名稱。</span><span class="sxs-lookup"><span data-stu-id="f67b1-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="f67b1-170">例如：</span><span class="sxs-lookup"><span data-stu-id="f67b1-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="f67b1-171">請注意，如果其中一或多個測試 (例如，DataConference) 已經在監看員節點上啟用，就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="f67b1-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="f67b1-172">在此情況下，您會收到類似下列的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f67b1-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="f67b1-173">發生此錯誤時，將不會套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="f67b1-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="f67b1-174">在移除重複的測試時，應重新執行該命令。</span><span class="sxs-lookup"><span data-stu-id="f67b1-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="f67b1-175">若要移除來自觀察者節點的綜合交易，請使用 Remove 方法，而不要使用 Add 方法。</span><span class="sxs-lookup"><span data-stu-id="f67b1-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="f67b1-176">例如，下列命令會從監看員節點中移除 ABWQ 測試：</span><span class="sxs-lookup"><span data-stu-id="f67b1-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="f67b1-177">您也可以使用 Replace 方法，將所有目前啟用的測試取代為一或多個新的測試。</span><span class="sxs-lookup"><span data-stu-id="f67b1-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="f67b1-178">例如，如果您只想要在監看員節點上執行 IM 測試，您可以使用下列命令來設定該測試：</span><span class="sxs-lookup"><span data-stu-id="f67b1-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="f67b1-179">當您執行上述命令時，將會停用指定的監看員節點上的所有綜合交易，但 IM 除外。</span><span class="sxs-lookup"><span data-stu-id="f67b1-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="f67b1-180">查看及測試監視節點設定</span><span class="sxs-lookup"><span data-stu-id="f67b1-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="f67b1-181">如果您想要查看已指派給觀察者節點的測試，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="f67b1-182">上述命令會根據指派給節點的綜合交易，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f67b1-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="f67b1-183">若要依字母順序查看綜合交易，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="f67b1-184">Get-CsWatcherNodeConfiguration –身分識別 "atl-cs-001.litwareinc.com" |Select-Object –ExpandProperty 測試 |Sort-Object</span><span class="sxs-lookup"><span data-stu-id="f67b1-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="f67b1-185">若要確認已建立監看員節點，請在 Lync Server 管理命令介面內輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="f67b1-186">您將會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f67b1-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="f67b1-187">若要確認是否已正確設定觀察程式節點，請在 Lync Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="f67b1-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="f67b1-188">上述命令會測試您部署中的每個監看員節點，並告訴您資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="f67b1-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="f67b1-189">已安裝必要的註冊器角色。</span><span class="sxs-lookup"><span data-stu-id="f67b1-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="f67b1-190">當您執行 Set-CsWatcherNodeConfiguration 時，會為您建立必要的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="f67b1-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="f67b1-191">您的伺服器正在執行正確版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="f67b1-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="f67b1-192">您的埠已正確設定。</span><span class="sxs-lookup"><span data-stu-id="f67b1-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="f67b1-193">您指派的測試使用者具備必要的認證。</span><span class="sxs-lookup"><span data-stu-id="f67b1-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

