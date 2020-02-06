---
title: 安裝和設定觀察程式節點
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
description: 摘要：針對商務用 Skype Server 合成事務安裝及設定觀察程式節點。
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816092"
---
# <a name="install-and-configure-watcher-nodes"></a>安裝和設定觀察程式節點
 
**摘要：** 針對商務用 Skype Server 合成事務安裝及設定觀察程式節點。
  
[觀察程式] 節點是定期執行商務用 Skype Server 綜合交易的電腦。 綜合交易是 Windows PowerShell Cmdlet，可驗證主要的使用者案例，例如登入或 exchange 立即訊息的功能是否如預期的方式運作。 如果是商務用 Skype Server 2015，系統中心作業管理員可以執行下表所示的綜合交易，包括三個綜合交易類型：
  
- **預設值**觀察程式節點預設會執行的綜合交易。 當您建立新的 [觀察程式] 節點時，您可以指定該節點要執行的綜合交易記錄。 （這是新的 CsWatcherNodeConfiguration Cmdlet 所使用的測試參數的用途）。如果您在建立觀察程式節點時不使用測試參數，就會自動執行所有預設的綜合交易，且不會執行任何非預設的綜合交易。 例如，這表示會將觀察程式節點設定為執行測試 CsAddressBookService 測試，但不會將其設定為執行測試 CsExumConnectivity 測試。
    
- **非預設值**測試觀察程式節點預設不會執行。 （如需詳細資訊，請參閱預設類型的描述）。不過，可以啟用觀察程式節點來執行任何非預設的綜合交易。 您可以在建立觀察程式節點（使用 New-CsWatcherNodeConfiguration Cmdlet），或在已建立觀察程式節點之後的任何時間執行此動作。 請注意，許多非預設的綜合交易需要額外的設定步驟。 如需這些步驟的詳細資訊，請參閱[綜合交易的特殊設定指示](test-users-and-settings.md#special_synthetictrans)。
    
- **延伸**非預設綜合交易的特殊類型。 與其他綜合交易不同，延長式測試可以在每一階段執行多次。 這在驗證行為（例如針對某個池的多個公用交換電話網絡（PSTN）語音路由）時很有用。 您只需將延伸測試的多個實例新增至觀察程式節點，就能進行這項設定。
    
如需有關新增其他綜合交易至觀察程式節點之程式的詳細資料，請參閱[設定觀察程式節點以執行綜合交易](watcher-nodes.md#enable_synthetic_trans)處理。 您也可以使用商務用 Skype Server Management Shell 來移除來自觀察程式節點的綜合交易。
  
可供觀察程式節點使用的綜合交易，包括下列各項：
  
|**Cmdlet 名稱（測試名稱）**|**說明**|
|:-----|:-----|
|Test-CsAddressBookService （ABS）  <br/> |確認使用者可以查詢不在連絡人清單中的使用者。  <br/> |
|CsAddressBookWebQuery （ABWQ）  <br/> |確認使用者可以透過 HTTP 找不在連絡人清單中的使用者。  <br/> |
|CsAVConference （AvConference）  <br/> |確認使用者可以建立並參與音訊/視訊會議。  <br/> |
|測試 CsGroupIM （IM 會議）  <br/> |確認使用者可以在會議中傳送立即訊息，並與三人或多位人員一起參與立即訊息交談。  <br/> |
|Test CsIM （P2P IM）  <br/> |確認使用者可以傳送對等立即訊息。  <br/> |
|CsP2PAV （P2PAV）  <br/> |確認使用者可以進行對等音訊通話（僅限通知）。  <br/> |
|CsPresence （目前狀態）  <br/> |確認使用者能夠查看其他使用者的目前狀態。  <br/> |
|Test CsRegistration （註冊）  <br/> |確認使用者可以登入商務用 Skype。  <br/> |
|CsPstnPeerToPeerCall （PSTN）  <br/> |確認使用者可以與企業外部的人員（PSTN 號碼）撥打電話和接聽來電。  <br/> |
|CsASConference （ASConference）  <br/> |確認使用者可以建立並參與應用程式共用會議。  <br/> |
|CsAVEdgeConnectivity （AVEdgeConnectivity）  <br/> |確認音訊視頻邊緣伺服器能夠接受對等通話和電話會議的連線。  <br/> |
|CsDataConference （DataConference）  <br/> |確認使用者可以參與資料共同作業會議（包括白板和投票等活動的線上會議）。  <br/> |
|CsDialinConferencing （DialinConferencing）  <br/> |確認使用者可以撥打電話號碼加入會議。  <br/> |
|CsDialinConferencing （DialinConferencing）  <br/> |確認使用者可以撥打電話號碼加入會議。  <br/> |
|CsExumConnectivity （ExumConnectivity）  <br/> |確認使用者可以連線到 Exchange 整合通訊（UM）。  <br/> |
|Test-CsGroupIM-TestJoinLauncher （JoinLauncher）  <br/> |確認使用者可以建立並加入排程的會議（透過網址連結）。  <br/> |
|CsMCXP2PIM （MCXP2PIM）  <br/> |確認行動裝置使用者可以註冊並傳送立即訊息。  <br/> |
|CsP2PVideoInteropServerSipTrunkAV （P2PVideoInteropServerSipTrunkAV）  <br/> |確認影片互通性伺服器已啟動，而且可以在視頻 SIP 主幹上處理傳入的連線。  <br/> **注意：** 商務用 Skype Server 2019 已不再提供舊版行動用戶端的 MCX 支援。 |
|CsPersistentChatMessage （PersistentChatMessage）  <br/> |確認使用者可以使用持續聊天服務來交換郵件。  <br/> |
|CsUcwaConference （UcwaConference）  <br/> |確認使用者可以透過網路加入會議。  <br/> |
|CsUnifiedContactStore （UnifiedContactStore）  <br/> |確認使用者的連絡人可以透過整合連絡人存放區存取。 「整合連絡人存放區」提供一種方式，讓使用者可以使用商務用 Skype Server 2015、Outlook 訊息與共同作業用戶端及/或 Outlook Web Access，來維護一組可存取的連絡人。  <br/> |
|CsXmppIM （XmppIM）  <br/> |確認立即訊息可透過可擴展訊息和目前狀態通訊協定（XMPP）閘道傳送。  <br/> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。  |

您不需要安裝觀察程式節點，就能使用 System Center Operations Manager。 如果您沒有安裝這些節點，您仍然可以在問題發生時，從商務用 Skype Server 2015 元件取得即時通知。 （元件和使用者管理套件不使用觀察程式節點）。不過，如果您想要使用主動監視管理套件監視端對端案例，則需要觀察程式節點。
  
> [!NOTE]
> 系統管理員也可以手動執行綜合交易，而不需使用或安裝 Operations Manager。 根據商務用 Skype Server 部署的大小而定，綜合交易可以使用大量的電腦記憶體和處理器時間。 因此，建議您使用專用電腦做為觀察程式節點。 例如，您不應該將商務用 Skype Server 前端伺服器設定為充當觀察者節點。 觀察程式節點應該符合商務用 Skype Server 拓朴中任何其他電腦的基本硬體需求。 
  
> [!NOTE]
> 舊版 Lync Server 2013 觀察程式節點無法在與商務用 Skype Server 2015 觀察程式節點相同的電腦上 collocated，因為 Lync Server 2013 和商務用 Skype Server 2015 的核心系統檔案無法安裝在同一部電腦上。 不過，商務用 Skype Server 2015 觀察程式節點可以同時監視商務用 Skype Server 2015 和 Lync Server 2013。 這兩個產品版本都支援預設的綜合交易記錄。 
  
Lync Server 2013 觀察程式節點可以部署在企業內部或外部，以協助驗證：
  
- 企業內部使用者的 [池連線]。
    
- 在企業外部工作的遠端使用者的周邊網路的連線能力。
    
- 連接至分支機搆裝置。
    
- 企業和周邊網路中的 Lync Server 2013 的連線能力。
    
為了協助簡化管理，在企業內部和外部都可以使用不同的驗證選項。 如需詳細資訊，請參閱[設定觀察程式節點以執行綜合交易](watcher-nodes.md#enable_synthetic_trans)。
  
若要將電腦設定為充當觀察者節點，您必須先完成下列先決條件： 
  
- 安裝 System Center Operations Manager，然後匯入商務用 Skype Server 2015 管理套件。 您也必須先確認觀察程式節點電腦符合安裝商務用 Skype Server 2015 的所有先決條件。
    
- 在觀察程式節點電腦上安裝下列專案：
    
  - 完整版的 .NET Framework 4。5
    
  - Windows 身分識別基礎
    
  - Windows PowerShell 3。0
    
在符合先決條件之後，您可以依照下列步驟來設定觀察程式節點：
  
1. 在觀察程式節點電腦上安裝商務用 Skype Server 2015 核心檔案。
    
2. 在觀察程式節點電腦上安裝 System Center Operations Manager 代理程式。
    
3. 執行 Watchernode 的可執行檔。
    
4. 使用**CsWatcherNodeConfiguration** Cmdlet 來設定要供觀察程式節點使用的測試使用者帳戶。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安裝商務用 Skype Server 2015 核心檔案和 RTCLocal 資料庫

若要在電腦上安裝商務用 Skype Server 2015 核心檔案，請完成下列程式。 當您安裝核心檔案時，系統會自動安裝 RTCLocal 資料庫。 請注意，您不需要在觀察程式節點上安裝 SQL Server。 SQL Server Express 將會自動安裝。
  
若要安裝商務用 Skype Server 2015 core 檔案和 RTCLocal 資料庫：
  
1. 在觀察程式節點電腦上，按一下 [開始]，按一下 [所有程式]，按一下 [附件]，以滑鼠右鍵按一下命令提示字元，然後按一下 [以系統管理員身分執行]。
    
2. 在主控台視窗中，輸入下列命令，然後按 ENTER 鍵。 請務必輸入商務用 Skype Server 設定檔案的適當路徑： D:\Setup.exe/BootstrapLocalMgmtTo 驗證已成功安裝核心商務用 Skype server 元件，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [商務用**skype server 2015**]，然後按一下 [**商務用 skype server 管理命令**介面]。 在商務用 Skype Server Management Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER 鍵：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 第一次執行此命令時，不會傳回任何資料，因為您尚未設定任何觀察程式節點電腦。 如果命令執行時不會傳回錯誤，您可以假設商務用 Skype Server 設定已順利完成。 
  
如果您的系統監控程式節點電腦位於您的周邊網路內，您可以執行下列命令來驗證商務用 Skype Server 2015 的安裝：
  
根據您在組織中設定使用的 PIN 原則數目，CsPinPolicyYou 將會收到類似以下內容的資訊：
  
身分識別：全域
  
說明
  
MinPasswordLength：5
  
PINHistoryCount：0
  
AllowCommonPatterns： False
  
PINLifetime：0
  
MaximumLogonAttempts :
  
如果您看到 PIN 原則的相關資訊，說明已成功安裝核心元件。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在觀察程式節點上安裝 Operation Manager 代理檔案

與商務用 Skype Server 設定類似，對於報告元件警示，商務用 Skype Server 2015 觀察程式節點需要安裝 System Center Operations Manager 代理檔案。 這可讓綜合交易執行，並將警示報告給 System Center Operations Manager 根管理伺服器。
  
若要安裝代理程式檔案，請按照[設定要監視之商務用 Skype Server 電腦](configure-computers-to-monitor.md)中所列的程式進行。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>設定觀察程式節點以執行綜合交易
<a name="enable_synthetic_trans"> </a>

安裝 System Center Operations Manager 代理檔案之後，您必須設定 [觀察程式] 節點本身。 您執行這項動作所採取的步驟會因您的觀察程式節點電腦是在周邊網路內或周邊網路以外的情況而有所不同。 
  
當您設定 [觀察程式] 節點時，您也必須選擇該節點要採用的驗證方法類型。 商務用 Skype Server 2015 可讓您選擇兩種驗證方法的其中一種：信任的伺服器或認證驗證。 下表顯示這兩種方法之間的差異：
  
||**說明**|**支援的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用憑證來類比內部伺服器並略過驗證難題。  <br/> 適用于喜歡管理單一憑證的系統管理員，而不是每個觀察程式節點上的許多使用者密碼。  <br/> |在企業內。  <br/> 使用這個方法，觀察程式節點必須與受監視的池位於同一個網域中。 如果觀察程式節點和池位於不同的網域中，請改用認證驗證。  <br/> |
|Negotiate  <br/> |在每個觀察程式節點上安全地儲存在 Windows 認證管理器中的使用者名稱和密碼。  <br/> 這個模式需要更多的密碼管理，但是企業外部之觀察程式節點的唯一選項。 這些觀察程式節點無法被視為受信任的端點以進行驗證。  <br/> |在企業外部。  <br/> 在企業內。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>將觀察程式節點設定為使用信任的伺服器驗證
<a name="enable_synthetic_trans"> </a>

如果您的 [觀察程式] 節點電腦位於周邊網路內，使用受信任的伺服器驗證，可維護單一憑證，而不是使用大量的使用者帳戶密碼，以大大減少管理工作。
  
若要設定信任的伺服器驗證，您必須先建立信任的應用程式池來託管觀察程式節點電腦。 在您建立受信任的應用程式池之後，您必須接著在該觀察程式節點上設定綜合交易，以執行為信任的應用程式。
  
> [!NOTE]
> 受信任的應用程式是以商務用 Skype Server 2015 （不是產品內建元件）的方式提供受信任狀態的應用程式。 [受信任的狀態] 表示應用程式在每次執行時不會受到驗證的挑戰。
  
若要建立信任的應用程式池，請開啟商務用 Skype Server 管理命令介面，並執行如下所示的命令：
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 如需上述命令中參數的詳細資訊，請從商務用 Skype Server Management Shell 提示輸入以下內容： 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

建立受信任的應用程式池之後，您就可以使用**新的 CsTrustedApplication** Cmdlet 和類似以下的命令，將 [觀察程式] 節點電腦設定為以受信任的應用程式執行綜合交易：
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

完成這個命令並建立受信任的應用程式後，您必須執行**Enable CsTopology** Cmdlet，以確保變更生效：
  
```PowerShell
Enable-CsTopology
```

觀察程式節點電腦帳戶必須能夠查詢 CMS，以尋找某些綜合交易。 若要允許這項功能，請將觀察程式節點的電腦帳戶新增至 RTCUniversalReadOnlyAdmins 安全性群組。 發生廣告複製之後，請重新開機電腦。
  
若要確認是否已建立新的受信任應用程式，請在商務用 Skype Server Management Shell 提示中輸入下列內容：
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在 [觀察程式] 節點上設定預設憑證
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 驗證的每個觀察程式節點，都必須有使用商務用 Skype Server 部署嚮導指派的預設憑證。 
  
若要指派預設憑證：
  
1. 按一下 [開始]，按一下 [所有程式]，按一下 [商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server 部署嚮導]。 
    
2. 在商務用 Skype Server 部署嚮導中，按一下 [安裝或更新商務用 Skype Server System]，然後按一下標題要求、安裝或指派憑證底下的 [執行]。 
    
> [!NOTE]
> 如果停用 [執行] 按鈕，您可能需要先按一下 [安裝本機設定儲存區] 下的 [執行]。 
  
請執行下列其中一項操作：
  
- 如果您已有可用作預設憑證的憑證，請按一下 [證書] 嚮導中的 [預設]，然後按一下 [指派]。 遵循 [證書指派] 嚮導中的步驟，將該憑證指派給您。
    
- 如果您需要要求使用預設憑證的憑證，請按一下 [要求]，然後依照 [證書申請] 嚮導中的步驟要求認證。 如果您使用的是 Web 服務器憑證的預設值，您會取得可指派為預設憑證的憑證。
    
## <a name="install-and-configure-a-watcher-node"></a>安裝和設定觀察程式節點
<a name="enable_synthetic_trans"> </a>

重新開機觀察程式節點電腦並設定憑證之後，您必須執行檔案 Watchernode。 （您必須在同時安裝 Operations Manager 代理程式和商務用 Skype Server 2015 核心元件的任何電腦上執行 Watchernode。） 
  
若要安裝和設定觀察程式節點：
  
1. 按一下 [開始]，按一下 [所有程式]，按一下 [商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server Management Shell]，即可開啟商務用 Skype Server 管理命令介面。 
    
2. 在管理命令介面中，輸入下列命令，然後按 ENTER （請確定並指定您 Watchernode 複本的實際路徑）：
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 您也可以從命令視窗執行 Watchernode n。 若要開啟命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。 當命令視窗開啟時，請輸入與上述步驟2所示的相同命令。 
  
> [!IMPORTANT]
> 在上述命令中，名稱/值對驗證 = TrustedServer 是區分大小寫的。 必須完全按照所示輸入。 例如，這個命令會因為不使用正確的字母大小寫而失敗： 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 模式只能與位於周邊網路內的電腦搭配使用。 當觀察程式節點以 TrustedServer 模式執行時，系統管理員不需要維護電腦上的測試使用者密碼。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>將觀察程式節點設定為使用 Negotiate
<a name="enable_synthetic_trans"> </a>

如果您的觀察程式節點電腦位於周邊網路之外，您必須遵循稍有不同的程式，才能設定該觀察程式節點執行綜合交易：尤其是，您不應該建立信任的應用程式池或信任的專案應用程式. 這表示您將需要完成後續兩項工作。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC 本機唯讀系統管理員群組中的成員資格

如果您的 [觀察程式] 節點位於周邊網路之外，您必須在 [觀察程式] 節點上完成下列程式，將 [網路服務] 帳戶新增到 [觀察程式] 節點電腦上的 RTC 本機唯讀系統管理員群組：
  
1. 按一下 [開始]，以滑鼠右鍵按一下 [電腦]，然後按一下 [管理]。
    
2. 在 [伺服器管理員] 中，展開 [設定]，展開 [本機使用者和群組]，然後按一下 [群組]。
    
3. 在 [群組] 窗格中，按兩下 [RTC 局部唯讀管理員]。
    
4. 在 [RTC 本機唯讀系統管理員屬性] 對話方塊中，按一下 [新增]。
    
5. 在 [選取使用者、電腦、服務帳戶或群組] 對話方塊中，按一下 [位置]。
    
6. 在 [位置] 對話方塊中，選取 [觀察程式] 節點電腦的名稱，然後按一下 [確定]。
    
7. 在 [輸入要選取的物件名稱] 方塊中，輸入 [網路服務]，然後按一下 [確定]。
    
8. 在 [RTC 本機唯讀系統管理員屬性] 對話方塊中，按一下 [確定]，然後關閉 [伺服器管理員]。
    
9. 重新開機觀察程式節點電腦。
    
### <a name="install-the-watcher-node-configuration-files"></a>安裝觀察程式節點設定檔

下一步是執行檔案 Watchernode： 
  
1. 開啟 Microsoft 商務用 Skype Server 2015 管理命令介面。 按一下 [開始]，按一下 [所有程式]，按一下 [Microsoft 商務用 Skype Server 2015]，然後按一下 [商務用 Skype Server Management Shell]。 
    
2. 在商務用 Skype Server 管理命令介面中，輸入下列命令，然後按 ENTER （請務必指定您 Watchernode 複本的實際路徑）：
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 如先前所述，Watchernode 也可以從命令視窗執行。 若要開啟命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下 [**命令提示**字元]，然後按一下 [**以系統管理員身分執行**]。 當命令視窗開啟時，請輸入與上述步驟2所示的相同命令。 
  
當無法將觀察程式節點設定為受信任的應用程式池時，就會使用 [協商] 模式。 在此模式中，系統管理員必須在 [觀察程式] 節點上管理測試使用者密碼。
  

