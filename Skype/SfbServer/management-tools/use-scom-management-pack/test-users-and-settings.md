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
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要：為商務用 Skype 伺服器綜合交易設定測試使用者帳戶和監視者節點設定。
ms.openlocfilehash: 4069b1b51dc826beb631306e941eb40146188f42
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111599"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="fdf74-103">設定監視節點測試使用者和設定</span><span class="sxs-lookup"><span data-stu-id="fdf74-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="fdf74-104">**摘要：** 為商務用 Skype 伺服器綜合交易設定測試使用者帳戶和監視者節點設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="fdf74-105">在設定將充當監視節點的電腦之後，您必須：</span><span class="sxs-lookup"><span data-stu-id="fdf74-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="fdf74-106">設定這些觀察器節點要使用的[測試使用者帳戶](test-users-and-settings.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="fdf74-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="fdf74-107">如果您使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 來啟用這些測試帳戶，以在監看員節點上使用。</span><span class="sxs-lookup"><span data-stu-id="fdf74-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="fdf74-108">更新監視節點的設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="fdf74-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fdf74-109">Configure Test User Accounts</span></span>
<span data-ttu-id="fdf74-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="fdf74-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="fdf74-111">測試帳戶不需要表示實際人員，但必須是有效的 Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="fdf74-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="fdf74-112">此外，必須為商務用 Skype Server 啟用這些帳戶，他們必須具有有效的 SIP 位址，而且應為 Enterprise Voice (啟用這些帳戶，才能使用 Test-CsPstnPeerToPeerCall 綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="fdf74-113">如果您使用的是 TrustedServer 驗證方法，您需要做的所有工作是確定這些帳戶都存在，並加以設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="fdf74-114">您應為每個您要測試的集區至少指派兩個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="fdf74-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="fdf74-115">如果您使用 Negotiate 驗證方法，您也必須使用 Set-CsTestUserCredential Cmdlet 和商務用 Skype Server 管理命令介面，讓這些測試帳戶能夠搭配綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="fdf74-116">執行下列命令，以執行類似下列的命令 (這些命令會假設已建立兩個 Active Directory 使用者帳戶，且已啟用這些帳戶的商務用 Skype Server) ：</span><span class="sxs-lookup"><span data-stu-id="fdf74-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="fdf74-117">您不僅必須包含 SIP 位址，也包含使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="fdf74-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="fdf74-118">如果您未加入密碼，Set-CsTestUserCredential Cmdlet 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="fdf74-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="fdf74-119">您可以使用上述程式碼區塊中所示的功能變數名稱 \ 功能變數名稱格式來指定使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="fdf74-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="fdf74-120">若要確認是否已建立測試使用者認證，請從商務用 Skype Server 管理命令介面執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="fdf74-121">會針對每位使用者傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="fdf74-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="fdf74-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="fdf74-122">**UserName**</span></span>|<span data-ttu-id="fdf74-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="fdf74-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fdf74-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="fdf74-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="fdf74-125">SecureString 的安全性</span><span class="sxs-lookup"><span data-stu-id="fdf74-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="fdf74-126">使用預設的綜合交易，設定基本的監看員節點</span><span class="sxs-lookup"><span data-stu-id="fdf74-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="fdf74-127">在測試使用者建立之後，您可以使用類似下列的命令來建立監看員節點：</span><span class="sxs-lookup"><span data-stu-id="fdf74-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="fdf74-128">這個命令會建立新的監看員節點，使用預設設定，並執行預設的綜合交易集合。</span><span class="sxs-lookup"><span data-stu-id="fdf74-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="fdf74-129">新的監看員節點也會使用 test users watcher1@litwareinc.com 及 watcher2@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="fdf74-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="fdf74-130">如果觀察程式節點使用 TrustedServer 驗證，則這兩個測試帳戶可以是啟用 Active Directory 和商務用 Skype 伺服器的任何有效使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fdf74-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="fdf74-131">如果監看員節點使用 Negotiate 驗證方法，也必須使用 Set-CsTestUserCredential Cmdlet 來啟用監視節點的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fdf74-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="fdf74-132">若要驗證已正確設定目標集區的自動探索，而不是以集區為目標，請改用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fdf74-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="fdf74-133">設定擴充測試</span><span class="sxs-lookup"><span data-stu-id="fdf74-133">Configuring Extended Tests</span></span>

<span data-ttu-id="fdf74-134">如果您想要啟用 PSTN 測試，以驗證與公用交換電話網路的連線，您必須在設定監看員節點時執行一些其他設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="fdf74-135">首先，您必須從商務用 Skype Server 管理命令介面中執行類似如下的命令，以將測試使用者與 PSTN 測試類型產生關聯：</span><span class="sxs-lookup"><span data-stu-id="fdf74-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="fdf74-136">這個命令的結果必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="fdf74-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="fdf74-137">在此範例中，變數命名為 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="fdf74-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="fdf74-138">接下來，您可以使用 **New-CsWatcherNodeConfiguration** 指令程式，將儲存在變數 $pstnTest) 中的測試類型 (關聯至商務用 Skype Server 集區。</span><span class="sxs-lookup"><span data-stu-id="fdf74-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="fdf74-139">例如，下列命令會為集區 atl-cs-001.litwareinc.com 建立新的監看員節點設定，加入先前建立的兩個測試使用者，並新增 PSTN 測試類型：</span><span class="sxs-lookup"><span data-stu-id="fdf74-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="fdf74-140">如果您尚未在監看員節點電腦上安裝商務用 Skype Server 核心檔案和 RTCLocal 資料庫，上述命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="fdf74-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="fdf74-141">若要測試多種語音原則，您可以使用 **New-CsExtendedTest** Cmdlet，為每個原則建立擴充測試。</span><span class="sxs-lookup"><span data-stu-id="fdf74-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="fdf74-142">提供的使用者應以所需的語音原則加以設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="fdf74-143">擴充測試會使用逗點分隔符號傳遞至 **New-CsWatcherNodeConfiguration** Cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="fdf74-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="fdf74-144">-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="fdf74-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="fdf74-145">因為 **New-CsWatcherNodeConfiguration** 指令程式呼叫時未使用測試參數，所以新的監看員節點只會啟用預設的綜合交易 (和指定的延伸綜合交易) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="fdf74-146">因此，觀察程式節點會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="fdf74-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="fdf74-147">登錄</span><span class="sxs-lookup"><span data-stu-id="fdf74-147">Registration</span></span>
    
- <span data-ttu-id="fdf74-148">我</span><span class="sxs-lookup"><span data-stu-id="fdf74-148">IM</span></span>
    
- <span data-ttu-id="fdf74-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="fdf74-149">GroupIM</span></span>
    
- <span data-ttu-id="fdf74-150">P2PAV (對等音訊/視頻會話) </span><span class="sxs-lookup"><span data-stu-id="fdf74-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="fdf74-151">AvConference (音訊/會議) </span><span class="sxs-lookup"><span data-stu-id="fdf74-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="fdf74-152">目前狀態</span><span class="sxs-lookup"><span data-stu-id="fdf74-152">Presence</span></span>
    
- <span data-ttu-id="fdf74-153">ABS (通訊錄服務) </span><span class="sxs-lookup"><span data-stu-id="fdf74-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="fdf74-154">ABWQ (通訊錄 web 服務) </span><span class="sxs-lookup"><span data-stu-id="fdf74-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="fdf74-155">預設不會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="fdf74-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="fdf74-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="fdf74-156">ASConference</span></span>
    
- <span data-ttu-id="fdf74-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="fdf74-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="fdf74-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="fdf74-158">DataConference</span></span>
    
- <span data-ttu-id="fdf74-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="fdf74-159">DialinConferencing</span></span>
    
- <span data-ttu-id="fdf74-160">ExumConnectivity (Exchange 整合通訊) </span><span class="sxs-lookup"><span data-stu-id="fdf74-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="fdf74-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="fdf74-161">JoinLauncher</span></span>
    
- <span data-ttu-id="fdf74-162">MCXP2PIM (舊版行動裝置立即訊息) </span><span class="sxs-lookup"><span data-stu-id="fdf74-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="fdf74-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="fdf74-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="fdf74-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="fdf74-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="fdf74-165">PSTN (PSTN 閘道通話，指定成擴充測試) </span><span class="sxs-lookup"><span data-stu-id="fdf74-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="fdf74-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="fdf74-166">UcwaConference</span></span>
    
- <span data-ttu-id="fdf74-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="fdf74-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="fdf74-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="fdf74-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="fdf74-169">新增及移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="fdf74-170">在設定了監看員節點之後，您可以使用 Set-CsWatcherNodeConfiguration Cmdlet 來新增或移除節點中的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="fdf74-171">例如，若要將 PersistentChatMessage 測試新增至監看員節點，請使用 Add 方法及類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="fdf74-172">若要新增多個測試，您可以使用逗號分隔測試名稱。</span><span class="sxs-lookup"><span data-stu-id="fdf74-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="fdf74-173">例如：</span><span class="sxs-lookup"><span data-stu-id="fdf74-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="fdf74-174">例如，如果其中一或多個測試 (（例如，DataConference) 已在監看員節點上啟用），便會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="fdf74-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="fdf74-175">在此情況下，您會收到類似下列的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="fdf74-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="fdf74-176">Set-CsWatcherNodeConfiguration： ' urn： schema： WatcherNode： TestName ' key or unique identity constraint 中有重複的按鍵順序 ' DataConference '。</span><span class="sxs-lookup"><span data-stu-id="fdf74-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="fdf74-177">發生此錯誤時，將不會套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="fdf74-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="fdf74-178">已移除重複的測試，應重新執行命令。</span><span class="sxs-lookup"><span data-stu-id="fdf74-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="fdf74-179">若要移除來自觀察者節點的綜合交易，請使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="fdf74-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="fdf74-180">例如，下列命令會從監看員節點中移除 ABWQ 測試：</span><span class="sxs-lookup"><span data-stu-id="fdf74-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="fdf74-181">您可以使用 Replace 方法，將所有目前啟用的測試取代為一或多個新的測試。</span><span class="sxs-lookup"><span data-stu-id="fdf74-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="fdf74-182">例如，如果您只想要監視節點執行 IM 測試，您可以使用下列命令來設定該節點：</span><span class="sxs-lookup"><span data-stu-id="fdf74-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="fdf74-183">當您執行此命令時，會停用指定的監看員節點上的所有綜合交易，但 IM 除外。</span><span class="sxs-lookup"><span data-stu-id="fdf74-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="fdf74-184">查看及測試監視節點設定</span><span class="sxs-lookup"><span data-stu-id="fdf74-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="fdf74-185">如果您想要查看已指派給觀察者節點的測試，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="fdf74-186">根據指派給節點的綜合交易，此命令會傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="fdf74-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="fdf74-187">註冊 IM GroupIM P2PAV AvConference 顯示狀態 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="fdf74-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="fdf74-188">若要依字母順序查看綜合交易，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="fdf74-189">若要確認已建立監看員節點，請在商務用 Skype Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="fdf74-190">您會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="fdf74-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="fdf74-191">身分識別： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fdf74-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="fdf74-192">TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="fdf74-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="fdf74-193">ExtendedTests： {TestUsers = IList<System.String>;Name = PSTN 測試;Te ...}</span><span class="sxs-lookup"><span data-stu-id="fdf74-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="fdf74-194">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fdf74-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="fdf74-195">埠：5061</span><span class="sxs-lookup"><span data-stu-id="fdf74-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="fdf74-196">若要確認是否已正確設定觀察程式節點，請從商務用 Skype Server 管理命令介面輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="fdf74-197">這個命令會測試您部署中的每個監看員節點，並確認是否已完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="fdf74-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="fdf74-198">已安裝必要的註冊機構角色。</span><span class="sxs-lookup"><span data-stu-id="fdf74-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="fdf74-199">當您執行 Set-CsWatcherNodeConfiguration Cmdlet) 時， (已完成，便會建立所需的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="fdf74-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="fdf74-200">您的伺服器正在執行正確版本的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="fdf74-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="fdf74-201">您的埠已正確設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="fdf74-202">您指派的測試使用者具備必要的認證。</span><span class="sxs-lookup"><span data-stu-id="fdf74-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="fdf74-203">管理監看員節點</span><span class="sxs-lookup"><span data-stu-id="fdf74-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="fdf74-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="fdf74-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="fdf74-205">除了修改在監看員節點上執行的綜合交易，您也可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來執行兩個其他重要的工作：啟用及停用監看員節點，以及設定監視節點在執行其測試時使用內部 Web URLs 或外部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="fdf74-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="fdf74-206">根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="fdf74-207">不過，有時候您可能想要暫掛這些交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="fdf74-208">例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="fdf74-209">若沒有網路連線，那些交易將會失敗。</span><span class="sxs-lookup"><span data-stu-id="fdf74-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="fdf74-210">若要暫時停用監看員節點，請從商務用 Skype Server 管理命令介面執行類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="fdf74-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="fdf74-211">此命令會停用在監看員節點上執行綜合交易的執行。 [atl 觀察程式 001.litwareinc.com]。</span><span class="sxs-lookup"><span data-stu-id="fdf74-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="fdf74-212">若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：</span><span class="sxs-lookup"><span data-stu-id="fdf74-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="fdf74-213">Enabled 屬性可用於開啟或關閉監看員節點。</span><span class="sxs-lookup"><span data-stu-id="fdf74-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="fdf74-214">如果要永久刪除監看員節點，請使用 **Remove-CsWatcherNodeConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fdf74-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="fdf74-215">該命令會從指定的電腦移除所有的監看員節點設定設定，以防止電腦自動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="fdf74-216">不過，此命令不會卸載 System Center 代理檔或商務用 Skype Server 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="fdf74-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="fdf74-217">依預設，觀察程式節點會在執行測試時使用組織的外部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="fdf74-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="fdf74-218">不過，觀察程式節點也可以設定為使用組織的內部 Web URLs。</span><span class="sxs-lookup"><span data-stu-id="fdf74-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="fdf74-219">這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。</span><span class="sxs-lookup"><span data-stu-id="fdf74-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="fdf74-220">若要設定監視節點使用內部 URLs，而不是外部 URLs，請將 UseInternalWebURls 屬性設定為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="fdf74-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="fdf74-221">將此屬性重設為預設值 False ($False) 將會再次使用外部 URLs：</span><span class="sxs-lookup"><span data-stu-id="fdf74-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="fdf74-222">綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="fdf74-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="fdf74-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="fdf74-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="fdf74-224">大多數綜合交易可依原樣在監看員節點上執行。</span><span class="sxs-lookup"><span data-stu-id="fdf74-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="fdf74-225">在大多數情況下，當綜合交易新增至監看員節點設定設定時，在其測試階段內，監看員節點便可以開始使用該綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="fdf74-226">不過，有一些需要特殊設定指示的綜合交易，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="fdf74-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="fdf74-227">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-228">如果您的監看員節點電腦位於周邊網路之外，除非您先停用 Windows Internet Explorer®網路服務帳戶的 Internet browser proxy 設定，請完成下列步驟，否則您將無法執行資料會議綜合交易：</span><span class="sxs-lookup"><span data-stu-id="fdf74-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="fdf74-229">在監看員節點電腦上，依序按一下 [**開始**]、[**所有程式**]、[**附件**] 及 [以 **系統管理員身分執行**]。 </span><span class="sxs-lookup"><span data-stu-id="fdf74-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="fdf74-230">在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="fdf74-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="fdf74-231">您會看到下列會顯示在命令視窗中的訊息：</span><span class="sxs-lookup"><span data-stu-id="fdf74-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="fdf74-232">此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="fdf74-233">Exchange 整合通訊綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-234">Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者是否可以連線至位於 Exchange 中的語音信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="fdf74-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="fdf74-235">測試使用者必須使用語音信箱帳戶進行預先設定。</span><span class="sxs-lookup"><span data-stu-id="fdf74-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="fdf74-236">Persistent Chat 綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-237">若要使用持續性聊天綜合交易，您必須先建立通道，並提供測試使用者的使用許可權。</span><span class="sxs-lookup"><span data-stu-id="fdf74-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="fdf74-238">您可以使用 Persistent Chat 綜合交易來設定此通道：</span><span class="sxs-lookup"><span data-stu-id="fdf74-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="fdf74-239">您必須執行此設定工作，您必須從企業內部執行：</span><span class="sxs-lookup"><span data-stu-id="fdf74-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="fdf74-240">如果從非伺服器電腦執行，則執行 Cmdlet 的使用者必須是 CsPersistentChatAdministrators 角色的成員，Role-Based 存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="fdf74-241">如果從伺服器自行執行，則執行 Cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fdf74-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="fdf74-242">PSTN Peer-to-Peer 呼叫綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-243">Test-CsPstnPeerToPeerCall 綜合交易會透過公用交換電話網路 (PSTN) 驗證撥打和接聽電話的能力。</span><span class="sxs-lookup"><span data-stu-id="fdf74-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="fdf74-244">若要執行此綜合交易，您必須進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="fdf74-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="fdf74-245">兩個啟用 UC 的測試使用者 (來電者和接收器) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="fdf74-246">每個使用者帳戶的直接內部撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="fdf74-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="fdf74-247">VoIP 原則及語音路由，可讓呼叫收件者的號碼，以到達 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="fdf74-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="fdf74-248">一種 PSTN 閘道，可接受通話和媒體，根據撥打的號碼，將來電路由回復回接收器的主集區。</span><span class="sxs-lookup"><span data-stu-id="fdf74-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="fdf74-249">整合連絡人存放區綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-250">整合連絡人存放區綜合交易可驗證商務用 Skype 伺服器代表使用者從 Exchange 取得連絡人的能力。</span><span class="sxs-lookup"><span data-stu-id="fdf74-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="fdf74-251">若要使用此綜合交易，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="fdf74-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="fdf74-252">必須設定 Lyss-Exchange 伺服器到伺服器的驗證。</span><span class="sxs-lookup"><span data-stu-id="fdf74-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="fdf74-253">測試使用者必須具有有效的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="fdf74-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="fdf74-254">在符合這些條件之後，您可以執行下列 Windows PowerShell Cmdlet，將測試使用者的連絡人清單遷移至 Exchange：</span><span class="sxs-lookup"><span data-stu-id="fdf74-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="fdf74-255">測試使用者連絡人清單若要遷移至 Exchange 可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="fdf74-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="fdf74-256">若要監視遷移進度，可在沒有-Setup 標誌的情況下執行相同的命令列：</span><span class="sxs-lookup"><span data-stu-id="fdf74-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="fdf74-257">完成遷移後，此命令列將會成功。</span><span class="sxs-lookup"><span data-stu-id="fdf74-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="fdf74-258">XMPP 綜合交易</span><span class="sxs-lookup"><span data-stu-id="fdf74-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-259">可延伸的訊息和顯示狀態通訊協定 (XMPP) IM 綜合交易，需要您使用一或多個同盟網域來設定 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="fdf74-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="fdf74-260">若要啟用 XMPP 綜合交易，您必須在可路由的 XMPP 網域中提供具有使用者帳戶的 XmppTestReceiverMailAddress 參數。</span><span class="sxs-lookup"><span data-stu-id="fdf74-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="fdf74-261">例如：</span><span class="sxs-lookup"><span data-stu-id="fdf74-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="fdf74-262">在此範例中，商務用 Skype 伺服器規則必須已存在，才能將 litwareinc.com 的郵件路由傳送至 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="fdf74-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="fdf74-263">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="fdf74-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fdf74-264">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="fdf74-265"> (VIS) 綜合交易的視頻 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="fdf74-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="fdf74-266">[！注意] VIS) 綜合交易的「影片互通性 (伺服器」會要求您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="fdf74-267">若要安裝 VISSTSupportPackage.msi 請確定已安裝 msi 的 [系統需求]) 的相依性 (。</span><span class="sxs-lookup"><span data-stu-id="fdf74-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="fdf74-268">執行 VISSTSupportPackage.msi 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="fdf74-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="fdf74-269">.Msi 會安裝下列路徑中的所有檔案：「%ProgramFiles%\VIS 綜合交易支援套件」。</span><span class="sxs-lookup"><span data-stu-id="fdf74-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="fdf74-270">如需如何執行 VIS 綜合交易的詳細資訊，請參閱 [CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="fdf74-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="fdf74-271">變更綜合交易的執行頻率</span><span class="sxs-lookup"><span data-stu-id="fdf74-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="fdf74-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="fdf74-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="fdf74-273">根據預設，綜合交易將會以設定的使用者每隔15分鐘執行。</span><span class="sxs-lookup"><span data-stu-id="fdf74-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="fdf74-274">綜合交易會依序在一組使用者中執行，以避免兩個綜合交易彼此衝突。</span><span class="sxs-lookup"><span data-stu-id="fdf74-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="fdf74-275">需要較長的時間間隔，以提供所有綜合交易完成的時間。</span><span class="sxs-lookup"><span data-stu-id="fdf74-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="fdf74-276">若要更經常執行綜合交易，請減少使用一組指定使用者執行的綜合交易，這樣測試就能在所需的時間範圍內完成，使測試能夠在所需的時間範圍內完成，而不需要偶爾的網路延遲。</span><span class="sxs-lookup"><span data-stu-id="fdf74-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="fdf74-277">如果需要執行更多綜合交易，請建立更多使用者集，以執行其他綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fdf74-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="fdf74-278">若要變更綜合交易的執行頻率，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fdf74-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="fdf74-279">開啟 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="fdf74-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="fdf74-280">按一下 [製作區段]。</span><span class="sxs-lookup"><span data-stu-id="fdf74-280">Click Authoring section.</span></span> <span data-ttu-id="fdf74-281">在 [製作) ] 下，按一下 [規則] 區段 (。</span><span class="sxs-lookup"><span data-stu-id="fdf74-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="fdf74-282">在 [規則] 區段中，尋找名稱為「主要綜合交易處理常式效能收集規則」的規則。</span><span class="sxs-lookup"><span data-stu-id="fdf74-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="fdf74-283">以滑鼠右鍵按一下規則，然後選取 [覆寫]，選取 [覆寫規則]，然後選取 [針對 class：集區觀察程式的所有物件]。</span><span class="sxs-lookup"><span data-stu-id="fdf74-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="fdf74-284">在 [覆寫屬性] 視窗中，選取 [參數名稱] [Frequency]，然後將覆寫值設定為所需的值。</span><span class="sxs-lookup"><span data-stu-id="fdf74-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="fdf74-285">在同一個視窗中，選取需要套用此覆寫的管理元件。</span><span class="sxs-lookup"><span data-stu-id="fdf74-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="fdf74-286">使用綜合交易的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="fdf74-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="fdf74-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="fdf74-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="fdf74-288">綜合交易會證明在協助識別系統問題方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="fdf74-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="fdf74-289">例如，Test-CsRegistration 指令程式可能會提醒系統管理員使用者在使用商務用 Skype 伺服器註冊時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="fdf74-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="fdf74-290">不過，您可能會需要其他詳細資料，以判斷失敗的實際原因。</span><span class="sxs-lookup"><span data-stu-id="fdf74-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="fdf74-291">因此，綜合交易會提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="fdf74-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="fdf74-292">使用豐富記錄，針對綜合交易 undertakes 的每個活動，會記錄下列資訊：</span><span class="sxs-lookup"><span data-stu-id="fdf74-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="fdf74-293">活動的開始時間。</span><span class="sxs-lookup"><span data-stu-id="fdf74-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="fdf74-294">活動完成的時間。</span><span class="sxs-lookup"><span data-stu-id="fdf74-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="fdf74-295">執行的動作 (例如，建立、加入或離開會議）;登入商務用 Skype 伺服器;傳送立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="fdf74-296">活動執行時產生的資訊、詳細、警告或錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fdf74-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="fdf74-297">SIP 註冊訊息。</span><span class="sxs-lookup"><span data-stu-id="fdf74-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="fdf74-298">活動執行時所產生的例外狀況記錄或診斷碼。</span><span class="sxs-lookup"><span data-stu-id="fdf74-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="fdf74-299">執行活動的實際結果。</span><span class="sxs-lookup"><span data-stu-id="fdf74-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="fdf74-300">這項資訊會在每次執行綜合交易時自動產生，但不會自動顯示或儲存至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="fdf74-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="fdf74-301">如果您是手動執行綜合交易，您可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="fdf74-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="fdf74-302">您可以從那裡使用下列兩種方法的其中一種，以 XML 或 HTML 格式在豐富記錄中儲存及/或查看錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fdf74-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="fdf74-303">若要取得疑難排解資訊，請指定 OutLoggerVariable 參數，後面接著所選擇的變數名稱：</span><span class="sxs-lookup"><span data-stu-id="fdf74-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="fdf74-304">請不要在變數名稱的開頭加上 $ 字元。</span><span class="sxs-lookup"><span data-stu-id="fdf74-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="fdf74-305">使用變數名稱，例如 RegistrationTest (不 $RegistrationTest) 。</span><span class="sxs-lookup"><span data-stu-id="fdf74-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="fdf74-306">當您執行此命令時，會看到如下的輸出：</span><span class="sxs-lookup"><span data-stu-id="fdf74-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="fdf74-307">目標 Fqdn： atl-cs-001.litwareinc.com 結果：失敗延遲：00:00:00 錯誤訊息：此機器沒有任何已指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="fdf74-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="fdf74-308">診斷：您可以針對這種失敗，存取更詳細的資訊，而不只是這裡顯示的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fdf74-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="fdf74-309">若要以 HTML 格式存取此資訊，請使用類似下列的命令，將儲存在變數 RegistrationTest 中的資訊儲存到 HTML 檔案：</span><span class="sxs-lookup"><span data-stu-id="fdf74-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="fdf74-310">或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="fdf74-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="fdf74-311">您可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何其他能夠開啟 HTML/XML 檔案的應用程式來查看這些檔案。</span><span class="sxs-lookup"><span data-stu-id="fdf74-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="fdf74-312">在 System Center Operations Manager 內執行的綜合交易，會自動產生這些記錄檔失敗。</span><span class="sxs-lookup"><span data-stu-id="fdf74-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="fdf74-313">如果執行失敗之前商務用 Skype Server PowerShell 能夠載入並執行綜合交易，將不會產生這些記錄。</span><span class="sxs-lookup"><span data-stu-id="fdf74-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fdf74-314">依預設，商務用 Skype 伺服器會將記錄檔儲存至未共用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="fdf74-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="fdf74-315">若要讓這些記錄立即可供存取，您應該共用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="fdf74-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="fdf74-316">例如： \\ atl-觀察程式-001。 litwareinc com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="fdf74-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>