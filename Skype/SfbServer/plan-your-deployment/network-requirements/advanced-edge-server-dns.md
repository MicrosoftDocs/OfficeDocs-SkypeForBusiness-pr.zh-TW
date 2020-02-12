---
title: 商務用 Skype Server 的高級邊緣伺服器 DNS 規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要：查看商務用 Skype Server 部署選項的案例。 無論您是要使用單一伺服器或慣用伺服器池（含 DNS 或 HLB），本主題都應該有所協助。
ms.openlocfilehash: b3893c11e1ce0cfdf9ab0b0452ef0a30a6442ee7
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887760"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>商務用 Skype Server 的高級邊緣伺服器 DNS 規劃
 
**摘要：** 查看商務用 Skype Server 部署選項的案例。 無論您是要使用單一伺服器或慣用伺服器池（含 DNS 或 HLB），本主題都應該有所協助。
  
當您參與商務用 Skype Server 的網域名稱系統（DNS）規劃時，可能會有許多因素可供您決定。 如果貴組織的網域結構已經存在，這可能是審查您要如何繼續進行的一個重要做法。 我們將從以下所述的主題開始：
  
- [商務用 Skype 用戶端尋找服務的逐步解說](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [分割大腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [不含分裂的 DNS 的自動設定](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 災害復原](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>商務用 Skype 用戶端尋找服務的逐步解說
<a name="WalkthroughOfSkype"> </a>

商務用 skype 用戶端與舊版 Lync 用戶端類似于在商務用 Skype Server 中尋找及存取服務的方式。 本節詳細說明伺服器位置處理常式。
  
1. lyncdiscoverinternal.\<網域\>
    
     *這是內部 web 服務的自動探索服務的主機記錄。* 
    
2. lyncdiscover.\<網域\>
    
     *這是外部 web 服務的自動探索服務的主機記錄。* 
    
3. _sipinternaltls. _tcp。\<網域\>
    
     *這是內部 TLS 連線的 SRV 記錄。* 
    
4. _sip. _tls。\<網域\>
    
     *這是外部 TLS 連線的 SRV 記錄。* 
    
5. sipinternal.\<網域\>
    
     *這是前端池或控制器的主機記錄，只能在內部網路上解析。* 
    
6. 呼吸.\<網域\>
    
     *這是前端池或控制器的主機記錄，只能在內部網路上解析。* 
    
7. sipexternal.\<網域\>
    
     *這是當用戶端為外部時，存取邊緣服務的主機記錄。* 
    
自動探索服務總是被認為是服務位置的首選方法，而其他則是後備方法。
  
> [!NOTE]
> 當您建立 SRV 記錄時，請務必記住，必須在建立 DNS SRV 記錄的同一個網域中，指向 DNS A （如果您使用的是 IPv6 定址，則是 AAAA）。 例如，如果其 SRV 記錄位於 contoso.com，則其指向的 A （和 AAAA）記錄不能位於 fabrikam.com 中。 
  
如果您傾向這樣做，您可以將行動裝置設定為手動搜尋服務。 如果這是您想要執行的動作，每個使用者都需要使用完整的內部和外部自動探索服務 Uri 來設定其行動裝置設定，包括通訊協定和路徑，如下所示：
  
- 外部存取： HTTPs://\<ExtPoolFQDN/Autodiscover/autodiscoverservice.svc/Root\>
    
- 內部存取： HTTPs://\<IntPoolFQDN/AutoDiscover/AutoDiscover.svc/Root\>
    
我們建議您使用 [自動探索]，而非手動搜尋。 但如果您正在進行一些疑難排解或測試，手動設定就很有説明。
  
## <a name="split-brain-dns"></a>分割大腦 DNS
<a name="SplitBrainDNS"> </a>

這是 DNS 配置，您有兩個具有相同命名空間的 DNS 區域。 第一個 DNS 區域會處理內部要求，而第二個 DNS 區域會處理外部要求。
  
公司為什麼要這麼做？ 它們可能需要在內部和外部使用相同的命名空間，但當然這會造成許多 DNS SRV 與記錄在單一區域或另一個區域中都是唯一的，而且有重複專案，與這些記錄相關聯的 IP 位址將是唯一的。
  
這會帶來一些挑戰。 最重要的是，**不支援**將分裂的 DNS 用於行動。 這是因為 LyncDiscover 和 LyncDiscoverInternal 的 DNS 記錄（LyncDiscover 必須在您的外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須在您的內部 DNS 伺服器上定義）。
  
我們將在這裡列出內部和外部區域的 DNS 記錄，但您可以在 Edge 伺服器的 [環境需求] 區段中找到詳細範例。
  
### <a name="internal-dns"></a>內部 DNS

- 包含名為 contoso.com 的 DNS 區域（例如），其為權威性。
    
- 這個內部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），適用于您的前端池、主管池或控制器池名稱，以及在貴組織的網路中執行商務用 Skype 伺服器的所有內部伺服器。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），適用于周邊網路中每個商務用 Skype Server Edge 伺服器的邊緣內部介面的記錄。
    
  - DNS A 和 AAAA （如果您是使用 IPv6 定址），用於提供周邊網路中每個反向 proxy 伺服器的內部介面（這是對反向 proxy 管理的**選擇性**）。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），以及內部商務用 Skype Server 用戶端自動設定（**選用**）的 SRV 記錄。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址）或 CNAME 記錄，以自動探索商務用 Skype Server Web 服務（**選用**）。
    
- 您周邊網路中的所有商務用 Skype Server 內部邊緣介面都使用這個內部 DNS 區域來解析要 contoso.com 的查詢。
    
- 所有執行商務用 Skype Server 的伺服器，以及在商業網路中執行商務用 Skype Server 的用戶端，指向 [內部 DNS 伺服器]，以便將查詢解析成 contoso.com，或在每個 Edge 伺服器上使用主機檔案並列出 A 和 AAAA （如果您使用的是IPv6 定址）適用于下一個躍點伺服器的記錄（特別是主管或控制器池 VIP、前端池 VIP 或標準版伺服器）。
    
### <a name="external-dns"></a>外部 DNS

- 包含名為 contoso.com 的 DNS 區域（例如），其為權威性。
    
- 這個外部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），或 CNAME 記錄，以自動探索商務用 Skype Server web 服務。 這是與行動性搭配使用。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），以及在周邊網路中每個商務用 Skype Server Edge 伺服器或硬體負載平衡（HLB） VIP 的邊緣外部介面的 SRV 記錄。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 定址），以及適用于反向 proxy 伺服器的外部介面（或反向 proxy 伺服器的 VIP），請在周邊網路中取得。
    
  - DNS A 與 AAAA （如果您使用的是 IPv6 定址）和商務用 Skype Server 用戶端自動設定的 SRV 記錄（**選用**）。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>不含分裂的 DNS 的自動設定
<a name="NoSplitBrainDNS"> </a>

如果您不使用分割大腦 DNS，除非您使用我們在這裡提供的其中一個因應措施，否則執行商務用 Skype 之用戶端的內部自動設定將無法運作。 為什麼不呢？ 因為商務用 Skype Server 需要使用者的 SIP URI，以符合為自動設定所指定的前端池網域。 這個版本沒有從舊版的 Lync Server 變更。
  
因此，如果您有兩個 SIP 網域在使用中，您就需要這些 DNS SRV 記錄：
  
- _sipinternaltls. _tcp。 在 SRV 0 0 5061 pool01.contoso.com 中的86400
    
     *如果使用者登入 bob@contoso.com，此記錄將可用於自動設定，因為使用者的 SIP 網域會與前端池（contoso.com）的網域相符。* 
    
- _sipinternaltls _tcp。 在 SRV 0 0 5061 pool01.fabrikam.com 中的86400
    
     *如果使用者登入 alice@fabrikam.com，則此記錄將可用於自動設定第二個網域，因為 SIP 網域符合該網域的 [前端] 池。* 
    
若要進一步執行這個範例，這將無法運作：
  
- _sipinternaltls _tcp。 在 SRV 0 0 5061 pool01.fabrikam.com 中的86400
    
     *以 tim@litwareinc.com 登入的使用者無法使用自動設定，因為其 SIP 網域（litwareinc.com）與池中的網域不相符（fabrikam.com）。* 
    
現在我們知道，如果您需要自動要求您的商務用 Skype 用戶端（沒有分裂大腦 DNS），您可以使用下列選項：
  
- **群組原則物件**
    
    您可以使用群組原則物件（Gpo）來填入正確的伺服器值。
    
    > [!NOTE]
    > 這個選項不會啟用自動設定，但會自動進行手動設定。 如果使用這個方法，就不需要與自動設定相關聯的 SRV 記錄。 
  
- **相符的內部區域**
    
    您需要在內部 DNS 中建立與您的外部 DNS 區域相符的區域（例如，contoso.com），然後建立 DNS A （如果您使用的是 IPv6 定址）與自動使用的商務用 Skype 伺服器池相對應的記錄（如果您使用的是 AAAA）configuration.
    
    例如，如果您的使用者是駐留在 pool01.contoso.net，但登入商務用 Skype （bob@contoso.com），請建立名為 contoso.com 的內部 DNS 區域，並將它放在其中，您必須建立 DNS A （以及 AAAA （如果使用 IPv6 定址）記錄 pool01.contoso.com。
    
- **固定點內部區域**
    
    如果在內部 DNS 中建立整個區域不是您的選項，您可以建立與自動設定所需的 SRV 記錄相對應的 pin 點（專用）區域，並使用 dnscmd 填入這些區域。 Dnscmd .exe 是必要的，因為 DNS 使用者介面不支援建立 pin 點區域。
    
    例如，如果您的 SIP 網域是 contoso.com，而您有一個名為 pool01 的前端池（其中包含兩個前端伺服器），您將需要下列 pin 點區域及內部 DNS 中的記錄：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    您的環境中可能會有第二個 SIP 網域。 在這種情況下，您將需要下列 pin 點區域及內部 DNS 中的記錄：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> 您會看到前端池 FQDN 出現了兩次，但有兩個不同的 IP 位址。 這是因為使用了 DNS 負載平衡。 如果使用 HLB，則只有一個前端池專案。 
  
> [!NOTE]
> 此外，前端池 FQDN 值會在 contoso.com 與 fabrikam.com 範例之間變更，但 IP 位址會保持不變。 這是因為從任一 SIP 網域登入的使用者將會使用相同的前端池來自動設定。 
  
## <a name="dns-disaster-recovery"></a>DNS 災害復原
<a name="DNSDR"> </a>

若要設定 DNS 將商務用 Skype Server web 流量重新導向到災難復原（DR）及容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。 您可以設定您的 DNS 記錄以支援災難復原，因此即使一個完整的前端池已停機，使用 web 服務的功能仍會繼續。 此 DR 功能支援自動探索、[符合] 和 [撥入] 簡單的 Url。
  
您可以在您的 GeoDNS 提供者處，定義及設定其他 DNS 主機 A （如果使用 IPv6，則是 AAAA）的內部和外部解析 web 服務的記錄。 下列詳細資料會假設成對式池、地理位置分散，且您的提供者所支援的 GeoDNS**要麼**具有迴圈 DNS，**要麼**是設定為使用 Pool1 作為主要，而且會在發生任何通訊遺失或電源故障時容錯移轉至 Pool2。
  
此資料表中的所有 DNS 記錄都是範例。
  
|**GeoDNS 記錄**|**資源庫記錄**|**CNAME 記錄**|**DNS 設定（選取一個選項）**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |在池之間進行迴圈複用  <br/> **或** <br/> 如果發生錯誤，請使用 [主要]，連線到副  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="DNSLB"> </a>

DNS 負載平衡通常是在應用程式層級實現。 應用程式（例如，執行商務用 Skype 的用戶端），會連線至 [DNS A] 和 [AAAA] （如果使用 IPv6 定址）中傳回的其中一個 IP 位址，以針對 [池 FQDN] 進行記錄查詢，連線至池中的伺服器。
  
例如，如果一個名為 pool01.contoso.com 的池中有三個前端伺服器，就會發生下列情況：
  
- 執行商務用 Skype 查詢 pool01.contoso.com 的用戶端。 查詢會傳回三個 IP 位址，並以下列順序將它們緩存：
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 用戶端嘗試建立與其中一個 IP 位址的 TCP 連線。 如果失敗，它會嘗試從該清單中快取的下一個 IP 位址。
    
- 如果 TCP 連線成功，用戶端會協商 TLS，連線到 pool01.contoso.com 上的主要註冊機構。
    
- 如果用戶端在未成功連線的情況下嘗試所有快取的專案，使用者就會收到一則通知，指出目前沒有任何伺服器執行商務用 Skype 伺服器。
    
> [!NOTE]
> 以 dns 為基礎的負載平衡與 DNS 迴圈（DNS RR）不同，通常是依靠 DNS，為您的池中的伺服器提供不同的 IP 位址順序來代表負載平衡。 通常，DNS RR 會啟用負載分配，但不允許您啟用容錯移轉。 例如，如果連線到您的 DNS A （或 IPv6 案例中的 AAAA）查詢所傳回的單一 IP 位址，該連線就會失敗。 這可讓 DNS RR 比以 DNS 為基礎的負載平衡更可靠。 如果您需要這麼做，您仍然可以將 DNS RR 與 DNS 的負載平衡搭配使用。 
  
您使用 DNS 負載平衡進行下列作業：
  
- 將伺服器間 SIP 的負載平衡到邊緣伺服器。
    
- [負載平衡] 的 [整合通訊應用程式服務（UCAS）] 應用程式，例如會議自動語音應答、回應群組，以及電話寄存。
    
- 防止新連線至 UCAS 應用程式（也稱為排出）。
    
- 在用戶端與邊緣伺服器之間，對所有用戶端與伺服器流量進行負載平衡。
    
您無法使用 DNS 負載平衡進行下列作業：
  
- 從用戶端到伺服器的 web 流量到您的前端伺服器或主管。
    
若要深入瞭解查詢傳回 mutiple DNS 記錄時所選取的 DNS SRV 記錄，Access Edge 服務會使用最低的數值優先順序來挑選該記錄，而且如果需要一個交叉斷路器，則是最高的數位寬度。 這與[網際網路工程工作強制檔](https://www.ietf.org/rfc/rfc2782.txt)是一致的。
  
例如，如果您的第一個 DNS SRV 記錄的權重是20且優先順序為40，而第二個 DNS SRV 記錄的權重為10且優先順序為50，則會選取第一筆記錄，因為它具有較低優先順序的40。 優先順序總是最先生效，而這是用戶端將最先進行目標的主機。 如果有兩個具有相同優先順序的目標，該怎麼辦？ 
  
在這種情況下，會考慮負擔。 在這種情況下，應為選取較大的權重。 如果沒有任何伺服器可供您選擇，DNS 管理員就應該使用權重0。 如果記錄中包含的權重大於0，則權重為0的記錄會有極小的選擇機會。
  
因此，如果傳回的多個 DNS SRV 記錄具有相同的優先順序和權重，就會發生什麼情況？ 在這種情況下，Access Edge 服務會先選擇它從 DNS 伺服器取得的 SRV 記錄。
  

