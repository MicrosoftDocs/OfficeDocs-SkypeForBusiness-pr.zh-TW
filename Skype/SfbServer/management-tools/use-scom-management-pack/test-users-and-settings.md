---
title: 設定觀察程式節點測試使用者和設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '摘要: 針對商務用 Skype Server 合成事務, 設定測試使用者帳戶和觀察程式節點設定。'
ms.openlocfilehash: 02c24d4f23b59dfa8ddab68e1c4a992312916b3a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187948"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>設定觀察程式節點測試使用者和設定
 
**摘要:** 針對商務用 Skype Server 合成事務, 設定測試使用者帳戶與觀察程式節點設定。
  
在設定將充當監視者節點的電腦之後, 您必須:
  
1. 設定這些觀察程式節點要使用的[測試使用者帳戶](test-users-and-settings.md#testuser)。 如果您使用的是 Negotiate 驗證方法, 您也必須使用**CsTestUserCredential** Cmdlet 來啟用這些測試帳戶, 以便在 [觀察程式] 節點上使用。
    
2. 更新觀察程式節點設定。
    
## <a name="configure-test-user-accounts"></a>設定測試使用者帳戶
<a name="testuser"> </a>

測試帳戶不需要代表實際的人員, 但必須是有效的 Active Directory 帳戶。 此外, 必須針對商務用 Skype Server 啟用這些帳戶, 他們必須擁有有效的 SIP 位址, 而且應該為企業語音啟用它們 (以使用測試 CsPstnPeerToPeerCall 綜合交易)。 
  
如果您使用的是 TrustedServer 驗證方法, 您只需確定這些帳戶存在, 然後依所述加以設定。 您應該為您要測試的每個池指派至少兩個測試使用者。 如果您使用的是 Negotiate 驗證方法, 您也必須使用 CsTestUserCredential Cmdlet 和商務用 Skype Server 管理命令介面, 以啟用這些測試帳戶來處理綜合交易。 若要執行此動作, 請執行類似下列的命令 (這些命令假設已建立兩個 Active Directory 使用者帳戶, 且已針對商務用 Skype Server 啟用這些帳戶):
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

您不僅必須包含 SIP 位址, 還要包括使用者名稱和密碼。 如果您不包含密碼, CsTestUserCredential Cmdlet 會提示您輸入該資訊。 您可以使用上述程式碼區塊中所示的功能變數名稱格式來指定使用者名稱。
  
若要確認已建立測試使用者認證, 請從商務用 Skype Server Management Shell 執行這些命令:
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

會針對每個使用者傳回類似以下內容的資訊:
  
|**UserName**|**口令**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設的綜合交易設定基本的觀察程式節點

在測試使用者建立之後, 您可以使用類似以下的命令來建立觀察程式節點:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

這個命令會建立使用預設設定的新的觀察程式節點, 並執行預設的綜合交易集合。 新的 [觀察程式] 節點也會使用 [測試使用者] watcher1@litwareinc.com 和 watcher2@litwareinc.com。 如果 [觀察程式] 節點使用 TrustedServer 驗證, 則這兩個測試帳戶可以是啟用 Active Directory 及商務用 Skype Server 的任何有效使用者帳戶。 如果觀察程式節點使用 Negotiate 驗證方法, 也必須使用 CsTestUserCredential Cmdlet 為觀察程式節點啟用這些使用者帳戶。
  
若要驗證是否正確設定目標池的自動探索, 而不是以某個池為目標, 請改為直接使用這些步驟:
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>設定延伸測試

如果您想要啟用 PSTN 測試, 這會驗證與公用交換電話網絡的連線, 您需要在設定觀察程式節點時, 進行一些額外的配置。 首先, 您必須從商務用 Skype Server Management Shell 執行如下的命令, 以將測試使用者與 PSTN 測試類型建立關聯:
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 這個命令的結果必須儲存在變數中。 在這個範例中, 變數稱為 [$pstnTest]。 
  
接著, 您可以使用**CsWatcherNodeConfiguration** Cmdlet, 將測試類型 (儲存在變數 $pstnTest 中) 與商務用 Skype 伺服器池產生關聯。 例如, 下列命令會針對 [池 atl-cs-001.litwareinc.com] 建立新的 [觀察程式] 節點設定, 並新增先前建立的兩個測試使用者, 並新增 PSTN 測試類型:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您沒有在監視程式節點電腦上安裝商務用 Skype Server core 檔案和 RTCLocal 資料庫, 上述命令就會失敗。 
  
若要測試多個語音原則, 您可以使用**CsExtendedTest** Cmdlet, 為每個原則建立延伸測試。 所提供的使用者應該使用所需的語音原則進行設定。 您可以使用逗號分隔符號將延伸測試傳到**新的 CsWatcherNodeConfiguration** Cmdlet, 例如:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
因為不使用測試參數就會呼叫**New-CsWatcherNodeConfiguration** Cmdlet, 所以只有預設的綜合交易 (以及指定的延伸綜合交易) 會針對新的 [觀察程式] 節點啟用。 因此, 觀察程式節點會測試下列元件:
  
- 註冊
    
- IM
    
- GroupIM
    
- P2PAV (對等音訊/視頻會話)
    
- AvConference (音訊/會議)
    
- 平臺
    
- ABS (通訊錄服務)
    
- ABWQ (通訊錄 web 服務)
    
預設不會測試下列元件:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange 整合通訊)
    
- JoinLauncher
    
- MCXP2PIM (傳統行動裝置立即訊息)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN 閘道通話, 指定為擴展測試)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>新增及移除綜合交易

在已設定觀察程式節點之後, 您可以使用 CsWatcherNodeConfiguration Cmdlet 來新增或移除節點中的綜合交易。 例如, 若要將 PersistentChatMessage 測試新增至 [觀察程式] 節點, 請使用如下所示的 Add 方法和命令:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

您可以使用逗號分隔測試名稱來新增多個測試。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果在 [觀察程式] 節點上已啟用其中一個或多個測試 (例如 DataConference), 就會發生錯誤。 在這種情況下, 您會收到類似以下的錯誤訊息:
  
設定-CsWatcherNodeConfiguration: "urn: schema: WatcherNode: TestName" 金鑰或唯一身分識別限制有重複的鍵順序 "DataConference"。
  
發生此錯誤時, 將不會套用任何變更。 必須重新執行此命令, 並移除重複的測試。
  
若要從觀察程式節點移除綜合交易, 請使用 Remove 方法。 例如, 此命令會從觀察程式節點中移除 ABWQ 測試:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

您可以使用 Replace 方法, 以一或多個新的測試取代所有目前啟用的測試。 例如, 如果您只想讓觀察程式節點執行 IM 測試, 您可以使用此命令來設定:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

當您執行此命令時, 除了 IM 之外, 指定的觀察程式節點上的所有綜合交易都將停用。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看及測試觀察程式節點設定

如果您想要查看已指派給觀察程式節點的測試, 請使用類似以下的命令:
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

根據已指派給節點的綜合交易, 此命令會傳回類似此的資訊:
  
註冊 IM GroupIM P2PAV AvConference 目前狀態 PersistentChatMessage DataConference
> [!TIP]
> 若要依字母順序查看綜合交易, 請改為使用此命令: 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要確認已建立觀察程式節點, 請從商務用 Skype Server Management 命令介面輸入下列命令:
  
```
Get-CsWatcherNodeConfiguration
```

您會收到類似以下的資訊:
  
身分識別: atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests: {TestUsers = IList<System.object>;Name = PSTN 測試;Te ...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
PortNumber: 5061<br/>

若要確認已正確設定觀察程式節點, 請從商務用 Skype Server Management 命令介面輸入下列命令:
  
```
Test-CsWatcherNodeConfiguration
```

這個命令會在您的部署中測試每個觀察程式節點, 並確認是否已完成下列動作:
  
- 已安裝所需的註冊機構角色。
    
- 所需的登錄機碼會建立 (在您執行 CsWatcherNodeConfiguration Cmdlet 時完成)。
    
- 您的伺服器正在執行正確版本的商務用 Skype Server。
    
- 您的埠設定正確。
    
- 您指派的測試使用者具有所需的認證。
    
## <a name="managing-watcher-nodes"></a>管理觀察程式節點
<a name="testuser"> </a>

除了修改在觀察程式節點上執行的綜合交易之外, 您也可以使用**CsWatcherNodeConfiguration** Cmdlet 來執行其他兩項重要工作: 啟用及停用 [觀察程式] 節點, 以及設定[觀察程式] 節點, 可在執行測試時使用內部網頁 Url 或外部 Web Url。
  
根據預設, 觀察程式節點是設計來定期執行所有已啟用的綜合交易。 不過, 有時您可能會想要暫停這些交易。 例如, 如果 [觀察程式] 節點暫時與網路中斷連線, 則沒有任何理由執行綜合交易。 若沒有網路連線, 這些事務將會失敗。 若要暫時停用 [觀察程式] 節點, 請從商務用 Skype Server Management 命令介面執行如下所示的命令:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

這個命令將停用在觀察程式節點的 [atl 觀察程式] 001.litwareinc.com 上執行綜合交易。 若要繼續執行綜合交易, 請將 Enabled 屬性設回 True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> 可使用 Enabled 屬性來開啟或關閉觀察程式節點。 如果您想要永久刪除 [觀察程式] 節點, 請使用**CsWatcherNodeConfiguration** Cmdlet:
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

該命令會從指定的電腦中移除所有的觀察程式節點設定, 這可防止電腦自動執行綜合交易。 不過, 命令不會卸載 System Center 代理程式檔案或商務用 Skype Server 系統檔案。
  
根據預設, 觀察程式節點會在進行測試時使用組織的外部 Web Url。 不過, 您也可以將觀察程式節點設定為使用組織的內部 Web Url。 這可讓系統管理員驗證位於周邊網路內之使用者的 URL 存取權。 若要將觀察程式節點設定為使用內部 Url, 而不是外部 Url, 請將 UseInternalWebURls 屬性設為 True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

如果將這個屬性重設為預設值 False ($False), 就會再次使用外部 Url:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>綜合交易的特殊設定指示
<a name="special_synthetictrans"> </a>

大多數的綜合交易都可以在觀察程式節點上以同樣的方式執行。 在大多數情況下, 當綜合交易新增至觀察程式節點設定設定之後, 觀察程式節點就可以在其測試階段中開始使用該綜合交易。 不過, 有一些需要特殊設定指示的綜合交易, 如下列各節所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>資料會議綜合交易

如果您的系統監控程式節點電腦位於周邊網路之外, 則您可能無法執行資料會議綜合交易, 除非您首先停用 Windows Internet Explorer®網路的 Internet 瀏覽器 proxy 設定[服務] 帳戶, 請完成下列步驟:
  
1. 在觀察程式節點電腦上, 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**附件**], 以滑鼠右鍵按一下**命令提示**字元, 然後按一下 [**以系統管理員身分執行**]
    
2. 在主控台視窗中, 輸入下列命令, 然後按 ENTER 鍵。 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您會在命令視窗中看到如下所示的訊息:
  
BITSAdmin 已過時, 且不保證可在未來版本的 Windows 中使用。 BITS 服務的管理工具現已由 BITS PowerShell Cmdlet 提供。
  
[帳戶 NetworkService] 設定為 [NO_PROXY] 的網際網路 proxy 設定。 
  
(連接 = 預設值)
  
此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 整合訊息綜合交易

Exchange 整合通訊 (UM) 綜合交易會確認測試使用者可以連線至位於 Exchange 中的語音信箱帳戶。
  
測試使用者將需要使用語音信箱帳戶預先設定。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持續聊天綜合交易

若要使用持續性聊天綜合交易, 您必須先建立一個通道, 然後給予測試使用者使用它的許可權。
  
您可以使用持續聊天綜合交易來設定此通道: 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

您必須執行此設定任務, 才能從企業內部執行:
  
- 如果從非伺服器電腦執行, 則執行 Cmdlet 的使用者必須是以角色為基礎的存取控制 (RBAC) 之 CsPersistentChatAdministrators 角色的成員。
    
- 如果從伺服器本身執行, 執行 Cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 對等呼叫綜合交易

Test CsPstnPeerToPeerCall 綜合交易會驗證透過公用交換電話網絡 (PSTN) 撥打及接聽電話的能力。
  
若要執行此綜合交易, 您必須設定:
  
- 兩個啟用 UC 的測試使用者 (來電者和接收人)。
    
- 針對每個使用者帳戶直接撥打 (已有) 號碼。
    
- [VoIP 原則] 和 [語音路由], 可讓呼叫接收器的號碼到達 PSTN 閘道。
    
- 可接受呼叫和媒體的 PSTN 閘道, 會根據撥打的號碼, 將呼叫路由回接收器的主區。
    
### <a name="unified-contact-store-synthetic-transaction"></a>整合連絡人商店綜合交易

[整合連絡人商店] 綜合交易記錄會驗證商務用 Skype Server 在 Exchange 中代表使用者取得連絡人的能力。
  
若要使用這個綜合交易, 必須符合下列條件:
  
- 必須設定 Lyss-Exchange server to server 驗證。
    
- 測試使用者必須具備有效的 Exchange 信箱。
    
在符合這些條件之後, 您可以執行下列 Windows PowerShell Cmdlet, 將測試使用者的連絡人清單遷移到 Exchange:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

測試使用者連絡人清單可能需要一些時間才能移植到 Exchange。 若要監視遷移進度, 在沒有-Setup 標誌的情況下, 可以執行相同的命令列:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

完成遷移之後, 此命令列將會成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 綜合交易

[可擴展訊息與目前狀態通訊協定 (XMPP) IM 綜合交易] 需要您設定一或多個聯盟網域的 XMPP 功能。
  
若要啟用 XMPP 綜合交易, 您必須在可路由的 XMPP 網域中提供使用者帳戶的 XmppTestReceiverMailAddress 參數。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在這個範例中, 商務用 Skype 伺服器規則必須存在, 才能將 litwareinc.com 的訊息路由至 XMPP 閘道。

> [!NOTE]
> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>影片互通性伺服器 (VIS) 綜合交易

影片交互操作伺服器 (VIS) 綜合交易需要您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。 
  
若要安裝 VISSTSupportPackage, 請確保已安裝 msi 的相依性 (在 [系統需求] 底下)。 執行 VISSTSupportPackage 以進行簡單的安裝。 .Msi 會安裝下列路徑中的所有檔案: 「%ProgramFiles%\VIS 綜合交易支援套件」。
  
如需如何執行 VIS 綜合交易的詳細資訊, 請參閱[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) Cmdlet 的檔。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>變更綜合交易的執行頻率
<a name="special_synthetictrans"> </a>

根據預設, 綜合交易會每隔15分鐘與已設定的使用者一起執行。 在一組使用者中循序執行綜合交易, 以避免兩個綜合交易彼此衝突。 需要較長的時間間隔, 才能提供所有綜合交易完成所需的時間。
  
如果想要更頻繁地執行綜合交易, 則應該減少使用指定使用者組執行的綜合交易數, 以便讓測試能在所需的時間範圍內完成, 而不需要偶爾的網路延遲的緩衝區。 如果想要執行更多綜合交易, 請建立更多使用者集來執行額外的綜合交易。
  
若要變更綜合交易的執行頻率, 請遵循下列步驟:
  
1. 開啟 System Center Operations Manager。 按一下 [創作節]。 按一下 [規則] 區段 (在 [創作] 底下)。
    
2. 在 [規則] 區段中, 找到名稱為「主要綜合交易處理常式效能集合規則」的規則。
    
3. 以滑鼠右鍵按一下規則, 然後選取 [覆寫], 選取 [覆寫規則], 然後選取 [針對類別: Pool 觀察程式的所有物件]。
    
4. 在 [覆寫屬性] 視窗中, 選取 [參數名稱 "Frequency], 然後將覆寫值設定為所需的值。
    
5. 在同一個視窗中, 選取需要套用此覆寫的管理套件。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用豐富的記錄來進行綜合交易
<a name="special_synthetictrans"> </a>

在協助找出系統問題時, 綜合交易證明非常有用。 例如, CsRegistration Cmdlet 可以提醒系統管理員使用者無法使用商務用 Skype 伺服器進行註冊。 不過, 您可能需要其他詳細資料來判斷失敗的實際原因。
  
基於這個原因, 綜合交易提供豐富的記錄。 對於綜合交易 undertakes 的每個活動, 都會有豐富的記錄, 記錄以下資訊:
  
- 活動開始的時間。
    
- 活動完成的時間。
    
- 所執行的動作 (例如, 建立、加入或離開會議; 登入商務用 Skype 伺服器; 傳送立即訊息)。
    
- 當活動執行時產生的資訊、詳細、警告或錯誤訊息。
    
- SIP 註冊訊息。
    
- 當活動執行時產生的例外記錄或診斷程式代碼。
    
- 執行活動的最終結果。
    
這項資訊會在每次執行綜合交易時自動產生, 但不會自動顯示或儲存至記錄檔。 如果您是手動執行綜合交易, 您可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。 在這裡, 您可以選擇使用兩種方法的其中一種, 以 XML 或 HTML 格式在豐富記錄中儲存和/或查看錯誤訊息。 
  
若要取得疑難排解資訊, 請指定 OutLoggerVariable 參數, 後面接著您選擇的變數名稱:
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 請勿在變數名稱前面加上 $ 字元。 使用變數名稱, 例如 RegistrationTest (not $RegistrationTest)。 
  
當您執行此命令時, 您會看到類似以下的輸出:
  
目標 Fqdn: atl-cs-001.litwareinc.com 結果: 失敗延遲: 00:00:00 錯誤訊息: 此電腦沒有任何指派的憑證。 診斷: 您可以針對此失敗, 存取更詳細的資訊, 而不只是此處顯示的錯誤訊息。

若要以 HTML 格式存取此資訊, 請使用類似這個的命令, 將儲存在可變 RegistrationTest 中的資訊儲存為 HTML 檔案:
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

或者, 您也可以使用 ToXML () 方法將資料儲存至 XML 檔案:
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以使用 Windows Internet Explorer、Microsoft Visual Studio, 或任何能夠開啟 HTML/XML 檔案的其他應用程式, 來查看這些檔案。
  
從系統中心作業管理員內部執行的綜合交易, 會自動產生這些記錄檔案, 以尋找失敗。 如果執行失敗, 在商務用 Skype Server PowerShell 無法載入並執行綜合交易之前, 則不會產生這些記錄。 
  
> [!IMPORTANT]
> 根據預設, 商務用 Skype 伺服器會將記錄檔案儲存到未共用的資料夾中。 若要讓這些記錄易於存取, 您應該共用此資料夾。 例如: \\atl-觀察程式-001. litwareinc. com\WatcherNode。 
