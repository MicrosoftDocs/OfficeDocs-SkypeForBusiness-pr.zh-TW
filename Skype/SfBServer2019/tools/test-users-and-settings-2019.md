---
title: 設定監視節點測試使用者和設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：為商務用 Skype 伺服器綜合交易設定測試使用者帳戶和監視者節點設定。
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812763"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="440a4-103">設定監視節點測試使用者和設定</span><span class="sxs-lookup"><span data-stu-id="440a4-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="440a4-104">**摘要：** 為商務用 Skype 伺服器綜合交易設定測試使用者帳戶和監視者節點設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="440a4-105">在設定將充當監視節點的電腦之後，您必須：</span><span class="sxs-lookup"><span data-stu-id="440a4-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="440a4-106">設定這些觀察器節點要使用的[測試使用者帳戶](test-users-and-settings-2019.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="440a4-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="440a4-107">如果您使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 來啟用這些測試帳戶，以在監看員節點上使用。</span><span class="sxs-lookup"><span data-stu-id="440a4-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="440a4-108">更新監視節點的設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="440a4-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="440a4-109">Configure Test User Accounts</span></span>
<span data-ttu-id="440a4-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="440a4-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="440a4-111">測試帳戶不需要表示實際人員，但必須是有效的 Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="440a4-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="440a4-112">此外，必須為商務用 Skype Server 啟用這些帳戶，他們必須具有有效的 SIP 位址，而且應為 Enterprise Voice (啟用這些帳戶，才能使用 Test-CsPstnPeerToPeerCall 綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="440a4-113">如果您使用的是 TrustedServer 驗證方法，您需要做的所有工作是確定這些帳戶都存在，並加以設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="440a4-114">您應為每個要測試的集區至少指派三個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="440a4-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="440a4-115">如果您使用 Negotiate 驗證方法，您也必須使用 Set-CsTestUserCredential Cmdlet 和商務用 Skype Server 管理命令介面，讓這些測試帳戶能夠搭配綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="440a4-116">執行下列命令，以執行類似下列的命令 (這些命令會假設已建立三個 Active Directory 使用者帳戶，且已為商務用 Skype Server) 啟用這些帳戶：</span><span class="sxs-lookup"><span data-stu-id="440a4-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="440a4-117">您不僅必須包含 SIP 位址，也包含使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="440a4-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="440a4-118">如果您未加入密碼，Set-CsTestUserCredential Cmdlet 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="440a4-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="440a4-119">您可以使用上述程式碼區塊中所示的功能變數名稱 \ 功能變數名稱格式來指定使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="440a4-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="440a4-120">若要確認是否已建立測試使用者認證，請從商務用 Skype Server 管理命令介面執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="440a4-121">會針對每位使用者傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="440a4-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="440a4-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="440a4-122">**UserName**</span></span>|<span data-ttu-id="440a4-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="440a4-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="440a4-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="440a4-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="440a4-125">SecureString 的安全性</span><span class="sxs-lookup"><span data-stu-id="440a4-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="440a4-126">使用預設的綜合交易，設定基本的監看員節點</span><span class="sxs-lookup"><span data-stu-id="440a4-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="440a4-127">在測試使用者建立之後，您可以使用類似下列的命令來建立監看員節點：</span><span class="sxs-lookup"><span data-stu-id="440a4-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="440a4-128">這個命令會建立新的監看員節點，使用預設設定，並執行預設的綜合交易集合。</span><span class="sxs-lookup"><span data-stu-id="440a4-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="440a4-129">新的監看員節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 及 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="440a4-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="440a4-130">如果監看員節點使用 TrustedServer 驗證，則三個測試帳戶可以是啟用 Active Directory 和商務用 Skype 伺服器的任何有效使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="440a4-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="440a4-131">如果監看員節點使用 Negotiate 驗證方法，也必須使用 Set-CsTestUserCredential Cmdlet 來啟用監視節點的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="440a4-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="440a4-132">若要驗證已正確設定目標集區的自動探索，而不是以集區為目標，請改用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="440a4-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="440a4-133">設定擴充測試</span><span class="sxs-lookup"><span data-stu-id="440a4-133">Configuring Extended Tests</span></span>

<span data-ttu-id="440a4-134">如果您想要啟用 PSTN 測試，以驗證與公用交換電話網路的連線，您必須在設定監看員節點時執行一些其他設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="440a4-135">首先，您必須從商務用 Skype Server 管理命令介面中執行類似如下的命令，以將測試使用者與 PSTN 測試類型產生關聯：</span><span class="sxs-lookup"><span data-stu-id="440a4-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="440a4-136">這個命令的結果必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="440a4-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="440a4-137">在此範例中，變數命名為 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="440a4-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="440a4-138">接下來，您可以使用 **New-CsWatcherNodeConfiguration** 指令程式，將儲存在變數 $pstnTest) 中的測試類型 (關聯至商務用 Skype Server 集區。</span><span class="sxs-lookup"><span data-stu-id="440a4-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="440a4-139">例如，下列命令會為集區 atl-cs-001.litwareinc.com 建立新的監看員節點設定，加入先前建立的三個測試使用者，並新增 PSTN 測試類型：</span><span class="sxs-lookup"><span data-stu-id="440a4-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="440a4-140">如果您尚未在監看員節點電腦上安裝商務用 Skype Server 核心檔案和 RTCLocal 資料庫，上述命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="440a4-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="440a4-141">若要測試多種語音原則，您可以使用 **New-CsExtendedTest** Cmdlet，為每個原則建立擴充測試。</span><span class="sxs-lookup"><span data-stu-id="440a4-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="440a4-142">提供的使用者應以所需的語音原則加以設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="440a4-143">擴充測試會使用逗點分隔符號傳遞至 **New-CsWatcherNodeConfiguration** Cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="440a4-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="440a4-144">-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="440a4-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="440a4-145">因為 **New-CsWatcherNodeConfiguration** 指令程式呼叫時未使用測試參數，所以新的監看員節點只會啟用預設的綜合交易 (和指定的延伸綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="440a4-146">因此，觀察程式節點會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="440a4-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="440a4-147">登錄</span><span class="sxs-lookup"><span data-stu-id="440a4-147">Registration</span></span>
    
- <span data-ttu-id="440a4-148">我</span><span class="sxs-lookup"><span data-stu-id="440a4-148">IM</span></span>
    
- <span data-ttu-id="440a4-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="440a4-149">GroupIM</span></span>
    
- <span data-ttu-id="440a4-150">P2PAV (對等音訊/視頻會話) </span><span class="sxs-lookup"><span data-stu-id="440a4-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="440a4-151">AvConference (音訊/會議) </span><span class="sxs-lookup"><span data-stu-id="440a4-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="440a4-152">目前狀態</span><span class="sxs-lookup"><span data-stu-id="440a4-152">Presence</span></span>
    
- <span data-ttu-id="440a4-153">ABS (通訊錄服務) </span><span class="sxs-lookup"><span data-stu-id="440a4-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="440a4-154">ABWQ (通訊錄 web 服務) </span><span class="sxs-lookup"><span data-stu-id="440a4-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="440a4-155">預設不會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="440a4-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="440a4-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="440a4-156">ASConference</span></span>
    
- <span data-ttu-id="440a4-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="440a4-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="440a4-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="440a4-158">DataConference</span></span>
    
- <span data-ttu-id="440a4-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="440a4-159">DialinConferencing</span></span>
    
- <span data-ttu-id="440a4-160">ExumConnectivity (Exchange 整合通訊) </span><span class="sxs-lookup"><span data-stu-id="440a4-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="440a4-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="440a4-161">JoinLauncher</span></span>
    
- <span data-ttu-id="440a4-162">MCXP2PIM (舊版行動裝置立即訊息) </span><span class="sxs-lookup"><span data-stu-id="440a4-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="440a4-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="440a4-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="440a4-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="440a4-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="440a4-165">PSTN (PSTN 閘道通話，指定成擴充測試) </span><span class="sxs-lookup"><span data-stu-id="440a4-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="440a4-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="440a4-166">UcwaConference</span></span>
    
- <span data-ttu-id="440a4-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="440a4-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="440a4-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="440a4-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="440a4-169">新增及移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="440a4-170">在設定了監看員節點之後，您可以使用 Set-CsWatcherNodeConfiguration Cmdlet 來新增或移除節點中的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="440a4-171">例如，若要將 PersistentChatMessage 測試新增至監看員節點，請使用 Add 方法及類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="440a4-172">若要新增多個測試，您可以使用逗號分隔測試名稱。</span><span class="sxs-lookup"><span data-stu-id="440a4-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="440a4-173">例如：</span><span class="sxs-lookup"><span data-stu-id="440a4-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="440a4-174">例如，如果其中一或多個測試 (（例如，DataConference) 已在監看員節點上啟用），便會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="440a4-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="440a4-175">在此情況下，您會收到類似下列的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="440a4-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="440a4-176">Set-CsWatcherNodeConfiguration： ' urn： schema： WatcherNode： TestName ' key or unique identity constraint 中有重複的按鍵順序 ' DataConference '。</span><span class="sxs-lookup"><span data-stu-id="440a4-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="440a4-177">發生此錯誤時，將不會套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="440a4-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="440a4-178">已移除重複的測試，應重新執行命令。</span><span class="sxs-lookup"><span data-stu-id="440a4-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="440a4-179">若要移除來自觀察者節點的綜合交易，請使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="440a4-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="440a4-180">例如，下列命令會從監看員節點中移除 ABWQ 測試：</span><span class="sxs-lookup"><span data-stu-id="440a4-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="440a4-181">您可以使用 Replace 方法，將所有目前啟用的測試取代為一或多個新的測試。</span><span class="sxs-lookup"><span data-stu-id="440a4-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="440a4-182">例如，如果您只想要監視節點執行 IM 測試，您可以使用下列命令來設定該節點：</span><span class="sxs-lookup"><span data-stu-id="440a4-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="440a4-183">當您執行此命令時，會停用指定的監看員節點上的所有綜合交易，但 IM 除外。</span><span class="sxs-lookup"><span data-stu-id="440a4-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="440a4-184">查看及測試監視節點設定</span><span class="sxs-lookup"><span data-stu-id="440a4-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="440a4-185">如果您想要查看已指派給觀察者節點的測試，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="440a4-186">根據指派給節點的綜合交易，此命令會傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="440a4-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="440a4-187">註冊 IM GroupIM P2PAV AvConference 顯示狀態 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="440a4-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="440a4-188">若要依字母順序查看綜合交易，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="440a4-189">若要確認已建立監看員節點，請在商務用 Skype Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="440a4-190">您會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="440a4-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="440a4-191">Identity： atl-cs-001.litwareinc.com TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="440a4-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="440a4-192">ExtendedTests： {TestUsers = IList<System.String>;Name = PSTN 測試;Te ...}</span><span class="sxs-lookup"><span data-stu-id="440a4-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="440a4-193">TargetFqdn： atl-cs-001.litwareinc.com 埠：5061To 確認已正確設定監視程式節點，請從商務用 Skype Server 管理命令介面輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="440a4-194">這個命令會測試您部署中的每個監看員節點，並確認是否已完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="440a4-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="440a4-195">已安裝必要的註冊機構角色</span><span class="sxs-lookup"><span data-stu-id="440a4-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="440a4-196">當您執行 Set-CsWatcherNodeConfiguration Cmdlet 時， (已完成，便會建立必要的登錄機碼) </span><span class="sxs-lookup"><span data-stu-id="440a4-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="440a4-197">您的伺服器正在執行正確版本的商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="440a4-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="440a4-198">您的埠已正確設定</span><span class="sxs-lookup"><span data-stu-id="440a4-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="440a4-199">您指派的測試使用者具備必要的認證</span><span class="sxs-lookup"><span data-stu-id="440a4-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="440a4-200">管理監看員節點</span><span class="sxs-lookup"><span data-stu-id="440a4-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="440a4-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="440a4-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="440a4-202">除了修改在監看員節點上執行的綜合交易，您也可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來執行兩個其他重要的工作：啟用及停用監看員節點，以及設定監視節點在執行其測試時使用內部 Web URLs 或外部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="440a4-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="440a4-203">根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="440a4-204">不過，有時候您可能想要暫掛這些交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="440a4-205">例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="440a4-206">若沒有網路連線，那些交易將會失敗。</span><span class="sxs-lookup"><span data-stu-id="440a4-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="440a4-207">若要暫時停用監看員節點，請從商務用 Skype Server 管理命令介面執行類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="440a4-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="440a4-208">此命令會停用在監看員節點上執行綜合交易的執行。 [atl 觀察程式 001.litwareinc.com]。</span><span class="sxs-lookup"><span data-stu-id="440a4-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="440a4-209">若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：</span><span class="sxs-lookup"><span data-stu-id="440a4-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="440a4-210">Enabled 屬性可用於開啟或關閉監看員節點。</span><span class="sxs-lookup"><span data-stu-id="440a4-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="440a4-211">如果要永久刪除監看員節點，請使用 **Remove-CsWatcherNodeConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="440a4-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="440a4-212">該命令會從指定的電腦移除所有的監看員節點設定設定，以防止電腦自動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="440a4-213">不過，此命令不會卸載 System Center 代理檔或商務用 Skype Server 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="440a4-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="440a4-214">依預設，觀察程式節點會在執行測試時使用組織的外部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="440a4-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="440a4-215">不過，觀察程式節點也可以設定為使用組織的內部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="440a4-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="440a4-216">這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。</span><span class="sxs-lookup"><span data-stu-id="440a4-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="440a4-217">若要設定監視節點使用內部 URLs，而不是外部 URLs，請將 UseInternalWebURls 屬性設定為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="440a4-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="440a4-218">將此屬性重設為預設值 False ($False) 將會再次使用外部 URLs：</span><span class="sxs-lookup"><span data-stu-id="440a4-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="440a4-219">綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="440a4-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="440a4-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="440a4-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="440a4-221">大多數綜合交易可依原樣在監看員節點上執行。</span><span class="sxs-lookup"><span data-stu-id="440a4-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="440a4-222">在大多數情況下，當綜合交易新增至監看員節點設定設定時，在其測試階段內，監看員節點便可以開始使用該綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="440a4-223">不過，有一些需要特殊設定指示的綜合交易，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="440a4-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="440a4-224">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="440a4-225">如果您的監看員節點電腦位於周邊網路之外，除非您先停用 Windows Internet Explorer®網路服務帳戶的 Internet browser proxy 設定，請完成下列步驟，否則您將無法執行資料會議綜合交易：</span><span class="sxs-lookup"><span data-stu-id="440a4-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="440a4-226">在監看員節點電腦上，依序按一下 [**開始**]、[**所有程式**]、[**附件**] 及 [以 **系統管理員身分執行**]。 </span><span class="sxs-lookup"><span data-stu-id="440a4-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="440a4-227">在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="440a4-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="440a4-228">您會看到下列會顯示在命令視窗中的訊息：</span><span class="sxs-lookup"><span data-stu-id="440a4-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="440a4-229">BITSAdmin 已被取代，而且不保證可在未來版本的 Windows 中使用。</span><span class="sxs-lookup"><span data-stu-id="440a4-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="440a4-230">BITS 服務的管理工具現在是由 BITS PowerShell Cmdlet 所提供。</span><span class="sxs-lookup"><span data-stu-id="440a4-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="440a4-231">NetworkService 設定為 NO_PROXY 的帳戶的網際網路 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="440a4-232"> (connection = default) </span><span class="sxs-lookup"><span data-stu-id="440a4-232">(connection = default)</span></span>
  
<span data-ttu-id="440a4-233">此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="440a4-234">Exchange 整合通訊綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="440a4-235">Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者是否可以連線至位於 Exchange 中的語音信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="440a4-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="440a4-236">測試使用者必須使用語音信箱帳戶進行預先設定。</span><span class="sxs-lookup"><span data-stu-id="440a4-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="440a4-237">Persistent Chat 綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="440a4-238">若要使用持續性聊天綜合交易，您必須先建立通道，並提供測試使用者的使用許可權。</span><span class="sxs-lookup"><span data-stu-id="440a4-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="440a4-239">您可以使用 Persistent Chat 綜合交易來設定此通道：</span><span class="sxs-lookup"><span data-stu-id="440a4-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="440a4-240">您必須執行此設定工作，您必須從企業內部執行：</span><span class="sxs-lookup"><span data-stu-id="440a4-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="440a4-241">如果從非伺服器電腦執行，則執行 Cmdlet 的使用者必須是 CsPersistentChatAdministrators 角色的成員，Role-Based 存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="440a4-242">如果從伺服器自行執行，則執行 Cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="440a4-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="440a4-243">PSTN Peer-to-Peer 呼叫綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="440a4-244">Test-CsPstnPeerToPeerCall 綜合交易會透過公用交換電話網路 (PSTN) 驗證撥打和接聽電話的能力。</span><span class="sxs-lookup"><span data-stu-id="440a4-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="440a4-245">若要執行此綜合交易，您必須進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="440a4-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="440a4-246">兩個啟用 UC 的測試使用者 (來電者和接收器) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="440a4-247">每個使用者帳戶的直接內部撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="440a4-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="440a4-248">VoIP 原則及語音路由，可讓呼叫收件者的號碼，以到達 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="440a4-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="440a4-249">一種 PSTN 閘道，可接受通話和媒體，根據撥打的號碼，將來電路由回復回接收器的主集區。</span><span class="sxs-lookup"><span data-stu-id="440a4-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="440a4-250">整合連絡人存放區綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="440a4-251">整合連絡人存放區綜合交易可驗證商務用 Skype 伺服器代表使用者從 Exchange 取得連絡人的能力。</span><span class="sxs-lookup"><span data-stu-id="440a4-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="440a4-252">若要使用此綜合交易，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="440a4-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="440a4-253">必須設定 Lyss-Exchange 伺服器到伺服器的驗證。</span><span class="sxs-lookup"><span data-stu-id="440a4-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="440a4-254">測試使用者必須具有有效的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="440a4-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="440a4-255">在符合這些條件之後，您可以執行下列 Windows PowerShell Cmdlet，將測試使用者的連絡人清單遷移至 Exchange：</span><span class="sxs-lookup"><span data-stu-id="440a4-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="440a4-256">測試使用者連絡人清單若要遷移至 Exchange 可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="440a4-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="440a4-257">若要監視遷移進度，可在沒有-Setup 標誌的情況下執行相同的命令列：</span><span class="sxs-lookup"><span data-stu-id="440a4-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="440a4-258">完成遷移後，此命令列將會成功。</span><span class="sxs-lookup"><span data-stu-id="440a4-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="440a4-259">XMPP 綜合交易</span><span class="sxs-lookup"><span data-stu-id="440a4-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="440a4-260">可延伸的訊息和顯示狀態通訊協定 (XMPP) IM 綜合交易，需要您使用一或多個同盟網域來設定 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="440a4-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="440a4-261">若要啟用 XMPP 綜合交易，您必須在可路由的 XMPP 網域中提供具有使用者帳戶的 XmppTestReceiverMailAddress 參數。</span><span class="sxs-lookup"><span data-stu-id="440a4-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="440a4-262">例如：</span><span class="sxs-lookup"><span data-stu-id="440a4-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="440a4-263">在此範例中，商務用 Skype 伺服器規則必須已存在，才能將 litwareinc.com 的郵件路由傳送至 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="440a4-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="440a4-264">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="440a4-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="440a4-265">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="440a4-266"> (VIS) 綜合交易的視頻 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="440a4-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="440a4-267">[！注意] VIS) 綜合交易的「影片互通性 (伺服器」會要求您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="440a4-268">若要安裝 VISSTSupportPackage.msi 請確定已安裝 msi 的 [系統需求]) 的相依性 (。</span><span class="sxs-lookup"><span data-stu-id="440a4-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="440a4-269">執行 VISSTSupportPackage.msi 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="440a4-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="440a4-270">.Msi 會安裝下列路徑中的所有檔案：「%ProgramFiles%\VIS 綜合交易支援套件」。</span><span class="sxs-lookup"><span data-stu-id="440a4-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="440a4-271">如需如何執行 VIS 綜合交易的詳細資訊，請參閱 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="440a4-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="440a4-272">變更綜合交易的執行頻率</span><span class="sxs-lookup"><span data-stu-id="440a4-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="440a4-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="440a4-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="440a4-274">根據預設，綜合交易將會以設定的使用者每隔15分鐘執行。</span><span class="sxs-lookup"><span data-stu-id="440a4-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="440a4-275">綜合交易會依序在一組使用者中執行，以避免兩個綜合交易彼此衝突。</span><span class="sxs-lookup"><span data-stu-id="440a4-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="440a4-276">需要較長的時間間隔，以提供所有綜合交易完成的時間。</span><span class="sxs-lookup"><span data-stu-id="440a4-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="440a4-277">若要更經常執行綜合交易，請減少使用一組指定使用者執行的綜合交易，這樣測試就能在所需的時間範圍內完成，使測試能夠在所需的時間範圍內完成，而不需要偶爾的網路延遲。</span><span class="sxs-lookup"><span data-stu-id="440a4-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="440a4-278">如果需要執行更多綜合交易，請建立更多使用者集，以執行其他綜合交易。</span><span class="sxs-lookup"><span data-stu-id="440a4-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="440a4-279">若要變更綜合交易的執行頻率，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="440a4-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="440a4-280">開啟 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="440a4-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="440a4-281">按一下 [製作區段]。</span><span class="sxs-lookup"><span data-stu-id="440a4-281">Click Authoring section.</span></span> <span data-ttu-id="440a4-282">在 [製作) 中按一下 [規則] 區段 (</span><span class="sxs-lookup"><span data-stu-id="440a4-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="440a4-283">在 [規則] 區段中，尋找名稱為「主要綜合交易處理常式效能收集規則」的規則</span><span class="sxs-lookup"><span data-stu-id="440a4-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="440a4-284">以滑鼠右鍵按一下該規則，然後選取 [覆寫]，選取 [覆寫規則]，然後選取 [適用于 class：集區觀察器的所有物件]</span><span class="sxs-lookup"><span data-stu-id="440a4-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="440a4-285">在 [覆寫屬性] 視窗中，選取 [參數名稱] [Frequency]，然後將覆寫值設定為所需的值。</span><span class="sxs-lookup"><span data-stu-id="440a4-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="440a4-286">在同一個視窗中，選取需要套用此覆寫的管理套件</span><span class="sxs-lookup"><span data-stu-id="440a4-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="440a4-287">使用綜合交易的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="440a4-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="440a4-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="440a4-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="440a4-289">綜合交易會證明在協助識別系統問題方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="440a4-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="440a4-290">例如，Test-CsRegistration 指令程式可能會提醒系統管理員使用者在使用商務用 Skype 伺服器註冊時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="440a4-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="440a4-291">不過，您可能會需要其他詳細資料，以判斷失敗的實際原因。</span><span class="sxs-lookup"><span data-stu-id="440a4-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="440a4-292">因此，綜合交易會提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="440a4-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="440a4-293">使用豐富記錄，針對綜合交易 undertakes 的每個活動，會記錄下列資訊：</span><span class="sxs-lookup"><span data-stu-id="440a4-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="440a4-294">活動的開始時間。</span><span class="sxs-lookup"><span data-stu-id="440a4-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="440a4-295">活動完成的時間。</span><span class="sxs-lookup"><span data-stu-id="440a4-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="440a4-296">執行的動作 (例如，建立、加入或離開會議）;登入商務用 Skype 伺服器;傳送立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="440a4-297">活動執行時所產生的資訊、詳細資料、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="440a4-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="440a4-298">SIP 註冊訊息。</span><span class="sxs-lookup"><span data-stu-id="440a4-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="440a4-299">活動執行時所產生的例外狀況記錄或診斷碼。</span><span class="sxs-lookup"><span data-stu-id="440a4-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="440a4-300">執行活動的實際結果。</span><span class="sxs-lookup"><span data-stu-id="440a4-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="440a4-301">這項資訊會在每次執行綜合交易時自動產生，但不會自動顯示或儲存至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="440a4-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="440a4-302">如果您是手動執行綜合交易，您可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="440a4-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="440a4-303">您可以從那裡使用下列兩種方法的其中一種，以 XML 或 HTML 格式在豐富記錄中儲存及/或查看錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="440a4-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="440a4-304">若要取得疑難排解資訊，請指定 OutLoggerVariable 參數，後面接著所選擇的變數名稱：</span><span class="sxs-lookup"><span data-stu-id="440a4-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="440a4-305">：請勿在變數名稱前面加上 $ 字元。</span><span class="sxs-lookup"><span data-stu-id="440a4-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="440a4-306">使用變數名稱，例如 RegistrationTest (不 $RegistrationTest) 。</span><span class="sxs-lookup"><span data-stu-id="440a4-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="440a4-307">當您執行此命令時，會看到如下的輸出：</span><span class="sxs-lookup"><span data-stu-id="440a4-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="440a4-308">目標 Fqdn： atl-cs-001.litwareinc.com 結果：失敗延遲：00:00:00 錯誤訊息：此機器沒有任何已指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="440a4-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="440a4-309">診斷：您可以針對這種失敗，存取更詳細的資訊，而不只是這裡顯示的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="440a4-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="440a4-310">若要以 HTML 格式存取此資訊，請使用類似下列的命令，將儲存在變數 RegistrationTest 中的資訊儲存到 HTML 檔案：</span><span class="sxs-lookup"><span data-stu-id="440a4-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="440a4-311">或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="440a4-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="440a4-312">您可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何其他能夠開啟 HTML/XML 檔案的應用程式來查看這些檔案。</span><span class="sxs-lookup"><span data-stu-id="440a4-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="440a4-313">在 System Center Operations Manager 內執行的綜合交易，會自動產生這些記錄檔失敗。</span><span class="sxs-lookup"><span data-stu-id="440a4-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="440a4-314">如果執行失敗之前商務用 Skype Server PowerShell 能夠載入並執行綜合交易，將不會產生這些記錄。</span><span class="sxs-lookup"><span data-stu-id="440a4-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="440a4-315">依預設，商務用 Skype 伺服器會將記錄檔儲存至未共用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="440a4-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="440a4-316">若要讓這些記錄立即可供存取，您應該共用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="440a4-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="440a4-317">例如： \\ atl-觀察程式-001。 litwareinc com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="440a4-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
