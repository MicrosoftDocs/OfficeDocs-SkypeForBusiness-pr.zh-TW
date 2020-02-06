---
title: 商務用 Skype 的負載平衡需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要：在執行商務用 Skype Server 前，請先檢查負載平衡考慮。
ms.openlocfilehash: 199c93528d89786573bdac16077f1e32feb1fe6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802043"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>商務用 Skype 的負載平衡需求
 
**摘要：** 在執行商務用 Skype Server 前，請先檢查負載平衡考慮。
  
負載平衡在池中的伺服器之間分佈流量。 如果您有前端池、中繼伺服器池或邊緣伺服器池，您必須為這些池部署負載平衡。
  
商務用 Skype 伺服器支援針對用戶端到伺服器流量的兩種負載平衡解決方案：網域名稱系統（DNS）負載平衡與硬體負載平衡（通常縮寫為 HLB）。 DNS 負載平衡提供數個優點，包括更簡單的管理、更有效率的疑難排解，以及將許多商務用 Skype 伺服器流量與任何可能的硬體負載平衡器問題隔離的能力。
  
自己決定哪一種負載平衡方案適合您部署中的每個池，但請記住下列限制： 
  
- 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您無法在一個介面上使用 DNS 負載平衡，另一種是在另一個介面上使用硬體負載平衡。
    
- 某些類型的流量需要硬體負載平衡器。 例如，HTTP 流量需要硬體負載平衡器，而不是 DNS 負載平衡。 DNS 負載平衡無法搭配用戶端到伺服器的網路流量使用。
    
如果您選擇要針對某個池使用 DNS 負載平衡，但仍需要為流量（例如 HTTP 流量）執行硬體負載平衡器，系統會大大簡化硬體負載平衡器的管理。 例如，設定硬體負載平衡器會比較簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都將由 DNS 負載平衡來管理。 如需詳細資訊，請參閱[DNS 負載平衡](load-balancing.md#BKMK_DNSLoadBalancing)。 
  
針對伺服器到伺服器的流量，商務用 Skype 伺服器使用拓撲感知負載平衡。 伺服器會在中央管理儲存體中讀取已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器之間自動散佈流量。 系統管理員不需要設定或管理這種類型的負載平衡。 
  
如果您使用 DNS 負載平衡，而且您需要封鎖流量至特定電腦，則只需從池 FQDN 中移除 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。 
  
## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

針對新部署的 DNS 負載平衡進行優化的商務用 Skype 伺服器縮放的邊緣拓朴，主要是與使用商務用 Skype Server 或 Lync Server 的其他組織聯盟。 如果下列任何案例都需要高可用性，則必須在 Edge 伺服器池中使用硬體負載平衡器，以進行下列作業： 
  
- 與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟
    
- 在 Exchange 2010 之前使用 Exchange UM 的遠端使用者的 exchange UM 與 SP1
    
- 公用 IM 使用者的連線能力
    
> [!IMPORTANT]
> 在一個介面上使用 DNS 負載平衡，而另一個介面上的硬體負載平衡則不受支援。 您必須針對兩種介面或 DNS 負載平衡使用硬體負載平衡。 
  
> [!NOTE]
> 如果您使用的是硬體負載平衡器，則必須將與內部網路的連線所部署的負載平衡器設定為只進行負載平衡，以便只對執行存取邊緣服務和 A/V 邊緣服務的伺服器進行負載平衡。 它無法將流量負載平衡到內部網路會議邊緣服務或內部 XMPP Proxy 服務。 
  
> [!NOTE]
> 商務用 Skype Server 不支援直接伺服器返回（DSR） NAT。 
  
若要判斷您的硬體負載平衡器是否支援商務用 Skype Server 所需的功能，請參閱[商務用 skype 的基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求

以下是執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求：
  
- 針對內部和外部埠443關閉 TCP Nagling。 Nagling 是將數個小型資料包合併成單一、較大的資料包以獲得更有效率的傳輸的程式。
    
- 關閉外部埠範圍 50000-59999 的 TCP Nagling。 
    
- 請勿在內部或外部防火牆上使用 NAT。 
    
- Edge 內部介面必須在不同的網路上，而不是 Edge 伺服器外部介面且必須停用它們之間的路由。 
    
- 執行 A/V 邊緣服務的邊緣伺服器外部介面必須使用可公開路由的 IP 位址，而且任何邊緣外部 IP 位址都沒有 NAT 或埠轉譯。 
    
- 負載平衡器不得變更用戶端的來源位址。
    
### <a name="other-hardware-load-balancer-requirements"></a>其他硬體負載平衡器需求

在商務用 Skype Server for Web 服務中，以 Cookie 為基礎的關聯需求大大減少。 如果您要部署商務用 Skype Server，且不會保留任何 Lync Server 2010 前端伺服器或前端池，則不需要以 cookie 為基礎的持久性。 不過，如果您要暫時或永久保留任何 Lync Server 2010 前端伺服器或前端池，您仍然會在針對 Lync Server 2010 部署和設定的情況下，使用以 cookie 為基礎的持久性。 
  
> [!NOTE]
> **如果您決定使用以 cookie 為基礎的關聯，即使您的部署不需要它**，也不會有任何負面影響可執行此動作。 
  
針對**將不會使用**cookie 的關聯的部署：
  
- 在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。 這可確保原始 URL 已轉寄。
    
針對**將使用**以 cookie 為基礎的關聯性的部署：
  
- 在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。 這可確保原始 URL 已轉寄。
    
- 硬體負載平衡器 cookie 不能標示為 HTTPOnly
    
- 硬體負載平衡器 cookie 不能有到期時間
    
- 硬體負載平衡器 cookie 必須命名為**MS-WSMAN** （這是 Web 服務預期的值，且無法變更）
    
- 硬體負載平衡器 cookie 必須在每一個 HTTP 回應中設定（無論是否已在相同的 TCP 連線中先前的 HTTP 回應都已取得 cookie）。 如果負載平衡器針對每個 TCP 連線優化 cookie 插入，則不一定要使用該優化
    
> [!NOTE]
> 典型的硬體負載平衡器設定使用來源位址關聯和20分鐘的 TCP 會話存留期，這對 Lync Server 和 Lync 2013 用戶端來說是很好的，因為會話狀態是透過用戶端使用量和/或應用程式互動來維護。 
  
如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 會話中的個別要求之間進行負載平衡（事實上，您必須能夠根據目標 IP 位址來載入個別的要求）。
  
> [!CAUTION]
> 如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 連線中針對每個要求逐一進行負載平衡。 最新的 Apple iOS 行動裝置 app 需要傳輸層安全性（TLS）版本1.2。  
  
> [!CAUTION]
> 如需協力廠商硬體負載平衡器的詳細資料，請參閱[商務用 Skype 的基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。  
  
以下是控制器和前臺端池 Web 服務的硬體負載平衡器需求：
  
- 如果是內部 Web 服務 Vip，請在硬體負載平衡器上設定 Source_addr 持久性（內部埠80，443）。 如果是商務用 Skype Server，Source_addr 暫留表示來自單一 IP 位址的多個連線，會一直傳送到一個伺服器，以維持會話狀態。
    
- 使用1800秒的 TCP 空閒超時。
    
- 在反向 proxy 與下一個躍點池的硬體負載平衡器之間，建立規則來允許 HTTPs：埠4443上的流量，從反向 proxy 傳送到硬體負載平衡器。 硬體負載平衡器必須設定為在埠80、443和4443上聆聽。
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬體負載平衡器關聯需求摘要

|**用戶端/使用者位置**|**外部 web 服務 FQDN 關聯需求**|**內部 web 服務 FQDN 關聯需求**|
|:-----|:-----|:-----|
|Lync Web App （內部與外部使用者）  <br/> 行動裝置（內部和外部使用者）  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
|Lync Web App （僅限外部使用者）  <br/> 行動裝置（內部和外部使用者）  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
|Lync Web App （僅限內部使用者）  <br/> 行動裝置（未部署）  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>硬體負載平衡器的埠監控

您可以在硬體負載平衡器上定義埠監視，以判斷因硬體或通訊失敗而無法使用特定服務的時間。 例如，如果前端伺服器或前端池發生故障，[前端伺服器服務（RTCSRV）] 停止，則 HLB 監視也應該停止在 Web 服務上接收流量。 您可以在 HLB 上執行埠監視，以監視下列各項：
  
**前端伺服器使用者池-HLB 內部介面**

|**虛擬 IP/埠**|**節點埠**|**節點電腦/監視器**|**持久性設定檔**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|
|\<網路\>池網頁-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |前端  <br/> 5061  <br/> |從源  <br/> |IP-HTTPS  <br/> |
|\<網路\>池網頁-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |前端  <br/> 5061  <br/> |從源  <br/> |HTTP  <br/> |
   
**前端伺服器使用者池-HLB 外部介面**

|**虛擬 IP/埠**|**節點埠**|**節點電腦/監視器**|**持久性設定檔**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |無  <br/> |IP-HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="BKMK_DNSLoadBalancing"> </a>

商務用 Skype 伺服器可啟用 DNS 負載平衡，這是可大大減少網路上負載平衡之管理負荷的軟體解決方案。 DNS 負載平衡會平衡商務用 Skype 伺服器（例如 SIP 流量及媒體流量）獨有的網路流量。
  
如果您部署 DNS 負載平衡，貴組織的硬體負載平衡器的系統管理開銷將會最小化。 此外，對於與 SIP 流量的負載平衡程式配置錯誤相關的問題，複雜的疑難排解將會消失。 您也可以避免伺服器連線，以便讓伺服器離線。 DNS 負載平衡也可確保硬體負載平衡器問題不會影響 SIP 流量的元素，例如基本呼叫路由。

下圖顯示包括內部和外部 DNS 負載平衡的範例： 
  
**使用公用 IPv4 位址的邊緣網狀圖**

![DNS network 圖表範例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
如果您使用 DNS 負載平衡，您可能也可以購買成本較低的硬體負載平衡器，而不是在所有類型的流量中使用硬體負載平衡器。 您應該使用已透過互通性驗證測試與商務用 Skype 伺服器的負載平衡器。 如需有關負載平衡程式互通性測試的詳細資料，請參閱[Lync Server 2010 負載平衡器合作夥伴](https://go.microsoft.com/fwlink/p/?linkId=202452)。 此內容適用于商務用 Skype 伺服器。
  
前端池、邊緣伺服器池、控制器池和獨立的中繼伺服器池都支援 DNS 負載平衡。
  
DNS 負載平衡通常是在應用程式層級實現。 應用程式（例如，執行商務用 Skype 的用戶端）會嘗試連線到池中從 DNS A 和 AAAA 傳回的其中一個 IP 位址（如果使用的是 IPv6 定址）記錄查詢，以取得池的完整功能變數名稱（FQDN）來連線至池中的伺服器。 
  
例如，如果在名為 pool01.contoso.com 的池中有三個前端伺服器，則會發生下列情況：
  
- 執行商務用 Skype 查詢 pool01.contoso.com 的用戶端。 查詢會傳回三個 IP 位址，並以下列方式將它們加以緩存（不一定依順序）：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- 用戶端會嘗試建立與其中一個 IP 位址的傳輸控制通訊協定（TCP）連線。 如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。
    
- 如果 TCP 連線成功，用戶端會協商 TLS，連線到 pool01.contoso.com 上的主要註冊機構。
    
- 如果用戶端在未成功連線的情況下嘗試所有快取的專案，系統會通知使用者目前沒有任何執行商務用 Skype 伺服器的伺服器可供使用。
    
> [!NOTE]
> 以 dns 為基礎的負載平衡不同于 DNS 迴圈（DNS RR），主要是依靠 DNS 來提供負載平衡，以提供與池中伺服器相對應的 IP 位址的不同順序。 通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。 例如，如果連線到 DNS A 和 AAAA 傳回的一個 IP 位址（如果您使用的是 IPv6 定址）查詢失敗，連線就會失敗。 因此，DNS 迴圈方式本身的可靠性低於 DNS 的負載平衡。 您可以將 DNS 迴圈與 DNS 負載平衡搭配使用。 
  
DNS 負載平衡用於下列用途：
  
- 將伺服器間 SIP 負載平衡到邊緣伺服器
    
- [負載平衡] 應用程式服務（UCAS）應用程式（例如會議自動語音應答、回應群組及通話駐留）
    
- 防止新連線至 UCAS 的應用程式（也稱為 "排出"）
    
- 負載平衡用戶端與邊緣伺服器之間的所有用戶端與伺服器流量
    
DNS 負載平衡無法用於下列專案：
  
- 從用戶端到伺服器的 web 流量到控制器或前端伺服器
    
DNS 負載平衡與同盟流量：
  
如果 DNS SRV 查詢傳回多個 DNS 記錄，存取邊緣服務將會使用最小的數值優先順序和最高的數位權重來挑選 DNS SRV 記錄。 網際網路工程工作強制檔「用於指定服務位置的 DNS RR （DNS SRV）」 [RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt)會指定是否已定義多個 DNS SRV 記錄、首先使用優先順序，然後再使用 [粗細]。 例如，DNS SRV 記錄 A 的粗細為20，且優先順序為40，而 DNS SRV 記錄 B 的權重為10且優先順序為50。 將會選取具有優先順序40的 DNS SRV 記錄 A。 下列規則適用于 DNS SRV 記錄選擇：
  
- 首先考慮優先順序。 用戶端必須嘗試與 DNS SRV 記錄所定義的目標主機取得其所能達到的最低優先順序。 必須按照權欄位所定義的順序來嘗試使用相同優先順序的目標。
    
- [體重] 欄位指定具有相同優先順序之專案的相對權重。 應將較大的粗細指定成按比例較高的選取幾率。 如果沒有任何伺服器可供您選擇，DNS 管理員就應該使用權重0。 如果記錄中包含的權重大於0，則權重為0的記錄應該有很小的選取機會。
    
如果傳回多個具有相同優先順序和寬度的 DNS SRV 記錄，則 Access Edge 服務會選取首先從 DNS 伺服器接收的 SRV 記錄。
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池與控制器池上的 DNS 負載平衡

您可以針對前端池和控制器池上的 SIP 流量使用 DNS 負載平衡。 在部署 DNS 負載平衡的情況下，您仍然需要同時針對這些池使用硬體負載平衡器，但僅適用于用戶端到伺服器的 HTTPS 流量。 硬體負載平衡器用於來自埠443和80的用戶端的 HTTPS 流量。 
  
雖然您仍需要這些池的硬體負載平衡器，但它們的設定和管理主要是針對 HTTPS 流量（硬體負載平衡器的系統管理員習慣）。
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 負載平衡及支援舊版用戶端和伺服器

DNS 負載平衡只支援針對執行商務用 Skype Server 或 Lync Server 2010 的伺服器，以及 Lync 2013 和商務用 Skype 用戶端的自動容錯移轉。 較舊版本的用戶端和 Office 通訊伺服器仍可連線到執行 DNS 負載平衡的池，但如果它們無法連線到 DNS 負載平衡所參照的第一個伺服器，則它們無法容錯移轉至池中的另一台伺服器. 
  
此外，如果您使用的是 Exchange UM，您必須至少使用 Exchange 2010 SP1，才能取得商務用 Skype Server DNS 負載平衡支援。 如果您使用的是舊版 Exchange，您的使用者將沒有這些 Exchange UM 案例的容錯移轉功能：
  
- 在電話上播放企業語音信箱
    
- 轉移來自 Exchange UM 自動語音應答的呼叫
    
所有其他 Exchange UM 案例都會正常運作。
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池上部署 DNS 負載平衡
<a name="BK_FE_Dir"> </a>

在前端池和控制器池上部署 DNS 負載平衡，您需要執行幾個額外步驟，使用 Fqdn 和 DNS 記錄。
  
- 使用 DNS 負載平衡的池必須有兩個 Fqdn：由 DNS 負載平衡所使用的一般池 FQDN （例如 pool01.contoso.com），並解析成池中伺服器的實際 Ip，以及該池 Web 服務的另一個 FQDN （例如web01.contoso.com），可解析為池的虛擬 IP 位址。 
    
    在拓撲建立器中，如果您想要為池的 Web 服務部署 DNS 負載平衡，您必須選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊，然後在 [**指定適用于此池的 Web 服務 url** ] 頁面上輸入 FQDN。
    
- 若要支援 DNS 負載平衡所使用的 FQDN，您必須提供 DNS，以將池 FQDN （例如 pool01.contoso.com）解析為池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等等）。 您應該只包含目前已部署之伺服器的 IP 位址。
    
    > [!CAUTION]
    > 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為**pool01.contoso.com**，則無法將**pool01.contoso.com**用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Edge 伺服器池中的 DNS 負載平衡
<a name="BK_Edge"> </a>

您可以在 Edge 伺服器池中部署 DNS 負載平衡。 如果您這樣做，您必須知道一些考慮。
  
在邊緣伺服器上使用 DNS 負載平衡，會造成下列案例中的容錯移轉能力損失：
  
- 與執行 Lync Server 2010 之前發行之商務用 Skype Server 版本之組織的同盟。
    
- 除了 XMPP 的提供者和伺服器（例如 Google 交談）之外，您還可以使用公用立即訊息（IM）服務 AOL 和 Yahoo！等的立即訊息交換，以及目前唯一支援的 XMPP 合作夥伴。
    
只要池中的所有邊緣伺服器都已啟動並執行，這些案例就能正常運作，但如果沒有一個 Edge 伺服器無法使用，傳送給它的這些案例的任何要求都會失敗，而不是路由到另一個 Edge 伺服器。
  
 如果您使用的是 Exchange UM，您必須使用 Exchange 2013 的最低限度，才能在 Edge 上取得商務用 Skype Server DNS 負載平衡支援。 如果您使用的是舊版 Exchange，您的遠端使用者將沒有這些 Exchange UM 案例的容錯移轉功能：
  
- 在電話上播放企業語音信箱
    
- 轉移來自 Exchange UM 自動語音應答的呼叫
    
所有其他 Exchange UM 案例都會正常運作。
  
內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge 伺服器池中部署 DNS 負載平衡

若要在 Edge 伺服器池的外部介面上部署 DNS 負載平衡，您需要下列 DNS 專案：
  
- 針對存取邊緣服務，您需要為池中的每個伺服器加入一個專案。 每個專案都必須將存取邊緣服務（例如，sip.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的存取邊緣服務的 IP 位址。
    
- 針對網路會議 Edge 服務，池中的每個伺服器都需要一個專案。 每個專案都必須將網路會議 Edge 服務（例如，webconf.contoso.com）的 FQDN 解析成池中某個邊緣伺服器的網路會議 Edge 服務的 IP 位址。
    
- 針對音訊/視頻邊緣服務，池中的每個伺服器都需要一個專案。 每個專案都必須將音訊/視頻邊緣服務（例如，av.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 A/V 邊緣服務的 IP 位址。
    
若要在 Edge 伺服器池的內部介面上部署 DNS 負載平衡，您必須加入一個 DNS A 記錄，該記錄會將 Edge 伺服器池的內部 FQDN 解析成池中每個伺服器的 IP 位址。
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中繼伺服器池中使用 DNS 負載平衡
<a name="BK_Mediation"> </a>

您可以在獨立的中繼伺服器池上使用 DNS 負載平衡。 所有 SIP 和媒體流量都是透過 DNS 負載平衡來平衡。
  
若要在轉送伺服器池中部署 DNS 負載平衡，您必須建立 DNS，以將池 FQDN （例如，mediationpool1.contoso.com）解析成池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等）。
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 負載平衡封鎖伺服器的流量
<a name="BK_Mediation"> </a>

如果您使用 DNS 負載平衡，而且您需要封鎖流量至特定電腦，則只需從池 FQDN 中移除 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。 
  
請注意，對於伺服器到伺服器的流量，商務用 Skype 伺服器會使用拓撲感知負載平衡。 伺服器會在中央管理儲存體中讀取已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器之間自動散佈流量。 若要封鎖伺服器接收伺服器對伺服器流量，您必須從拓撲中移除伺服器。 
  

