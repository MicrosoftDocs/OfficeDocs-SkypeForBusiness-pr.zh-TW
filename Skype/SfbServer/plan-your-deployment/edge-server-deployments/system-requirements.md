---
title: 商務用 Skype Server 中的 Edge Server 系統需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：瞭解在商務用 Skype Server 中 Edge Server 的系統需求。
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221023"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>商務用 Skype Server 中的 Edge Server 系統需求
 
**摘要：** 深入瞭解在商務用 Skype Server 中的 Edge Server 的系統需求。
  
當您前往商務用 Skype Server Edge Server 部署時，您需要針對環境本身中的伺服器或伺服器進行下列作業，以及規劃環境結構。 如需拓撲、DNS、憑證及其他基礎結構問題的詳細資訊，請參閱環境需求檔。
  
## <a name="components"></a>零件

當您討論 Edge Server 環境時，我們正在參考大多數在周邊網路中部署的元件（也就是在您的工作組或位於商務用 Skype Server 域結構之外的網域中）。
  
請記住，這些是您在成功部署 Edge 時需要記住的元件：
  
- [Edge Server](system-requirements.md#EdgeServers)
    
- [反向 proxy](system-requirements.md#ReverseProxies)
    
- [防火牆](system-requirements.md#Firewalls)
    
- [Director](system-requirements.md#Directors) （這些是選用性，如果有的話），就會位於您的內部網路上。
    
- [負載平衡](system-requirements.md#LoadBalancers)器（您可以使用 DNS 負載平衡或硬體負載平衡器（HLB），但是針對單一 Edge Server，不需要這麼做。
    
我們每個下列各項都有詳細資訊：
  
### <a name="edge-servers"></a>Edge Server
<a name="EdgeServers"> </a>

這些是部署在周邊環境中的商務用 Skype 伺服器。 其角色是針對內部商務用 Skype Server 部署所提供的服務，傳送和接收網路流量給外部使用者。 若要成功執行這項作業，每個 Edge Server 都會執行：
  
- **Access Edge service**：為輸出和輸入會話初始通訊協定（SIP）流量提供單一、受信任的連接點。
    
- **Web 會議 Edge service**：可讓外部使用者加入內部商務用 Skype 伺服器環境所主控的會議。
    
- **A/V Edge service**：讓外部使用者可以使用音訊、影片、應用程式共用和檔案傳輸。
    
- **XMPP Proxy 服務**：接受及傳送可延伸的訊息和顯示狀態通訊協定（XMPP）郵件，並從設定的 XMPP 同盟協力廠商傳送。
    
已授權的外部使用者可以使用 Edge Server 連線到內部的商務用 Skype Server 部署，但在其他情況下，不會為任何人提供內部網路的其他存取權。
  
> [!NOTE]
> 部署 Edge Server 以提供連線至已啟用商務用 Skype 用戶端和其他 Edge Server （在同盟情況下）的連線。 您無法從其他端點用戶端或伺服器類型進行連線。 XMPP 閘道伺服器可允許與已設定 XMPP 合作夥伴的連線。 不過，這些是唯一可以運作的用戶端和同盟類型。 

> [!NOTE]
> XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="reverse-proxies"></a>反向 proxy
<a name="ReverseProxies"> </a>

反向 proxy （RP）伺服器沒有商務用 Skype 伺服器角色，但為 Edge Server 部署的基本元件。 反向 proxy 允許外部使用者執行下列作業：
  
- 使用簡單 URLs 連線到會議或電話撥入式會議。
    
- 下載會議內容。
    
- 展開 [通訊群組]。
    
- 取得以使用者為基礎的憑證，以供用戶端憑證驗證
    
- 從通訊錄服務器下載檔案，或將查詢提交至通訊錄 Web 查詢服務。
    
- 取得用戶端和裝置軟體的更新。
    
對於行動裝置：
  
- 它可讓他們自動探索前端伺服器提供行動性服務。
    
- 它會啟用從 Microsoft 365 或 Office 365 到行動裝置的推播通知。
    
目前的反向 proxy 建議可在商務用 Skype 頁面的[電話語音基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)上找到。 您的反向 proxy：
  
- 應該能夠使用透過公用憑證引入您環境的傳輸層安全性（TLS），以連線至已發佈的外部 Web 服務：
    
  - Director 或 Director 集區
    
  - 前端伺服器或前端集區
    
- 必須能夠發佈使用憑證進行加密的內部網站，或在必要時以未加密的方式發佈。
    
- 應該能夠使用完整功能變數名稱（FQDN），從外部發佈內部主控的網站。
    
- 必須能夠發佈主控網站的所有內容。 根據預設，您可以使用 **/\\** * 指令，大多數的網頁伺服器都能辨識此指令，以表示「在網頁伺服器上發行所有內容」。 您也可以修改此指令（例如，* */Uwca/ \\ * * *），這表示「發行虛擬目錄 Ucwa 下的所有內容」。
    
- 必須要求與用戶端的 TLS 連線，用戶端會從您發佈的網站要求內容。
    
- 必須接受主體替代名稱（SAN）專案的憑證。
    
- 必須能夠允許將憑證系結至攔截器或介面，以供外部 web 服務 FQDN 解析。 監聽器設定優於介面。 在單一介面上可以設定許多監聽器。
    
- 必須允許設定主機標頭處理。 通常會以透明的方式傳遞要求用戶端所傳送的原始主機標頭，而不是反向 proxy 進行修改。
    
- 應該允許將 TLS 流量從一個外部定義的埠（例如，TCP 443）橋接至另一個已定義的埠（例如，TCP 4443）。 您的反向 proxy 可能會在接收時解密封包，然後在傳送時重新加密封包。
    
- 應該允許將未加密的 TCP 流量從一個埠（例如，TCP 80）橋接至另一個埠（例如，TCP 8080）。
    
- 需要允許設定或接受 NTLM 驗證、沒有驗證，以及透過驗證。
    
如果您的反向 proxy 可以解決此清單中的所有需求，您應該可以走好，但請在上述連結中記住我們的建議。
  
### <a name="firewalls"></a>防火牆
<a name="Firewalls"> </a>

您必須將 Edge 部署置於外部防火牆背後，但建議您在 Edge 環境和您的內部環境之間有兩個防火牆，一個外部的防火牆，一個內部的防火牆。 我們案例中的所有檔都有兩個防火牆。 我們建議兩個防火牆，因為它可確保從一個網路 edge 嚴格地路由傳送到另一個，並將內部網路的防火牆保護加倍。
  
### <a name="directors"></a>董事
<a name="Directors"> </a>

這是選用的角色。 它可以是單一伺服器或執行 Director 角色之伺服器的集區。 這是在內部商務用 Skype 伺服器環境中找到的角色。
  
Director 是一個內部的下一個躍點伺服器，可從目的地為商務用 Skype 伺服器內部伺服器的 Edge server 接收輸入 SIP 流量。 它會 preauthenticates 輸入要求並將其重新導向至使用者的主集區或伺服器。 這種預驗證可讓您丟棄未識別的使用者帳戶要求。
  
為何這麼做？ Director 的一個重要功能是保護 Standard Edition server 和前端伺服器或前端集區免受惡意流量的攻擊，例如拒絕服務（DoS）攻擊。 如果您的網路因外部流量無效而淹沒，則流量會停止在 Director 上。
  
### <a name="load-balancers"></a>負載平衡器
<a name="LoadBalancers"> </a>

商務用 Skype 伺服器調整式合併 Edge 拓撲已針對新部署的 DNS 負載平衡進行優化，我們建議這樣做。 如果您需要高可用性，建議使用硬體負載平衡器以取得一個特定狀況：
  
- Exchange 2013**之前**使用 exchange um 的遠端使用者的 exchange um。
    
> [!IMPORTANT]
> 請務必注意，您不能混合負載平衡器。 在商務用 Skype 伺服器環境中，所有介面都必須使用 DNS 或 HLB。 
  
> [!NOTE]
> 商務用 Skype Server 不支援 Direct server return （DSR） NAT。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>執行 A/V Edge service 之 Edge Server Edge Server 的硬體負載平衡器需求

針對執行 A/V Edge service 的任何 Edge Server，這些需求如下：
  
- 關閉內部及外部埠443的 TCP Nagling （Nagling 是將數個小型封包組合成單一、較大的資料包，以取得更有效率的傳輸）的程式。
    
- 關閉外部埠範圍 50000-59999 的 TCP Nagling。
    
- 請勿在您的內部或外部防火牆上使用 NAT。
    
- 您的 Edge 內部介面必須位於與 Edge Server 外部介面不同的網路上，而且必須停用兩者之間的路由。
    
- 任何執行 A/V Edge service 之 Edge Server 的外部介面，都必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。
    
#### <a name="hlb-requirements"></a>HLB 需求

商務用 Skype 伺服器沒有許多 cookie 的關聯性需求。 所以您不需要使用 cookie 型持續性，**除非**（而且這是商務用 skype server 2015 特有的 skype server），您就會在商務用 skype 伺服器環境中擁有 Lync Server 2010 前端伺服器或前端集區。 在 Lync Server 2010 的設定方法中，將需要以 cookie 為基礎的關聯性。
  
> [!NOTE]
> 如果您決定為您的 HLB 開啟 cookie 基礎的親近性，即使您的環境不需要，也不會發生問題。 
  
如果您的環境**不**需要以 cookie 為基礎的相似性：
  
- 在埠443的反向 proxy 發行規則上，將 [**轉寄主機標頭**] 設定為**True**。 這可確保原始 URL 已轉寄。
    
針對需要以 cookie 為基礎之**相似性的部署**：
  
- 在埠443的反向 proxy 發行規則上，將 [**轉寄主機標頭**] 設定為**True**。 這可確保原始 URL 已轉寄。
    
- 硬體負載平衡器 cookie**不得**標示為 HTTPOnly。
    
- 硬體負載平衡器 cookie**不得**具有到期時間。
    
- 硬體負載平衡器 cookie**必須**命名為**MS-WSMAN** （這是 Web 服務預期的值，而且無法變更）。
    
- 您**必須**在每個傳入的 HTTP 要求沒有 COOKIE 的 HTTP 回應中設定硬體負載平衡器 cookie，不論相同 TCP 連線上先前的 HTTP 回應是否已取得 cookie。 如果您的硬體負載平衡器優化 cookie 插入只會在每個 TCP 連線時發生一次，則**不得**使用該優化。
    
> [!NOTE]
> 對於商務用 Skype 伺服器及其用戶端，HLB 設定使用來源-親近性和20分鐘的 TCP 會話存留時間，因為會話狀態是透過用戶端使用狀況和/或應用程式互動來維護的，所以很正常。 
  
如果您要部署行動裝置，HLB 必須能夠在 TCP 會話內對個別要求進行負載平衡（實際上，您必須能夠根據目標 IP 位址來負載平衡個別要求）。
  
> [!IMPORTANT]
> F5 HLBs 具有一個稱為 OneConnect 的功能。 它可確保針對 TCP 連線中的每個要求進行個別的負載平衡。 如果您要部署行動裝置，請確定您的 HLB 廠商支援相同的功能。 最新的 iOS 行動裝置應用程式需要 TLS 版本1.2。 如果您需要深入瞭解，按 F5 會為此提供特定設定。 
  
以下是（optional） Director 及（必要）前端集區 Web 服務的 HLB 需求：
  
- 針對您的內部 Web 服務 VIPs，設定 HLB 上的 Source_addr 持久性（內部埠80，443）。 若為商務用 Skype Server，Source_addr 持續性表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器，以維護會話狀態。
    
- 使用的 TCP 閒置超時為1800秒。
    
- 在反向 proxy 與下一個躍點集區 HLB 之間的防火牆上，建立規則以允許埠4443上的 HTTPs：流量，從反向 proxy 到您的 HLB。 您的 HLB 需要設定為接聽埠80、443及4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相關性需求摘要

|**用戶端/使用者位置**|**外部 Web 服務 FQDN 相似性需求**|**內部 web 服務 FQSN 關聯性需求**|
|:-----|:-----|:-----|
|商務用 Skype Web App （內部和外部使用者）  <br/> 行動裝置（內部和外部使用者  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
|商務用 Skype Web App （僅限外部使用者）  <br/> 行動裝置（內部和外部使用者  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
|商務用 Skype Web App （僅限內部使用者）  <br/> 行動裝置 (未部署)  <br/> |無相似性  <br/> |來源位址相似性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLBs 的埠監視

您可以在硬體負載平衡器上定義埠監視，以決定何時不再提供特定服務，因為硬體或通訊失敗。 例如，如果前端伺服器服務（RTCSRV）停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。 您應該在 HLB 上執行埠監視，以監視下列 HLB 外部介面：
  
|**虛擬 IP/連接埠**|**節點連接埠**|**節點電腦/監視器**|**持續性設定檔**|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|\<集區 \> web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTPS:  <br/> |
|\<集區 \> web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTP:  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬體及軟體需求

我們已在商務用 skype server 2015 的整體[伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[商務用 skype server 2019 檔的系統需求](../../../SfBServer2019/plan/system-requirements.md)中，涵蓋了 Edge server 的硬體和軟體需求。
  
## <a name="collocation"></a>搭配

我們已在我們的《商務用[Skype server 檔」的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)上涵蓋 Edge server 組合。
  

