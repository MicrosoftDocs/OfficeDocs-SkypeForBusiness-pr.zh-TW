---
title: 商務用 Skype Server 2015 的環境需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要：針對商務用 Skype Server 2015 設定您的非伺服器需求。 在進行部署之前，您需要先設定多種不同的專案，包括 Active Directory、DNS、證書及 Fileshares。
ms.openlocfilehash: 60244391a04b1bab31464bd0ef0b804510e40955
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41678957"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的環境需求
 
**摘要：** 針對商務用 Skype Server 2015 設定您的非伺服器需求。 在進行部署之前，您需要先設定多種不同的專案，包括 Active Directory、DNS、證書及 Fileshares。
  
商務用 Skype Server 2015 的環境需求為何？ 嗯，我們將並非直接與伺服器相關的所有專案放在本主題中，因此您不需要執行任何按一下動作。 如果您正在尋找伺服器必備元件，您可以查看商務用[Skype server 2015 檔的伺服器需求](server-requirements.md)。[網路規劃](../../plan-your-deployment/network-requirements/network-requirements.md)也會另行說明。 否則，這就是我們在本文中所掌握的內容：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [網功能變數名稱稱系統（DNS）](environmental-requirements.md#DNS)
  
- [證書](environmental-requirements.md#Certs)
  
- [檔案共用](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

雖然伺服器與服務的許多設定資料都儲存在商務用 Skype Server 2015 的中央管理存放區中，但仍有一些專案儲存在 Active Directory 中：
  
|**Active Directory 物件**|**物件類型**|
|:-----|:-----|
|架構延伸  <br/> |使用者物件延伸  <br/> |
||Lync Server 2013 和 Lync Server 2010 的擴充功能，可維持與先前支援版本的向後相容性。  <br/> |
|資料  <br/> |使用者 SIP URI 和其他使用者設定  <br/> |
||應用程式的連絡人物件（例如回應群組應用程式和會議助理應用程式）。  <br/> |
||針對向後相容性發佈的資料。  <br/> |
||中央管理存放區的服務控制點（SCP）。  <br/> |
||Kerberos 驗證帳戶（選擇性電腦物件）。  <br/> |
   
### <a name="os-for-domain-controllers"></a>網網域控制站的作業系統

那麼，您可以使用哪些網網域控制站作業系統？ 我們有下列清單：

- Windows Server 2019 （您必須具備商務用 Skype Server 2015 累計更新5或更新版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
現在，您部署商務用 Skype Server 2015 的任何網域的網域功能層級，以及您部署商務用 Skype Server 2015 的任何目錄林功能層級，都必須是下列其中一項：

- Windows Server 2019 （您必須具備商務用 Skype Server 2015 累計更新5或更新版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
在這些環境中，您可以有唯讀的網網域控制站嗎？ 只要有可寫入的網網域控制站，就能確定。
  
現在，請務必知道商務用 Skype Server 2015 不支援單一標示的網域。 他們是什麼？ 如果您有一個標示為 [contoso. 當地] 的根網域，那將會有任何問題。 如果您的根網域剛剛命名為 local，即表示不起作用，因此結果不支援此功能。 我們已[在這個知識庫文章中](https://support.microsoft.com/kb/300684/en-us)撰寫了更多相關資訊。
  
商務用 Skype Server 2015 也不支援重新命名網域。 如果您確實要這樣做，您必須卸載商務用 Skype Server 2015、執行網域重新命名，然後重新安裝商務用 Skype Server 2015。
  
最後，您可能會使用鎖定的 AD DS 環境來處理網域，而這是完全正確的。 我們有更多關於如何在部署檔中將商務用 Skype Server 2015 部署到該類型的環境的資訊。
  
### <a name="ad-topologies"></a>廣告拓朴

商務用 Skype Server 2015 的支援拓撲如下：
  
- 單一目錄林與單一網域
    
- 具有單一樹狀結構和多個網域的單一目錄林
    
- 具有多個樹和不連續命名空間的單一目錄林
    
- 中央目錄林拓撲中的多個林
    
- 資原始目錄林拓朴中的多個目錄林
    
- 在商務用 Skype 資原始目錄林拓朴中有多個森林與 Exchange Online
    
- 包含商務用 Skype Online 和 Azure Active Directory Connect 的資原始目錄林拓撲中的多個林
    
我們有一些圖表和描述，可協助您判斷您的環境中有何種拓撲，或在安裝商務用 Skype Server 2015 之前，您可能需要進行的設定。 若要保持簡單，我們也會包含一個按鍵：
  
![是用於商務用 Skype 拓撲圖之圖示的索引鍵](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>單一目錄林與單一網域

![含有單一網域的 Active Directory 單一目錄林圖表](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不會變得簡單，因為它是單一網域林，這是常見的拓撲。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有單一樹狀結構和多個網域的單一目錄林

![單一目錄林、單一樹狀結構及 mutiple 網域圖表](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
這個圖表會再次顯示單一目錄林，但它也有一個或多個子網域（在這個特定範例中，有三個）。 因此，建立使用者的網域可能與部署到的網域商務用 Skype Server 2015 不同。 為什麼要擔心這個問題？ 請務必記住，當您部署商務用 Skype Server 前端池時，該池中的所有伺服器必須在單一網域中。 您可以透過商務用 Skype 伺服器支援 Windows 通用管理員群組，以進行跨網域管理。
  
回到上方的圖表，您可以看到一個網域中的使用者能夠從同一個網域或不同的網域存取商務用 Skype Server pool，即使這些使用者位於子域中也一樣。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多個樹和不連續命名空間的單一目錄林

![單一目錄林、多個樹和不連續的命名空間圖表](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
可能是您有一個類似此圖表的拓撲，您有一個目錄林，但在該樹林中是多個網域，有個別的 AD 命名空間。 如果是這種情況，此圖表就是一個很好的圖例，因為我們在三個不同網域中的使用者存取商務用 Skype Server 2015。 實線表示他們正在存取自己網域中的商務用 Skype 伺服器池，而虛線則表示它們將會在不同的樹狀結構中完全移至池中。
  
如您所見，同一個網域中的使用者、相同的樹狀結構，甚至是不同的樹狀結構，都能順利存取池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央目錄林拓撲中的多個林

![中央目錄林拓撲圖中的多個目錄林](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
商務用 Skype Server 2015 支援在中央林拓撲中設定多個林。 如果您不確定這是您所擁有的，拓撲結構中的中央目錄林會使用其中的物件來代表其他林中的使用者，並為樹林中的任何使用者承載使用者帳戶。
  
這會如何運作？ 嗯，目錄同步處理產品（例如 Forefront Identity Manager，或 FIM）會管理貴組織的使用者帳戶。 當您在林中建立或刪除帳戶時，該變更會同步處理到中央林中的對應連絡人。
  
顯然，如果您的 AD 基礎結構是就地移到此拓撲，可能並不容易，但如果您已經存在，或者仍在規劃您的林結構，這可能是一個不錯的選擇。 您可以將商務用 Skype Server 2015 部署集中在單一目錄林中，使用者可以在任何林中搜尋、溝通及查看其他使用者的目前狀態。 所有使用者連絡人更新都會自動使用同步處理軟體來處理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>商務用 Skype 資原始目錄林拓朴中的多個目錄林
<a name="BKMK_multipleforestopology"> </a>

![資原始目錄林拓撲圖中的多個目錄林](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
也支援資源林拓朴;這是林專用於執行伺服器應用程式的位置，例如 Microsoft Exchange Server 和商務用 Skype Server 2015。 此資原始目錄林也會託管作用中使用者物件的同步表示，但沒有登入的使用者帳戶。 因此，資原始目錄林是使用者物件所駐留之其他目錄林的共用服務環境，而且與資原始目錄林有一個林層級的信任關係。
  
請注意，Exchange Server 可以部署在與商務用 Skype 伺服器相同的資源林中，或在不同的林中。
  
若要在這種類型的拓朴中部署商務用 Skype Server 2015，您可以在資原始目錄林中為使用者林中的每個使用者帳戶建立一個停用的使用者物件（如果 Microsoft Exchange Server 已經在環境中，這可能會為您完成）。 接著您需要目錄同步處理工具（例如 Forefront Identity Manager 或 FIM），以透過其生命週期管理使用者帳戶。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>在商務用 Skype 資原始目錄林拓朴中有多個森林與 Exchange Online
<a name="BKMK_multipleforestopology"> </a>

這個拓朴與[商務用 Skype 資原始目錄林拓朴中多個林內](environmental-requirements.md#BKMK_multipleforestopology)所述的拓撲類似。
  
在此拓撲中，有一個或多個使用者目錄林，而商務用 Skype 伺服器則是在專用的資原始目錄林中部署。 Exchange Server 可以在內部部署的同一資原始目錄林中或不同的林中，且已設定為與 Exchange Online 混合式，或者電子郵件服務可能會以 Exchange Online 專為內部部署帳戶提供。 沒有適用于此拓朴的圖表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>包含商務用 Skype Online 和 Azure Active Directory Connect 的資原始目錄林拓撲中的多個林
<a name="BKMK_multipleforestopology"> </a>

![顯示兩個 AD 目錄林、一個使用者目錄林和一個資原始目錄林。 兩個目錄林具有信任關係。 它們會與 Office 365 （使用 Azure AD Connect）同步處理。 所有使用者都可透過 Office 365 啟用商務用 Skype。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在這個案例中，有多個目錄林內部部署，有一個資原始目錄林拓撲。 Active Directory 目錄林之間有完全信任關係。 Azure Active Directory Connect 工具是用來同步處理內部部署使用者目錄林與 Office 365 之間的帳戶。
  
 組織也有 Office 365，並使用[Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836)將其內部部署帳戶與 Office 365 同步處理。 啟用商務用 Skype 的使用者可透過 Office 365 和商務用 Skype Online 來啟用。 商務用 Skype Server 未部署于內部部署。
  
單一登入驗證是由位於使用者林中的 Active Directory 同盟服務群所提供。
  
在這種情況下，支援部署 Exchange 內部部署、Exchange Online、混合式 Exchange 解決方案，或是根本不部署 Exchange。 （圖表只會顯示 Exchange 內部部署，但也完全支援其他 Exchange 解決方案）。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>使用混合式商務用 Skype 的資原始目錄林拓撲結構中的多個目錄林
<a name="BKMK_multipleforestopology"> </a>

在此案例中，有一個或多個內部部署使用者目錄林，且商務用 Skype 是在專用的資原始目錄林中部署，且是針對商務用 Skype Online 設定混合式模式。 Exchange Server 可以在同一資原始目錄林或不同的林中部署內部部署，而且可以針對 Exchange Online 進行混合式設定。 或者，電子郵件服務可能會以 Exchange Online 專為內部部署帳戶提供。
  
如需詳細資訊，請參閱[設定混合式商務用 Skype 的多林環境](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>網功能變數名稱稱系統（DNS）
<a name="DNS"> </a>

商務用 Skype Server 2015 需要 DNS，原因如下：
  
- DNS 可讓商務用 Skype Server 2015 探索內部伺服器或池，以便進行伺服器對伺服器的通訊。
    
- DNS 可讓用戶端電腦探索要用於 SIP 交易的前端池或標準版伺服器。
    
- 它會將會議的簡單 Url 與主持這些會議的伺服器進行關聯。
    
- DNS 允許外部使用者與用戶端電腦連線到您的邊緣伺服器，或 HTTP 反向 proxy （適用于立即訊息（IM）或會議）。
    
- 它可讓未登入的整合通訊（UC）裝置探索可執行裝置更新 web 服務的前端池或標準版伺服器來取得更新及傳送記錄。
    
- 使用 DNS 可讓行動用戶端自動探索 web 服務資源，而不需要使用者在其裝置設定中手動輸入 Url。
    
- 在 DNS 負載平衡中使用。
    
請務必注意，商務用 Skype Server 2015 不支援國際化功能變數名稱（IDNs）。
  
切記，請務必記住，DNS 中的任何名稱都與商務用 Skype Server 2015 所使用的任何伺服器上設定的電腦名稱稱相同。 具體說來，在環境中不能有任何短名稱，且必須有 [拓撲建立器] 的 Fqdn。
  
這看起來對已加入網域的任何電腦而言都是合乎邏輯的，但如果您有沒有加入網域的邊緣伺服器，則它可能會有一個短名稱的預設值，沒有網域尾碼。 在 DNS 或邊緣伺服器上，或在任何商務用 Skype Server 2015 server 或 pool 中，請確定這種情況不是如此。
  
而且絕對不要使用 Unicode 字元或底線。 標準字元（A-z、a-z、0-9 和連字號）是外部 DNS 和公用憑證授權單位所支援的字元（您必須將 Fqdn 指派給憑證中的 SN，別忘了），因此如果有的話，您將會有大量的 grief。您可以記住這一點。
  
如需進一步瞭解網路的 DNS 需求，請參閱我們規劃檔的 [[網路](../../plan-your-deployment/network-requirements/network-requirements.md)] 區段。
  
## <a name="certificates"></a>證書
<a name="Certs"> </a>

在部署前，您可以執行的其中一個最重要的動作就是確定您的憑證有序。 商務用 Skype Server 2015 需要傳輸層安全性（TLS）和相互傳輸層安全性（MTLS）連線的公開金鑰基礎結構（PKI）。 一般來說，若要以標準化的方式安全地通訊，商務用 Skype Server 會使用由憑證授權單位（Ca）頒發的憑證。
  
以下是商務用 Skype Server 2015 使用憑證的一些事項：
  
- 用戶端與伺服器之間的 TLS 連接
    
- 伺服器之間的 MTLS 連線
    
- 同盟 usin 合作夥伴的自動 DNS 探索
    
- 立即訊息（IM）的遠端使用者存取權
    
- 外部使用者存取音訊/視頻（AV）會話、應用程式共用和會議
    
- 與 web 應用程式和 Outlook Web Access （OWA）交談
    
因此，必須擁有認證規劃。 現在，讓我們來看看要求證書時必須牢記的一些事項清單：
  
- 所有伺服器憑證都必須支援伺服器授權（伺服器 EKU）。
    
- 所有伺服器憑證都必須包含 CRL 發佈點（CDP）。
    
- 所有憑證都必須使用作業系統支援的簽名演算法進行簽署。 商務用 Skype Server 2015 支援 SHA-1 和 SHA-1 組成的摘要大小（224、256、384和512位），並符合或超過作業系統需求。
    
- 運行商務用 Skype Server 2015 的內部伺服器支援自動註冊。
    
- 商務用 Skype Server 2015 Edge 伺服器不支援自動註冊。
    
- 當您將 web 型證書申請提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 的電腦，以 SP2 或 Windows XP 提交。
    
> [!NOTE]
> 雖然 KB922706 針對使用 Windows Server 2003 認證服務 web 登記來解決網頁憑證的問題提供支援，但它不能使用 Windows Server 2008、Windows Vista 或 Windows 7 來要求認證從 Windows Server 2003 CA。 
  
> [!NOTE]
> 不支援使用 RSASSA-PSS 簽章演算法，而且可能會導致登入和來電轉接問題等錯誤，以及其他問題。 

> [!NOTE]
> 商務用 Skype Server 2015 不支援 CNG 憑證。
  
- 支援1024、2048和4096的加密金鑰長度。 建議使用2048和更大的金鑰長度。
    
- 預設摘要（即雜湊簽章）演算法是 RSA。 也支援 ECDH_P256、ECDH_P384 及 ECDH_P521 演算法。
    
所以，考慮到從 CA 申請證書，這是一個很大的用處。 我們將在下方提供一些進一步的指導方針，讓您的規劃盡可能順利進行。
  
### <a name="certificates-for-your-internal-servers"></a>內部伺服器的憑證

您將需要大多數內部伺服器的憑證，而且最可能的是，您可以從內部 CA （位於您網域中的 CA）取得它們。 如果您想要的話，您可以從外部 CA （位於網際網路的一級）要求這些憑證。 如果您不知道應該移至哪個公用 CA，您可以查看 [[整合通訊憑證合作夥伴](/SkypeForBusiness/certification/services-ssl)] 清單。
  
當商務用 Skype Server 2015 與其他應用程式和伺服器通訊時（例如 Microsoft Exchange Server），您也會需要證書。 這顯然會需要是其他這些 app 和伺服器可以以支援的方式使用的憑證。 商務用 Skype Server 2015 和其他 Microsoft 產品都支援「開啟授權（OAuth）」通訊協定，以進行伺服器對伺服器驗證和授權。 如果您對此感興趣，我們會針對 OAuth 和商務用 Skype Server 2015 進行額外的規劃文章。
  
商務用 Skype Server 2015 也包含使用 SHA-256 加密雜湊函數簽署（不需要）憑證的支援。 若要使用 SHA-256 支援外部存取，外部憑證必須由使用 SHA-256 的公用 CA 頒發。
  
若要嘗試簡單明瞭，我們已將標準版伺服器、前端池及其他角色的憑證需求放在下清單格中，並在範例中使用虛構的 contoso.com （您可能會使用某個專案）。對於您的環境）。 這些都是所有標準的 web 伺服器憑證，其中包含無法匯出的私用金鑰。 需要注意的一些其他事項：
  
- 當您使用 [憑證] 嚮導來申請證書時，系統會自動設定 [伺服器增強型金鑰用法（EKU）]。
    
- 每個證書易記名稱在電腦存放區中都必須是唯一的。
    
- 根據下面的範例名稱，如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，則需要將它們新增至證書的消費者備用名稱（SAN）。
    
標準版伺服器的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|**批註**|
|:-----|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |伺服器的 [池] 和 [FQDN] FQDN  <br/> 如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。  <br/> 如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。  <br/> |SN = se01;SAN = se01  <br/> 如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |在標準版伺服器標準版伺服器上，伺服器 FQDN 與池 FQDN 相同。  <br/> 此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。  <br/> 您也可以使用此憑證進行伺服器對伺服器驗證。  <br/> |
|網頁內部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 相同）  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = se01;SAN = se01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = se01;SAN = se01;SAN =\*. contoso.com  <br/> |您無法在拓撲建立器中覆寫內部網頁 FQDN。  <br/> 如果您有多個符合簡單的 Url，您必須將它們全部納入 San 中。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
|網頁外部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •撥入式簡易 URL  <br/> •符合每個 SIP 網域的簡單 Url  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = se01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = se01;SAN = webcon01;SAN =\*. contoso.com  <br/> |如果您有多個 [符合簡單的 Url]，您就可以將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
   
前端池中的前端伺服器憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|**批註**|
|:-----|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |伺服器的 [池] 和 [FQDN] FQDN  <br/> 如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。  <br/> 如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。  <br/> |SN = eepool;SAN = eepool;SAN = ee01  <br/> 如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。  <br/> 您也可以使用此憑證進行伺服器對伺服器驗證。  <br/> |
|網頁內部  <br/> |池的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 不同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 池 FQDN  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = ee01;SAN = ee01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01;SAN = ee01;SAN =\*. contoso.com  <br/> |如果您有多個 [符合簡單的 Url]，您就可以將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
|網頁外部  <br/> |池的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = ee01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01;SAN = webcon01;SAN =\*. contoso.com  <br/> |如果您有多個 [符合簡單的 Url]，您就可以將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
   
主管的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |主管池  <br/> |主管的 FQDN，控制器池的 FQDN。  <br/> 如果此池是用戶端的自動登入伺服器，且群組原則中需要嚴格的 DNS 相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）的專案。  <br/> |pool.contoso.com;SAN = dir01  <br/> 如果此主管池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |
|網頁內部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 相同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 池 FQDN  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = dir01;SAN = dir01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01;SAN = dir01 =\*. contoso.com  <br/> |
|網頁外部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •符合每個 SIP 網域的簡單 Url  <br/> •撥入式簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |控制器外部 web FQDN 必須與前端池或前端伺服器不同。  <br/> SN = dir01;SAN = directorwebcon01 （contoso .com） SAN = 符合 contoso;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01;SAN = directorwebcon01 =\*. contoso.com  <br/> |
   
獨立中繼伺服器的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成員伺服器的 FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
Survivable 分支裝置的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |裝置的 FQDN  <br/> |呼吸.\<sipdomain\> （每個 SIP 網域只需要一個專案）  <br/> |SN = sba01;SAN = sip. .com;SAN = sip. .com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>持久聊天伺服器的憑證

安裝持久聊天伺服器時，您會需要與商務用 Skype Server 2015 內部伺服器所使用的 CA 所頒發的憑證。 需要針對執行持續聊天 Web 服務的每個伺服器完成檔案上傳/下載。 我們強烈建議您在開始持續進行的聊天安裝之前，您有必要的憑證，而且如果您的 CA 是外部的，則更是如此（這些內容可能需要一些時間才會發出）。
  
### <a name="certificates-for-external-user-access-edge"></a>外部使用者存取權的憑證（邊緣）

商務用 Skype Server 2015 支援使用**單一公用憑證**來存取和網路會議 Edge 外部介面，加上 a/V 驗證服務，這一切都是透過 Edge 伺服器提供。 您的邊緣內部介面通常會使用內部 CA 所頒發的私人憑證，但如果您想要的話，您也可以使用公用憑證（如果它來自受信任的 CA）。
  
您的反向 proxy （RP）也會使用公用憑證，並使用 HTTP （或更精確地說是 HTTP 上的 TLS），將來自您的 RP 的通訊加密到用戶端，以及 RP 到內部伺服器。
  
### <a name="certificates-for-mobility"></a>行動性憑證

如果您要部署行動裝置，且支援行動用戶端的自動探索，您必須在您的憑證上加入一些其他的主題替換名稱專案，以支援行動用戶端的安全連線。
  
哪些是哪一種證書？ 您必須在以下位置，在 [憑證] 中自動探索的 SAN 名稱：
  
- 主管池
    
- 前端集區
    
- 反向 Proxy
    
我們將在下表列出每個表格的詳細資訊。
  
現在，這是一個很好的預先規劃，但有時候您已部署商務用 Skype Server 2015，而不想要部署行動性，而且當您在您的環境中已經有憑證時，就會出現這種情況。 透過內部 CA 重新頒發它們通常相當簡單，但使用公用 CA 的公用憑證，可能會有更多的 pricy。
  
如果這是您要查看的內容，而且如果您有許多 SIP 網域（這會增加 SAN 的費用），您可以設定您的反向 proxy，將 HTTP 用於初始自動探索服務要求，而不是使用 HTTPS （這是預設值）。配置）。 行動規劃主題有更多關於此內容的資訊。
  
主管池與前端池的憑證需求：
  
|**說明**|**SAN 專案**|
|:-----|:-----|
|內部自動探索服務 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
您也可以使用 SAN =\*。\<sipdomain\>
  
反向 Proxy （公用 CA）證書需求：
  
|**說明**|**SAN 專案**|
|:-----|:-----|
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
這個 SAN 需要指派給您在反向 proxy 上指派給 SSL 偵聽程式的憑證。
  
> [!NOTE]
> 您的反向 proxy 偵聽程式會將 San 用於您的外部 Web 服務 URL。 例如，如果您已部署 Director （選擇性），一些範例就會是 SAN = skypewebextpool01 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>檔案共用
<a name="Fileshare"> </a>

商務用 Skype Server 2015 可以針對所有檔案儲存空間使用相同的檔案共用。 您必須牢記下列事項：
  
- 檔案共用必須是直接附加的儲存空間（DAS）或儲存區域網路（SAN），這包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。 如需 Windows Server 2012 DFS 的進一步閱讀，請參閱[此 DFS 頁面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 我們建議使用共用的群集來共用檔案。 如果您使用的是，您應該群集 Windows Server 2012 或 Windows Server 2012 R2。 Windows Server 2008 R2 也是可接受的。 為什麼是最新的 Windows？ 較舊的版本可能不具備啟用所有功能的適當許可權。 您可以使用 [群集管理員] 來建立檔案共用，以及[如何在群集專案上建立檔案共用](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster)，將會協助您處理這些詳細資料。
    
> [!CAUTION] 
> 您應該知道，不支援使用 network 附加儲存空間（NAS）作為檔案共用，所以請使用上述其中一個選項。 
  

