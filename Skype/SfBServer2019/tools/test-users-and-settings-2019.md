---
title: 設定觀察程式節點測試使用者和設定
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 針對商務用 Skype Server 合成事務, 設定測試使用者帳戶和觀察程式節點設定。'
ms.openlocfilehash: 0da038f90538cce62f2e811471a2ebc8ba685fb2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189760"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="a1a58-103">設定觀察程式節點測試使用者和設定</span><span class="sxs-lookup"><span data-stu-id="a1a58-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="a1a58-104">**摘要:** 針對商務用 Skype Server 合成事務, 設定測試使用者帳戶與觀察程式節點設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="a1a58-105">在設定將充當監視者節點的電腦之後, 您必須:</span><span class="sxs-lookup"><span data-stu-id="a1a58-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="a1a58-106">設定這些觀察程式節點要使用的[測試使用者帳戶](test-users-and-settings-2019.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="a1a58-107">如果您使用的是 Negotiate 驗證方法, 您也必須使用**CsTestUserCredential** Cmdlet 來啟用這些測試帳戶, 以便在 [觀察程式] 節點上使用。</span><span class="sxs-lookup"><span data-stu-id="a1a58-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="a1a58-108">更新觀察程式節點設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="a1a58-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a1a58-109">Configure Test User Accounts</span></span>
<span data-ttu-id="a1a58-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a58-110"></span></span>

<span data-ttu-id="a1a58-111">測試帳戶不需要代表實際的人員, 但必須是有效的 Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1a58-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="a1a58-112">此外, 必須針對商務用 Skype Server 啟用這些帳戶, 他們必須擁有有效的 SIP 位址, 而且應該為企業語音啟用它們 (以使用測試 CsPstnPeerToPeerCall 綜合交易)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="a1a58-113">如果您使用的是 TrustedServer 驗證方法, 您只需確定這些帳戶存在, 然後依所述加以設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="a1a58-114">您應該為您要測試的每個池指派至少三個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="a1a58-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="a1a58-115">如果您使用的是 Negotiate 驗證方法, 您也必須使用 CsTestUserCredential Cmdlet 和商務用 Skype Server 管理命令介面, 以啟用這些測試帳戶來處理綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="a1a58-116">若要執行此動作, 請執行類似下列的命令 (這些命令假設已建立三個 Active Directory 使用者帳戶, 且已針對商務用 Skype Server 啟用這些帳戶):</span><span class="sxs-lookup"><span data-stu-id="a1a58-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="a1a58-117">您不僅必須包含 SIP 位址, 還要包括使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="a1a58-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="a1a58-118">如果您不包含密碼, CsTestUserCredential Cmdlet 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="a1a58-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="a1a58-119">您可以使用上述程式碼區塊中所示的功能變數名稱格式來指定使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="a1a58-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="a1a58-120">若要確認已建立測試使用者認證, 請從商務用 Skype Server Management Shell 執行這些命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="a1a58-121">會針對每個使用者傳回類似以下內容的資訊:</span><span class="sxs-lookup"><span data-stu-id="a1a58-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="a1a58-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="a1a58-122">**UserName**</span></span>|<span data-ttu-id="a1a58-123">**口令**</span><span class="sxs-lookup"><span data-stu-id="a1a58-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a1a58-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="a1a58-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="a1a58-125">SecureString</span><span class="sxs-lookup"><span data-stu-id="a1a58-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="a1a58-126">使用預設的綜合交易設定基本的觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="a1a58-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="a1a58-127">在測試使用者建立之後, 您可以使用類似以下的命令來建立觀察程式節點:</span><span class="sxs-lookup"><span data-stu-id="a1a58-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="a1a58-128">這個命令會建立使用預設設定的新的觀察程式節點, 並執行預設的綜合交易集合。</span><span class="sxs-lookup"><span data-stu-id="a1a58-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="a1a58-129">新的 [觀察程式] 節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="a1a58-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="a1a58-130">如果 [觀察程式] 節點使用 TrustedServer 驗證, 則三個測試帳戶可以是啟用 Active Directory 及商務用 Skype Server 的任何有效使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1a58-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="a1a58-131">如果觀察程式節點使用 Negotiate 驗證方法, 也必須使用 CsTestUserCredential Cmdlet 為觀察程式節點啟用這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1a58-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="a1a58-132">若要驗證是否正確設定目標池的自動探索, 而不是以某個池為目標, 請改為直接使用這些步驟:</span><span class="sxs-lookup"><span data-stu-id="a1a58-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="a1a58-133">設定延伸測試</span><span class="sxs-lookup"><span data-stu-id="a1a58-133">Configuring Extended Tests</span></span>

<span data-ttu-id="a1a58-134">如果您想要啟用 PSTN 測試, 這會驗證與公用交換電話網絡的連線, 您需要在設定觀察程式節點時, 進行一些額外的配置。</span><span class="sxs-lookup"><span data-stu-id="a1a58-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="a1a58-135">首先, 您必須從商務用 Skype Server Management Shell 執行如下的命令, 以將測試使用者與 PSTN 測試類型建立關聯:</span><span class="sxs-lookup"><span data-stu-id="a1a58-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="a1a58-136">這個命令的結果必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="a1a58-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="a1a58-137">在這個範例中, 變數稱為 [$pstnTest]。</span><span class="sxs-lookup"><span data-stu-id="a1a58-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="a1a58-138">接著, 您可以使用**CsWatcherNodeConfiguration** Cmdlet, 將測試類型 (儲存在變數 $pstnTest 中) 與商務用 Skype 伺服器池產生關聯。</span><span class="sxs-lookup"><span data-stu-id="a1a58-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="a1a58-139">例如, 下列命令會針對 [池 atl-cs-001.litwareinc.com] 建立新的 [觀察程式] 節點設定, 並新增先前建立的三個測試使用者, 並新增 PSTN 測試類型:</span><span class="sxs-lookup"><span data-stu-id="a1a58-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="a1a58-140">如果您沒有在監視程式節點電腦上安裝商務用 Skype Server core 檔案和 RTCLocal 資料庫, 上述命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="a1a58-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="a1a58-141">若要測試多個語音原則, 您可以使用**CsExtendedTest** Cmdlet, 為每個原則建立延伸測試。</span><span class="sxs-lookup"><span data-stu-id="a1a58-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="a1a58-142">所提供的使用者應該使用所需的語音原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="a1a58-143">您可以使用逗號分隔符號將延伸測試傳到**新的 CsWatcherNodeConfiguration** Cmdlet, 例如:</span><span class="sxs-lookup"><span data-stu-id="a1a58-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="a1a58-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="a1a58-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="a1a58-145">因為不使用測試參數就會呼叫**New-CsWatcherNodeConfiguration** Cmdlet, 所以只有預設的綜合交易 (以及指定的延伸綜合交易) 會針對新的 [觀察程式] 節點啟用。</span><span class="sxs-lookup"><span data-stu-id="a1a58-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="a1a58-146">因此, 觀察程式節點會測試下列元件:</span><span class="sxs-lookup"><span data-stu-id="a1a58-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="a1a58-147">註冊</span><span class="sxs-lookup"><span data-stu-id="a1a58-147">Registration</span></span>
    
- <span data-ttu-id="a1a58-148">IM</span><span class="sxs-lookup"><span data-stu-id="a1a58-148">IM</span></span>
    
- <span data-ttu-id="a1a58-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="a1a58-149">GroupIM</span></span>
    
- <span data-ttu-id="a1a58-150">P2PAV (對等音訊/視頻會話)</span><span class="sxs-lookup"><span data-stu-id="a1a58-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="a1a58-151">AvConference (音訊/會議)</span><span class="sxs-lookup"><span data-stu-id="a1a58-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="a1a58-152">平臺</span><span class="sxs-lookup"><span data-stu-id="a1a58-152">Presence</span></span>
    
- <span data-ttu-id="a1a58-153">ABS (通訊錄服務)</span><span class="sxs-lookup"><span data-stu-id="a1a58-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="a1a58-154">ABWQ (通訊錄 web 服務)</span><span class="sxs-lookup"><span data-stu-id="a1a58-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="a1a58-155">預設不會測試下列元件:</span><span class="sxs-lookup"><span data-stu-id="a1a58-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="a1a58-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="a1a58-156">ASConference</span></span>
    
- <span data-ttu-id="a1a58-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="a1a58-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="a1a58-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="a1a58-158">DataConference</span></span>
    
- <span data-ttu-id="a1a58-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="a1a58-159">DialinConferencing</span></span>
    
- <span data-ttu-id="a1a58-160">ExumConnectivity (Exchange 整合通訊)</span><span class="sxs-lookup"><span data-stu-id="a1a58-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="a1a58-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="a1a58-161">JoinLauncher</span></span>
    
- <span data-ttu-id="a1a58-162">MCXP2PIM (傳統行動裝置立即訊息)</span><span class="sxs-lookup"><span data-stu-id="a1a58-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="a1a58-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="a1a58-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="a1a58-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="a1a58-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="a1a58-165">PSTN (PSTN 閘道通話, 指定為擴展測試)</span><span class="sxs-lookup"><span data-stu-id="a1a58-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="a1a58-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="a1a58-166">UcwaConference</span></span>
    
- <span data-ttu-id="a1a58-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="a1a58-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="a1a58-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="a1a58-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="a1a58-169">新增及移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="a1a58-170">在已設定觀察程式節點之後, 您可以使用 CsWatcherNodeConfiguration Cmdlet 來新增或移除節點中的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="a1a58-171">例如, 若要將 PersistentChatMessage 測試新增至 [觀察程式] 節點, 請使用如下所示的 Add 方法和命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="a1a58-172">您可以使用逗號分隔測試名稱來新增多個測試。</span><span class="sxs-lookup"><span data-stu-id="a1a58-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="a1a58-173">例如：</span><span class="sxs-lookup"><span data-stu-id="a1a58-173">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="a1a58-174">如果在 [觀察程式] 節點上已啟用其中一個或多個測試 (例如 DataConference), 就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="a1a58-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="a1a58-175">在這種情況下, 您會收到類似以下的錯誤訊息:</span><span class="sxs-lookup"><span data-stu-id="a1a58-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="a1a58-176">設定-CsWatcherNodeConfiguration: "urn: schema: WatcherNode: TestName" 金鑰或唯一身分識別限制有重複的鍵順序 "DataConference"。</span><span class="sxs-lookup"><span data-stu-id="a1a58-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="a1a58-177">發生此錯誤時, 將不會套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="a1a58-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="a1a58-178">必須重新執行此命令, 並移除重複的測試。</span><span class="sxs-lookup"><span data-stu-id="a1a58-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="a1a58-179">若要從觀察程式節點移除綜合交易, 請使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="a1a58-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="a1a58-180">例如, 此命令會從觀察程式節點中移除 ABWQ 測試:</span><span class="sxs-lookup"><span data-stu-id="a1a58-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="a1a58-181">您可以使用 Replace 方法, 以一或多個新的測試取代所有目前啟用的測試。</span><span class="sxs-lookup"><span data-stu-id="a1a58-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="a1a58-182">例如, 如果您只想讓觀察程式節點執行 IM 測試, 您可以使用此命令來設定:</span><span class="sxs-lookup"><span data-stu-id="a1a58-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="a1a58-183">當您執行此命令時, 除了 IM 之外, 指定的觀察程式節點上的所有綜合交易都將停用。</span><span class="sxs-lookup"><span data-stu-id="a1a58-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="a1a58-184">查看及測試觀察程式節點設定</span><span class="sxs-lookup"><span data-stu-id="a1a58-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="a1a58-185">如果您想要查看已指派給觀察程式節點的測試, 請使用類似以下的命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="a1a58-186">根據已指派給節點的綜合交易, 此命令會傳回類似此的資訊:</span><span class="sxs-lookup"><span data-stu-id="a1a58-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="a1a58-187">註冊 IM GroupIM P2PAV AvConference 目前狀態 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="a1a58-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="a1a58-188">若要依字母順序查看綜合交易, 請改為使用此命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="a1a58-189">若要確認已建立觀察程式節點, 請從商務用 Skype Server Management 命令介面輸入下列命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="a1a58-190">您會收到類似以下的資訊:</span><span class="sxs-lookup"><span data-stu-id="a1a58-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="a1a58-191">身分識別: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="a1a58-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="a1a58-192">ExtendedTests: {TestUsers = IList<System.object>;Name = PSTN 測試;Te ...}</span><span class="sxs-lookup"><span data-stu-id="a1a58-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="a1a58-193">TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To 確認已正確設定觀察程式節點, 請從商務用 Skype Server 管理命令介面輸入下列命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="a1a58-194">這個命令會在您的部署中測試每個觀察程式節點, 並確認是否已完成下列動作:</span><span class="sxs-lookup"><span data-stu-id="a1a58-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="a1a58-195">已安裝所需的註冊機構角色</span><span class="sxs-lookup"><span data-stu-id="a1a58-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="a1a58-196">已建立所需的登錄機碼 (在您執行 CsWatcherNodeConfiguration Cmdlet 時完成)</span><span class="sxs-lookup"><span data-stu-id="a1a58-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="a1a58-197">您的伺服器正在執行正確版本的商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="a1a58-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="a1a58-198">已正確設定您的埠</span><span class="sxs-lookup"><span data-stu-id="a1a58-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="a1a58-199">您指派的測試使用者具有所需的認證</span><span class="sxs-lookup"><span data-stu-id="a1a58-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="a1a58-200">管理觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="a1a58-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="a1a58-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a58-201"></span></span>

<span data-ttu-id="a1a58-202">除了修改在觀察程式節點上執行的綜合交易之外, 您也可以使用**CsWatcherNodeConfiguration** Cmdlet 來執行其他兩項重要工作: 啟用及停用 [觀察程式] 節點, 以及設定[觀察程式] 節點, 可在執行測試時使用內部網頁 Url 或外部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="a1a58-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="a1a58-203">根據預設, 觀察程式節點是設計來定期執行所有已啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="a1a58-204">不過, 有時您可能會想要暫停這些交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="a1a58-205">例如, 如果 [觀察程式] 節點暫時與網路中斷連線, 則沒有任何理由執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="a1a58-206">若沒有網路連線, 這些事務將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a1a58-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="a1a58-207">若要暫時停用 [觀察程式] 節點, 請從商務用 Skype Server Management 命令介面執行如下所示的命令:</span><span class="sxs-lookup"><span data-stu-id="a1a58-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="a1a58-208">這個命令將停用在觀察程式節點的 [atl 觀察程式] 001.litwareinc.com 上執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="a1a58-209">若要繼續執行綜合交易, 請將 Enabled 屬性設回 True ($True):</span><span class="sxs-lookup"><span data-stu-id="a1a58-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="a1a58-210">可使用 Enabled 屬性來開啟或關閉觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="a1a58-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="a1a58-211">如果您想要永久刪除 [觀察程式] 節點, 請使用**CsWatcherNodeConfiguration** Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a1a58-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="a1a58-212">該命令會從指定的電腦中移除所有的觀察程式節點設定, 這可防止電腦自動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="a1a58-213">不過, 命令不會卸載 System Center 代理程式檔案或商務用 Skype Server 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="a1a58-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="a1a58-214">根據預設, 觀察程式節點會在進行測試時使用組織的外部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="a1a58-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="a1a58-215">不過, 您也可以將觀察程式節點設定為使用組織的內部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="a1a58-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="a1a58-216">這可讓系統管理員驗證位於周邊網路內之使用者的 URL 存取權。</span><span class="sxs-lookup"><span data-stu-id="a1a58-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="a1a58-217">若要將觀察程式節點設定為使用內部 Url, 而不是外部 Url, 請將 UseInternalWebURls 屬性設為 True ($True):</span><span class="sxs-lookup"><span data-stu-id="a1a58-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="a1a58-218">如果將這個屬性重設為預設值 False ($False), 就會再次使用外部 Url:</span><span class="sxs-lookup"><span data-stu-id="a1a58-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="a1a58-219">綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="a1a58-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="a1a58-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a58-220"></span></span>

<span data-ttu-id="a1a58-221">大多數的綜合交易都可以在觀察程式節點上以同樣的方式執行。</span><span class="sxs-lookup"><span data-stu-id="a1a58-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="a1a58-222">在大多數情況下, 當綜合交易新增至觀察程式節點設定設定之後, 觀察程式節點就可以在其測試階段中開始使用該綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="a1a58-223">不過, 有一些需要特殊設定指示的綜合交易, 如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="a1a58-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="a1a58-224">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-225">如果您的系統監控程式節點電腦位於周邊網路之外, 則您可能無法執行資料會議綜合交易, 除非您首先停用 Windows Internet Explorer®網路的 Internet 瀏覽器 proxy 設定[服務] 帳戶, 請完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="a1a58-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="a1a58-226">在觀察程式節點電腦上, 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**附件**], 以滑鼠右鍵按一下**命令提示**字元, 然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="a1a58-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a1a58-227">在主控台視窗中, 輸入下列命令, 然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="a1a58-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="a1a58-228">您會在命令視窗中看到如下所示的訊息:</span><span class="sxs-lookup"><span data-stu-id="a1a58-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="a1a58-229">BITSAdmin 已過時, 且不保證可在未來版本的 Windows 中使用。</span><span class="sxs-lookup"><span data-stu-id="a1a58-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="a1a58-230">BITS 服務的管理工具現已由 BITS PowerShell Cmdlet 提供。</span><span class="sxs-lookup"><span data-stu-id="a1a58-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="a1a58-231">[帳戶 NetworkService] 設定為 [NO_PROXY] 的網際網路 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="a1a58-232">(連接 = 預設值)</span><span class="sxs-lookup"><span data-stu-id="a1a58-232">(connection = default)</span></span>
  
<span data-ttu-id="a1a58-233">此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="a1a58-234">Exchange 整合訊息綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-235">Exchange 整合通訊 (UM) 綜合交易會確認測試使用者可以連線至位於 Exchange 中的語音信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1a58-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="a1a58-236">測試使用者將需要使用語音信箱帳戶預先設定。</span><span class="sxs-lookup"><span data-stu-id="a1a58-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="a1a58-237">持續聊天綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-238">若要使用持續性聊天綜合交易, 您必須先建立一個通道, 然後給予測試使用者使用它的許可權。</span><span class="sxs-lookup"><span data-stu-id="a1a58-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="a1a58-239">您可以使用持續聊天綜合交易來設定此通道:</span><span class="sxs-lookup"><span data-stu-id="a1a58-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="a1a58-240">您必須執行此設定任務, 才能從企業內部執行:</span><span class="sxs-lookup"><span data-stu-id="a1a58-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="a1a58-241">如果從非伺服器電腦執行, 則執行 Cmdlet 的使用者必須是以角色為基礎的存取控制 (RBAC) 之 CsPersistentChatAdministrators 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="a1a58-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="a1a58-242">如果從伺服器本身執行, 執行 Cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a1a58-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="a1a58-243">PSTN 對等呼叫綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-244">Test CsPstnPeerToPeerCall 綜合交易會驗證透過公用交換電話網絡 (PSTN) 撥打及接聽電話的能力。</span><span class="sxs-lookup"><span data-stu-id="a1a58-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="a1a58-245">若要執行此綜合交易, 您必須設定:</span><span class="sxs-lookup"><span data-stu-id="a1a58-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="a1a58-246">兩個啟用 UC 的測試使用者 (來電者和接收人)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="a1a58-247">針對每個使用者帳戶直接撥打 (已有) 號碼。</span><span class="sxs-lookup"><span data-stu-id="a1a58-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="a1a58-248">[VoIP 原則] 和 [語音路由], 可讓呼叫接收器的號碼到達 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="a1a58-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="a1a58-249">可接受呼叫和媒體的 PSTN 閘道, 會根據撥打的號碼, 將呼叫路由回接收器的主區。</span><span class="sxs-lookup"><span data-stu-id="a1a58-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="a1a58-250">整合連絡人商店綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-251">[整合連絡人商店] 綜合交易記錄會驗證商務用 Skype Server 在 Exchange 中代表使用者取得連絡人的能力。</span><span class="sxs-lookup"><span data-stu-id="a1a58-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="a1a58-252">若要使用這個綜合交易, 必須符合下列條件:</span><span class="sxs-lookup"><span data-stu-id="a1a58-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="a1a58-253">必須設定 Lyss-Exchange server to server 驗證。</span><span class="sxs-lookup"><span data-stu-id="a1a58-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="a1a58-254">測試使用者必須具備有效的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="a1a58-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="a1a58-255">在符合這些條件之後, 您可以執行下列 Windows PowerShell Cmdlet, 將測試使用者的連絡人清單遷移到 Exchange:</span><span class="sxs-lookup"><span data-stu-id="a1a58-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="a1a58-256">測試使用者連絡人清單可能需要一些時間才能移植到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="a1a58-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="a1a58-257">若要監視遷移進度, 在沒有-Setup 標誌的情況下, 可以執行相同的命令列:</span><span class="sxs-lookup"><span data-stu-id="a1a58-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="a1a58-258">完成遷移之後, 此命令列將會成功。</span><span class="sxs-lookup"><span data-stu-id="a1a58-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="a1a58-259">XMPP 綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-260">[可擴展訊息與目前狀態通訊協定 (XMPP) IM 綜合交易] 需要您設定一或多個聯盟網域的 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="a1a58-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="a1a58-261">若要啟用 XMPP 綜合交易, 您必須在可路由的 XMPP 網域中提供使用者帳戶的 XmppTestReceiverMailAddress 參數。</span><span class="sxs-lookup"><span data-stu-id="a1a58-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="a1a58-262">例如：</span><span class="sxs-lookup"><span data-stu-id="a1a58-262">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="a1a58-263">在這個範例中, 商務用 Skype 伺服器規則必須存在, 才能將 litwareinc.com 的訊息路由至 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="a1a58-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="a1a58-264">XMPP 閘道和 proxy 在商務用 Skype Server 2015 中提供, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="a1a58-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a1a58-265">如需詳細資訊, 請參閱[遷移 XMPP 同盟](../migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="a1a58-266">影片互通性伺服器 (VIS) 綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="a1a58-267">影片交互操作伺服器 (VIS) 綜合交易需要您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。</span><span class="sxs-lookup"><span data-stu-id="a1a58-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="a1a58-268">若要安裝 VISSTSupportPackage, 請確保已安裝 msi 的相依性 (在 [系統需求] 底下)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="a1a58-269">執行 VISSTSupportPackage 以進行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="a1a58-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="a1a58-270">.Msi 會安裝下列路徑中的所有檔案: 「%ProgramFiles%\VIS 綜合交易支援套件」。</span><span class="sxs-lookup"><span data-stu-id="a1a58-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="a1a58-271">如需如何執行 VIS 綜合交易的詳細資訊, 請參閱[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="a1a58-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="a1a58-272">變更綜合交易的執行頻率</span><span class="sxs-lookup"><span data-stu-id="a1a58-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="a1a58-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a58-273"></span></span>

<span data-ttu-id="a1a58-274">根據預設, 綜合交易會每隔15分鐘與已設定的使用者一起執行。</span><span class="sxs-lookup"><span data-stu-id="a1a58-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="a1a58-275">在一組使用者中循序執行綜合交易, 以避免兩個綜合交易彼此衝突。</span><span class="sxs-lookup"><span data-stu-id="a1a58-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="a1a58-276">需要較長的時間間隔, 才能提供所有綜合交易完成所需的時間。</span><span class="sxs-lookup"><span data-stu-id="a1a58-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="a1a58-277">如果想要更頻繁地執行綜合交易, 則應該減少使用指定使用者組執行的綜合交易數, 以便讓測試能在所需的時間範圍內完成, 而不需要偶爾的網路延遲的緩衝區。</span><span class="sxs-lookup"><span data-stu-id="a1a58-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="a1a58-278">如果想要執行更多綜合交易, 請建立更多使用者集來執行額外的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="a1a58-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="a1a58-279">若要變更綜合交易的執行頻率, 請遵循下列步驟:</span><span class="sxs-lookup"><span data-stu-id="a1a58-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="a1a58-280">開啟 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="a1a58-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="a1a58-281">按一下 [創作節]。</span><span class="sxs-lookup"><span data-stu-id="a1a58-281">Click Authoring section.</span></span> <span data-ttu-id="a1a58-282">按一下 [規則] 區段 (在 [創作] 下)</span><span class="sxs-lookup"><span data-stu-id="a1a58-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="a1a58-283">在 [規則] 區段中, 找到名稱為「主要綜合交易處理常式效能集合規則」的規則</span><span class="sxs-lookup"><span data-stu-id="a1a58-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="a1a58-284">以滑鼠右鍵按一下規則, 然後選取 [覆寫], 選取 [覆寫規則], 然後選取 [針對類別: Pool 觀察程式的所有物件]</span><span class="sxs-lookup"><span data-stu-id="a1a58-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="a1a58-285">在 [覆寫屬性] 視窗中, 選取 [參數名稱 "Frequency], 然後將覆寫值設定為所需的值。</span><span class="sxs-lookup"><span data-stu-id="a1a58-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="a1a58-286">在同一個視窗中, 選取需要套用此覆寫的管理套件</span><span class="sxs-lookup"><span data-stu-id="a1a58-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="a1a58-287">使用豐富的記錄來進行綜合交易</span><span class="sxs-lookup"><span data-stu-id="a1a58-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="a1a58-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a1a58-288"></span></span>

<span data-ttu-id="a1a58-289">在協助找出系統問題時, 綜合交易證明非常有用。</span><span class="sxs-lookup"><span data-stu-id="a1a58-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="a1a58-290">例如, CsRegistration Cmdlet 可以提醒系統管理員使用者無法使用商務用 Skype 伺服器進行註冊。</span><span class="sxs-lookup"><span data-stu-id="a1a58-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="a1a58-291">不過, 您可能需要其他詳細資料來判斷失敗的實際原因。</span><span class="sxs-lookup"><span data-stu-id="a1a58-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="a1a58-292">基於這個原因, 綜合交易提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="a1a58-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="a1a58-293">對於綜合交易 undertakes 的每個活動, 都會有豐富的記錄, 記錄以下資訊:</span><span class="sxs-lookup"><span data-stu-id="a1a58-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="a1a58-294">活動開始的時間。</span><span class="sxs-lookup"><span data-stu-id="a1a58-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="a1a58-295">活動完成的時間。</span><span class="sxs-lookup"><span data-stu-id="a1a58-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="a1a58-296">所執行的動作 (例如, 建立、加入或離開會議; 登入商務用 Skype 伺服器; 傳送立即訊息)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="a1a58-297">當活動執行時產生的資訊、詳細、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="a1a58-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="a1a58-298">SIP 註冊訊息。</span><span class="sxs-lookup"><span data-stu-id="a1a58-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="a1a58-299">當活動執行時產生的例外記錄或診斷程式代碼。</span><span class="sxs-lookup"><span data-stu-id="a1a58-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="a1a58-300">執行活動的最終結果。</span><span class="sxs-lookup"><span data-stu-id="a1a58-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="a1a58-301">這項資訊會在每次執行綜合交易時自動產生, 但不會自動顯示或儲存至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a1a58-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="a1a58-302">如果您是手動執行綜合交易, 您可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="a1a58-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="a1a58-303">在這裡, 您可以選擇使用兩種方法的其中一種, 以 XML 或 HTML 格式在豐富記錄中儲存和/或查看錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a1a58-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="a1a58-304">若要取得疑難排解資訊, 請指定 OutLoggerVariable 參數, 後面接著您選擇的變數名稱:</span><span class="sxs-lookup"><span data-stu-id="a1a58-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="a1a58-305">: 請勿在變數名稱前面加上 $ 字元。</span><span class="sxs-lookup"><span data-stu-id="a1a58-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="a1a58-306">使用變數名稱, 例如 RegistrationTest (not $RegistrationTest)。</span><span class="sxs-lookup"><span data-stu-id="a1a58-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="a1a58-307">當您執行此命令時, 您會看到類似以下的輸出:</span><span class="sxs-lookup"><span data-stu-id="a1a58-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="a1a58-308">目標 Fqdn: atl-cs-001.litwareinc.com 結果: 失敗延遲: 00:00:00 錯誤訊息: 此電腦沒有任何指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="a1a58-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="a1a58-309">診斷: 您可以針對此失敗, 存取更詳細的資訊, 而不只是此處顯示的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a1a58-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="a1a58-310">若要以 HTML 格式存取此資訊, 請使用類似這個的命令, 將儲存在可變 RegistrationTest 中的資訊儲存為 HTML 檔案:</span><span class="sxs-lookup"><span data-stu-id="a1a58-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="a1a58-311">或者, 您也可以使用 ToXML () 方法將資料儲存至 XML 檔案:</span><span class="sxs-lookup"><span data-stu-id="a1a58-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="a1a58-312">您可以使用 Windows Internet Explorer、Microsoft Visual Studio, 或任何能夠開啟 HTML/XML 檔案的其他應用程式, 來查看這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a1a58-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="a1a58-313">從系統中心作業管理員內部執行的綜合交易, 會自動產生這些記錄檔案, 以尋找失敗。</span><span class="sxs-lookup"><span data-stu-id="a1a58-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="a1a58-314">如果執行失敗, 在商務用 Skype Server PowerShell 無法載入並執行綜合交易之前, 則不會產生這些記錄。</span><span class="sxs-lookup"><span data-stu-id="a1a58-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a1a58-315">根據預設, 商務用 Skype 伺服器會將記錄檔案儲存到未共用的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a1a58-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="a1a58-316">若要讓這些記錄易於存取, 您應該共用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="a1a58-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="a1a58-317">例如: \\atl-觀察程式-001. litwareinc. com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="a1a58-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
