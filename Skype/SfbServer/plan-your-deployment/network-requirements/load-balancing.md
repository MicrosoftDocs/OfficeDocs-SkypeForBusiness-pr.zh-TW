---
title: 商務用 Skype 的負載平衡需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要：在實施商務用 Skype Server 之前，請先複查負載平衡考慮。
ms.openlocfilehash: ba8ab3e4659ea7e17e91b4bf725e8bd1fe8b59ca
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733392"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>商務用 Skype 的負載平衡需求
 
**摘要：** 在實施商務用 Skype Server 之前，請先複查負載平衡考慮。
  
負載平衡會在集區中的伺服器之間散佈流量。 如果您有前端集區、轉送伺服器集區或 Edge Server 集區，則需要為這些集區部署負載平衡。
  
商務用 Skype Server 支援用戶端對伺服器流量的兩種負載平衡解決方案：網域名稱系統 (DNS) 負載平衡與硬體負載平衡 (通常縮寫為 HLB) 。 DNS 負載平衡提供數種優點，包括簡化管理、更有效率的疑難排解，以及隔離任何可能的硬體負載平衡器問題的商務用 Skype Server 流量的功能。
  
決定您的部署中每個集區適用的負載平衡解決方案，但切記下列限制： 
  
- 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您無法在一個介面上使用 DNS 負載平衡，另一個在另一個介面上使用硬體負載平衡。
    
- 某些類型的流量需要硬體負載平衡器。 例如，HTTP 流量需要硬體負載平衡器，而不是使用 DNS 負載平衡。 DNS 負載平衡無法搭配用戶端對伺服器的 web 流量使用。
    
如果您選擇針對集區使用 DNS 負載平衡，但仍需要針對流量（例如 HTTP 流量）執行硬體負載平衡器，則可大幅簡化硬體負載平衡器的管理。 例如，設定硬體負載平衡器會變得更簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都會透過 DNS 負載平衡來管理。 如需詳細資訊，請參閱 [DNS 負載平衡](load-balancing.md#BKMK_DNSLoadBalancing)。 
  
針對伺服器對伺服器的流量，商務用 Skype Server 使用拓撲感知負載平衡。 伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。 管理員不需要設定或管理這種類型的負載平衡。 
  
如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。 
  
## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

商務用 Skype Server 調整式合併 Edge 拓撲已針對新的部署，針對 DNS 負載平衡進行優化，主要與使用商務用 Skype Server 或 Lync Server 的其他組織合作。 如果在下列任一情況下需要高可用性，則必須在 Edge Server 集區上使用硬體負載平衡器予以因應： 
  
- 與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟
    
- Exchange在 2010 Exchange SP1 之前，使用 Exchange um 進行遠端使用者的 um
    
- 公用 IM 使用者的連線
    
> [!IMPORTANT]
> 不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。 
  
> [!NOTE]
> 在您使用硬體負載平衡器時，針對內部網路的連線所部署的負載平衡器必須經過設定，使其僅對流向執行 Access Edge Service 與 A/V Edge Service 之伺服器的流量執行負載平衡。對於流向內部 Web Conferencing Edge Service 或內部 XMPP Proxy 服務的流量，不可執行負載平衡。 
  
> [!NOTE]
> 商務用 Skype Server 不支援 direct server return (DSR) NAT。 
  
若要判斷您的硬體負載平衡器是否支援商務用 Skype Server 所需的必要功能，請參閱[基礎結構 for 商務用 Skype](../../../SfbPartnerCertification/certification/infra-gateways.md)。 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>執行 A/V Edge Service 之 Edge Server 的硬體負載平衡器需求

以下是執行 A/V Edge service 之 Edge Server 的硬體負載平衡器需求：
  
- 關閉內部及外部連接埠 443 的 TCP Nagling。Nagling 是一種程序，將數個小型封包合併為較大型的單一封包以進行有效傳輸。
    
- 關閉外部埠範圍 50000-59999 的 TCP Nagling。 
    
- 不要在內部或外部防火牆上使用 NAT。 
    
- Edge 內部介面必須與 Edge 外部介面位在不同的網路上，而且必須停用在它們之間進行的路由傳送作業。 
    
- 執行 A/V Edge Service 之 Edge Server 的外部介面必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。 
    
- 負載平衡器不得變更用戶端的來源位址。
    
### <a name="other-hardware-load-balancer-requirements"></a>其他硬體負載平衡器需求

在 Web 服務的商務用 Skype Server 中，以 Cookie 為基礎的親近性需求會大幅降低。 如果您要部署商務用 Skype Server，但不會保留任何 Lync Server 2010 前端伺服器或前端集區，則不需要以 cookie 為基礎的持久性集。 不過，如果您暫時或永久保留任何 Lync Server 2010 前端伺服器或前端集區，您仍會使用以 cookie 為基礎的持久性，因為它是針對 Lync Server 2010 部署及設定。 
  
> [!NOTE]
> **如果您決定使用 Cookie 型相似性 (即使您的部署不需要它)**，則這樣做並不會產生任何負面影響。 
  
針對 **不使用** Cookie 型相似性的部署：
  
- 在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。
    
針對 **將使用** Cookie 型相似性的部署：
  
- 在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。
    
- 硬體負載平衡器 Cookie「絕不能」標示為 httpOnly
    
- 硬體負載平衡器 Cookie「絕不能」有到期時間
    
- 硬體負載平衡器 Cookie「必須」命名為 **MS-WSMAN** (此為 Web 服務預期的值且無法變更)
    
- 無論該相同 TCP 連線上先前的 HTTP 回應是否已取得 Cookie，在傳入 HTTP 要求沒有 Cookie 的每個 HTTP 回應中，都「必須」設定硬體負載平衡器 Cookie。如果負載平衡器將 Cookie 插入最佳化成針對每個 TCP 連線只出現一次，則「絕不能」使用該最佳化
    
> [!NOTE]
> 一般硬體負載平衡器設定會使用來源位址親近性和20分鐘的 TCP 會話壽命，這對 Lync Server 和 Lync 2013 用戶端而言是很好的，因為會話狀態是透過用戶端使用方式和/或應用程式互動來維護。 
  
如果您正在部署行動裝置，硬體負載平衡器就必須能夠在 TCP 工作階段中負載平衡個別要求 (實際上，您必須能夠根據目標 IP 位址來負載平衡個別要求)。
  
> [!CAUTION]
> 如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 連線中個別地對每個要求進行負載平衡。 最新版的 Apple iOS 行動應用程式需要傳輸層安全性 (TLS) 版本 1.2。  
  
> [!CAUTION]
> 如需協力廠商硬體負載平衡器的詳細資訊，請參閱[基礎結構的商務用 Skype](../../../SfbPartnerCertification/certification/infra-gateways.md)。  
  
下面是 Director 與前端集區 Web 服務的硬體負載平衡器需求：
  
- 針對內部 Web 服務 VIP，在硬體負載平衡器上設定 Source_addr 持續性 (內部連接埠 80、443)。 針對商務用 Skype Server，Source_addr 暫留表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器以維護會話狀態。
    
- 使用 TCP 閒置逾時：1800 秒。
    
- 在反向 proxy 與下一個躍點集區之硬體負載平衡器之間的防火牆上，建立規則以允許從反向 proxy 到硬體負載平衡器的埠4443上的 HTTPs：流量。 硬體負載平衡器必須設定成接聽連接埠 80、443 及 4443。
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬體負載平衡器相似性需求摘要

|**用戶端/使用者位置**|**外部 Web 服務 FQDN 相似性需求**|**內部 Web 服務 FQDN 相似性需求**|
|:-----|:-----|:-----|
|Lync Web App (內部及外部使用者)   <br/> 行動裝置 (內部和外部使用者)  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
|Lync Web App (僅限外部使用者)   <br/> 行動裝置 (內部和外部使用者)  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
|Lync Web App (僅限內部使用者)   <br/> 行動裝置 (未部署)  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>適用於硬體負載平衡器的連接埠監控

您可以在硬體負載平衡器上定義連接埠監控，以判斷特定的服務何時因為發生硬體或通訊失敗而無法使用。 例如，如果前端伺服器服務 (RTCSRV) 停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。 您可以在 HLB 上實作連接埠監控以監控下列各項：
  
**前端伺服器使用者集區-HLB 內部介面**

|**虛擬 IP/連接埠**|**節點連接埠**|**節點電腦/監視器**|**持續性設定檔**|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web int_mco_443_vs  <br/> 443  <br/> |443  <br/> |前端  <br/> 5061  <br/> |來源  <br/> |HTTPS:  <br/> |
|\<pool\>web int_mco_80_vs  <br/> 80  <br/> |80  <br/> |前端  <br/> 5061  <br/> |來源  <br/> |HTTP  <br/> |
   
**前端伺服器使用者集區-HLB 外部介面**

|**虛擬 IP/連接埠**|**節點連接埠**|**節點電腦/監視器**|**持續性設定檔**|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTPS:  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="BKMK_DNSLoadBalancing"> </a>

商務用 Skype Server 可讓您在網路上大幅減少負載平衡之管理負荷的軟體解決方案，啟用 DNS 負載平衡。 DNS 負載平衡會平衡商務用 Skype Server 特有的網路流量，例如 SIP 流量和媒體流量。
  
如果您部署 DNS 負載平衡，您組織的硬體負載平衡器的管理系統開銷將會降到最低。 此外，負載平衡器中針對 SIP 流量的設定錯誤問題所涉及的複雜疑難排解也得以排除。 您也可以防止伺服器連線，以便將伺服器離線。 DNS 負載平衡也可以確保硬體負載平衡器問題不會影響基本通話路由等這類 SIP 流量元素。

下圖顯示一個範例，其中包括內部和外部 DNS 負載平衡： 
  
**使用公用 IPv4 位址的 Edge network 圖表**

![DNS network 圖表的範例。](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
相較於將硬體負載平衡器用於全部的流量類型，如果使用 DNS 負載平衡也能讓您購買成本較低的硬體負載平衡器。 您應該使用已通過互通性驗證測試的負載平衡器與商務用 Skype Server。 如需負載平衡器互通性測試的詳細資訊，請參閱 [Lync Server 2010 負載平衡器合作夥伴](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 套用至商務用 Skype Server 的內容。
  
DNS 負載平衡支援前端集區、Edge Server 集區、Director 集區和獨立中繼伺服器集區。
  
DNS 負載平衡通常是在應用層級實施。 應用程式 (例如，執行商務用 Skype) 的用戶端會嘗試連線至伺服器集區中從 DNS a 和 AAAA (傳回的其中一個 IP 位址，如果 IPv6 定址是用於集區完整功能變數名稱) FQDN (的記錄查詢。 
  
例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：
  
- 執行商務用 Skype 的用戶端會查詢 pool01.contoso.com 的 DNS。 查詢會傳回三個 IP 位址，並將其快取如下 (不一定要依此順序) ：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- 用戶端會嘗試建立傳輸控制通訊協定 (TCP) 連接至其中一個 IP 位址。 如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。
    
- 如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。
    
- 如果用戶端嘗試所有的快取專案，但連線失敗，則會通知使用者目前沒有任何執行商務用 Skype Server 的伺服器可供使用。
    
> [!NOTE]
> DNS 的負載平衡與 DNS 迴圈使用不同 (DNS RR) ，其主要指的是透過 DNS 提供與集區中伺服器對應的不同順序的負載平衡。 通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。 例如，如果您在使用 IPv6 定址) 查詢失敗時，由 DNS A 和 AAAA (所傳回的一個 IP 位址進行連線，連接就會失敗。 因此，來自于 DNS 的負載平衡，其本身的 [DNS] 迴圈是不夠可靠的。 您可以搭配 DNS 負載平衡使用 DNS 迴圈。 
  
DNS 負載平衡用於下列專案：
  
- 將伺服器對伺服器的 SIP 負載平衡至 Edge server
    
- 負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留
    
- 防止新連線 UCAS 應用程式 (也稱為「耗盡」 ) 
    
- 在用戶端和 Edge server 之間負載平衡所有用戶端對伺服器流量
    
DNS 負載平衡無法用於下列專案：
  
- 對 Director 或前端伺服器的用戶端對伺服器網頁流量
    
DNS 負載平衡及同盟流量：
  
如果 DNS SRV 查詢傳回多個 DNS 記錄，Access Edge service 一定會選取具有最低的數值優先順序和最高數值權重的 DNS SRV 記錄。 網際網路工程工作強制檔「用於指定服務位置 (DNS SRV) " [RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) 會指定如果已定義多個 DNS srv 記錄，則會先使用優先順序，然後再使用「加權」。 例如，DNS SRV 記錄 A 的權重為20，優先順序為40，而 DNS SRV 記錄 B 的權重為10，優先順序為50。 將會選取具有優先順序40的 DNS SRV 記錄 A。 下列規則適用于 DNS SRV 記錄選取：
  
- 優先順序會先考慮。 用戶端必須嘗試聯繫 DNS SRV 記錄所定義的目標主機，其可達到的最低優先順序。 應以「加權」欄位所定義的順序，嘗試相同優先順序的目標。
    
- [加權] 欄位會指定具有相同優先順序之專案的相對權重。 應將較大的權重按比例增加選取的概率。 DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。 當記錄中包含的權重大於0時，具有權重0的記錄應該會有很小的可能被選取。
    
若傳回多個具有相同優先順序和權重的 DNS SRV 記錄，Access Edge service 會選取最先從 DNS 伺服器接收的 SRV 記錄。
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端集區和 Director 集區上的 DNS 負載平衡

您可以針對前端集區和 Director 集區上的 SIP 流量使用 DNS 負載平衡。部署 DNS 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限用戶端到伺服器的 HTTPS 流量。硬體負載平衡器會用於用戶端透過連接埠 443 和 80 送出的 HTTPS 流量。 
  
雖然這些集區仍然需要硬體負載平衡器，但是其設定和系統管理主要是針對 HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 負載平衡以及支援的舊版用戶端和伺服器

DNS 負載平衡僅支援執行商務用 Skype Server 或 lync Server 2010 的伺服器，以及 Lync 2013 和商務用 Skype 用戶端的自動容錯移轉。 較舊版本的用戶端和 Office 通訊伺服器仍可連線到執行 dns 負載平衡的集區，但如果這些集區無法連線至 dns 負載平衡所參照的第一部伺服器，則他們無法容錯移轉至集區中的另一部伺服器。 
  
此外，如果您使用 Exchange UM，您必須至少使用 Exchange 2010 SP1 才能取得商務用 Skype Server DNS 負載平衡的支援。 如果您使用舊版的 Exchange，您的使用者將不會有這些 Exchange UM 案例的容錯移轉功能：
  
- 在電話上播放其 Enterprise 語音信箱
    
- 從 Exchange UM 自動語音應答轉接通話
    
所有其他 Exchange UM 案例則會正常運作。
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端集區和 Director 集區上部署 DNS 負載平衡
<a name="BK_FE_Dir"> </a>

在前端集區和 Director 集區上部署 DNS 負載平衡，需要您對 FQDN 和 DNS 記錄執行一些額外步驟。
  
- 使用 DNS 負載平衡的集區必須有兩個 Fqdn： DNS 負載平衡 (所使用的一般集區 FQDN，例如 pool01.contoso.com) ，並解析為集區中伺服器的實體 Ip，以及集區 Web 服務的另一個 FQDN (例如，web01.contoso.com) ，可解析為集區的虛擬 IP 位址。 
    
    在 [拓撲產生器] 中，如果您想要為集區部署 DNS 負載平衡，若要為集區的 Web 服務建立額外的 FQDN，您必須選取 [覆 **寫內部 Web 服務集區 FQDN** ] 核取方塊，然後在 [ **指定 Web 服務 URLs 中為此集** 區] 頁面中輸入 FQDN。
    
- 若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。
    
    > [!CAUTION]
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 **pool01.contoso.com**，則無法將 **pool01.contoso.com** 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Edge Server 集區上的 DNS 負載平衡
<a name="BK_Edge"> </a>

您可以在 Edge Server 集區上部署 DNS 負載平衡。如果這麼做，則必須注意下列考量。
  
在 Edge Server 上使用 DNS 負載平衡，會導致下列案例喪失容錯移轉能力：
  
- 與執行 Lync Server 2010 前發行的商務用 Skype Server 版本的組織同盟。
    
- 透過 XMPP IM) 服務 AOL 和 Yahoo！，除了型提供者和伺服器（如 Google 談話）之外的立即訊息 (交換，您也是目前唯一支援的 XMPP 合作夥伴。
    
只要集區中的所有 Edge Server 都啟動並執行，這些案例就能運作，但是如果其中一個 Edge Server 無法使用，則在這些案例中任何傳送給該 Edge Server 的要求都會失敗，而不是路由至另一個 Edge Server。
  
 如果您使用 Exchange UM，您必須至少使用 Exchange 2013，以取得對 Edge 商務用 Skype Server DNS 負載平衡的支援。 如果您使用舊版的 Exchange，您的遠端使用者將不會有這些 Exchange UM 案例的容錯移轉功能：
  
- 在電話上播放其 Enterprise 語音信箱
    
- 從 Exchange UM 自動語音應答轉接通話
    
所有其他 Exchange UM 案例則會正常運作。
  
內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge Server 集區上部署 DNS 負載平衡

若要在 Edge Server 集區的外部介面上部署 DNS 負載平衡，您需要下列 DNS 項目：
  
- 對於 Access Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Access Edge service 的 IP 位址。
    
- 針對 Web 會議 Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 至集區中某一部 Edge Server 上的 Web 會議 Edge service 的 IP 位址。
    
- 針對 Audio/Video Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 A/V Edge service 的 IP 位址。
    
若要在 Edge Server 集區的內部介面上部署 DNS 負載平衡，您必須新增一筆 DNS A 記錄，並讓它將 Edge Server 集區的內部 FQDN 解析為集區中每部伺服器的 IP 位址。
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中繼伺服器集區上使用 DNS 負載平衡
<a name="BK_Mediation"> </a>

您可以在獨立中繼伺服器集區上使用 DNS 負載平衡，所有 SIP 和媒體流量都是透過 DNS 負載平衡進行平衡處理。
  
若要在中繼伺服器集區上部署 DNS 負載平衡，您必須佈建 DNS，以將集區 FQDN (例如，mediationpool1.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 負載平衡封鎖伺服器的流量
<a name="BK_Mediation"> </a>

如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。 
  
請注意，針對伺服器對伺服器的流量，商務用 Skype Server 使用拓撲感知負載平衡。 伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。 若要封鎖伺服器接收伺服器對伺服器的流量，您必須從拓撲中移除伺服器。 
