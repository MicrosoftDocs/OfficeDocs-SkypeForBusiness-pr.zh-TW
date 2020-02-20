---
title: 設定監看員節點測試使用者及組態設定
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
ms.openlocfilehash: 8d66eb347fbd26f2d50828924d41075680fdcc09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fe93e-102">在 Lync Server 2013 中設定監看員節點測試使用者與組態設定</span><span class="sxs-lookup"><span data-stu-id="fe93e-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe93e-103">_**上次修改主題：** 2013年-07-29_</span><span class="sxs-lookup"><span data-stu-id="fe93e-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fe93e-104">設定將作為監看員節點的電腦之後, 您必須：</span><span class="sxs-lookup"><span data-stu-id="fe93e-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="fe93e-105">建立這些監看員節點所使用的測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="fe93e-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="fe93e-106">如果您使用的交涉驗證方法，您也必須使用[Set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))指令程式來啟用這些測試監看員節點上使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fe93e-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="fe93e-107">更新監看員節點組態設定。</span><span class="sxs-lookup"><span data-stu-id="fe93e-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="fe93e-108">本章節將說明：</span><span class="sxs-lookup"><span data-stu-id="fe93e-108">This section covers:</span></span>

  - <span data-ttu-id="fe93e-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fe93e-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="fe93e-110">使用預設綜合交易設定基本監看員節點</span><span class="sxs-lookup"><span data-stu-id="fe93e-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="fe93e-111">設定擴充的測試</span><span class="sxs-lookup"><span data-stu-id="fe93e-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="fe93e-112">新增與移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="fe93e-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="fe93e-113">檢視與測試監看員節點組態</span><span class="sxs-lookup"><span data-stu-id="fe93e-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="fe93e-114">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fe93e-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="fe93e-115">測試使用者不需要來代表實際的人員，但它們必須是有效的 Active Directory 網域服務帳戶。此外，這些帳戶必須啟用 Lync Server 2013，他們必須具備有效的 SIP 位址，和他們應該啟用 Enterprise voice （以使用 Test-cspstnpeertopeercall 綜合交易）。</span><span class="sxs-lookup"><span data-stu-id="fe93e-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="fe93e-116">如果您使用 TrustedServer 驗證方法，那麼您只需要是確定這些帳戶存在，而且已設定為在這裡指定。</span><span class="sxs-lookup"><span data-stu-id="fe93e-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="fe93e-117">您應該指定您想要測試每個集區，至少有三個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="fe93e-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="fe93e-118">如果您使用的交涉驗證方法，您也必須使用**Set-cstestusercredential** cmdlet 和 Lync Server 管理命令介面來啟用這些測試帳戶來使用綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fe93e-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="fe93e-119">您可以執行類似下列的命令來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="fe93e-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="fe93e-120">（這些命令假設已經已建立的三個 Active Directory 使用者帳戶，以及這些帳戶，已啟用 Lync Server 2013。）：</span><span class="sxs-lookup"><span data-stu-id="fe93e-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="fe93e-121">請注意，您必須包含不只的 SIP 位址，但也的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="fe93e-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="fe93e-122">如果未加上密碼 Set-cstestusercredential 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="fe93e-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="fe93e-123">可以使用的網域名稱指定的使用者名稱\\使用者名稱 」 格式顯示上方，或藉由使用格式的使用者 name@domain 名稱;例如：</span><span class="sxs-lookup"><span data-stu-id="fe93e-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="fe93e-124">若要確認已建立測試使用者認證，執行這些命令在 Lync Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="fe93e-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="fe93e-125">每位使用者，應該會傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="fe93e-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="fe93e-126">使用預設綜合交易設定基本監看員節點</span><span class="sxs-lookup"><span data-stu-id="fe93e-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="fe93e-127">建立測試使用者之後您然後可以使用類似如下的命令來建立監看員節點：</span><span class="sxs-lookup"><span data-stu-id="fe93e-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="fe93e-128">此命令會建立新的監看員節點，會使用預設設定，並執行綜合交易的預設集合。</span><span class="sxs-lookup"><span data-stu-id="fe93e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="fe93e-129">新的監看員節點也會使用測試使用者 watcher1@litwareinc.com、 watcher2@litwareinc.com 及 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="fe93e-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="fe93e-130">如果監看員節點要使用 TrustedServer 驗證，三個測試帳戶可以是任何有效的使用者帳戶啟用 Active Directory 與 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="fe93e-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="fe93e-131">如果監看員節點要使用的交涉驗證方法，您也必須使用**Set-cstestusercredential** cmdlet 來啟用監看員節點這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fe93e-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="fe93e-132">設定擴充的測試</span><span class="sxs-lookup"><span data-stu-id="fe93e-132">Configuring Extended Tests</span></span>

<span data-ttu-id="fe93e-133">如果您想要啟用公用交換的電話網路 （PSTN 測試），這會驗證與公用交換的電話網路的連線，您必須設定監看員節點時進行一些額外的設定。</span><span class="sxs-lookup"><span data-stu-id="fe93e-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="fe93e-134">首先，您必須建立測試使用者與 PSTN 測試類型的關聯。</span><span class="sxs-lookup"><span data-stu-id="fe93e-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="fe93e-135">若要這麼做，請執行 Lync Server 管理命令介面從如下的命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="fe93e-136">請注意此命令的結果，必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="fe93e-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="fe93e-137">在這個範例中，是名為 $pstnTest 的變數。</span><span class="sxs-lookup"><span data-stu-id="fe93e-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="fe93e-138">此時，您可以使用**New-cswatchernodeconfiguration** cmdlet 建立測試類型 （儲存在變數 $pstnTest） 至 Lync Server 2013 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="fe93e-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="fe93e-139">例如，下列命令會建立新的監看員節點組態的集區 atl-cs-001.litwareinc.com，新增的三個測試之前建立的使用者和也新增 PSTN 測試類型：</span><span class="sxs-lookup"><span data-stu-id="fe93e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="fe93e-140">請注意，如果您不具有監看員節點電腦上安裝 Lync Server 核心檔案與 RTCLocal 資料庫，上述命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="fe93e-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="fe93e-141">若要測試多個語音原則，您需要使用**New-csextendedtest** cmdlet 建立每個原則延伸的測試。</span><span class="sxs-lookup"><span data-stu-id="fe93e-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="fe93e-142">已指派給這項測試使用者應設有所需的語音原則。</span><span class="sxs-lookup"><span data-stu-id="fe93e-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="fe93e-143">擴充的測試然後會使用類似下列的命令傳遞至**New-cswatchernodeconfiguration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fe93e-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="fe93e-144">如果 New-cswatchernodeconfiguration 會呼叫不含使用 Tests 參數，表示預設綜合交易 （與指定的擴充綜合交易） 將會啟用新的監看員節點。</span><span class="sxs-lookup"><span data-stu-id="fe93e-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="fe93e-145">這表示監看員節點，將會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="fe93e-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="fe93e-146">註冊</span><span class="sxs-lookup"><span data-stu-id="fe93e-146">Registration</span></span>

  - <span data-ttu-id="fe93e-147">IM</span><span class="sxs-lookup"><span data-stu-id="fe93e-147">IM</span></span>

  - <span data-ttu-id="fe93e-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="fe93e-148">GroupIM</span></span>

  - <span data-ttu-id="fe93e-149">P2PAV （對等音訊/視訊工作階段）</span><span class="sxs-lookup"><span data-stu-id="fe93e-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="fe93e-150">AvConference （音訊/會議）</span><span class="sxs-lookup"><span data-stu-id="fe93e-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="fe93e-151">目前狀態</span><span class="sxs-lookup"><span data-stu-id="fe93e-151">Presence</span></span>

  - <span data-ttu-id="fe93e-152">ABS （通訊錄服務）</span><span class="sxs-lookup"><span data-stu-id="fe93e-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="fe93e-153">ABWQ （通訊錄網頁服務）</span><span class="sxs-lookup"><span data-stu-id="fe93e-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="fe93e-154">PSTN （PSTN 閘道的呼叫，指定為擴充的測試。</span><span class="sxs-lookup"><span data-stu-id="fe93e-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="fe93e-155">根據預設，會停用 PSTN。</span><span class="sxs-lookup"><span data-stu-id="fe93e-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="fe93e-156">測試為啟用，在此情況下只因為命令啟用 PSTN 使用 ExtendedTests 參數。）</span><span class="sxs-lookup"><span data-stu-id="fe93e-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="fe93e-157">這也表示不會預設情況下測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="fe93e-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="fe93e-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="fe93e-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="fe93e-159">MCXP2PIM （行動裝置立即訊息）</span><span class="sxs-lookup"><span data-stu-id="fe93e-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="fe93e-160">ExumConnectivity （Exchange 整合通訊）</span><span class="sxs-lookup"><span data-stu-id="fe93e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="fe93e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="fe93e-161">JoinLauncher</span></span>

  - <span data-ttu-id="fe93e-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="fe93e-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="fe93e-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="fe93e-163">DataConference</span></span>

  - <span data-ttu-id="fe93e-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="fe93e-164">XmppIM</span></span>

  - <span data-ttu-id="fe93e-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="fe93e-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="fe93e-166">新增與移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="fe93e-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="fe93e-167">在設定監看員節點之後，您可以使用**Set-cswatchernodeconfiguration** cmdlet 來新增或移除之節點的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fe93e-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="fe93e-168">例如，若要新增的監看員節點 PersistentChatMessage 測試，使用 Add 方法與類似這樣的命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="fe93e-169">您可以加入多項測試使用逗號分隔的測試名稱。</span><span class="sxs-lookup"><span data-stu-id="fe93e-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="fe93e-170">例如：</span><span class="sxs-lookup"><span data-stu-id="fe93e-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="fe93e-171">請注意，是否一或多個這些測試 (例如，DataConference) 已啟用的監看員節點上，將會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="fe93e-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="fe93e-172">在此情況下，您會收到類似如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="fe93e-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="fe93e-173">發生此錯誤時，將會不套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="fe93e-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="fe93e-174">移除重複測試與要重新執行命令。</span><span class="sxs-lookup"><span data-stu-id="fe93e-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="fe93e-175">若要從監看員節點移除綜合交易，請使用 Remove 方法而不是 Add 方法。</span><span class="sxs-lookup"><span data-stu-id="fe93e-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="fe93e-176">例如，此命令可移除 ABWQ 測試從監看員節點：</span><span class="sxs-lookup"><span data-stu-id="fe93e-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="fe93e-177">您也可以使用 Replace 方法來取代所有目前已啟用測試，以下列一或多新測試。</span><span class="sxs-lookup"><span data-stu-id="fe93e-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="fe93e-178">例如，如果您只想要執行的 IM 測試監看員節點，您可以使用下列命令，設定：</span><span class="sxs-lookup"><span data-stu-id="fe93e-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="fe93e-179">當您執行上述命令時，將會停用指定監看員節點上的所有綜合交易除了 IM 之外。</span><span class="sxs-lookup"><span data-stu-id="fe93e-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="fe93e-180">檢視與測試監看員節點組態</span><span class="sxs-lookup"><span data-stu-id="fe93e-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="fe93e-181">如果您想要檢視已指派給監看員節點測試，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="fe93e-182">上述命令將傳回的資訊類似，根據已指派給節點的綜合交易：</span><span class="sxs-lookup"><span data-stu-id="fe93e-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="fe93e-183">若要依字母順序檢視綜合交易，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="fe93e-184">Get-cswatchernodeconfiguration – Identity"atl-cs-001.litwareinc.com"|Select-object – ExpandProperty 測試 |Sort 物件</span><span class="sxs-lookup"><span data-stu-id="fe93e-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="fe93e-185">若要確認監看員節點已建立，請輸入從 Lync Server 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="fe93e-186">您會收到類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="fe93e-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="fe93e-187">若要確認已正確設定監看員節點，請輸入從 Lync Server 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="fe93e-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="fe93e-188">上述命令會測試您的部署中的每個監看員節點，並告訴您的資訊，例如是否：</span><span class="sxs-lookup"><span data-stu-id="fe93e-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="fe93e-189">登錄器角色已安裝。</span><span class="sxs-lookup"><span data-stu-id="fe93e-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="fe93e-190">當您執行 Set-cswatchernodeconfiguration 時，會為您建立必要的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="fe93e-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="fe93e-191">您的伺服器執行正確版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="fe93e-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="fe93e-192">連接埠已正確設定。</span><span class="sxs-lookup"><span data-stu-id="fe93e-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="fe93e-193">指派的測試使用者具有必要的認證。</span><span class="sxs-lookup"><span data-stu-id="fe93e-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

