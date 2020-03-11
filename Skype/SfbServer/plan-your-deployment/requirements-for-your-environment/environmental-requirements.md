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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要：設定商務用 Skype Server 2015 的非伺服器需求。 進行部署之前，您需要先設定許多專案，包括 Active Directory、DNS、證書和 Fileshares。
ms.openlocfilehash: 164f4b8037c972907eb6d1375f77b3cc350959e5
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572801"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的環境需求
 
**摘要：** 設定商務用 Skype Server 2015 的非伺服器需求。 進行部署之前，您需要先設定許多專案，包括 Active Directory、DNS、證書和 Fileshares。
  
商務用 Skype Server 2015 的環境需求為何？ 我們已將並非直接與伺服器相關聯的所有專案放入本主題，所以您不需要這麼做。 如果您正在尋找伺服器必要條件，您可以查看[商務用 Skype server 2015 doc 的伺服器需求](server-requirements.md)。[網路規劃](../../plan-your-deployment/network-requirements/network-requirements.md)也會另外進行記錄。 否則，這是我們在本文中所掌握的功能：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [憑證](environmental-requirements.md#Certs)
  
- [檔案共用](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

當伺服器和服務的大量設定資料儲存在商務用 Skype Server 2015 的中央管理存放區中時，有些專案仍會儲存在 Active Directory 中：
  
|**Active Directory 物件**|**物件類型**|
|:-----|:-----|
|架構擴充  <br/> |使用者物件擴充  <br/> |
||Lync Server 2013 和 Lync Server 2010 的延伸部分，以維護先前支援版本的回溯相容性。  <br/> |
|資料  <br/> |使用者 SIP URI 及其他使用者設定  <br/> |
||應用程式的連絡人物件（如回應群組應用程式和會議助理應用程式）。  <br/> |
||為了回溯相容性發佈的資料。  <br/> |
||中央管理存放區的服務控制點（SCP）。  <br/> |
||Kerberos 驗證帳戶（選擇性的電腦物件）。  <br/> |
   
### <a name="os-for-domain-controllers"></a>網域控制站的作業系統

那麼，您可以使用哪些網域控制站作業系統？ 我們有下列清單：

- Windows Server 2019 （您必須具有商務用 Skype Server 2015 累計更新5或更新版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
現在，您部署商務用 Skype Server 2015 的任何網域的網域功能層級，以及您部署商務用 Skype Server 2015 的任何樹系的樹系功能層級，都必須是下列其中一項：

- Windows Server 2019 （您必須具有商務用 Skype Server 2015 累計更新5或更新版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
在這些環境中，是否可以擁有唯讀的網域控制站？ 請確定，只要還有其他可寫入的網域控制站與商務用 Skype Server 位於相同的網站上。
  
現在，請務必瞭解商務用 Skype Server 2015 不支援單一標示的網域。 它們是什麼？ 如果您有一個標示為 contoso 的根網域，就會正常。 如果您擁有的根功能變數名稱只有命名為 [本機]，就不會使用，因此不支援此功能。 您還可以[在此知識庫文章中](https://support.microsoft.com/kb/300684/en-us)寫入這項資訊。
  
商務用 Skype Server 2015 也不支援重新命名網域。 如果您真的會這麼做，您將需要卸載商務用 Skype Server 2015，請執行網域重新命名，然後重新安裝商務用 Skype Server 2015。
  
最後，您可能會使用鎖定的 AD DS 環境處理網域，這完全正確。 關於如何在部署檔中將商務用 Skype Server 2015 部署到該環境中的詳細資訊，請稍候。
  
### <a name="ad-topologies"></a>AD 拓撲

商務用 Skype Server 2015 支援的拓撲包括：
  
- 具單一網域的單一樹系
    
- 具單一樹狀結構和多個網域的單一樹系
    
- 具多重樹狀結構和斷續命名空間的單一樹系
    
- 中央樹系拓撲中的多重樹系
    
- 資源樹系拓撲中的多重樹系
    
- 使用 Exchange Online 的商務用 Skype 資源樹系拓撲中的多個樹系
    
- 具有商務用 Skype Online 和 Azure Active Directory Connect 之資源樹系拓撲中的多個樹系
    
我們有圖表和描述，可協助您決定環境中所具備的拓撲，或在安裝商務用 Skype Server 2015 之前必須設定的專案。 為了簡化，我們也包含重要：
  
![為商務用 Skype 拓朴圖表所用的圖示的索引鍵](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具單一網域的單一樹系

![具有單一網域之 Active Directory 單一樹系圖表](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不會變得簡單，它是單一網域樹系，這是常見的拓撲。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具單一樹狀結構和多個網域的單一樹系

![單一樹系、單一樹系和 mutiple 網域圖表](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
這個圖表會再次顯示單一樹系，但也有一個或多個子網域（此特定範例中有三個）。 因此，使用者建立所在的網域可能與將商務用 Skype Server 2015 部署在不同的網域。 為什麼要擔心呢？ 請務必記住，當您部署商務用 Skype Server 前端集區時，該集區中的所有伺服器都必須在單一網域中。 您可以透過商務用 Skype 伺服器支援 Windows 通用管理員群組，以進行跨網域管理。
  
回到上圖，您可以看到來自一個網域的使用者可以從同一個網域或不同的網域存取商務用 Skype 伺服器集區，即使這些使用者位於子網域中也是一樣。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具多重樹狀結構和斷續命名空間的單一樹系

![單一樹系、多樹系和脫節命名空間圖表](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
這可能是您已有類似于此圖表的拓撲，您有一個樹系，但在該樹系中有多個網域，具有不同的 AD 命名空間。 如果是這種情況，此圖表是一個很好的圖解，因為我們有三個不同網域存取商務用 Skype Server 2015 的使用者。 實線表示他們在自己的網域中存取商務用 Skype 伺服器集區，而虛線表示他們只會進入其他樹狀目錄中的集區。
  
如您所見，相同網域中的使用者、相同的樹狀目錄，甚至不同的樹狀目錄，都能夠順利存取集區。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央樹系拓撲中的多重樹系

![中央樹系拓撲圖表中的多個樹系](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
商務用 Skype Server 2015 不支援在中央樹系拓撲中設定多個樹系。 如果您不確定這是您擁有的內容，拓撲中的中央樹系會使用其中的物件來代表其他樹系中的使用者，並為樹系中的任何使用者主控使用者帳戶。
  
這是如何運作的？ 嗯，目錄同步處理產品（例如 Forefront Identity Manager 或 FIM）會管理組織的使用者帳戶，使其成為現有的使用者帳戶。 建立或刪除樹系中的帳戶時，此變更會同步到中央樹系中的對應連絡人。
  
很清楚的是，如果您的 AD 基礎結構已就地移至此拓撲，則可能不容易，但是如果您已存在，或仍在規劃樹系基礎結構，則這是一個不錯的選擇。 您可以在單一樹系中將商務用 Skype Server 2015 部署集中在一起，使用者可以搜尋、通訊和查看任何樹系中的其他使用者的目前狀態。 所有使用者連絡人更新都會以同步處理軟體自動進行處理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>商務用 Skype 資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

![資源樹系拓撲圖表中的多個樹系](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
也支援資源樹系拓撲;這是樹系專用於執行伺服器應用程式（如 Microsoft Exchange Server 和商務用 Skype Server 2015）的所在位置。 這個資源樹系也會主控作用中使用者物件的同步標記法，但沒有啟用登入的使用者帳戶。 因此，資源樹系是使用者物件所在之其他樹系的共用服務環境，而且與資源樹系具有樹系層級的信任關係。
  
請注意，Exchange Server 可以部署在與商務用 Skype 伺服器相同的資源樹系中，也可以部署在不同的樹系中。
  
若要在這種類型的拓撲中部署商務用 Skype Server 2015，您可以在資源樹系中為使用者樹系中的每個使用者帳戶建立一個已停用的使用者物件（如果 Microsoft Exchange Server 已經在環境中，可能會為您完成）。 接著，您將需要目錄同步處理工具（如 Forefront Identity Manager 或 FIM）以透過生命週期管理使用者帳戶。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>使用 Exchange Online 的商務用 Skype 資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

此拓撲類似于[商務用 Skype 資源樹系拓撲中的多個](environmental-requirements.md#BKMK_multipleforestopology)樹系中所述的拓撲。
  
在此拓撲中，有一或多個使用者樹系，但商務用 Skype 伺服器部署在專屬的資源樹系中。 Exchange Server 可以在相同的資源樹系或不同的樹系中部署，也可以在不同的樹系中部署，也可以設定為搭配 Exchange Online 使用，Exchange Online 可提供電子郵件服務，以供內部部署帳戶使用。 沒有此拓撲的可用圖表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>具有商務用 Skype Online 和 Azure Active Directory Connect 之資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

![顯示兩個 AD 樹系、一個使用者樹系及一個資源樹系。 這兩個樹系具有信任關係。 它們是使用 Azure AD Connect 與 Office 365 同步處理。 所有使用者都透過 Office 365 啟用商務用 Skype。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
使用此案例時，會有多個樹系內部部署，具有資源樹系拓撲。 Active Directory 樹系之間有完全信任關係。 使用 Azure Active Directory Connect 工具，可同步處理內部部署使用者樹系與 Office 365 之間的帳戶。
  
 組織也有 Office 365，並使用[Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) ，將其內部部署帳戶與 Office 365 同步。 已啟用商務用 Skype 的使用者可透過 Office 365 和商務用 Skype Online 啟用。 商務用 Skype Server 不會部署在內部部署。
  
單一登入驗證是由位於使用者樹系中的 Active Directory Federation Services 伺服器陣列所提供。
  
在此案例中，支援部署 Exchange 內部部署、Exchange Online、混合式 Exchange 解決方案，或根本不部署 Exchange。 （圖表只顯示 Exchange 內部部署，但也完全支援另一種 Exchange 解決方案。）
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>具有混合式商務用 Skype 的資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

在此案例中，有一或多個內部部署使用者樹系，但商務用 Skype 是部署在專屬的資源樹系中，並設定為搭配商務用 Skype Online 的混合模式。 Exchange Server 可以在相同的資源樹系或不同的樹系中部署內部部署，也可以設定為搭配 Exchange Online 進行混合。 或者，電子郵件服務可由 Exchange Online 專門提供給內部部署帳戶。
  
如需詳細資訊，請參閱[設定混合式商務用 Skype 的多樹系環境](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

商務用 Skype Server 2015 需要 DNS，原因如下：
  
- DNS 可讓商務用 Skype Server 2015 探索內部伺服器或集區，允許伺服器對伺服器的通訊。
    
- DNS 允許用戶端電腦探索用於 SIP 交易的前端集區或 Standard Edition server。
    
- 它會將會議的簡易 URLs 與主控這些會議的伺服器產生關聯。
    
- DNS 允許外部使用者和用戶端電腦連線至 Edge Server 或 HTTP 反向 proxy，以進行立即訊息（IM）或會議。
    
- 它可讓未登入的整合通訊（UC）裝置探索執行裝置更新 web 服務的前端集區或 Standard Edition server，以取得更新及傳送記錄。
    
- 使用 DNS 可讓行動用戶端自動探索 web 服務資源，而不需要使用者在其裝置設定中手動輸入 URLs。
    
- 在 DNS 負載平衡中使用。
    
請務必注意，商務用 Skype Server 2015 不支援國際化功能變數名稱（Idn）。
  
因此，請務必記住，DNS 中的任何名稱與商務用 Skype Server 2015 所使用之任何伺服器上設定的電腦名稱稱相同。 具體而言，在環境中不能有任何短名稱，而且拓撲產生器必須具有 Fqdn。
  
這似乎是任何已加入網域的電腦都是合乎邏輯的，但是如果您有未加入至網域的 Edge Server，它可能會有預設的短名稱，但沒有網域尾碼。 在此情況下，請確定不是在 DNS 或 Edge Server 上，或任何商務用 Skype Server 2015 server 或集區的情況。
  
而且絕對不會使用 Unicode 字元或底線。 標準字元（A-Z，a-z，0-9 和連字號）是要由外部 DNS 和公用憑證授權單位支援的字元（您必須將 Fqdn 指派給憑證中的 SN，但不要忘記），這樣您就可以在 grief請記住此名稱。
  
如需聯網的 DNS 需求的進一步閱讀，請參閱規劃檔中的 [[網路](../../plan-your-deployment/network-requirements/network-requirements.md)] 區段。
  
## <a name="certificates"></a>憑證
<a name="Certs"> </a>

部署之前您可以執行的最重要的其中一個工作是，請確定您的憑證有序。 商務用 Skype Server 2015 需要公開金鑰基礎結構（PKI），以用於傳輸層安全性（TLS）和相互傳輸層安全性（MTLS）連線。 一般來說，若要以標準化的方式安全地通訊，商務用 Skype 伺服器會使用憑證授權單位（Ca）所發出的憑證。
  
以下是商務用 Skype Server 2015 使用憑證的一些事項：
  
- 用戶端與伺服器之間的 TLS 連線
    
- 伺服器之間的 MTLS 連線
    
- 同盟 usin 合作夥伴的自動 DNS 探索
    
- 遠端使用者存取即時訊息 (IM)
    
- 外部使用者存取音訊/視頻（AV）會話、應用程式共用和會議
    
- 與 web 應用程式和 Outlook Web Access （OWA）交談
    
因此，必須使用憑證規劃。 現在，讓我們看一下要求憑證時必須注意的一些事項清單：
  
- 所有的伺服器憑證必須支援伺服器授權 (伺服器 EKU)。
    
- 所有的伺服器憑證必須包含一個 CRL 發佈點 (CDP)。
    
- 所有憑證必須使用作業系統支援的簽署演算法進行簽署。 商務用 Skype Server 2015 支援摘要大小的 SHA-1 和 SHA-2 套件（224、256、384和512位），並符合或超過作業系統需求。
    
- 對執行商務用 Skype Server 2015 的內部伺服器支援自動註冊。
    
- 商務用 Skype Server 2015 Edge Server 不支援自動註冊。
    
- 當您將 Web 憑證要求提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 (SP2) 或 Windows XP 的電腦進行提交。
    
> [!NOTE]
> 雖然 KB922706 為解決使用 Windows Server 2003 憑證服務 web 登記的 web 憑證進行問題提供支援，但不能使用 Windows Server 2008、Windows Vista 或 Windows 7 來要求憑證。從 Windows Server 2003 CA。 
  
> [!NOTE]
> 不支援使用 RSASSA-PSS 簽名演算法，而且可能會導致登入和來電轉接問題的錯誤，以及其他問題。 

> [!NOTE]
> 商務用 Skype Server 2015 不支援 CNG 憑證。
  
- 支援加密金鑰長度（1024、2048及4096）。 建議使用的金鑰長度2048和更大。
    
- 預設摘要（或雜湊簽署）演算法為 RSA。 也支援 ECDH_P256、ECDH_P384 及 ECDH_P521 演算法。
    
因此，請務必考慮，從 CA 要求憑證的方式很多，而且肯定會有許多舒適的層次。 我們將提供下列進一步的指導，讓您的計畫盡可能順利。
  
### <a name="certificates-for-your-internal-servers"></a>內部伺服器的憑證

您將需要大部分內部伺服器的憑證，而且很可能會從內部 CA （位於您網域中的 CA）取得憑證。 如有需要，您可以從外部 CA 要求這些憑證（位於網際網路上的憑證）。 如果您不想要移至哪一個公用 CA，您可以查看「[整合通訊憑證合作夥伴](/SkypeForBusiness/certification/services-ssl)」清單。
  
當商務用 Skype Server 2015 與其他應用程式和伺服器（例如 Microsoft Exchange Server）通訊時，您也會需要憑證。 這顯然會需要成為其他應用程式和伺服器可以以支援的方式使用的憑證。 商務用 Skype Server 2015 和其他 Microsoft 產品支援「開放授權」（OAuth）通訊協定，以進行伺服器對伺服器驗證和授權。 如果您想要這樣做，我們有其他的 OAuth 和商務用 Skype Server 2015 的規劃文章。
  
商務用 Skype Server 2015 也包含對（不需要）使用 SHA-256 加密雜湊函數簽署憑證的支援。 若要使用 SHA-256 支援外部存取，使用 SHA-256 公用 CA 必須發行外部憑證。
  
為了以直接的方式進行處理，我們將 Standard Edition server、前端集區和其他角色的憑證需求，放入下表，並使用虛構的 contoso.com 做為範例（您可能會使用一些專案）。適用于您的環境）。 這些都是標準網頁伺服器憑證，具有不可匯出的私密金鑰。 需要注意的一些其他事項：
  
- 當您使用憑證嚮導要求憑證時，會自動設定 Server 增強金鑰使用方式（EKU）。
    
- 每個憑證好記的名稱在電腦存放區中必須是唯一的。
    
- 根據下列範例名稱，如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，則必須將它們新增至憑證的主體替代名稱（SAN）。
    
Standard Edition server 的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|**註解**|
|:-----|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |伺服器集區的 FQDN 和伺服器的 FQDN  <br/> 如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。  <br/> |SN = se01，SAN = se01  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |在 Standard Edition servers Standard Edition server 上，伺服器 FQDN 與集區 FQDN 相同。  <br/> 精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。  <br/> 您也可以使用此憑證進行 Server-to-Server 驗證。  <br/> |
|Web 內部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 相同）  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = se01，SAN = se01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = se01，SAN = se01;SAN =\*contoso.com  <br/> |您無法在拓撲產生器中覆寫內部 web FQDN。  <br/> 如果您有多個符合簡易的 URLs，您必須將它們全部包含為 SANs。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
|Web 外部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •撥入式簡易 URL  <br/> •符合每個 SIP 網域的簡易 URLs  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = se01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = se01，SAN = webcon01;SAN =\*contoso.com  <br/> |如果您有多個符合簡易的 URLs，您必須將它們全部包含為主體替代名稱。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
   
前端集區中前端伺服器的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|**註解**|
|:-----|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |伺服器集區的 FQDN 和伺服器的 FQDN  <br/> 如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。  <br/> |SN = eepool，SAN = eepool;SAN = ee01  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。  <br/> 您也可以使用此憑證進行 Server-to-Server 驗證。  <br/> |
|Web 內部  <br/> |集區的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 不同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 集區 FQDN  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = ee01，SAN = ee01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01，SAN = ee01;SAN =\*contoso.com  <br/> |如果您有多個符合簡易的 URLs，您必須將它們全部包含為主體替代名稱。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
|Web 外部  <br/> |集區的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = ee01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01，SAN = webcon01;SAN =\*contoso.com  <br/> |如果您有多個符合簡易的 URLs，您必須將它們全部包含為主體替代名稱。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
   
Director 的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |Director pool  <br/> |Director 的 FQDN （Director 集區的 FQDN）。  <br/> 如果此集區是用戶端的自動登入伺服器，且群組原則中需要嚴格 DNS 比對，則您也需要 microsoft.rtc.management.xds.sipdomain （適用于每個 SIP 網域）的專案。  <br/> |pool.contoso.com;SAN = dir01  <br/> 如果此 Director 集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |
|Web 內部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 相同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 集區 FQDN  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = dir01，SAN = dir01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01，SAN = dir01 SAN =\*。 contoso.com  <br/> |
|Web 外部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •符合每個 SIP 網域的簡易 URLs  <br/> •撥入式簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |Director 外部 web FQDN 必須不同于前端集區或前端伺服器。  <br/> SN = dir01，SAN = directorwebcon01 SAN = "contoso .com"，SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01，SAN = directorwebcon01 SAN =\*。 contoso.com  <br/> |
   
獨立轉送伺服器的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |集區的 FQDN  <br/> 集區成員伺服器的 FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
Survivable 分支裝置的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |Appliance 的 FQDN  <br/> |SIP:。\<microsoft.rtc.management.xds.sipdomain\> （每個 SIP 網域只需要一個專案）  <br/> |SN = sba01SAN = sip .com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Persistent Chat Server 的憑證

安裝 Persistent Chat Server 時，您將需要與商務用 Skype Server 2015 內部伺服器所使用的 CA 所發行的憑證。 針對檔案上傳/下載執行 Persistent Chat Web 服務的每一部伺服器，都必須執行此動作。 強烈建議您在開始持續性聊天安裝之前，您已具備必要的憑證，而且如果您的 CA 是外部的，甚至更詳細的情況（可能需要一些時間才能發出）。
  
### <a name="certificates-for-external-user-access-edge"></a>外部使用者存取的憑證（Edge）

商務用 Skype Server 2015 支援使用**單一公用憑證**進行 access 和 Web 會議 Edge 外部介面，以及 A/V 驗證服務，這是透過 Edge Server 所提供的。 您的 Edge 內部介面一般會使用您的內部 CA 所發出的私人憑證，但是如果您願意，也可以使用公用憑證，如果是來自信任的 CA。
  
反向 proxy （RP）也會使用公用憑證，並使用 HTTP （或更確切地說是 TLS over HTTP），將您的 RP 中的通訊加密到用戶端，並將 RP 加密為內部伺服器。
  
### <a name="certificates-for-mobility"></a>行動的憑證

如果您正在部署行動性，且支援行動用戶端的自動探索，您必須在憑證上加入一些額外的主體替代名稱專案，以支援行動用戶端的安全連線。
  
哪一個證書？ 您將需要在下列憑證上自動探索的 SAN 名稱：
  
- Director pool
    
- 前端集區
    
- 反向 Proxy
    
下表將列出每個表格中的詳細資料。
  
現在，這是很少預先規劃的情況，但是有時候您已部署商務用 Skype Server 2015，而不是想要部署行動性，當您已在環境中已有憑證時，會出現在該行下方。 透過內部 CA 重新發起它們通常相當簡單，但有來自公用 CA 的公用憑證，則可能會有一點的 pricy。
  
如果這是您所看到的專案，而且如果您有許多 SIP 網域（這會增加 SAN 的成本），您可以設定反向 proxy，以使用 HTTP 進行初始自動探索服務要求，而不是使用 HTTPS （預設值為設定）。 行動計畫主題具有這方面的詳細資訊。
  
Director 集區和前端集區憑證需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|內部自動探索服務 URL  <br/> |SAN = lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>  <br/> |
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
您也可以使用 SAN =\*。\<microsoft.rtc.management.xds.sipdomain\>
  
反向 Proxy （公用 CA）憑證需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
此 SAN 必須指派給反向 proxy 上的 SSL 攔截器所指派的憑證。
  
> [!NOTE]
> 您的反向 proxy 監聽器會為您的外部 Web 服務 URL 提供 SANs。 例如，如果您已部署 Director （這是選用），則某些範例會是 SAN = skypewebextpool01 .com 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>檔案共用
<a name="Fileshare"> </a>

商務用 Skype Server 2015 可對所有檔案存放區使用相同的檔案共用。 您必須謹記下列各項：
  
- 檔案共用必須位於直接附加儲存裝置（DAS）或儲存區域網路（SAN）上，而且這包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。 如需有關 Windows Server 2012 的 DFS 的進一步閱讀，請參閱[此 DFS 頁面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 我們建議使用共用叢集進行檔案共用。 如果您使用其中一個，則應該是群集 Windows Server 2012 或 Windows Server 2012 R2。 Windows Server 2008 R2 也是可接受的。 為什麼是最新的視窗？ 舊版本可能沒有適當的許可權可啟用所有功能。 您可以使用 [群集管理員] 來建立檔案共用，以及[如何在叢集專案上建立檔案共用](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster)，將協助您瞭解這些詳細資料。
    
> [!CAUTION] 
> 您應該知道，不支援使用網路連接儲存（NAS）做為檔案共用，所以請使用以上所列的其中一個選項。 
  
