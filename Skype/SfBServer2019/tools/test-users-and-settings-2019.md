---
title: 設定監視節點測試使用者和設定
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 為商務用 Skype Server 綜合交易設定測試使用者帳戶和監視節點設定。
ms.openlocfilehash: 31dac13da3d41316d047eca4746fd7af11197c82
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396194"
---
# <a name="skype-for-business-server-configure-watcher-node-test-users-and-settings"></a>商務用 Skype Server：設定觀察者節點測試使用者和設定
 
**總結：** 為商務用 Skype Server 綜合交易設定測試使用者帳戶和監視節點設定。
  
在設定將充當監視節點的電腦之後，您必須：
  
1. 設定這些觀察器節點要使用的[測試使用者帳戶](test-users-and-settings-2019.md#testuser)。 如果您使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 來啟用這些測試帳戶，以在監看員節點上使用。
    
2. 更新監視節點的設定。
    
## <a name="configure-test-user-accounts"></a>設定測試使用者帳戶
<a name="testuser"> </a>

測試帳戶不需要表示實際人員，但必須是有效的 Active Directory 帳戶。 此外，必須為商務用 Skype Server 啟用這些帳戶，他們必須具有有效的 SIP 位址，而且應為企業語音啟用這些帳戶， (才能使用 Test-CsPstnPeerToPeerCall 綜合交易) 。 
  
如果您使用的是 TrustedServer 驗證方法，您需要做的所有工作是確定這些帳戶都存在，並加以設定。 為每個您要測試的集區至少指派三個測試使用者。 如果您使用 Negotiate 驗證方法，您也必須使用 Set-CsTestUserCredential Cmdlet 和商務用 Skype Server 管理命令介面，讓這些測試帳戶能夠搭配綜合交易。 執行下列命令，以執行類似下列的命令 (這些命令會假設已建立三個 Active Directory 使用者帳戶，且已啟用這些帳戶商務用 Skype Server) ：
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

不僅包含 SIP 位址，也包含使用者名稱和密碼。 如果您未加入密碼，Set-CsTestUserCredential Cmdlet 會提示您輸入該資訊。 您可以使用上述程式碼區塊中所示的功能變數名稱 \ 功能變數名稱格式來指定使用者名稱。
  
若要確認是否已建立測試使用者認證，請從商務用 Skype Server 管理命令介面執行下列命令：
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

會針對每位使用者傳回類似以下的資訊：
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |SecureString 的安全性  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設的綜合交易，設定基本的監看員節點

在測試使用者建立之後，您可以使用類似下列的命令來建立監看員節點：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

這個命令會建立新的監看員節點，使用預設設定，並執行預設的綜合交易集合。 新的監看員節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 及 watcher3@litwareinc.com。 如果監看員節點使用 TrustedServer 驗證，則三個測試帳戶可以是為 Active Directory 及商務用 Skype Server 啟用的任何有效使用者帳戶。 如果監看員節點使用 Negotiate 驗證方法，也必須使用 Set-CsTestUserCredential Cmdlet 來啟用監視節點的使用者帳戶。
  
若要驗證已正確設定目標集區的自動探索，而不是以集區為目標，請改用下列步驟：
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>設定擴充測試

如果您想要啟用 PSTN 測試，它會驗證與公用交換電話網路的連線，則在設定監看員節點時，您需要執行其他一些設定。 首先，您必須從商務用 Skype Server 管理命令介面中執行類似下列的命令，以將測試使用者與 PSTN 測試類型關聯：
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 這個命令的結果必須儲存在變數中。 在此範例中，變數命名為 $pstnTest。 
  
接下來，您可以使用 **New-CsWatcherNodeConfiguration** Cmdlet，將 $pstnTest) 中儲存的測試類型 (關聯至商務用 Skype Server 集區。 例如，下列命令會為集區 atl-cs-001.litwareinc.com 建立新的監看員節點設定，加入先前建立的三個測試使用者，並新增 PSTN 測試類型：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您尚未在監看員節點電腦上安裝商務用 Skype Server 核心檔案和 RTCLocal 資料庫，上述命令將會失敗。 
  
若要測試多種語音原則，您可以使用 **New-CsExtendedTest** Cmdlet，為每個原則建立擴充測試。 提供的使用者應以所需的語音原則加以設定。 擴充測試會使用逗點分隔符號傳遞至 **New-CsWatcherNodeConfiguration** Cmdlet，例如：
  
-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}
  
因為 **New-CsWatcherNodeConfiguration** 指令程式呼叫時未使用測試參數，所以新的監看員節點只會啟用預設的綜合交易 (和指定的延伸綜合交易) 。 因此，觀察程式節點會測試下列元件：
  
- 註冊
    
- 我
    
- GroupIM
    
- P2PAV (對等音訊/視頻會話) 
    
- AvConference (音訊/會議) 
    
- 目前狀態
    
- ABS (通訊錄服務) 
    
- ABWQ (通訊錄 web 服務) 
    
預設不會測試下列元件：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange 整合通訊) 
    
- JoinLauncher
    
- MCXP2PIM (舊版行動裝置立即訊息) 
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN 閘道通話，指定成擴充測試) 
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>新增及移除綜合交易

在設定了監看員節點之後，您可以使用 Set-CsWatcherNodeConfiguration Cmdlet 來新增或移除節點中的綜合交易。 例如，若要將 PersistentChatMessage 測試新增至監看員節點，請使用 Add 方法及類似如下的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

若要新增多個測試，您可以使用逗號分隔測試名稱。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

例如，如果其中一或多個測試 (（例如，DataConference) 已在監看員節點上啟用），便會發生錯誤。 在此情況下，您會收到類似下列訊息的錯誤訊息：
  
Set-CsWatcherNodeConfiguration： ' urn： schema： DataConference ' 是重複的 key sequence ' '。設定。WatcherNode。2010： TestName ' 鍵或唯一識別碼限制。
  
發生此錯誤時，將不會套用任何變更。 在移除重複的測試時，應重新執行該命令。
  
若要移除來自觀察者節點的綜合交易，請使用 Remove 方法。 例如，下列命令會從監看員節點中移除 ABWQ 測試：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

您可以使用 Replace 方法，將所有目前啟用的測試取代為一或多個新的測試。 例如，如果您只想要監視節點執行 IM 測試，您可以使用下列命令來設定該節點：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

當您執行此命令時，會停用指定的監看員節點上的所有綜合交易，但 IM 除外。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看及測試監視節點設定

如果您想要查看已指派給觀察者節點的測試，請使用類似下列的命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

根據指派給節點的綜合交易，此命令會傳回類似下列的資訊：
  
註冊 IM GroupIM P2PAV AvConference 顯示狀態 PersistentChatMessage DataConference
> [!TIP]
> 若要依字母順序查看綜合交易，請改為使用此命令： 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要確認已建立監看員節點，請從商務用 Skype Server 管理命令介面輸入下列命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

您會收到類似以下的資訊：
  
Identity： atl-cs-001.litwareinc.com TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...} ExtendedTests： {TestUsers = IList<System.String>;Name = PSTN 測試;Te ...} TargetFqdn： atl-cs-001.litwareinc.com 埠：5061To 確認已正確設定監視程式節點，請從商務用 Skype Server 管理命令介面輸入下列命令：
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

這個命令會測試您部署中的每個監看員節點，並確認是否已完成下列動作：
  
- 已安裝必要的註冊機構角色
    
- 當您執行 Set-CsWatcherNodeConfiguration Cmdlet 時， (已完成，便會建立必要的登錄機碼) 
    
- 您的伺服器正在執行正確版本的商務用 Skype Server
    
- 您的埠已正確設定
    
- 您指派的測試使用者具備必要的認證
    
## <a name="managing-watcher-nodes"></a>管理監看員節點
<a name="testuser"> </a>

除了修改在監看員節點上執行的綜合交易，您也可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來執行兩個其他重要的工作：啟用及停用監看員節點，以及設定監視節點在執行其測試時使用內部 Web URLs 或外部 Web URLs。
  
根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。 不過，有時候您可能想要暫掛這些交易。 例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。 若沒有網路連線，那些交易將會失敗。 若要暫時停用監看員節點，請從商務用 Skype Server 管理命令介面執行類似以下的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令會停用在監看員節點上執行綜合交易的執行。 [atl 觀察程式 001.litwareinc.com]。 若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 屬性可用於開啟或關閉監看員節點。如果要永久刪除監看員節點，請使用 **Remove-CsWatcherNodeConfiguration** Cmdlet：
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

該命令會從指定的電腦移除所有的監看員節點設定設定，以防止電腦自動執行綜合交易。 不過，此命令不會卸載 System Center 代理程式檔案或商務用 Skype Server 系統檔案。
  
依預設，觀察程式節點會在執行測試時使用組織的外部 Web URLs。 不過，觀察程式節點也可以設定為使用組織的內部 Web URLs。 這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。 若要設定監視節點使用內部 URLs，而不是外部 URLs，請將 UseInternalWebURls 屬性設定為 True ($True) ：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

將此屬性重設為預設值 False ($False) 將會再次使用外部 URLs：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>綜合交易的特殊設定指示
<a name="special_synthetictrans"> </a>

大多數綜合交易可依原樣在監看員節點上執行。 在大多數情況下，當綜合交易新增至監看員節點設定設定時，在其測試階段內，監看員節點便可以開始使用該綜合交易。 不過，有一些需要特殊設定指示的綜合交易，如下列各節所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>資料會議綜合交易

如果您的監看員節點電腦位於周邊網路之外，除非您先停用 Windows internet Explorer® internet browser proxy 設定，請完成下列步驟，否則您將無法執行資料會議綜合交易：
  
1. 在監看員節點電腦上，依序按一下 [**開始**]、[**所有程式**]、[**附件**] 及 [以 **系統管理員身分執行**]。 
    
2. 在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您會看到下列會顯示在命令視窗中的訊息：
  
BITSAdmin 已被取代，且不保證會在未來版本的 Windows 中使用。 BITS 服務的管理工具現在是由 BITS PowerShell Cmdlet 所提供。
  
NetworkService 設定為 NO_PROXY 的帳戶的網際網路 proxy 設定。 
  
 (connection = default) 
  
此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 整合通訊綜合交易

Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者是否可以連線至位於 Exchange 的語音信箱帳戶。
  
測試使用者必須使用語音信箱帳戶進行預先設定。 
  
### <a name="persistent-chat-synthetic-transaction"></a>Persistent Chat 綜合交易

若要使用持續性聊天綜合交易，您必須先建立通道，並提供測試使用者的使用許可權。
  
您可以使用 Persistent Chat 綜合交易來設定此通道： 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

從企業內部執行此設定工作：
  
- 如果從非伺服器電腦執行，則執行 Cmdlet 的使用者必須是 CsPersistentChatAdministrators 角色的成員，Role-Based 存取控制 (RBAC) 。
    
- 如果從伺服器自行執行，則執行 Cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN Peer-to-Peer 呼叫綜合交易

Test-CsPstnPeerToPeerCall 綜合交易會透過公用交換電話網路 (PSTN) 驗證撥打和接聽電話的能力。
  
若要執行此綜合交易，您必須進行下列設定：
  
- 兩個啟用 UC 的測試使用者 (來電者和接收器) 。
    
- 每個使用者帳戶的直接內部撥號 (DID) 號碼。
    
- VoIP 原則及語音路由，可讓呼叫收件者的號碼，以到達 PSTN 閘道。
    
- 一種 PSTN 閘道，可接受通話和媒體，根據撥打的號碼，將來電路由回復回接收器的主集區。
    
### <a name="unified-contact-store-synthetic-transaction"></a>整合連絡人存放區綜合交易

整合連絡人存放區綜合交易會驗證商務用 Skype Server 以代表使用者從 Exchange 中取得連絡人的能力。
  
若要使用此綜合交易，必須符合下列條件：
  
- 必須設定 Lyss-Exchange 伺服器到伺服器的驗證。
    
- 測試使用者必須具有有效的 Exchange 信箱。
    
在符合這些條件之後，您可以執行下列 Windows PowerShell Cmdlet，將測試使用者的連絡人清單遷移至 Exchange：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

測試使用者連絡人清單若要遷移至 Exchange 可能需要一些時間。 若要監視遷移進度，可在沒有-Setup 標誌的情況下執行相同的命令列：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

完成遷移後，此命令列將會成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 綜合交易

可延伸的訊息和顯示狀態通訊協定 (XMPP) IM 綜合交易，需要您使用一或多個同盟網域來設定 XMPP 功能。
  
若要啟用 XMPP 綜合交易，您必須在可路由的 XMPP 網域中提供具有使用者帳戶的 XmppTestReceiverMailAddress 參數。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在此範例中，需要有商務用 Skype Server 規則，才能將 litwareinc.com 的郵件路由傳送至 XMPP 閘道。

> [!NOTE]
> XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../migration/migrating-xmpp-federation.md) 。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a> (VIS) 綜合交易的視頻 Interop 伺服器

[！注意] VIS) 綜合交易的「影片互通性 (伺服器」會要求您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)) 。 
  
若要安裝 VISSTSupportPackage.msi，請確定已安裝 msi 的 [系統需求]) 的相依性 (。 執行 VISSTSupportPackage.msi 以執行簡單安裝。 .msi 會安裝下列路徑中的所有檔案：「%ProgramFiles%\VIS 綜合交易支援套件」。
  
如需如何執行 VIS 綜合交易的詳細資訊，請參閱 [CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) Cmdlet 的檔。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>變更綜合交易的執行頻率
<a name="special_synthetictrans"> </a>

根據預設，綜合交易將會以設定的使用者每隔15分鐘執行。 綜合交易會依序在一組使用者中執行，以避免兩個綜合交易彼此衝突。 需要較長的時間間隔，以提供所有綜合交易完成的時間。
  
若要更經常執行綜合交易，請減少使用一組指定使用者執行的綜合交易，這樣測試就能在所需的時間範圍內完成，使測試能夠在所需的時間範圍內完成，而不需要偶爾的網路延遲。 如果需要執行更多綜合交易，請建立更多使用者集，以執行更多綜合交易。
  
若要變更綜合交易的執行頻率，請遵循下列步驟：
  
1. 開啟 System Center Operations Manager。 按一下 [製作區段]。 在 [製作) 中按一下 [規則] 區段 (
    
2. 在 [規則] 區段中，尋找名稱為「主要綜合交易處理常式效能收集規則」的規則
    
3. 以滑鼠右鍵按一下該規則，然後選取 [覆寫]，選取 [覆寫規則]，然後選取 [針對 class：集區觀察程式的所有物件]
    
4. 在 [覆寫屬性] 視窗中，選取 [參數名稱] [Frequency]，然後將覆寫值設定為所需的值。
    
5. 在同一個視窗中，選取需要套用此覆寫的管理套件
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用綜合交易的豐富記錄
<a name="special_synthetictrans"> </a>

綜合交易可用於協助識別系統中的問題。 例如，Test-CsRegistration 指令程式可能會提醒系統管理員使用者在向商務用 Skype Server 註冊時遇到問題。 不過，您可能需要更多詳細資料，以判斷失敗的實際原因。
  
因此，綜合交易會提供豐富的記錄。 使用豐富記錄，針對綜合交易 undertakes 的每個活動，會記錄下列資訊：
  
- 活動的開始時間。
    
- 活動完成的時間。
    
- 執行的動作 (例如，建立、加入或離開會議）;登入商務用 Skype Server; 送出立即訊息) 。
    
- 活動執行時所產生的資訊、詳細資料、警告或錯誤訊息
    
- SIP 註冊訊息。
    
- 活動執行時所產生的例外狀況記錄或診斷碼。
    
- 執行活動的實際結果。
    
這項資訊會在每次執行綜合交易時自動產生，但不會自動顯示或儲存至記錄檔。 如果您是手動執行綜合交易，您可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。 您可以從那裡使用下列兩種方法的其中一種，以 XML 或 HTML 格式在豐富記錄中儲存及/或查看錯誤訊息。 
  
若要取得疑難排解資訊，請指定 OutLoggerVariable 參數，後面接著所選擇的變數名稱：
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> ：請勿在變數名稱前面加上 $ 字元。 使用變數名稱，例如 RegistrationTest (不 $RegistrationTest) 。 
  
當您執行此命令時，會看到如下的輸出：
  
目標 Fqdn： atl-cs-001.litwareinc.com 結果：失敗延遲：00:00:00 錯誤訊息：此機器沒有任何已指派的憑證。 診斷：您可以針對這種失敗，存取更詳細的資訊，而不只是這裡顯示的錯誤訊息。 若要以 HTML 格式存取此資訊，請使用類似下列的命令，將儲存在變數 RegistrationTest 中的資訊儲存到 HTML 檔案：
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何其他能夠開啟 HTML/XML 檔的應用程式，來查看這些檔案。
  
在 System Center Operations Manager 內執行綜合交易會自動產生這些記錄檔失敗。 若執行失敗之前商務用 Skype Server PowerShell 能夠載入和執行綜合交易，將不會產生這些記錄。 
  
> [!IMPORTANT]
> 根據預設，商務用 Skype Server 會將記錄檔儲存至未共用的資料夾。 若要讓這些記錄立即可供存取，您應該共用此資料夾。 例如： \\ atl-觀察程式-001。 litwareinc com\WatcherNode。
