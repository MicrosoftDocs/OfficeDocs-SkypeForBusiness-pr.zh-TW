---
title: 設定監看員節點測試使用者及設定
ms.reviewer: ''
ms.author: jambirk
author: jambirk
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
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033672"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>設定監看員節點測試使用者及設定
 
**摘要：** 設定測試使用者帳戶與 skype for Business Server 綜合交易的監看員節點設定。
  
設定將作為監看員節點的電腦之後, 您必須：
  
1. 若要使用這些監看員節點[設定的測試使用者帳戶](test-users-and-settings-2019.md#testuser)。 如果您使用的交涉驗證方法，您也必須使用**Set-cstestusercredential**指令程式來啟用這些測試監看員節點上使用的帳戶。
    
2. 更新監看員節點組態設定。
    
## <a name="configure-test-user-accounts"></a>設定測試使用者帳戶
<a name="testuser"> </a>

測試帳戶不需要來代表實際的人員，但它們必須是有效的 Active Directory 帳戶。 此外，這些帳戶必須能夠 skype for Business Server，他們必須具備有效的 SIP 位址，和他們應該啟用 Enterprise voice （以使用 Test-cspstnpeertopeercall 綜合交易）。 
  
如果您使用 TrustedServer 驗證方法，您只需要是確定這些帳戶存在，並將其如所述設定。 您應該指定您想要測試每個集區，至少有三個測試使用者。 如果您使用的交涉驗證方法，您也必須使用 Set-cstestusercredential cmdlet 與 Skype for Business Server 管理命令介面來啟用這些測試帳戶來使用綜合交易。 執行此動作執行類似 （這些命令會假設已建立的三個 Active Directory 使用者帳戶，而且這些帳戶，已啟用 skype 商務伺服器） 的下列命令：
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

您必須包含不只 SIP 位址] 中，但也的使用者名稱和密碼。 如果您未包含的密碼，Set-cstestusercredential cmdlet 會提示您輸入該資訊。 可以使用前述的程式碼區塊中顯示 「 網域名稱 \ 使用者名稱 」 格式來指定的使用者名稱。
  
若要確認已建立測試使用者認證，從 Skype for Business Server 管理命令介面執行下列命令：
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

會傳回每位使用者的資訊類似這樣：
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設綜合交易來設定基本監看員節點

建立測試使用者之後，您可以使用類似如下的命令來建立監看員節點：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

此命令會建立新的監看員節點，會使用預設設定，並執行綜合交易的預設集合。 新的監看員節點也會使用測試使用者 watcher1@litwareinc.com、 watcher2@litwareinc.com 及 watcher3@litwareinc.com。 如果監看員節點使用 TrustedServer 驗證，三個測試帳戶可以是任何有效的使用者帳戶啟用 Active Directory 與 Skype for Business Server。 如果監看員節點使用交涉驗證方法，這些使用者帳戶必須也啟用監看員節點使用 Set-cstestusercredential cmdlet。
  
若要驗證目標的自動探索登入的集區已正確設定，而不是直接目標集區改為使用下列步驟：
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>設定擴充的測試

如果您想要啟用 PSTN 測試、 驗證與公用交換的電話網路的連線，您需要設定監看員節點時進行一些額外的設定。 首先，您必須建立與 PSTN 測試類型的測試使用者，藉由執行命令類似從 Skype for Business Server 管理命令介面：
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的結果必須儲存在變數中。 在這個範例中，變數是名為 $pstnTest。 
  
接下來，您可以使用**New-cswatchernodeconfiguration** cmdlet 建立測試類型 （儲存在變數 $pstnTest） 到 Skype for Business Server 集區的關聯。 例如，下列命令會建立新的監看員節點組態的集區 atl-cs-001.litwareinc.com，新增三個先前，建立測試使用者，並新增 PSTN 測試類型：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您尚未安裝 Skype for Business Server 核心檔案與 RTCLocal 資料庫監看員節點電腦上，上述命令會失敗。 
  
若要測試多個語音原則，您可以使用**New-csextendedtest** cmdlet 來建立每個原則延伸的測試。 提供使用者應設有所需的語音原則。 擴充的測試會傳遞至**New-cswatchernodeconfiguration** cmdlet，利用逗號分隔，例如：
  
-ExtendedTests @{新增 = $pstnTest1、 $pstnTest2、 $pstnTest3}
  
因為不使用 Tests 參數呼叫**New-cswatchernodeconfiguration**指令程式，針對新的監看員節點會啟用預設綜合交易 （和指定的擴充綜合交易）。 因此，監看員節點會測試下列元件：
  
- 註冊
    
- IM
    
- GroupIM
    
- P2PAV （對等音訊/視訊工作階段）
    
- AvConference （音訊/會議）
    
- 目前狀態
    
- ABS （通訊錄服務）
    
- ABWQ （通訊錄網頁服務）
    
根據預設，也不會測試下列元件：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity （Exchange 整合通訊）
    
- JoinLauncher
    
- MCXP2PIM （舊版的行動裝置立即訊息）
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN （PSTN 閘道的呼叫，指定為延伸測試）
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>新增與移除綜合交易

在設定監看員節點之後，您可以使用 Set-cswatchernodeconfiguration cmdlet 來新增或移除之節點的綜合交易。 例如，若要新增的監看員節點 PersistentChatMessage 測試，使用 Add 方法與類似這樣的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

您可以加入多項測試使用逗號分隔的測試名稱。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果一或多個這些測試 (例如，DataConference) 已啟用的監看員節點上，會發生錯誤。 在此情況下，您會收到類似如下的錯誤訊息：
  
Set-cswatchernodeconfiguration： 沒有重複的按鍵組合 'DataConference' 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' 索引鍵或唯一識別條件約束。
  
發生此錯誤時，將會不套用任何變更。 使用移除重複測試應重新執行命令。
  
若要從監看員節點移除綜合交易，請使用 Remove 方法。 例如，此命令可移除 ABWQ 測試從監看員節點：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

您可以使用 Replace 方法來取代所有目前已啟用測試，以下列一或多新測試。 例如，如果您想僅限來執行 IM 測試監看員節點，您可以使用下列命令，設定：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

當您執行此命令時，將會停用指定監看員節點上的所有綜合交易除了 IM 之外。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>檢視與測試監看員節點組態

如果您想要檢視已指派給監看員節點測試，請使用類似如下的命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令會傳回的資訊類似，根據已指派給節點的綜合交易：
  
註冊 IM GroupIM P2PAV AvConference 平台服務 PersistentChatMessage DataConference
> [!TIP]
> 若要依字母順序檢視綜合交易，請改為使用此命令： 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要確認已建立監看員節點，輸入下列命令從 Skype for Business Server 管理命令介面：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

您會得到的資訊類似這樣：
  
身分識別： atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com、 sip:watcher2@litwareinc.com...} ExtendedTests: {TestUsers = IList<System.String>;名稱 = PSTN 測試;尋找...} TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To 確認監看員節點已設定正確，下列從輸入命令 Skype for Business Server 管理命令介面：
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

此命令會測試您的部署中的每個監看員節點，並確認是否已完成下列動作：
  
- 已安裝登錄器角色
    
- 建立必要的登錄機碼 （當您執行 Set-cswatchernodeconfiguration cmdlet 時已完成）
    
- 您的伺服器執行正確版本的 Skype for Business Server
    
- 連接埠已正確設定
    
- 指派的測試使用者具有必要的認證
    
## <a name="managing-watcher-nodes"></a>管理監看員節點
<a name="testuser"> </a>

除了修改在監看員節點執行的綜合交易，您也可以使用**Set-cswatchernodeconfiguration** cmdlet 來執行其他兩項重要工作： 啟用及停用監看員節點，以及設定監看員節點以執行測試時使用內部的 Web Url 或外部網頁 Url。
  
根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。 有些時候，不過，您可能想要暫停的那些交易。 例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。 檢查網路連線，而這些交易都會失敗。 若要暫時停用監看員節點，請執行命令類似從 Skype for Business Server 管理命令介面：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令會停用綜合交易監看員節點 atl 監看員 001.litwareinc.com 上的執行。 若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 屬性可用於開啟或關閉監看員節點。 如果要永久刪除監看員節點，請使用 **Remove-CsWatcherNodeConfiguration** Cmdlet：
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

該命令會從指定的電腦，可防止該電腦自動執行的綜合交易，移除所有的監看員節點組態設定。 不過，命令不會解除安裝 System Center 代理程式檔案或 Skype for Business Server 系統檔案。
  
根據預設，監看員節點測試時使用的組織外部的網頁 Url。 不過，監看員節點也可以設定成使用組織的內部網頁 Url。 這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。 若要設定監看員節點以使用內部 Url，而不是外部 Url，請將 UseInternalWebURls 屬性設為 True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

重設為預設值為 False ($False) 的這個屬性會導致監看員再次使用外部 Url:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>綜合交易的特殊設定指示
<a name="special_synthetictrans"> </a>

大部分的綜合交易可以作為監看員節點上執行的是。 在大多數情況下，只要綜合交易新增至監看員節點組態設定，監看員節點可以開始使用其測試期間的綜合交易會傳遞。 不過，有一些綜合交易，需要特殊設定指示，如下列各節所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>資料會議綜合交易

如果您的監看員節點電腦位於周邊網路外，您可能無法執行資料會議綜合交易，除非您先停用網路的 Windows Internet Explorer® 網際網路瀏覽器 proxy 設定服務帳戶，請完成下列步驟：
  
1. 在監看員節點電腦上，按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**、 以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。
    
2. 在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您會看到命令視窗中顯示下列訊息：
  
BITSAdmin 已被取代，並不保證可在未來版本的 Windows。 由個位元 PowerShell cmdlet 現在提供的位元服務管理工具。
  
NO_PROXY 設為帳戶 NetworkService 網際網路 proxy 設定。 
  
(連線 = 預設值)
  
這則訊息會指出您已停用網路服務帳戶的 Internet Explorer proxy 設定。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 整合通訊綜合交易

Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者可連線的帳戶位於 Exchange 中的語音信箱。
  
測試使用者必須是預先設定的具有語音信箱帳戶。 
  
### <a name="persistent-chat-synthetic-transaction"></a>常設聊天室綜合交易

若要使用的常設聊天室的綜合交易，您必須先建立通道，並使用它的使用者權限授與測試。
  
您可以使用的常設聊天室的綜合交易來設定此通道： 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

您必須執行此安裝程式必須從執行工作，企業內：
  
- 如果從非伺服器電腦執行，請執行此 cmdlet 的使用者必須是角色型存取控制 (RBAC) CsPersistentChatAdministrators 角色的成員。
    
- 如果從伺服器本身執行，請執行此 cmdlet 的使用者必須是 RTCUniversalServerAdmins 群組的成員。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 對等通話綜合交易

Test-cspstnpeertopeercall 綜合交易會驗證撥出及接聽透過公用交換的電話網路 (PSTN) 通話的能力。
  
若要執行此綜合交易，您必須設定：
  
- 兩個 UC 啟用測試使用者 （發話者和收件者）。
    
- 每個使用者帳戶的直接內部撥號 (DID) 號碼。
    
- 允許受話者號碼的通話到達 PSTN 閘道的 VoIP 原則和語音路由。
    
- 接受來電和會路由傳送回受話者主集區，根據數通話的媒體的 PSTN 閘道的撥接。
    
### <a name="unified-contact-store-synthetic-transaction"></a>整合的連絡人存放區綜合交易

整合連絡人存放區綜合交易會驗證商務伺服器來從 Exchange 擷取代表使用者的連絡人的 Skype 的能力。
  
若要使用此綜合交易，必須符合下列條件：
  
- Lyss Exchange 必須設定伺服器對伺服器驗證。
    
- 測試使用者必須具備有效的 Exchange 信箱。
    
符合這些條件後，您可以執行下列 Windows PowerShell cmdlet 將測試使用者的連絡人清單移轉到 Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

它可能需要一些時間讓測試移轉至 Exchange 的使用者連絡人清單。 若要監控移轉進度，相同的命令列可執行沒有-設定旗標：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

這個命令列會成功完成移轉後。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 綜合交易

Extensible Messaging and Presence Protocol (XMPP) IM 綜合交易需要您使用一或多個同盟網域設定 XMPP 功能。
  
若要啟用 XMPP 綜合交易，您必須在路由傳送的 XMPP 網域使用者帳戶，以提供 XmppTestReceiverMailAddress 參數。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在這個範例中，Skype for Business Server 規則必須存在，才可將郵件路由傳送至 XMPP 閘道 litwareinc.com。

> [!NOTE]
> XMPP 閘道及 proxy 可在商務用 Skype Server 2015，但不再支援 skype for Business Server 2019。 如需詳細資訊，請參閱[移轉 XMPP 同盟](../migration/migrating-xmpp-federation.md)。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>視訊 Interop 伺服器 (VIS) 綜合交易

視訊 Interop 伺服器 (VIS) 綜合交易需要您下載並安裝綜合交易支援檔案 ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921))。 
  
若要安裝 VISSTSupportPackage.msi 確保相依性 （在系統需求） 的已安裝 msi。 執行 VISSTSupportPackage.msi 執行簡單的安裝。 .msi 安裝的所有檔案在下列路徑: 「 %ProgramFiles%\VIS 綜合交易支援套件 」。
  
如需有關如何執行 VIS 綜合交易的詳細資訊，請參閱[測試 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx)指令程式的說明文件。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>變更的執行的頻率的綜合交易
<a name="special_synthetictrans"> </a>

根據預設，綜合交易，會執行與已設定的使用者每隔 15 分鐘。 若要避免兩個綜合交易的彼此衝突的使用者的一組內循序執行綜合交易。 需要較長的時間間隔，才能提供完成的所有綜合交易的時間。
  
如果它是而言更頻繁地執行綜合交易，以便測試可以完成在某些緩衝區，以供偶爾網路延遲所需的時間範圍內，應該會減少使用一組特定的使用者執行的綜合交易數目。 如果執行更多的綜合交易是令人滿意，建立多個使用者設定來執行其他的綜合交易。
  
若要變更速率執行綜合交易的頻率，請遵循下列步驟：
  
1. 開啟 System Center Operations Manager。 按一下 [撰寫] 區段中。 按一下 [規則] 區段中的 （在撰寫）
    
2. 在 [規則] 區段中，尋找名稱為"Main 綜合交易自由效能集合 Rule"的規則
    
3. 以滑鼠右鍵按一下規則，並選取 [覆寫，選取 [覆寫規則，，然後選取 「 類別的所有物件： 集區監看員 」
    
4. 在 [覆寫的屬性] 視窗中，選取參數名稱 」 頻率 」，並將覆寫值所想要。
    
5. 在同一個視窗中，選取 [需要套用這個覆寫要管理組件
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用綜合交易的豐富記錄
<a name="special_synthetictrans"> </a>

綜合交易證明極幫助系統找出問題。 例如，Test-csregistration cmdlet 無法發出警示系統管理員的使用者已有困難註冊與 Skype for Business Server 的事實。 不過，可能需要其他細節，若要判斷實際失敗的原因。
  
基於這個理由，綜合交易提供豐富的記錄。 使用的綜合交易齊備，每個活動的豐富記錄會記錄下列資訊：
  
- 活動開始時間。
    
- 活動完成時間。
    
- 已執行的動作 (例如，建立、 加入或離開會議; 登入 Skype for Business Server; 傳送立即訊息)。
    
- 活動執行時所產生的資訊、詳細資料、警告或錯誤訊息
    
- SIP 登錄訊息。
    
- 例外狀況記錄或診斷碼活動執行時所產生。
    
- 執行活動的最終結果。
    
這項資訊會自動產生每次執行綜合交易，但不是會自動顯示或儲存記錄檔。 如果您以手動方式執行綜合交易，您可以使用之後包含 OutLoggerVariable 參數來指定的資訊會儲存在 Windows PowerShell 變數。 從那裡，您可以選擇使用兩種方法之一來儲存及/或檢視錯誤訊息中 rtf 登入 [XML] 或 [HTML 格式。 
  
若要擷取的疑難排解資訊，請指定之後包含 OutLoggerVariable 參數，您選擇的變數名稱：
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> ： 請勿不在開頭上 $ 字元變數的名稱。 使用變數名稱，例如 RegistrationTest (不 $RegistrationTest)。 
  
當您執行此命令時，您會看到類似的輸出：
  
目標 Fqdn: atl-cs-001.litwareinc.com 結果： 失敗延遲： 00:00:00 錯誤訊息： 這台機器沒有任何已指派的憑證。 診斷： 您可以存取此失敗更詳細的資訊比只是錯誤訊息，如下所示。 若要存取這項資訊以 HTML 格式，請使用類似以下的命令若要將儲存在變數 RegistrationTest 為 HTML 檔案中的資訊：
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以使用 Windows Internet Explorer、 Microsoft Visual Studio 中或任何其他應用程式能夠開啟 HTML/XML 檔案，以檢視這些檔案。
  
綜合交易，從執行 System Center Operations Manager 中的內容會自動產生失敗這些記錄檔。 如果執行作業失敗之前 Skype for Business Server PowerShell 是能夠載入及執行綜合交易，將不會產生這些記錄檔。 
  
> [!IMPORTANT]
> 根據預設，Skype for Business Server 會將記錄檔儲存至未共用資料夾。 若要讓這些記錄檔隨時都能存取，您應該共用此資料夾。 例如： \\atl-watcher-001.litwareinc.com\WatcherNode。 
