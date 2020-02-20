---
title: 設定監看員節點測試使用者及設定
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 設定測試使用者帳戶與 skype for Business Server 綜合交易的監看員節點設定。
ms.openlocfilehash: bfbad6fbeb68100adaaee781c135531d226f43bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150494"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="68c58-103">設定監看員節點測試使用者及設定</span><span class="sxs-lookup"><span data-stu-id="68c58-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="68c58-104">**摘要：** 設定測試使用者帳戶與 skype for Business Server 綜合交易的監看員節點設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="68c58-105">設定將作為監看員節點的電腦之後, 您必須：</span><span class="sxs-lookup"><span data-stu-id="68c58-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="68c58-106">若要使用這些監看員節點[設定的測試使用者帳戶](test-users-and-settings-2019.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="68c58-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="68c58-107">如果您使用的交涉驗證方法，您也必須使用**Set-cstestusercredential**指令程式來啟用這些測試監看員節點上使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="68c58-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="68c58-108">更新監看員節點組態設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="68c58-109">設定測試使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="68c58-109">Configure Test User Accounts</span></span>
<span data-ttu-id="68c58-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="68c58-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="68c58-111">測試帳戶不需要來代表實際的人員，但它們必須是有效的 Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="68c58-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="68c58-112">此外，這些帳戶必須能夠 skype for Business Server，他們必須具備有效的 SIP 位址，和他們應該啟用 Enterprise voice （以使用 Test-cspstnpeertopeercall 綜合交易）。</span><span class="sxs-lookup"><span data-stu-id="68c58-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="68c58-113">如果您使用 TrustedServer 驗證方法，您只需要是確定這些帳戶存在，並將其如所述設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="68c58-114">您應該指定您想要測試每個集區，至少有三個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="68c58-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="68c58-115">如果您使用的交涉驗證方法，您也必須使用 Set-cstestusercredential cmdlet 與 Skype for Business Server 管理命令介面來啟用這些測試帳戶來使用綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="68c58-116">執行此動作執行類似 （這些命令會假設已建立的三個 Active Directory 使用者帳戶，而且這些帳戶，已啟用 skype 商務伺服器） 的下列命令：</span><span class="sxs-lookup"><span data-stu-id="68c58-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="68c58-117">您必須包含不只 SIP 位址] 中，但也的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="68c58-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="68c58-118">如果您未包含的密碼，Set-cstestusercredential cmdlet 會提示您輸入該資訊。</span><span class="sxs-lookup"><span data-stu-id="68c58-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="68c58-119">可以使用前述的程式碼區塊中顯示 「 網域名稱 \ 使用者名稱 」 格式來指定的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="68c58-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="68c58-120">若要確認已建立測試使用者認證，從 Skype for Business Server 管理命令介面執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="68c58-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="68c58-121">會傳回每位使用者的資訊類似這樣：</span><span class="sxs-lookup"><span data-stu-id="68c58-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="68c58-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="68c58-122">**UserName**</span></span>|<span data-ttu-id="68c58-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="68c58-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68c58-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="68c58-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="68c58-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="68c58-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="68c58-126">使用預設綜合交易來設定基本監看員節點</span><span class="sxs-lookup"><span data-stu-id="68c58-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="68c58-127">建立測試使用者之後，您可以使用類似如下的命令來建立監看員節點：</span><span class="sxs-lookup"><span data-stu-id="68c58-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="68c58-128">此命令會建立新的監看員節點，會使用預設設定，並執行綜合交易的預設集合。</span><span class="sxs-lookup"><span data-stu-id="68c58-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="68c58-129">新的監看員節點也會使用測試使用者 watcher1@litwareinc.com、 watcher2@litwareinc.com 及 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="68c58-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="68c58-130">如果監看員節點使用 TrustedServer 驗證，三個測試帳戶可以是任何有效的使用者帳戶啟用 Active Directory 與 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="68c58-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="68c58-131">如果監看員節點使用交涉驗證方法，這些使用者帳戶必須也啟用監看員節點使用 Set-cstestusercredential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="68c58-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="68c58-132">若要驗證目標的自動探索登入的集區已正確設定，而不是直接目標集區改為使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="68c58-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="68c58-133">設定擴充的測試</span><span class="sxs-lookup"><span data-stu-id="68c58-133">Configuring Extended Tests</span></span>

<span data-ttu-id="68c58-134">如果您想要啟用 PSTN 測試、 驗證與公用交換的電話網路的連線，您需要設定監看員節點時進行一些額外的設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="68c58-135">首先，您必須建立與 PSTN 測試類型的測試使用者，藉由執行命令類似從 Skype for Business Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="68c58-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="68c58-136">此命令的結果必須儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="68c58-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="68c58-137">在這個範例中，變數是名為 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="68c58-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="68c58-138">接下來，您可以使用**New-cswatchernodeconfiguration** cmdlet 建立測試類型 （儲存在變數 $pstnTest） 到 Skype for Business Server 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="68c58-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="68c58-139">例如，下列命令會建立新的監看員節點組態的集區 atl-cs-001.litwareinc.com，新增三個先前，建立測試使用者，並新增 PSTN 測試類型：</span><span class="sxs-lookup"><span data-stu-id="68c58-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="68c58-140">如果您尚未安裝 Skype for Business Server 核心檔案與 RTCLocal 資料庫監看員節點電腦上，上述命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="68c58-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="68c58-141">若要測試多個語音原則，您可以使用**New-csextendedtest** cmdlet 來建立每個原則延伸的測試。</span><span class="sxs-lookup"><span data-stu-id="68c58-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="68c58-142">提供使用者應設有所需的語音原則。</span><span class="sxs-lookup"><span data-stu-id="68c58-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="68c58-143">擴充的測試會傳遞至**New-cswatchernodeconfiguration** cmdlet，利用逗號分隔，例如：</span><span class="sxs-lookup"><span data-stu-id="68c58-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="68c58-144">-ExtendedTests @{新增 = $pstnTest1、 $pstnTest2、 $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="68c58-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="68c58-145">因為不使用 Tests 參數呼叫**New-cswatchernodeconfiguration**指令程式，針對新的監看員節點會啟用預設綜合交易 （和指定的擴充綜合交易）。</span><span class="sxs-lookup"><span data-stu-id="68c58-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="68c58-146">因此，監看員節點會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="68c58-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="68c58-147">註冊</span><span class="sxs-lookup"><span data-stu-id="68c58-147">Registration</span></span>
    
- <span data-ttu-id="68c58-148">IM</span><span class="sxs-lookup"><span data-stu-id="68c58-148">IM</span></span>
    
- <span data-ttu-id="68c58-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="68c58-149">GroupIM</span></span>
    
- <span data-ttu-id="68c58-150">P2PAV （對等音訊/視訊工作階段）</span><span class="sxs-lookup"><span data-stu-id="68c58-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="68c58-151">AvConference （音訊/會議）</span><span class="sxs-lookup"><span data-stu-id="68c58-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="68c58-152">目前狀態</span><span class="sxs-lookup"><span data-stu-id="68c58-152">Presence</span></span>
    
- <span data-ttu-id="68c58-153">ABS （通訊錄服務）</span><span class="sxs-lookup"><span data-stu-id="68c58-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="68c58-154">ABWQ （通訊錄網頁服務）</span><span class="sxs-lookup"><span data-stu-id="68c58-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="68c58-155">根據預設，也不會測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="68c58-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="68c58-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="68c58-156">ASConference</span></span>
    
- <span data-ttu-id="68c58-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="68c58-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="68c58-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="68c58-158">DataConference</span></span>
    
- <span data-ttu-id="68c58-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="68c58-159">DialinConferencing</span></span>
    
- <span data-ttu-id="68c58-160">ExumConnectivity （Exchange 整合通訊）</span><span class="sxs-lookup"><span data-stu-id="68c58-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="68c58-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="68c58-161">JoinLauncher</span></span>
    
- <span data-ttu-id="68c58-162">MCXP2PIM （舊版的行動裝置立即訊息）</span><span class="sxs-lookup"><span data-stu-id="68c58-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="68c58-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="68c58-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="68c58-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="68c58-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="68c58-165">PSTN （PSTN 閘道的呼叫，指定為延伸測試）</span><span class="sxs-lookup"><span data-stu-id="68c58-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="68c58-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="68c58-166">UcwaConference</span></span>
    
- <span data-ttu-id="68c58-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="68c58-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="68c58-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="68c58-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="68c58-169">新增與移除綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="68c58-170">在設定監看員節點之後，您可以使用 Set-cswatchernodeconfiguration cmdlet 來新增或移除之節點的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="68c58-171">例如，若要新增的監看員節點 PersistentChatMessage 測試，使用 Add 方法與類似這樣的命令：</span><span class="sxs-lookup"><span data-stu-id="68c58-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="68c58-172">您可以加入多項測試使用逗號分隔的測試名稱。</span><span class="sxs-lookup"><span data-stu-id="68c58-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="68c58-173">例如：</span><span class="sxs-lookup"><span data-stu-id="68c58-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="68c58-174">如果一或多個這些測試 (例如，DataConference) 已啟用的監看員節點上，會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="68c58-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="68c58-175">在此情況下，您會收到類似如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="68c58-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="68c58-176">Set-cswatchernodeconfiguration： 沒有重複的按鍵組合 'DataConference' 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' 索引鍵或唯一識別條件約束。</span><span class="sxs-lookup"><span data-stu-id="68c58-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="68c58-177">發生此錯誤時，將會不套用任何變更。</span><span class="sxs-lookup"><span data-stu-id="68c58-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="68c58-178">使用移除重複測試應重新執行命令。</span><span class="sxs-lookup"><span data-stu-id="68c58-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="68c58-179">若要從監看員節點移除綜合交易，請使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="68c58-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="68c58-180">例如，此命令可移除 ABWQ 測試從監看員節點：</span><span class="sxs-lookup"><span data-stu-id="68c58-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="68c58-181">您可以使用 Replace 方法來取代所有目前已啟用測試，以下列一或多新測試。</span><span class="sxs-lookup"><span data-stu-id="68c58-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="68c58-182">例如，如果您想僅限來執行 IM 測試監看員節點，您可以使用下列命令，設定：</span><span class="sxs-lookup"><span data-stu-id="68c58-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="68c58-183">當您執行此命令時，將會停用指定監看員節點上的所有綜合交易除了 IM 之外。</span><span class="sxs-lookup"><span data-stu-id="68c58-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="68c58-184">檢視與測試監看員節點組態</span><span class="sxs-lookup"><span data-stu-id="68c58-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="68c58-185">如果您想要檢視已指派給監看員節點測試，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="68c58-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="68c58-186">此命令會傳回的資訊類似，根據已指派給節點的綜合交易：</span><span class="sxs-lookup"><span data-stu-id="68c58-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="68c58-187">註冊 IM GroupIM P2PAV AvConference 平台服務 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="68c58-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="68c58-188">若要依字母順序檢視綜合交易，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="68c58-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="68c58-189">若要確認已建立監看員節點，輸入下列命令從 Skype for Business Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="68c58-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="68c58-190">您會得到的資訊類似這樣：</span><span class="sxs-lookup"><span data-stu-id="68c58-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="68c58-191">身分識別： atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com、 sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="68c58-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="68c58-192">ExtendedTests: {TestUsers = IList<System.String>;名稱 = PSTN 測試;尋找...}</span><span class="sxs-lookup"><span data-stu-id="68c58-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="68c58-193">TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To 確認監看員節點已設定正確，下列從輸入命令 Skype for Business Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="68c58-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="68c58-194">此命令會測試您的部署中的每個監看員節點，並確認是否已完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="68c58-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="68c58-195">已安裝登錄器角色</span><span class="sxs-lookup"><span data-stu-id="68c58-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="68c58-196">建立必要的登錄機碼 （當您執行 Set-cswatchernodeconfiguration cmdlet 時已完成）</span><span class="sxs-lookup"><span data-stu-id="68c58-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="68c58-197">您的伺服器執行正確版本的 Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="68c58-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="68c58-198">連接埠已正確設定</span><span class="sxs-lookup"><span data-stu-id="68c58-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="68c58-199">指派的測試使用者具有必要的認證</span><span class="sxs-lookup"><span data-stu-id="68c58-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="68c58-200">管理監看員節點</span><span class="sxs-lookup"><span data-stu-id="68c58-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="68c58-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="68c58-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="68c58-202">除了修改在監看員節點執行的綜合交易，您也可以使用**Set-cswatchernodeconfiguration** cmdlet 來執行其他兩項重要工作： 啟用及停用監看員節點，以及設定監看員節點以執行測試時使用內部的 Web Url 或外部網頁 Url。</span><span class="sxs-lookup"><span data-stu-id="68c58-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="68c58-203">根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="68c58-204">有些時候，不過，您可能想要暫停的那些交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="68c58-205">例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="68c58-206">檢查網路連線，而這些交易都會失敗。</span><span class="sxs-lookup"><span data-stu-id="68c58-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="68c58-207">若要暫時停用監看員節點，請執行命令類似從 Skype for Business Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="68c58-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="68c58-208">此命令會停用綜合交易監看員節點 atl 監看員 001.litwareinc.com 上的執行。</span><span class="sxs-lookup"><span data-stu-id="68c58-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="68c58-209">若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：</span><span class="sxs-lookup"><span data-stu-id="68c58-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="68c58-210">Enabled 屬性可用於開啟或關閉監看員節點。</span><span class="sxs-lookup"><span data-stu-id="68c58-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="68c58-211">如果要永久刪除監看員節點，請使用 **Remove-CsWatcherNodeConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="68c58-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="68c58-212">該命令會從指定的電腦，可防止該電腦自動執行的綜合交易，移除所有的監看員節點組態設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="68c58-213">不過，命令不會解除安裝 System Center 代理程式檔案或 Skype for Business Server 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="68c58-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="68c58-214">根據預設，監看員節點測試時使用的組織外部的網頁 Url。</span><span class="sxs-lookup"><span data-stu-id="68c58-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="68c58-215">不過，監看員節點也可以設定成使用組織的內部網頁 Url。</span><span class="sxs-lookup"><span data-stu-id="68c58-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="68c58-216">這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。</span><span class="sxs-lookup"><span data-stu-id="68c58-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="68c58-217">若要設定監看員節點以使用內部 Url，而不是外部 Url，請將 UseInternalWebURls 屬性設為 True ($True):</span><span class="sxs-lookup"><span data-stu-id="68c58-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="68c58-218">重設為預設值為 False ($False) 的這個屬性會導致監看員再次使用外部 Url:</span><span class="sxs-lookup"><span data-stu-id="68c58-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="68c58-219">綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="68c58-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="68c58-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="68c58-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="68c58-221">大部分的綜合交易可以作為監看員節點上執行的是。</span><span class="sxs-lookup"><span data-stu-id="68c58-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="68c58-222">在大多數情況下，只要綜合交易新增至監看員節點組態設定，監看員節點可以開始使用其測試期間的綜合交易會傳遞。</span><span class="sxs-lookup"><span data-stu-id="68c58-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="68c58-223">不過，有一些綜合交易，需要特殊設定指示，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="68c58-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="68c58-224">資料會議綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="68c58-225">如果您的監看員節點電腦位於周邊網路外，您可能無法執行資料會議綜合交易，除非您先停用網路的 Windows Internet Explorer® 網際網路瀏覽器 proxy 設定服務帳戶，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="68c58-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="68c58-226">在監看員節點電腦上，按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**、 以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="68c58-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="68c58-227">在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="68c58-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="68c58-228">您會看到命令視窗中顯示下列訊息：</span><span class="sxs-lookup"><span data-stu-id="68c58-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="68c58-229">BITSAdmin 已被取代，並不保證可在未來版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="68c58-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="68c58-230">由個位元 PowerShell cmdlet 現在提供的位元服務管理工具。</span><span class="sxs-lookup"><span data-stu-id="68c58-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="68c58-231">NO_PROXY 設為帳戶 NetworkService 網際網路 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="68c58-232">(連線 = 預設值)</span><span class="sxs-lookup"><span data-stu-id="68c58-232">(connection = default)</span></span>
  
<span data-ttu-id="68c58-233">這則訊息會指出您已停用網路服務帳戶的 Internet Explorer proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="68c58-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="68c58-234">Exchange 整合通訊綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="68c58-235">Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者可連線的帳戶位於 Exchange 中的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="68c58-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="68c58-236">測試使用者必須是預先設定的具有語音信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="68c58-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="68c58-237">常設聊天室綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="68c58-238">若要使用的常設聊天室的綜合交易，您必須先建立通道，並使用它的使用者權限授與測試。</span><span class="sxs-lookup"><span data-stu-id="68c58-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="68c58-239">您可以使用的常設聊天室的綜合交易來設定此通道：</span><span class="sxs-lookup"><span data-stu-id="68c58-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="68c58-240">您必須執行此安裝程式必須從執行工作，企業內：</span><span class="sxs-lookup"><span data-stu-id="68c58-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="68c58-241">如果從非伺服器電腦執行，請執行此 cmdlet 的使用者必須是角色型存取控制 (RBAC) CsPersistentChatAdministrators 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="68c58-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="68c58-242">如果從伺服器本身執行，請執行此 cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="68c58-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="68c58-243">PSTN 對等通話綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="68c58-244">Test-cspstnpeertopeercall 綜合交易會驗證撥出及接聽透過公用交換的電話網路 (PSTN) 通話的能力。</span><span class="sxs-lookup"><span data-stu-id="68c58-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="68c58-245">若要執行此綜合交易，您必須設定：</span><span class="sxs-lookup"><span data-stu-id="68c58-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="68c58-246">兩個 UC 啟用測試使用者 （發話者和收件者）。</span><span class="sxs-lookup"><span data-stu-id="68c58-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="68c58-247">每個使用者帳戶的直接內部撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="68c58-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="68c58-248">允許受話者號碼的通話到達 PSTN 閘道的 VoIP 原則和語音路由。</span><span class="sxs-lookup"><span data-stu-id="68c58-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="68c58-249">接受來電和會路由傳送回受話者主集區，根據數通話的媒體的 PSTN 閘道的撥接。</span><span class="sxs-lookup"><span data-stu-id="68c58-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="68c58-250">整合的連絡人存放區綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="68c58-251">整合連絡人存放區綜合交易會驗證商務伺服器來從 Exchange 擷取代表使用者的連絡人的 Skype 的能力。</span><span class="sxs-lookup"><span data-stu-id="68c58-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="68c58-252">若要使用此綜合交易，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="68c58-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="68c58-253">Lyss Exchange 必須設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="68c58-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="68c58-254">測試使用者必須具備有效的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="68c58-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="68c58-255">符合這些條件後，您可以執行下列 Windows PowerShell cmdlet 將測試使用者的連絡人清單移轉到 Exchange:</span><span class="sxs-lookup"><span data-stu-id="68c58-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="68c58-256">它可能需要一些時間讓測試移轉至 Exchange 的使用者連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="68c58-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="68c58-257">若要監控移轉進度，相同的命令列可執行沒有-設定旗標：</span><span class="sxs-lookup"><span data-stu-id="68c58-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="68c58-258">這個命令列會成功完成移轉後。</span><span class="sxs-lookup"><span data-stu-id="68c58-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="68c58-259">XMPP 綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="68c58-260">Extensible Messaging and Presence Protocol (XMPP) IM 綜合交易需要您使用一或多個同盟網域設定 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="68c58-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="68c58-261">若要啟用 XMPP 綜合交易，您必須在路由傳送的 XMPP 網域使用者帳戶，以提供 XmppTestReceiverMailAddress 參數。</span><span class="sxs-lookup"><span data-stu-id="68c58-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="68c58-262">例如：</span><span class="sxs-lookup"><span data-stu-id="68c58-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="68c58-263">在這個範例中，Skype for Business Server 規則必須存在，才可將郵件路由傳送至 XMPP 閘道 litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="68c58-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="68c58-264">XMPP 閘道及 proxy 可在商務用 Skype Server 2015，但不再支援 skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="68c58-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="68c58-265">如需詳細資訊，請參閱[移轉 XMPP 同盟](../migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="68c58-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="68c58-266">視訊 Interop 伺服器 (VIS) 綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="68c58-267">視訊 Interop 伺服器 (VIS) 綜合交易需要您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921))。</span><span class="sxs-lookup"><span data-stu-id="68c58-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="68c58-268">若要安裝 VISSTSupportPackage.msi 確保相依性 （在系統需求） 的已安裝 msi。</span><span class="sxs-lookup"><span data-stu-id="68c58-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="68c58-269">執行 VISSTSupportPackage.msi 執行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="68c58-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="68c58-270">.msi 安裝的所有檔案在下列路徑: 「 %ProgramFiles%\VIS 綜合交易支援套件 」。</span><span class="sxs-lookup"><span data-stu-id="68c58-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="68c58-271">如需有關如何執行 VIS 綜合交易的詳細資訊，請參閱[測試 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx)指令程式的說明文件。</span><span class="sxs-lookup"><span data-stu-id="68c58-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="68c58-272">變更的執行的頻率的綜合交易</span><span class="sxs-lookup"><span data-stu-id="68c58-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="68c58-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="68c58-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="68c58-274">根據預設，綜合交易，會執行與已設定的使用者每隔 15 分鐘。</span><span class="sxs-lookup"><span data-stu-id="68c58-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="68c58-275">若要避免兩個綜合交易的彼此衝突的使用者的一組內循序執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="68c58-276">需要較長的時間間隔，才能提供完成的所有綜合交易的時間。</span><span class="sxs-lookup"><span data-stu-id="68c58-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="68c58-277">如果它是而言更頻繁地執行綜合交易，以便測試可以完成在某些緩衝區，以供偶爾網路延遲所需的時間範圍內，應該會減少使用一組特定的使用者執行的綜合交易數目。</span><span class="sxs-lookup"><span data-stu-id="68c58-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="68c58-278">如果執行更多的綜合交易是令人滿意，建立多個使用者設定來執行其他的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="68c58-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="68c58-279">若要變更速率執行綜合交易的頻率，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="68c58-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="68c58-280">開啟 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="68c58-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="68c58-281">按一下 [撰寫] 區段中。</span><span class="sxs-lookup"><span data-stu-id="68c58-281">Click Authoring section.</span></span> <span data-ttu-id="68c58-282">按一下 [規則] 區段中的 （在撰寫）</span><span class="sxs-lookup"><span data-stu-id="68c58-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="68c58-283">在 [規則] 區段中，尋找名稱為"Main 綜合交易自由效能集合 Rule"的規則</span><span class="sxs-lookup"><span data-stu-id="68c58-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="68c58-284">以滑鼠右鍵按一下規則，並選取 [覆寫，選取 [覆寫規則，，然後選取 「 類別的所有物件： 集區監看員 」</span><span class="sxs-lookup"><span data-stu-id="68c58-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="68c58-285">在 [覆寫的屬性] 視窗中，選取參數名稱 」 頻率 」，並將覆寫值所想要。</span><span class="sxs-lookup"><span data-stu-id="68c58-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="68c58-286">在同一個視窗中，選取 [需要套用這個覆寫要管理組件</span><span class="sxs-lookup"><span data-stu-id="68c58-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="68c58-287">使用綜合交易的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="68c58-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="68c58-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="68c58-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="68c58-289">綜合交易證明極幫助系統找出問題。</span><span class="sxs-lookup"><span data-stu-id="68c58-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="68c58-290">例如，Test-csregistration cmdlet 無法發出警示系統管理員的使用者已有困難註冊與 Skype for Business Server 的事實。</span><span class="sxs-lookup"><span data-stu-id="68c58-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="68c58-291">不過，可能需要其他細節，若要判斷實際失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="68c58-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="68c58-292">基於這個理由，綜合交易提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="68c58-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="68c58-293">使用的綜合交易齊備，每個活動的豐富記錄會記錄下列資訊：</span><span class="sxs-lookup"><span data-stu-id="68c58-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="68c58-294">活動開始時間。</span><span class="sxs-lookup"><span data-stu-id="68c58-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="68c58-295">活動完成時間。</span><span class="sxs-lookup"><span data-stu-id="68c58-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="68c58-296">已執行的動作 (例如，建立、 加入或離開會議; 登入 Skype for Business Server; 傳送立即訊息)。</span><span class="sxs-lookup"><span data-stu-id="68c58-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="68c58-297">活動執行時所產生的資訊、詳細資料、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="68c58-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="68c58-298">SIP 登錄訊息。</span><span class="sxs-lookup"><span data-stu-id="68c58-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="68c58-299">例外狀況記錄或診斷碼活動執行時所產生。</span><span class="sxs-lookup"><span data-stu-id="68c58-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="68c58-300">執行活動的最終結果。</span><span class="sxs-lookup"><span data-stu-id="68c58-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="68c58-301">這項資訊會自動產生每次執行綜合交易，但不是會自動顯示或儲存記錄檔。</span><span class="sxs-lookup"><span data-stu-id="68c58-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="68c58-302">如果您以手動方式執行綜合交易，您可以使用之後包含 OutLoggerVariable 參數來指定的資訊會儲存在 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="68c58-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="68c58-303">從那裡，您可以選擇使用兩種方法之一來儲存及/或檢視錯誤訊息中 rtf 登入 [XML] 或 [HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="68c58-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="68c58-304">若要擷取的疑難排解資訊，請指定之後包含 OutLoggerVariable 參數，您選擇的變數名稱：</span><span class="sxs-lookup"><span data-stu-id="68c58-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="68c58-305">： 請勿不在開頭上 $ 字元變數的名稱。</span><span class="sxs-lookup"><span data-stu-id="68c58-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="68c58-306">使用變數名稱，例如 RegistrationTest (不 $RegistrationTest)。</span><span class="sxs-lookup"><span data-stu-id="68c58-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="68c58-307">當您執行此命令時，您會看到類似的輸出：</span><span class="sxs-lookup"><span data-stu-id="68c58-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="68c58-308">目標 Fqdn: atl-cs-001.litwareinc.com 結果： 失敗延遲： 00:00:00 錯誤訊息： 這台機器沒有任何已指派的憑證。</span><span class="sxs-lookup"><span data-stu-id="68c58-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="68c58-309">診斷： 您可以存取此失敗更詳細的資訊比只是錯誤訊息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="68c58-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="68c58-310">若要存取這項資訊以 HTML 格式，請使用類似以下的命令若要將儲存在變數 RegistrationTest 為 HTML 檔案中的資訊：</span><span class="sxs-lookup"><span data-stu-id="68c58-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="68c58-311">或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="68c58-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="68c58-312">您可以使用 Windows Internet Explorer、 Microsoft Visual Studio 中或任何其他應用程式能夠開啟 HTML/XML 檔案，以檢視這些檔案。</span><span class="sxs-lookup"><span data-stu-id="68c58-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="68c58-313">綜合交易，從執行 System Center Operations Manager 中的內容會自動產生失敗這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="68c58-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="68c58-314">如果執行作業失敗之前 Skype for Business Server PowerShell 是能夠載入及執行綜合交易，將不會產生這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="68c58-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="68c58-315">根據預設，Skype for Business Server 會將記錄檔儲存至未共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="68c58-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="68c58-316">若要讓這些記錄檔隨時都能存取，您應該共用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="68c58-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="68c58-317">例如： \\atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="68c58-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
