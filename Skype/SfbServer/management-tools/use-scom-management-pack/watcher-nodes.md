---
title: 安裝及設定觀察程式節點
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 摘要：為商務用 Skype 伺服器綜合交易安裝及設定監視節點。
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2020
ms.locfileid: "48599777"
---
# <a name="install-and-configure-watcher-nodes"></a>安裝及設定觀察程式節點
 
**摘要：** 為商務用 Skype 伺服器綜合交易安裝及設定監視節點。
  
觀察程式節點是定期執行商務用 Skype Server 綜合交易的電腦。 綜合交易是 Windows PowerShell Cmdlet，用來驗證主要使用者案例，例如登入或 exchange 立即訊息的功能是否如預期般運作。 若為商務用 Skype Server 2015，System Center Operations Manager 可以執行下表所示的綜合交易，包括三個綜合交易類型：
  
- **預設值** 監視節點預設會執行的綜合交易。 當您建立新的監看員節點時，您可以指定要執行節點的綜合交易。  (New-CsWatcherNodeConfiguration 指令程式所使用之測試參數的目的。 ) 如果在建立監看員節點時未使用 [測試] 參數，它會自動執行所有預設的綜合交易，而且不會執行任何非預設的綜合交易。 例如，這表示會將監視節點設定為執行 Test-CsAddressBookService 測試，但不會設定為執行 Test-CsExumConnectivity 測試。
    
- **非預設** 測試觀察程式節點預設不會執行。  (如需詳細資訊，請參閱預設類型的描述。 ) 不過，可以啟用監視節點來執行任何非預設的綜合交易。 當您使用 New-CsWatcherNodeConfiguration Cmdlet) ，或在建立監看員節點之後的任何時間建立監看員 (節點時，您就可以這麼做。 請注意，許多非預設的綜合交易都需要額外的設定步驟。 如需這些步驟的詳細資訊，請參閱 [綜合交易的特殊設定指示](test-users-and-settings.md#special_synthetictrans)。
    
- **擴充** 非預設綜合交易的特殊類型。 與其他綜合交易不同的是，延伸測試在每個行程中可以執行多次。 這在驗證行為時非常有用，例如多個公用交換電話網路 (PSTN) 的集區的語音路由。 您可以將多個擴充測試實例新增至監看員節點，以進行設定。
    
如需有關將其他綜合交易新增至監視節點之程式的詳細資訊，請參閱 [Configure a 監 The node To Run 綜合交易](watcher-nodes.md#enable_synthetic_trans)。 您也可以使用商務用 Skype Server 管理命令介面，從監看員節點中移除綜合交易。
  
監看員節點可用的綜合交易包括下列：
  
|**Cmdlet 名稱 (測試名稱)**|**描述**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |確認使用者可以查詢不在其連絡人清單中的使用者。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |確認使用者可以透過 HTTP 查詢不在其連絡人清單中的使用者。  <br/> |
|Test-CsAVConference (AvConference)   <br/> |確認使用者可以建立並參與音訊/視訊會議。  <br/> |
|Test-CsGroupIM (IM 會議)   <br/> |確認使用者可以在會議中傳送立即訊息，並參與有三位或更多位人員的立即訊息交談。  <br/> |
|Test-CsIM (P2P IM)   <br/> |確認使用者可以傳送對等立即訊息。  <br/> |
|Test-CsP2PAV (P2PAV)   <br/> |確認使用者可以撥出對等音訊通話 (僅訊號)。  <br/> |
|Test-CsPresence (Presence)  <br/> |確認使用者可以查看其他使用者的目前狀態。  <br/> |
|Test-CsRegistration (Registration)  <br/> |確認使用者可以登入商務用 Skype。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |確認使用者可以對企業外人員 (PSTN 號碼) 撥出及接聽通話。  <br/> |
|Test-CsASConference (ASConference)   <br/> |確認使用者可以建立及加入應用程式共用會議。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)   <br/> |確認音訊影片 Edge 伺服器能夠接受對等通話和會議呼叫的連線。  <br/> |
|Test-CsDataConference (DataConference)   <br/> |確認使用者可以參與資料共同作業會議 (包含諸如白板和輪詢等活動的線上會議) 。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)   <br/> |確認使用者可以撥打電話號碼加入會議。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)   <br/> |確認使用者可以撥打電話號碼加入會議。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)   <br/> |確認使用者可以連線至 Exchange 整合通訊 (UM) 。  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)   <br/> |確認使用者可以使用網址連結) 來建立及加入已排程的會議 (。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)   <br/> |確認行動裝置使用者可以註冊並傳送立即訊息。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)   <br/> |確認影片 Interop 伺服器已開啟，而且可以透過影片 SIP 主幹來處理傳入的連線。  <br/> **附注：** 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX 支援。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)   <br/> |確認使用者可以使用 Persistent Chat service 來交換郵件。  <br/> |
|Test-CsUcwaConference (UcwaConference)   <br/> |確認使用者可以透過 web 加入會議。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)   <br/> |確認可以透過整合連絡人存放區來存取使用者的連絡人。 整合連絡人存放區提供一種方式，讓使用者可以使用商務用 Skype Server 2015、Outlook 郵件和共同作業用戶端，以及/或 Outlook Web Access 來維護一組可以存取的連絡人。  <br/> |
|Test-CsXmppIM (XmppIM)   <br/> |確認立即訊息可以透過可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道傳送。  <br/> XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。  |

您不需要安裝觀察器節點即可使用 System Center Operations Manager。 如果您未安裝這些節點，您仍然可以在發生問題時，從商務用 Skype Server 2015 元件取得即時警示。  (元件和 User Management Pack 不會使用觀察器節點。 ) 不過，如果您想要使用作用中的監控管理元件來監視端對端案例，則必須要有觀察程式節點。
  
> [!NOTE]
> 管理員也可以手動執行綜合交易，而不需要使用或安裝 Operations Manager。 根據商務用 Skype Server 部署的大小，綜合交易可使用大量的電腦記憶體和處理器時間。 因此，建議您使用專用的電腦做為監看員節點。 例如，您不應該設定商務用 Skype Server 前端伺服器做為監看員節點。 觀察程式節點應該符合與商務用 Skype Server 拓撲中的任何其他電腦相同的基本硬體需求。 
  
> [!NOTE]
> 由於 Lync Server 2013 和商務用 Skype Server 2015 的核心系統檔案不能安裝在同一部電腦上，因此舊版 Lync Server 2013 觀察器節點不能在與商務用 Skype Server 2015 觀察器節點相同的機器上組合。 不過，商務用 Skype Server 2015 觀察器節點可以同時監視商務用 Skype Server 2015 和 Lync Server 2013。 這兩種產品版本都支援預設的綜合交易。 
  
Lync Server 2013 觀察程式節點可能會部署在企業內部或外部，以協助確認：
  
- 企業內使用者對集區的連線。
    
- 透過周邊網路連接，以供位於企業外部的遠端使用者使用。
    
- 對分公司設備的連線。
    
- 企業內和周邊網路中的 Lync Server 2013 的連線能力。
    
為了協助簡化管理，企業內部和外部都可以使用不同的驗證選項。 如需詳細資訊，請參閱 [設定監視節點以執行綜合交易](watcher-nodes.md#enable_synthetic_trans)。
  
若要將電腦設定為監視節點，您必須先完成下列必要條件： 
  
- 安裝 System Center Operations Manager 並匯入商務用 Skype Server 2015 管理套件。 您也必須先確認觀察程式節點電腦符合安裝商務用 Skype Server 2015 的所有必要條件。
    
- 在監看員節點電腦上安裝下列專案：
    
  - .NET Framework 4.5 的完整版本
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
符合先決條件後，您可以遵循下列步驟來設定監看員節點：
  
1. 在監看員節點電腦上安裝商務用 Skype Server 2015 核心檔案。
    
2. 在監看員節點電腦上安裝 System Center Operations Manager 代理程式。
    
3. 執行 Watchernode.msi 的可執行檔。
    
4. 使用 **New-CsWatcherNodeConfiguration** Cmdlet 來設定要由監看員節點採用的測試使用者帳戶。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安裝商務用 Skype Server 2015 核心檔案和 RTCLocal 資料庫

若要在電腦上安裝商務用 Skype Server 2015 核心檔案，請完成下列程式。 當您安裝核心檔案時，會自動安裝 RTCLocal 資料庫。 請注意，您不需要在觀察程式節點上安裝 SQL Server。 將會自動安裝 SQL Server Express。
  
若要安裝商務用 Skype Server 2015 核心檔案和 RTCLocal 資料庫：
  
1. 在監看員節點電腦上，依序按一下 [開始]、[所有程式] 及 [附屬應用程式]，再以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。
    
2. 在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。 請務必輸入商務用 Skype Server 安裝盤的適當路徑： D:\Setup.exe/BootstrapLocalMgmtTo 確認已成功安裝核心商務用 Skype Server 元件，請依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 管理命令**介面]。 在商務用 Skype Server 管理命令介面中，輸入下列 Windows PowerShell 命令，然後按 ENTER：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 當您第一次執行此命令時，不會傳回任何資料，因為您尚未設定任何的監看員節點電腦。 如果執行命令時未傳回錯誤，您可以假定商務用 Skype Server 安裝已成功完成。 
  
如果您的監看員節點電腦位於周邊網路內，您可以執行下列命令來驗證商務用 Skype Server 2015 的安裝：
  
根據您在組織中設定供使用的 PIN 碼原則數目而定，Get-CsPinPolicyYou 將會收到與下列類似的資訊：
  
身分識別：全域
  
描述：
  
MinPasswordLength：5
  
PINHistoryCount：0
  
AllowCommonPatterns： False
  
PINLifetime：0
  
MaximumLogonAttempts :
  
如果您看到 PIN 原則的相關資訊，核心元件已成功安裝。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在監看員節點上安裝 Operation Manager 代理程式檔案

類似于商務用 Skype 伺服器設定來報告元件警示，商務用 Skype Server 2015 監看員需要安裝 System Center Operations Manager 代理程式檔案。 這可讓您執行綜合交易，並將警示報告給 System Center Operations Manager 根管理伺服器。
  
若要安裝代理程式檔案，請遵循 [設定要監視之商務用 Skype Server 電腦](configure-computers-to-monitor.md)中所列的程式。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>設定監視節點以執行綜合交易
<a name="enable_synthetic_trans"> </a>

安裝 System Center Operations Manager 代理程式檔案之後，您必須設定觀察程式節點本身。 您採取的步驟會因您的監看員節點電腦位於周邊網路內還是周邊網路之外而異。 
  
當您設定監視節點時，您也必須選擇該節點要使用的驗證方法類型。 商務用 Skype Server 2015 可讓您選擇兩種驗證方法之一：「信任的伺服器」或「憑證驗證」。 下表顯示這兩種方法之間的差異：
  
||**描述**|**支援的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用憑證來模擬內部伺服器並略過驗證挑戰。  <br/> 適用于喜歡管理單一憑證的系統管理員，而不是每個監看員節點上的許多使用者密碼。  <br/> |在企業內。  <br/> 使用此方法，觀察者節點必須與受監控的集區位於相同的網域中。 如果觀察程式節點與集區位於不同的網域，請改用認證驗證。  <br/> |
|洽談  <br/> |在每個監看員節點上安全地將使用者名稱和密碼儲存在 Windows 認證管理員中。  <br/> 此模式需要較多的密碼管理，但為企業外部的觀察程式節點的唯一選項。 這些觀察器節點不能視為可信任的端點以進行驗證。  <br/> |在企業外。  <br/> 在企業內。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>設定監視節點以使用信任的伺服器驗證
<a name="enable_synthetic_trans"> </a>

如果您的監看員節點電腦位於周邊網路內，則使用受信任的伺服器驗證可以維護單一憑證，而不是使用大量的使用者帳戶密碼，以大幅減少管理工作。
  
若要設定信任的伺服器驗證，您必須先建立信任的應用程式集區，以裝載監看員節點電腦。 在您建立信任的應用程式集區之後，您必須將該監看員節點上的綜合交易，設定為執行為信任的應用程式。
  
> [!NOTE]
> 信任的應用程式是指以商務用 Skype Server 2015 的方式執行的受信任狀態的應用程式，但不是產品的內建部分。 信任狀態表示每次執行應用程式時，其驗證不會受到質疑。
  
若要建立信任的應用程式集區，請開啟商務用 Skype Server 管理命令介面，並執行類似如下的命令：
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 如需前述命令中參數的詳細資訊，請在商務用 Skype Server 管理命令介面提示字元中輸入下列命令： 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

在建立信任的應用程式集區之後，您可以使用 **New-CsTrustedApplication** Cmdlet 及類似如下的命令，設定監看員節點電腦以執行綜合交易，做為信任的應用程式：
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

完成此命令並建立信任的應用程式之後，您必須執行 **Enable-CsTopology** Cmdlet，以確保變更生效：
  
```PowerShell
Enable-CsTopology
```

監看員節點電腦帳戶需要能夠查詢某些綜合交易的 CMS。 若要允許這項功能，請將監看員節點的電腦帳戶新增至 RTCUniversalReadOnlyAdmins 安全性群組。 發生 AD 複寫之後，請重新開機電腦。
  
若要確認是否已建立新的受信任應用程式，請在商務用 Skype Server 管理命令介面提示字元處輸入下列專案：
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在監看員節點上設定預設憑證
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 驗證的每個監看員節點都必須有使用商務用 Skype Server 部署嚮導所指派的預設憑證。 
  
若要指派預設憑證：
  
1. 依序按一下 [開始]、[所有程式]、[商務用 Skype Server 2015] 及 [商務用 Skype 伺服器部署嚮導]。 
    
2. 在 [商務用 Skype 伺服器部署] 嚮導中，按一下 [安裝或更新商務用 Skype 伺服器系統]，然後按一下 [標題要求、安裝或指派憑證] 底下的 [執行]。 
    
> [!NOTE]
> 如果 [執行] 按鈕停用，需先按一下 [安裝本機組態存放區] 下方的 [執行]。 
  
執行下列其中一項：
  
- 如果您已經有可當作預設憑證使用的憑證，請按一下 [憑證嚮導] 中的 [預設]，然後按一下 [指派]。 遵循 [證書指派] 嚮導中的步驟，指派該憑證。
    
- 如果您需要要求憑證以使用預設憑證，請按一下 [要求]，然後依照憑證要求嚮導中的步驟要求憑證。 如果使用網頁伺服器憑證的預設值，則可獲得一個憑證並將其指派為預設憑證。
    
## <a name="install-and-configure-a-watcher-node"></a>安裝及設定監視節點
<a name="enable_synthetic_trans"> </a>

重新開機監看員節點電腦及設定憑證之後，您必須執行 Watchernode.msi 的檔案。  (您必須在同時安裝 Operations Manager 代理程式檔案和商務用 Skype Server 2015 核心元件的任何電腦上執行 Watchernode.msi。 )  
  
若要安裝及設定監視節點：
  
1. 依序按一下 [開始]、[所有程式]、[商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server 管理命令介面]，以開啟商務用 Skype Server 管理命令介面。 
    
2. 在管理命令介面中，輸入下列命令，然後按 ENTER (確定並指定您 Watchernode.msi) 副本的實際路徑：
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 您也可以從命令視窗執行 Watchernode.msi n。 若要開啟命令視窗，請按一下 [開始]、在 [命令提示字元] 上按滑鼠右鍵，然後按一下 [以系統管理員身分執行]。 當命令視窗開啟時，輸入與上述步驟2中所示的相同命令。 
  
> [!IMPORTANT]
> 在上述命令中，name/value 組 Authentication = TrustedServer 是區分大小寫的。 其輸入方式必須與顯示完全相同。 例如，此命令將會失敗，因為它未使用正確的字母大小寫： 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 模式只能與位於周邊網路內部的電腦搭配使用。 當觀察程式節點以 TrustedServer 模式執行時，系統管理員不需要維護電腦上的測試使用者密碼。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>設定監視節點以使用協商
<a name="enable_synthetic_trans"> </a>

如果您的監看員節點電腦位於周邊網路之外，您必須遵循稍有不同的程式，才能設定該監看員節點執行綜合交易：尤其是，您不應該建立信任的應用程式集區或受信任的應用程式。 這表示您將需要完成後續兩項工作。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC Local Read-Only Administrators 群組中的成員資格

如果您的監看員節點位於周邊網路之外，您必須在監看員節點上完成下列程式，以將網路服務帳戶新增至監看員節點電腦上的 RTC 本機唯讀管理員群組：
  
1. 按一下 [開始]，然後以滑鼠右鍵按一下 [電腦]，再按一下 [管理]。
    
2. 在伺服器管理員中，依序展開 [設定] 及 [本機使用者和群組]，然後按一下 [群組]。
    
3. 在 [群組] 窗格中，按兩下 [RTC Local Read-only Administrators]。
    
4. 在 [RTC Local Read-only Administrators 內容] 對話方塊中，按一下 [新增]。
    
5. 在 [選取使用者、電腦、服務帳戶或群組] 對話方塊中，按一下 [位置]。
    
6. 在 [位置] 對話方塊中，選取監看員節點電腦的名稱，然後按一下 [確定]。
    
7. 在 [輸入物件名稱來選取] 方塊中，輸入 [網路服務]，然後按一下 [確定]。
    
8. 在 [RTC Local Read-only Administrators 內容] 對話方塊中，按一下 [確定]，然後關閉 [伺服器管理員]。
    
9. 重新啟動監看員節點電腦。
    
### <a name="install-the-watcher-node-configuration-files"></a>安裝監看員節點設定檔

下一步是執行檔 Watchernode.msi： 
  
1. 開啟 Microsoft 商務用 Skype Server 2015 管理命令介面。 依序按一下 [開始]、[所有程式]、[Microsoft 商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server 管理命令介面]。 
    
2. 在商務用 Skype Server 管理命令介面中，輸入下列命令，然後按 ENTER (確定您 Watchernode.msi) 副本的實際路徑：
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 如先前所述，也可以從命令視窗執行 Watchernode.msi。 若要開啟命令視窗，請按一下 **[開始]**、在 **[命令提示字元]** 上按滑鼠右鍵，然後按一下 **[以系統管理員身分執行]**。 當命令視窗開啟時，輸入與上述步驟2中所示的相同命令。 
  
您可以在無法將監看員節點設為信任的應用程式集區時，使用交涉模式。 在此模式中，系統管理員必須在監看員節點上管理測試使用者密碼。
  

