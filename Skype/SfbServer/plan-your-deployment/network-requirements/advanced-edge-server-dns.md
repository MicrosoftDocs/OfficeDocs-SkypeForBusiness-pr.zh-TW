---
title: 商務用 Skype Server 的高級 Edge Server DNS 規劃
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 商務用 Skype Server 部署選項的查看案例。 不管您是想要單一伺服器或喜歡使用 DNS 或 HLB 的伺服器集區，本主題都應該有所説明。
ms.openlocfilehash: 208098fe44238d9d96debbde7b8c00daf6622b91
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602348"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>商務用 Skype Server 的高級 Edge Server DNS 規劃
 
**摘要：** 商務用 Skype Server 部署選項的評審案例。 不管您是想要單一伺服器或喜歡使用 DNS 或 HLB 的伺服器集區，本主題都應該有所説明。
  
 (DNS) 規劃商務用 Skype Server 的網域名稱系統時，可能會有許多因素可納入您的決策。 如果您的組織的域結構已存在，這可能是複查您要繼續的方式。 我們將從以下找到的主題開始：
  
- [商務用 Skype 用戶端尋找服務的逐步解說](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [裂腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [沒有 split-大腦 DNS 的自動設定](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 災難修復](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>商務用 Skype 用戶端尋找服務的逐步解說
<a name="WalkthroughOfSkype"> </a>

商務用 Skype 用戶端在商務用 Skype Server 中尋找及存取服務的方式，類似于舊版的 Lync 用戶端。 本節詳細說明伺服器位置的處理常式。
  
1. lyncdiscoverinternal.\<domain\>
    
     *這是內部 web 服務上的自動探索服務的主機記錄。* 
    
2. lyncdiscover.\<domain\>
    
     *這是外部 web 服務上的自動探索服務的主機記錄。* 
    
3. _sipinternaltls _sipinternaltls._tcp。\<domain\>
    
     *這是內部 TLS 連線的 SRV 記錄。* 
    
4. _sip _sip._tls。\<domain\>
    
     *這是外部 TLS 連線的 SRV 記錄。* 
    
5. sipinternal.\<domain\>
    
     *這是前端集區或 Director 的主機記錄，只能在內部網路上加以解析。* 
    
6. Sip。\<domain\>
    
     *這是前端集區或 Director 的主機記錄，只能在內部網路上加以解析。* 
    
7. sipexternal.\<domain\>
    
     *當用戶端為外部用戶端時，這是 Access Edge service 的主機記錄。* 
    
自動探索服務的慣用習慣是服務位置的慣用方法，其他是 fallback 方法。
  
> [!NOTE]
> 當您建立 SRV 記錄時，請務必記住，如果您要使用 IPv6 定址) 在所建立 DNS SRV 記錄的相同網域中，則必須記住這些記錄必須指向 DNS A (和 AAAA。 例如，如果他們的 SRV 記錄在 contoso.com 中，則 (和 AAAA) 記錄會指向 fabrikam.com。 
  
如果您很傾向這麼做，您可以設定行動裝置，以供手動探索服務。 如果這是您想要做的事，每個使用者都必須使用完整的內部及外部自動探索服務 URIs （包括通訊協定和路徑）來設定其行動裝置設定，如下所示：
  
- 若為外部存取： HTTPs:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- 若為內部存取： HTTPs:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
我們建議您使用「自動探索」，而非手動探索。 不過，如果您要進行一些疑難排解或測試，手動設定會很有説明。
  
## <a name="split-brain-dns"></a>裂腦 DNS
<a name="SplitBrainDNS"> </a>

這是您有兩個具有相同命名空間的 DNS 區域的 DNS 設定。 第一個 DNS 區域會處理內部要求，而第二個 DNS 區域會處理外部要求。
  
為什麼公司會這麼做？ 他們可能需要在內部和外部使用相同的命名空間，但當然，這會導致許多 DNS SRV 和記錄在某個區域或另一個區域中是唯一的，而且有重複的記錄，與這些記錄相關聯的 IP 位址會是唯一的。
  
這種情況會帶來一些挑戰。 最重要的是， **不支援** 行動性的大腦 DNS。 這是因為 LyncDiscover 和 LyncDiscoverInternal DNS 記錄 (LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須在內部 DNS 伺服器上定義) 。
  
我們將在這裡列出內部及外部區域的 DNS 記錄，但您可以在 Edge Server 環境需求區段中尋找詳細的範例。
  
### <a name="internal-dns"></a>內部 DNS

- 包含名為 (的 DNS 區域，例如) contoso.com，其具有權威性。
    
- 這個內部 contoso.com 包含：
    
  - DNS A 和 AAAA (如果您要使用 IPv6 定址) 前端集區、director 集區或 director 集區名稱，以及組織網路中執行商務用 Skype Server 所有內部伺服器的記錄。
    
  - DNS A 和 AAAA (如果您針對周邊網路中的每個商務用 Skype Server edge Server 使用 IPv6 定址您 Edge 內部介面的) 記錄。
    
  - DNS A 和 AAAA (如果您要使用 IPv6 定址周邊 (網路中每個反向 proxy 伺服器的內部介面) 記錄，這是對反向 proxy) 的管理的 **選用** 。
    
  - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行內部商務用 Skype Server 用戶端自動設定 (（**選用**) ）。
    
  - DNS A 和 AAAA (如果您是使用 IPv6 定址) 或 CNAME 記錄來自動探索商務用 Skype Server Web 服務 (（**選用**) ）。
    
- 您周邊網路中的所有商務用 Skype Server 內部 Edge 介面都會使用此內部 DNS 區域來解析 contoso.com 的查詢。
    
- 所有執行商務用 Skype Server 的伺服器，以及在公司網路中執行商務用 Skype Server 的用戶端，指向 [內部 DNS 伺服器]，以將查詢解析為 contoso.com，或是在每一部 Edge server 上使用主機檔，也 IPv6 可以使用清單 A 和 AAAA (（特別是針對 Director 或 Director 集區 vip、前端集區 vip 或) Server (）。
    
### <a name="external-dns"></a>外部 DNS

- 包含名為 (的 DNS 區域，例如) contoso.com，其具有權威性。
    
- 此外部 contoso.com 包含：
    
  - 當您使用 IPv6 定址) 或 CNAME 記錄來自動探索商務用 Skype Server web 服務時，DNS A 和 AAAA (。 這與行動性搭配使用。
    
  - DNS A 和 AAAA (如果您正在使用 IPv6 定址) 和 SRV 記錄，以供每個商務用 Skype Server edge Server 的 edge 外部介面使用，或在周邊網路中 (的硬體負載平衡) HLB VIP。
    
  - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄的反向 proxy 伺服器或 (VIP 集區的反向 proxy 伺服器集區（在周邊網路中) ）。
    
  - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行商務用 Skype Server 用戶端自動設定 (**選用**) 。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>沒有 split-大腦 DNS 的自動設定
<a name="NoSplitBrainDNS"> </a>

[！附注] 如果您不使用「分裂大腦」 DNS，則執行商務用 Skype 之用戶端的內部自動設定將無法運作，除非您使用我們在這裡所用的其中一個變通方法。 為什麼？ 因為商務用 Skype Server 需要使用者的 SIP URI，以符合為自動設定指定之前端集區的網域。 這尚未從舊版的 Lync Server 變更。
  
因此，如果您有兩個使用中的 SIP 網域，則需要下列 DNS SRV 記錄：
  
- _sipinternaltls _sipinternaltls._tcp .com。 pool01.contoso.com SRV 0 0 5061 中的86400
    
     *如果使用者登入 bob@contoso.com，則此記錄可用於自動設定，因為使用者的 SIP 網域會符合前端集區的網域 (contoso.com) 。* 
    
- _sipinternaltls _sipinternaltls._tcp .com。 pool01.fabrikam.com SRV 0 0 5061 中的86400
    
     *如果使用者登入 alice@fabrikam.com，則此記錄會在第二個網域的自動設定中運作，因為 SIP 網域符合該網域的前端集區。* 
    
若要進一步採取此範例，這將無法運作：
  
- _sipinternaltls _sipinternaltls._tcp 的 litwareinc。 pool01.fabrikam.com SRV 0 0 5061 中的86400
    
     *以 tim@litwareinc.com 登入的使用者無法使用自動設定，因為其 SIP 網域 (litwareinc.com) 不符合集區中的網域 (fabrikam.com) 。* 
    
現在，我們已知道，如果您需要商務用 Skype 未使用大腦的 DNS 的用戶端自動需求，您可以使用下列選項：
  
- **群組原則物件**
    
    您可以使用「Gpo)  (的群組原則物件，以填入正確的伺服器值。
    
    > [!NOTE]
    > 此選項不會啟用自動設定，但會自動進行手動設定。 若使用此方法，則不需要與自動設定相關聯的 SRV 記錄。 
  
- **相符的內部區域**
    
    您必須在內部 DNS 中建立與您的外部 dns 區域相符的區域 (例如，contoso.com) ，然後在您使用 IPv6 定址) 記錄，而這些記錄對應到用於自動設定的商務用 Skype Server 集區時，建立 dns a (和 AAAA。
    
    例如，如果您擁有位於 pool01.contoso.net 的使用者，但登入商務用 Skype 為 bob@contoso.com，請建立名為 contoso.com 的內部 DNS 區域，並在此區域內建立 dns a (和 AAAA （如果 IPv6 定址為 pool01.contoso.com 的) 記錄使用）。
    
- **Pin 點內部區域**
    
    若在內部 DNS 中建立整個區域不是您的選項，您可以建立 pin 點 (專用的) 區域，該區域會對應至自動設定所需的 SRV 記錄，並使用 dnscmd.exe 填入這些區域。 因為 DNS 使用者介面不支援建立 pin 點區域，所以需要 Dnscmd.exe。
    
    例如，如果您的 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端集區，其中包含兩部前端伺服器，則您必須在內部 DNS 中包含下列 pin 點區域和記錄：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    在您的環境中，您可能會有第二個 SIP 網域。 在此情況下，您必須在內部 DNS 中包含下列 pin 點區域和記錄：
    
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
> 您會看到前端集區 FQDN 顯示兩次，但有兩個不同的 IP 位址。 這是因為使用 DNS 負載平衡。 如果使用 HLB，則只有一個前端集區專案。 
  
> [!NOTE]
> 此外，contoso.com 與 fabrikam.com 範例間的前端集區 FQDN 值也會變更，但 IP 位址仍然保持不變。 這是因為從任一 SIP 網域登入的使用者，將會使用相同的前端集區進行自動設定。 
  
## <a name="dns-disaster-recovery"></a>DNS 災難修復
<a name="DNSDR"> </a>

若要設定 DNS 將商務用 Skype Server web 流量重新導向至災難回復 (DR) 和容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。 您可以設定您的 DNS 記錄以支援嚴重損壞修復，這樣即使一個整個前端集區中斷時，使用 web 服務的功能仍會繼續進行。 這項 DR 功能支援自動探索、符合和撥入簡易 URLs。
  
您可以定義及設定其他 DNS 主機 A (AAAA （如果使用 IPv6) GeoDNS 提供者的內部及外部 web 服務的記錄）。 下列詳細資料假設成對的集區、地理位置上的集區，以及您 **的提供者** 所支援的 GeoDNS 都具有迴圈 DNS， **或** 設定為使用 Pool1 做為主要，並在發生任何通信遺失或電源故障時，容錯移轉至 Pool2。
  
此表格中的所有 DNS 記錄皆為範例。
  
|**GeoDNS 記錄**|**集區記錄**|**CNAME 記錄**|**DNS 設定 (選取一個選項)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com  <br/> |集區間的迴圈  <br/> **OR** <br/> 使用主要，如果發生故障，請連接至次要。  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="DNSLB"> </a>

DNS 負載平衡通常是在應用層級實施。 應用程式 (例如，執行商務用 Skype) 的用戶端，如果 IPv6 定址是用於集區 FQDN) 記錄查詢，則會連接至 DNS a 和 AAAA (所傳回的其中一個 IP 位址，以嘗試連線至集區中的伺服器。
  
例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：
  
- 執行商務用 Skype 的用戶端會查詢 pool01.contoso.com 的 DNS。 查詢會傳回三個 IP 位址，並將它們快取為 (依某些順序) ：
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 用戶端嘗試建立與其中一個 IP 位址的 TCP 連接。 如果失敗，它會嘗試從該清單快取的下一個 IP 位址。
    
- 如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。
    
- 如果用戶端嘗試所有的快取專案，但沒有成功的連線，使用者會收到通知，指出目前沒有任何執行商務用 Skype Server 的伺服器可供使用。
    
> [!NOTE]
> DNS 的負載平衡不同于 DNS 迴圈 (DNS RR) ，它通常是指以 DNS 為集區中的伺服器提供不同的 IP 位址順序的負載平衡。 通常，DNS RR 會啟用負載分配，但不會允許您啟用容錯移轉。 例如，如果您在 IPv6 案例中的 DNS A (或 AAAA 所傳回的一個 IP 位址的連線) 查詢會失敗，該連線會失敗。 這會使 DNS RR 不如以 DNS 為基礎的負載平衡更可靠。 如果您需要這麼做，您仍然可以搭配 DNS 的負載平衡使用 DNS RR。 
  
您可以使用 DNS 負載平衡來執行下列作業：
  
- 將伺服器對伺服器 SIP 的負載平衡至 Edge server。
    
- 負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留。
    
- 防止新的連線 UCAS 應用程式 (也稱為排出) 。
    
- 負載平衡用戶端和 Edge server 之間的所有用戶端對伺服器流量。
    
您不能使用的 DNS 負載平衡：
  
- 您的前端伺服器或 Director 的用戶端對伺服器網頁流量。
    
若要深入瞭解查詢傳回多個 DNS 記錄時，如何選取 DNS SRV 記錄，Access Edge service 一定會以最低的數值優先順序來挑選記錄，而且如果需要斷詞，則最高的數值權重。 這與 [網際網路工程任務強制檔](https://www.ietf.org/rfc/rfc2782.txt)一致。
  
舉例來說，如果您的第一個 DNS SRV 記錄的權重為20，優先順序為40，而第二個 DNS SRV 記錄的權重為10，優先順序為50，則第一筆記錄會因其優先順序低於40而選取。 優先順序一定會先開始，也就是用戶端將優先進行目標的主機。 如果有兩個具有相同優先順序的目標，該怎麼辦？ 
  
在此情況下，會考慮重量。 在此情況下，應將較大的權重指定為非常高的概率。 DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。 當記錄中包含的權重大於0時，具有權重0的記錄會有極小的進入選擇狀態。
  
那麼，當傳回具有相同優先順序和權重的多個 DNS SRV 記錄時，會發生什麼事？ 在此情況下，Access Edge service 會從 DNS 伺服器開始選擇它所獲得的 SRV 記錄。
  

