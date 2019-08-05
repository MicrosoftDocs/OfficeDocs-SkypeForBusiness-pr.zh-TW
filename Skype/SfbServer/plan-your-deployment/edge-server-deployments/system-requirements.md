---
title: 商務用 Skype Server 中的邊緣伺服器系統需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: '摘要: 瞭解在商務用 Skype Server 中 Edge 伺服器的系統需求。'
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187807"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>商務用 Skype Server 中的邊緣伺服器系統需求
 
**摘要:** 瞭解商務用 Skype Server 中 Edge 伺服器的系統需求。
  
在您的商務用 Skype Server Edge 伺服器部署中, 這些是您針對環境本身中的伺服器或伺服器所需執行的操作, 以及規劃環境結構。 如需有關拓撲、DNS、憑證及其他基礎結構問題的詳細資訊, 請參閱環境需求檔。
  
## <a name="components"></a>元件

在討論 Edge 伺服器環境時, 我們會參照大多數在周邊網路中部署的元件 (也就是在工作組或商務用 Skype Server 網域結構以外的網域中)。
  
請記住這一點, 您必須牢記以下元件, 才能成功部署 Edge:
  
- [Edge 伺服器](system-requirements.md#EdgeServers)
    
- [反向代理](system-requirements.md#ReverseProxies)
    
- [道](system-requirements.md#Firewalls)
    
- [主管](system-requirements.md#Directors)(這是選擇性的, 如果包含的話, 它們就會位於您的內部網路上)
    
- [負載平衡](system-requirements.md#LoadBalancers)器(您可以使用 DNS 負載平衡或硬體負載平衡器 (HLB), 但針對單一邊緣伺服器則不需要這麼做。
    
我們在下列各項中有更多詳細資料:
  
### <a name="edge-servers"></a>Edge 伺服器
<a name="EdgeServers"> </a>

這些是部署在週邊環境中的商務用 Skype 伺服器。 其角色是針對您內部商務用 Skype Server 部署所提供的服務, 傳送和接收外部使用者的網路流量。 若要成功執行此動作, 每個 Edge 伺服器都會執行:
  
- **存取邊緣服務**: 針對輸出與輸入會話初始通訊協定 (SIP) 流量, 提供單一、受信任的連接點。
    
- **網路會議 Edge 服務**: 可讓外部使用者加入託管在內部商務用 Skype Server 環境中的會議。
    
- **A/V 邊緣服務**: 讓外部使用者可以使用音訊、影片、應用程式共用和檔案傳輸。
    
- **XMPP Proxy service**: 在已設定的 XMPP 同盟合作夥伴中, 接受和傳送可擴展的訊息和目前狀態通訊協定 (XMPP) 訊息。
    
已授權的外部使用者可以使用 Edge 伺服器連線到內部商務用 Skype Server 部署, 否則不會提供任何人對您內部網路的其他存取權。
  
> [!NOTE]
> 已部署邊緣伺服器來提供已啟用商務用 Skype 用戶端和其他邊緣伺服器 (在同盟情況中) 的連線。 您無法從其他端點用戶端或伺服器類型進行連線。 XMPP 閘道伺服器可以允許與已設定 XMPP 夥伴的連線。 但同樣地, 這些都是唯一的用戶端和同盟類型可運作。 

> [!NOTE]
> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="reverse-proxies"></a>反向代理
<a name="ReverseProxies"> </a>

反向 proxy (RP) 伺服器沒有商務用 Skype 伺服器角色, 但是 Edge 伺服器部署的基本元件。 反向 proxy 允許外部使用者進行下列動作:
  
- 使用簡單的 Url 連線至會議或電話撥入式會議。
    
- 下載會議內容。
    
- 展開 [通訊群組]。
    
- 取得用戶端憑證的基於使用者認證的驗證
    
- 從通訊錄服務器下載檔案, 或將查詢提交至通訊錄網頁查詢服務。
    
- 取得用戶端與裝置軟體的更新。
    
針對行動裝置:
  
- 它可讓他們自動探索提供行動服務的前端伺服器。
    
- 它可讓您從 Office 365 推播通知至行動裝置。
    
我們可以在商務用 Skype 頁面的[電話架構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)中找到目前的反向 proxy 建議。 所以您的反向 proxy:
  
- 應該能夠使用您的環境中引入的傳輸層安全性 (TLS), 透過公用憑證連線到已發佈的外部 Web 服務:
    
  - 主管或主管池
    
  - 前端伺服器或前端池
    
- 需要能夠使用憑證進行加密來發佈內部網站, 或以未加密的方式發佈它們 (如果需要的話)。
    
- 應該能夠使用完全限定的功能變數名稱 (FQDN), 在外部發佈內部託管的網站。
    
- 需要能夠發佈您所託管網站的所有內容。 根據預設, 您可以使用** / *** 指令, 大多數的 web 伺服器都會辨識此程式, 表示「在 web 伺服器上發佈所有內容」。 您也可以修改指令, 例如 * */Uwca/\\* * *, 這表示「在虛擬目錄 Ucwa 中發佈所有內容」。
    
- 必須與從您發佈的網站要求內容的用戶端, 才需要 TLS 連線。
    
- 必須接受使用 [消費者備用名稱 (SAN)] 專案的憑證。
    
- 需要能夠將憑證系結到偵聽程式或介面, 才能透過外部 web 服務 FQDN 解析。 偵聽程式設定優於介面。 許多監聽器可以在單一介面上設定。
    
- 必須允許主機標頭處理的設定。 通常, 由要求用戶端傳送的原始主機標頭必須透明地傳遞, 而不是由反向 proxy 進行修改。
    
- 應該允許將 TLS 流量從一個外部定義的埠 (例如, TCP 443) 橋接到另一個已定義的埠 (例如, TCP 4443)。 您的反向 proxy 可能會在接收時解密資料包, 然後在傳送時 reencrypt 該資料包。
    
- 應該允許將未加密 TCP 流量從一個埠 (例如 TCP 80) 橋接到另一個埠 (例如 TCP 8080)。
    
- 需要允許設定或接受 NTLM 驗證、無驗證, 以及傳遞驗證。
    
如果您的反向 proxy 能滿足此清單中的所有需求, 您應該可以開始使用, 但請記住上述連結的建議。
  
### <a name="firewalls"></a>道
<a name="Firewalls"> </a>

您需要將 Edge 部署放在外部防火牆後面, 但我們建議您在邊緣環境和您的內部環境中, 有兩個防火牆 (一個外部, 一個內部)。 我們所有案例中的所有檔都將會有兩個防火牆。 我們建議您兩個防火牆, 因為它可確保嚴格地從一個網路邊緣路由至另一個, 並將內部網路的防火牆保護加倍。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

此為選用的角色。 它可以是單一伺服器或執行主管角色的伺服器池。 它是在內部商務用 Skype Server 環境中找到的角色。
  
Director 是內部的下一個躍點伺服器, 會從傳送給商務用 Skype Server 內部伺服器的邊緣伺服器接收入站 SIP 流量。 它會 preauthenticates 輸入要求, 並將它們重新導向至使用者的主文件池或伺服器。 這個預驗證可讓您刪除不可識別的使用者帳戶要求。
  
為什麼這麼重要？ 主管的重要功能是保護標準版伺服器與前端伺服器或前端池免遭惡意流量 (例如拒絕服務 (DoS) 攻擊)。 如果您的網路充斥了不正確外部流量, 通信量就會停止在 Director 上。
  
### <a name="load-balancers"></a>負載平衡器
<a name="LoadBalancers"> </a>

商務用 Skype 伺服器伸縮的合併邊緣拓朴已針對新部署的 DNS 負載平衡進行優化, 我們建議這樣做。 如果您需要高可用性, 建議您針對其中一個特定情況使用硬體負載平衡器:
  
- Exchange 2013**之前**使用 exchange um 的遠端使用者的 exchange um。
    
> [!IMPORTANT]
> 請務必注意, 您無法混合負載平衡器。 在您的商務用 Skype Server 環境中, 所有介面都必須使用 DNS 或 HLB。 
  
> [!NOTE]
> 商務用 Skype Server 不支援直接伺服器返回 (DSR) NAT。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>執行 A/V 邊緣服務的邊緣伺服器邊緣伺服器的硬體負載平衡器需求

針對執行 A/V 邊緣服務的任何邊緣伺服器, 以下是一些需求:
  
- 關閉內部和外部埠443的 TCP Nagling (Nagling 是將幾個小型資料包合併成一個較大的資料包, 以更有效率地傳輸) 的程式。
    
- 關閉外部埠範圍 50000-59999 的 TCP Nagling。
    
- 請勿在您的內部或外部防火牆上使用 NAT。
    
- 您的 Edge 內部介面必須與邊緣伺服器外部介面在不同的網路上, 而且必須停用它們之間的路由。
    
- 執行 A/V 邊緣服務的任何邊緣伺服器的外部介面, 都必須使用可公開路由的 IP 位址, 而且任何邊緣外部 IP 位址都沒有 NAT 或埠轉譯。
    
#### <a name="hlb-requirements"></a>HLB 需求

商務用 Skype 伺服器不會有許多 cookie 關聯需求。 因此, 您不需要使用以 cookie 為基礎的持久性,**除非**(這是商務用 skype server 2015), 否則您會在商務用 skype server 環境中擁有 Lync Server 2010 前端伺服器或前端池。 它們在 Lync Server 2010 建議的設定方法中需要以 cookie 為基礎的關聯性。
  
> [!NOTE]
> 如果您決定針對您的 HLB 開啟以 cookie 為基礎的關聯性, 即使您的環境不需要它, 也不會發生問題。 
  
如果您的環境**不**需要以 cookie 為基礎的關聯:
  
- 在埠443的反向 proxy 發佈規則中, 將 [**轉寄主機頭**] 設定為**True**。 這可確保原始 URL 已轉寄。
    
針對需要以**** cookie 為基礎的關聯的部署:
  
- 在埠443的反向 proxy 發佈規則中, 將 [**轉寄主機頭**] 設定為**True**。 這可確保原始 URL 已轉寄。
    
- 硬體負載平衡器 cookie**不**能標示為 [HTTPOnly]。
    
- 硬體負載平衡器 cookie**不**能有到期時間。
    
- 硬體負載平衡器 cookie**必須**命名為**MS-WSMAN** (這是 Web 服務預期的值, 且無法變更)。
    
- 硬體負載平衡器 cookie**必須**在每一個 HTTP 回應中設定 (無論是否已在相同的 TCP 連線中先前的 HTTP 回應都已取得 cookie)。 如果您的硬體負載平衡器針對每個 TCP 連線優化 cookie 插入, 則**不一定**要使用這種優化。
    
> [!NOTE]
> 典型的 HLB 設定是使用來源關聯和20分鐘 TCP 會話存留期 (適用于商務用 Skype Server 及其用戶端), 因為會話狀態是透過用戶端使用量和/或應用程式互動來維護。 
  
如果您要部署行動裝置, 您的 HLB 必須能夠在 TCP 會話中的個別要求之間進行負載平衡 (事實上, 您必須能夠根據目標 IP 位址來負載平衡個別要求)。
  
> [!IMPORTANT]
> F5 HLBs 具有稱為 [OneConnect] 的功能。 它可確保 TCP 連線中的每個要求都有個別的負載平衡。 如果您要部署行動裝置, 請確定您的 HLB 供應商支援相同的功能。 最新的 iOS 行動裝置 app 需要 TLS 版本1.2。 如果您需要進一步瞭解, F5 會針對此提供特定設定。 
  
以下是 (選用) 主管及 (必要) 前端池 Web 服務的 HLB 需求:
  
- 針對您的內部 Web 服務 Vip, 請在您的 HLB 上設定 Source_addr 暫留 (內部埠 80, 443)。 在商務用 Skype Server 中, Source_addr [暫留] 表示來自單一 IP 位址的多個連線總是傳送到一台伺服器, 以維持會話狀態。
    
- 使用1800秒的 TCP 空閒超時。
    
- 在您的反向 proxy 與下一個躍點池的 HLB 之間, 建立規則, 允許從您的反向 proxy 到您的 HLB, 在埠4443上進行 HTTPs: 流量。 您的 HLB 需要設定為偵聽埠80、443和4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 關聯需求摘要

|**用戶端/使用者位置**|**外部 web 服務 FQDN 關聯需求**|**內部 web 服務 FQSN 關聯需求**|
|:-----|:-----|:-----|
|商務用 Skype Web App (內部和外部使用者)  <br/> 行動裝置 (內部和外部使用者  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
|商務用 Skype Web App (僅限外部使用者)  <br/> 行動裝置 (內部和外部使用者  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
|商務用 Skype Web App (僅限內部使用者)  <br/> 行動裝置 (未部署)  <br/> |沒有關聯性  <br/> |來源位址關聯  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLBs 的埠監視

您可以在硬體負載平衡器上定義埠監視, 以判斷特定服務何時無法使用, 因為硬體或通訊失敗。 例如, 如果前端伺服器或前端池發生故障, [前端伺服器服務 (RTCSRV)] 停止, 則 HLB 監視也應該停止在 Web 服務上接收流量。 您應該在 HLB 上執行埠監視, 以監視 HLB 外部介面的下列事項:
  
|**虛擬 IP/埠**|**節點埠**|**節點電腦/監視器**|**持久性設定檔**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |無  <br/> |IP-HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |無  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬體和軟體需求

我們已在商務用 skype Server 2015 和[商務用 Skype server 2019 檔的系統需求](../../../SfBServer2019/plan/system-requirements.md)[的完整伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)中, 涵蓋了 Edge 伺服器硬體和軟體需求。
  
## <a name="collocation"></a>Collocation

我們已在我們[針對商務用 Skype Server 檔的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)中涵蓋了 Edge 伺服器 collocation。
  

