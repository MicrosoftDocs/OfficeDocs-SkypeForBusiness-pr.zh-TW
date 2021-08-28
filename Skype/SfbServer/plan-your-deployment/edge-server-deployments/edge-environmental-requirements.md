---
title: 商務用 Skype Server 中的 Edge Server 環境需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 摘要：瞭解商務用 Skype Server 中 Edge Server 的環境需求。
ms.openlocfilehash: 492a4c2ec5a90ea8e2c3eb55ea48a4afec16c67f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635237"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>商務用 Skype Server 中的 Edge Server 環境需求
 
**摘要：** 深入瞭解商務用 Skype Server 中的 Edge Server 環境需求。
  
您必須在商務用 Skype Server Edge Server 環境本身之外進行許多規劃與準備工作。 在本文中，我們將回顧在組織環境中所需進行的準備工作，如下列清單所示：
  
- [拓撲規劃](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 規劃](edge-environmental-requirements.md#DNSPlan)
    
- [憑證規劃](edge-environmental-requirements.md#CertPlan)
    
- [埠與防火牆規劃](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓撲規劃
<a name="TopoPlan"> </a>

商務用 Skype ServerEdge Server 拓撲可使用：
  
- 可路由的公用 IP 位址。
    
- 非路由的私人 IP 位址（如果使用 **對稱** 網路位址轉譯 (NAT) ）。
    
> [!TIP]
> 您可以將 Edge Server 設定為使用具有不同埠的單一 IP 位址，以供每個服務使用，也可以針對每個服務使用不同的 IP 位址，但預設埠 (預設埠會是 TCP 443) 。 以下是我們的 IP 位址需求區段中的詳細資訊。 
  
如果您選擇與 NAT 的非路由私人 IP 位址，請記住下列幾點：
  
- 您必須在 **所有三個** 外部介面上使用可路由的私人 IP 位址。
    
- 您必須針對內送和外送流量設定 **對稱** NAT。 「對稱 nat」是唯一支援的商務用 Skype Server Edge Server 所能使用的 nat。
    
- 將您的 NAT 設定為不變更傳入來源位址。 A/V Edge service 必須能夠接收傳入的來源位址，以找出最佳的媒體路徑。
    
- 您的 Edge Server 必須能夠與彼此的公用 A/V Edge IP 位址彼此進行通訊。 您的防火牆必須允許這種流量。
    
- 如果您使用 DNS 負載平衡，則 NAT **只** 可用於調整式合併 Edge server。 如果您使用硬體負載平衡 (HLB) ，您必須使用 **沒有** NAT 的可公開路由傳送的 IP 位址。
    
只要您不是使用硬體負載平衡) ，您就不會在路由器或防火牆背後對單一及調整式合併 Edge Server (拓撲執行對稱 NAT 的情況下，進行 Access、Web 會議和 A/V Edge 介面的問題。
  
### <a name="summary-of-edge-server-topology-options"></a>Edge Server 拓撲選項摘要

我們有數個可用於商務用 Skype Server Edge Server 部署的拓撲選項：
  
- 單一合併 Edge （利用私人 IP 位址及 NAT）
    
- 單一合併 Edge （利用公用 IP 位址）
    
- 調整式合併 Edge （利用私人 IP 位址及 NAT）
    
- 調整式合併 Edge （利用公用 IP 位址）
    
- 調整式合併 Edge （使用硬體負載平衡器）
    
為了協助您選擇其中一個，我們有下表會提供您針對每個拓撲的選項摘要：
  
|**拓撲**|**高可用性**|**Edge 集區中的外部 Edge Server 所需的其他 DNS 記錄？**|**商務用 Skype Server 會話的 Edge 容錯移轉**|**商務用 Skype Server 同盟會話的 Edge 容錯移轉**|
|:-----|:-----|:-----|:-----|:-----|
|單一合併 Edge （利用私人 IP 位址及 NAT）  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|單一合併 Edge （利用公用 IP 位址）  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|調整式合併 Edge （利用私人 IP 位址及 NAT (DNS 負載平衡)   <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|調整式合併 Edge （利用公用 IP 位址 (DNS 負載平衡）)   <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|調整式合併 Edge （使用硬體負載平衡器）  <br/> |是  <br/> |否 (每個 VIP 各一個 DNS A 記錄)  <br/> |是  <br/> |是  <br/> |
   
&sup1;Exchange整合通訊 (UM) 使用 DNS 負載平衡的遠端使用者容錯移轉需要 Exchange 2013 或更新版本。
  
### <a name="ip-address-requirements"></a>IP 位址需求

在基礎層級，三項服務需要 IP 位址;Access Edge service、Web 會議 Edge service 及 A/V Edge service。 您可以選擇使用三個 IP 位址，一個用於每個服務，也可以使用一個和選擇將每個服務放在不同的埠 (您可以查看 [埠與防火牆的計畫](edge-environmental-requirements.md#PortFirewallPlan) 區段，以取得部分) 的詳細資訊。 針對單一合併 Edge 環境，其非常大。
  
> [!NOTE]
> 如以上所述，您可以選擇讓所有三種服務具有一個 IP 位址，並在不同的埠上執行這些服務。 不過，建議您不要這麼做。 如果您的客戶無法存取您在此案例中所使用的備用埠，則他們也無法存取 Edge 環境的完整功能。 
  
調整式合併拓撲會變得更複雜，讓我們來看看一些配置 IP 位址需求的表格，請記住，拓撲選擇的主要決策點是高可用性和負載平衡。 高可用性需求可能會影響您的負載平衡選擇 (我們將在資料表) 之後討論這種情況。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>調整式合併 Edge 的 IP 位址需求 (每個角色的 IP 位址) 

|**每個集區的 Edge Server 數目**|**DNS 負載平衡所需的 IP 位址數目**|**硬體負載平衡所需的 IP 位址數目**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (每個 VIP 各 1 個) + 6  <br/> |
|3   <br/> |9   <br/> |3 (每個 VIP 各 1 個) + 9  <br/> |
|4   <br/> |12   <br/> |3 (每個 VIP 各 1 個) + 12  <br/> |
|5   <br/> |15   <br/> |每個 VIP 3 (1) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>縮放合併 Edge 的 IP 位址需求所有角色 (單一 IP 位址) 

|**每個集區的 Edge Server 數目**|**DNS 負載平衡所需的 IP 位址數目**|**硬體負載平衡所需的 IP 位址數目**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (每個 VIP 各 1 個) + 2  <br/> |
|3   <br/> |3   <br/> |1 (每個 VIP 各 1 個) + 3  <br/> |
|4   <br/> |4   <br/> |1 (每個 VIP 各 1 個) + 4  <br/> |
|5   <br/> |5   <br/> |1 (每個 VIP 各 1 個) + 5  <br/> |
   
讓我們看看在規劃時需要考慮的一些其他事項。
  
- **高可用性**：若您的部署需要高可用性，您應該在集區中至少部署兩部 Edge server。 值得注意的一點是，單一 Edge 集區最多可支援12部伺服器 (不過，拓撲產生器允許您新增高達20個（未測試或不受支援），因此我們建議您不要執行該) 。 如果您需要超過12部 Edge Server，則應該為它們建立其他 Edge 集區。
    
- **硬體負載平衡**：建議您在大部分情況下，對 DNS 進行負載平衡。 當然也支援硬體負載平衡，但特別是在使用 DNS 負載平衡的單一案例中，它是必要的：
    
  - 外部存取 Exchange 2007 或 Exchange 2010 (，但沒有 SP) 整合通訊 (UM) 。
    
- **dns 負載平衡**：針對 UM，Exchange 2010 SP1 和更新版本可由 DNS 負載平衡所支援。 請注意，如果您需要為舊版的 Exchange 使用 DNS 負載平衡，它會正常運作，但是此項的所有流量都會移至集區中的第一部伺服器; 如果無法使用，則該流量會隨後失敗。
    
    如果您使用下列方式與公司同盟，也建議使用 DNS 負載平衡：
- 商務用 Skype Server 2015：
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 或 Office 365
- 商務用 Skype Server 2019：
    - Lync Server 2013
    - 商務用 Skype Server 2015
    - Microsoft 365 或 Office 365
    
## <a name="dns-planning"></a>DNS 規劃
<a name="DNSPlan"> </a>

商務用 Skype Server Edge Server 部署時，請務必正確地準備 DNS。 適當的記錄適當時，部署會變得更簡單。 但願您已在上述區段中選擇拓撲，正如我們即將執行概要，然後列出幾個表格，以概括顯示這些案例的 DNS 記錄。 如果您需要，我們也會為商務用 Skype Server 的一些[高級 Edge Server DNS 規劃](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)，以進行更深入的閱讀。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>單一合併 Edge Server 案例的 DNS 記錄

這些是您要對單一 Edge Server 所需的 DNS 記錄，您可以使用公用 Ip 或使用 NAT 的私人 Ip。 由於這是範例資料，因此我們將提供範例 IPs，讓您可以更輕鬆地使用您自己的專案：
  
- 內部網路介面卡： 172.25.33.10 (未指派任何預設閘道) 
    
    > [!NOTE]
    > 確定有從包含 Edge 內部介面的網路到包含執行商務用 Skype Server 或 Lync Server 2013 客戶 (端之伺服器的網路的路由，例如從172.25.33.0 到 192.168.10.0) 。 
  
- 外部網路介面卡：
    
  - 公用 Ip：
    
  - Access Edge： 131.107.155.10 (此為主要的，其預設閘道會設定為您的公用路由器，ex： 131.107.155.1) 
    
  - Web 會議 Edge： 131.107.155.20 (次要) 
    
  - A/V Edge： 131.107.155.30 (次要) 
    
  Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
    
  - 私人 Ip：
    
  - Access Edge： 10.45.16.10 (此為主要的，其預設閘道設定為您的路由器，ex： 10.45.16.1) 
    
  - Web 會議 Edge： 10.45.16.20 (次要) 
    
  - A/V Edge： 10.45.16.30 (次要) 
    
Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
  
> [!TIP]
>其他可能的設定如下：
  
- 您可以在外部網路介面卡上使用一個 IP 位址。 建議您不要這麼) 商務用 Skype Server 做，因為接下來，您將需要使用 (的不同埠來區分 thee 服務，但有些防火牆可能會封鎖備用埠。 如需此方面的詳細資訊，請參閱 [埠與防火牆計畫](edge-environmental-requirements.md#PortFirewallPlan) 一節。
    
- 您可以有三個外部網路介面卡，而不是一個，而將其中一個服務 Ip 指派給每個。 為何這麼做？ 它會分開服務，如果發生錯誤，則會使疑難排解變得更容易，當您解決問題時，可能會讓其他服務繼續運作。
    
|**Location**|**類型**|**Port**|**FQDN 或 DNS 記錄**|**IP 位址或 FQDN**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public：** 131.107.155.10 <br/> **私人：** 10.45.16.10 <br/> |Access Edge service 的外部介面。 您將需要商務用 Skype 使用者的每個 SIP 網域的一個。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public：** 131.107.155.20 <br/> **私人：** 10.45.16.20 <br/> |Web 會議 Edge service 的外部介面。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |av.contoso.com  <br/> |**public：** 131.107.155.30 <br/> **私人：** 10.45.16.30 <br/> |A/V Edge service 的外部介面。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |443  <br/> |_sip _sip._tls .com  <br/> |sip.contoso.com  <br/> |Access Edge service 的外部介面。 商務用 Skype Server、lync server 2013 和 lync server 2010 用戶端可以在外部工作時，需要此 SRV 記錄。 您將需要商務用 Skype 使用者的每個網域的一個。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |5061  <br/> |_sipfederationtls _sipfederationtls._tcp .com  <br/> |sip.contoso.com  <br/> |Access Edge service 的外部介面。 自動 DNS 探索稱為「允許的 SIP 網域」的同盟合作夥伴需要此 SRV 記錄。 您將需要商務用 Skype 使用者的每個網域的一個。  <br/> |
|內部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |合併 Edge 的內部介面。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>調整式 DNS 和硬體 Edge Server 案例的 DNS 記錄

這些是您要對單一 Edge Server 所需的 DNS 記錄，您可以使用公用 Ip 或使用 NAT 的私人 Ip。 由於這是範例資料，因此我們將提供範例 IPs，讓您可以更輕鬆地使用您自己的專案：
  
- 內部網路介面卡：
    
  - 節點1： 172.25.33.10 (未指派任何預設閘道) 
    
  - 節點2： 172.25.33.11 (未指派任何預設閘道) 
    
    > [!NOTE]
    > 確定有從包含 Edge 內部介面的網路到包含執行商務用 Skype Server 或 Lync Server 2013 客戶 (端之伺服器的網路的路由，例如從172.25.33.0 到 192.168.10.0) 。 
  
- 外部網路介面卡：
    
  - 節點1
    
     - 公用 Ip：
    
        - Access Edge： 131.107.155.10 (此為主要的，其預設閘道會設定為您的公用路由器，ex： 131.107.155.1) 
    
        - Web 會議 Edge： 131.107.155.20 (次要) 
    
        - A/V Edge： 131.107.155.30 (次要) 
    
          Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
    
    - 私人 Ip：
    
         - Access Edge： 10.45.16.10 (此為主要的，其預設閘道設定為您的路由器，ex： 10.45.16.1) 
    
         - Web 會議 Edge： 10.45.16.20 (次要) 
    
         - A/V Edge： 10.45.16.30 (次要) 
    
      Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
    
  - 節點2
    
    - 公用 Ip：
    
      - Access Edge： 131.107.155.11 (此為主要的，其預設閘道會設定為您的公用路由器，ex： 131.107.155.1) 
    
      - Web 會議 Edge： 131.107.155.21 (次要) 
    
      - A/V Edge： 131.107.155.31 (次要) 
    
      Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
    
  - 私人 Ip：
    
    - Access Edge： 10.45.16.11 (此為主要的，其預設閘道設定為您的路由器，ex： 10.45.16.1) 
    
    - Web 會議 Edge： 10.45.16.21 (次要) 
    
    - A/V Edge： 10.45.16.31 (次要) 
    
      Web 會議和 A/V 邊際公開 IP 位址是 (的 Internet protocol version 4 (的 [高級] 區段中的次要) IP 位址，以及 TCP/IPv4 Server 中的局域線上內容之 [internet protocol version 6)  (TCP/IPv6。
    
其他可能的設定如下：
  
- 您可以在外部網路介面卡上使用一個 IP 位址。 建議您不要這麼) 商務用 Skype Server 做，因為接下來，您將需要使用 (的不同埠來區分 thee 服務，但有些防火牆可能會封鎖備用埠。 如需此方面的詳細資訊，請參閱 [埠與防火牆計畫](edge-environmental-requirements.md#PortFirewallPlan) 一節。
    
- 您可以有三個外部網路介面卡，而不是一個，而將其中一個服務 Ip 指派給每個。 為何這麼做？ 它會分開服務，如果發生錯誤，則會使疑難排解變得更容易，當您解決問題時，可能會讓其他服務繼續運作。
    
|**Location**|**類型**|**Port**|**FQDN 或 DNS 記錄**|**IP 位址或 FQDN**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public：** 131.107.155.10 和131.107.155.11 <br/> **private：** 10.45.16.10 和10.45.16.11 <br/> |Access Edge service 的外部介面。 您將需要商務用 Skype 使用者的每個 SIP 網域的一個。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public：** 131.107.155.20 和131.107.155.21 <br/> **private：** 10.45.16.20 和10.45.16.21 <br/> |Web 會議 Edge service 的外部介面。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |av.contoso.com  <br/> |**public：** 131.107.155.30 和131.107.155.31 <br/> **private：** 10.45.16.30 和10.45.16.31 <br/> |A/V Edge service 的外部介面。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |443  <br/> |_sip _sip._tls .com  <br/> |sip.contoso.com  <br/> |Access Edge service 的外部介面。 商務用 Skype Server、lync server 2013 和 lync server 2010 用戶端可以在外部工作時，需要此 SRV 記錄。 您將需要每個具有商務用 Skype 的網域的一個。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |5061  <br/> |_sipfederationtls _sipfederationtls._tcp .com  <br/> |sip.contoso.com  <br/> |Access Edge service 的外部介面。 自動 DNS 探索稱為「允許的 SIP 網域」的同盟合作夥伴需要此 SRV 記錄。 您將需要每個具有商務用 Skype 的網域的一個。  <br/> |
|內部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 及 172.25.33.11  <br/> |合併 Edge 的內部介面。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>所有案例的同盟 (DNS 記錄) 

|**Location**|**類型**|**Port**|**FQDN**|**FQDN 主機記錄**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp .com  <br/> |sip.contoso.com  <br/> |自動 DNS 探索所需的 SIP 存取 Edge 外部介面。 其他潛在同盟協力廠商使用。 也稱為「允許 SIP 網域」。 您將需要與商務用 Skype 使用者一起使用的每個 SIP 網域的其中一個。  <br/><br/> **附注：** 您將需要此 SRV 記錄的行動性及推播通知結算。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和顯示狀態通訊協定的 DNS 記錄

|**Location**|**類型**|**Port**|**FQDN**|**IP 位址或 FQDN 主機記錄**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp .com  <br/> |xmpp.contoso.com  <br/> |您的 Access Edge service 或 Edge 集區上的 XMPP proxy 介面。 您必須針對具有商務用 Skype Server 已啟用使用者的所有內部 SIP 網域，依需要重複此動作，以便允許具有已啟用之連絡人的連絡人：  <br/> •全域原則  <br/> •使用者已啟用的網站原則  <br/> •套用至商務用 Skype Server 已啟用使用者的使用者原則  <br/> 您也需要在 XMPP 同盟使用者原則中設定允許的 XMPP 原則。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |主控 XMPP Proxy 服務之 Edge Server 或 Edge 集區上之 Access Edge service 的 IP 位址  <br/> |這會指向主控 XMPP Proxy 服務之 Edge Server 或 Edge 集區上的 Access Edge service。 一般來說，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) record。  <br/> |
   
> [!NOTE]
> XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。

## <a name="certificate-planning"></a>憑證規劃
<a name="CertPlan"> </a>

商務用 Skype Server 會在伺服器之間和伺服器之間，使用憑證進行安全、加密的通訊。 如您所料，您的憑證必須具有伺服器的 DNS 記錄，使其符合您憑證上的任何主體名稱 (SN) 和主體替代名稱 (SAN) 。 這現在會在規劃階段進行，以確保您在 DNS 中為您的憑證註冊 SN 和 SAN 專案的正確 Fqdn。
  
我們會個別討論外部和內部的憑證需求，然後查看提供兩者需求的表格。
  
### <a name="external-certificates"></a>外部憑證

指定給外部 Edge Server 介面的憑證至少必須由公用憑證頒發機構單位 (CA) 所提供。 我們無法為您推薦特定 CA，但我們有一個 Ca、 [整合通訊憑證合作夥伴](../../../SfbPartnerCertification/certification/services-ssl.md) 清單，您可以查看您的首選 CA 是否已列出。
  
您何時需要向 CA 提交此公用憑證的要求，以及您如何執行此動作？ 有幾種方式可以完成此作業：
  
- 您可以逐步執行商務用 Skype Server 的安裝，然後進行 Edge Server 部署。 商務用 Skype Server 部署嚮導具有一個產生憑證要求的步驟，您可以將此要求傳送給您所選擇的 CA。
    
- 您也可以使用 Windows PowerShell 命令來產生此要求（如果這與您的業務需求或部署策略更內聯）。
    
- 最後，您的 CA 可能會有自己的提交程式，也可能包括 Windows PowerShell 或另一種方法。 在此情況下，除了這裡提供的參考資訊之外，您還必須依賴其檔。
    
當您獲得憑證之後，您必須先繼續，然後在商務用 Skype Server 中將其指派給這些服務：
  
- Access Edge service 介面
    
- Web 會議 Edge service 介面
    
- Audio/Video 驗證服務 (不會將這種方式與 A/V Edge service 混淆，因為這不會使用憑證來加密音訊和影片資料流程) 
    
> [!IMPORTANT]
> 所有 Edge Server (如果它們屬於相同的 Edge Server 集區) 必須具有相同的相同憑證，具有媒體轉送驗證服務的相同私密金鑰。 
  
### <a name="internal-certificates"></a>內部憑證

針對內部 Edge Server 介面，您可以使用公用 CA 的公用憑證，或是從組織的內部 CA 發出的憑證。 有關內部憑證的切記是使用 SN 專案，而不是 SAN 專案，因此您根本不必擔心內部 cert 上的 SAN。
  
### <a name="required-certificates-table"></a>必要的憑證表格

我們有一個表格可協助您使用您的要求。 此處的 FQDN 專案只適用于範例網域。 您將需要根據您自己的私密和公用網域來進行要求，但這裡是我們所使用之專案的指南：
  
- contoso <span></span> .com：公用 FQDN
    
- fabrikam <span></span> ：第二個公用 FQDN (新增為您有多個 SIP 網域時要求的示範) 
    
- Contoso <span></span> .net：內部網域
    
#### <a name="edge-certificate-table"></a>Edge 憑證表格

不論您執行的是單一 Edge Server 或 Edge 集區，您的憑證都會需要這種方式：
  
|**元件**|**主體名稱 (SN)**|**(SAN) /order 的主體替代名稱**|**附註**|
|:-----|:-----|:-----|:-----|
|外部 Edge  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |這是您從公用 CA 要求所需的憑證。 您必須將其指派給下列各項的外部 Edge 介面：  <br/> • Access Edge  <br/> • Web 會議 Edge  <br/> • Audio/Video 驗證  <br/> <br/>好消息是，San 會自動新增至您的憑證要求，因此您提交要求之後，您可以根據您在拓撲產生器中為此部署定義的專案來提交要求。 您只需要新增 SAN 專案供任何額外的 SIP 網域或您需要支援的其他專案。 為何 sip.contoso.com 在此實例中複寫？ 這種情況也會自動發生，而且必須有哪些專案才能正常運作。  <br/><br/> **附注：** 此憑證也可用於公用立即訊息連線。 您不需要對它執行任何不同的作業，但是在此檔的先前版本中，它會列為個別的資料表，而現在也是不是。 <br/> |
|內部 Edge  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |您可以從公用 CA 或內部 CA 取得此憑證。 它需要包含伺服器 EKU (增強型金鑰使用狀況) ，而且您會將其指派給內部 Edge 介面。  <br/> |
   
如果您需要憑證以進行可延伸的訊息和顯示狀態通訊協定 (XMPP) ，它看起來會與上述的外部 Edge 表專案完全相同，但會有下列兩個額外的 SAN 專案：
  
- xmpp。 <span></span>contoso <span></span>
    
- \*<span></span>.com
    
請記住，目前 XMPP 只支援 Google 交談的商務用 Skype Server，如果您想要或需要使用它做任何其他事情，您必須使用協力廠商廠商確認該功能。
  
## <a name="port-and-firewall-planning"></a>埠與防火牆規劃
<a name="PortFirewallPlan"> </a>

為商務用 Skype Server Edge Server 部署的埠及防火牆取得您的規劃許可權，可在疑難排解與壓力的情況中節約天數或周數。 因此，我們會列出兩個表格，以指出我們的通訊協定使用方式，以及您對 NAT 和公用 IP 案例必須具有開啟、輸入和輸出的埠。 我們也會針對硬體負載平衡案例使用不同的表格， (HLB) ，還有一些進一步的指導方針。 為了進一步閱讀，我們也會[在商務用 Skype Server 中有一些 Edge Server 案例](scenarios.md)，您可以查看您的特定部署考慮。
  
### <a name="general-protocol-usage"></a>一般通訊協定用法

在查看外部和內部防火牆的摘要表格之前，請先考慮下表：
  
|**Audio/Video 傳輸**|**Usage**|
|:-----|:-----|
|UDP  <br/> |音訊和影片的慣用傳輸層通訊協定。  <br/> |
|TCP  <br/> |音訊和影片的 fallback transport layer 通訊協定。  <br/> 商務用 Skype Server、lync server 2013 和 lync server 2010 之應用程式共用所需的傳輸層通訊協定。  <br/> 用於商務用 Skype Server、lync server 2013 和 lync server 2010 的檔案轉接所需的傳輸層通訊協定。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部埠防火牆摘要表格

來源 IP 位址和目的地 IP 位址會包含使用 NAT 的私人 IP 位址的使用者，以及使用公用 IP 位址的人員資訊。 這將涵蓋[商務用 Skype Server 區段中的 Edge Server 案例](scenarios.md)中的所有排列。
  
|**角色或通訊協定**|**TCP 或 UDP**|**目的地埠或埠範圍**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 商務用 Skype Server 2019 不支援 |TCP  <br/> |5269  <br/> |任何  <br/> |XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址  <br/> |XMPP Proxy 服務接受定義之 XMPP 同盟中 XMPP 連絡人的流量。  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |任何  <br/> |憑證吊銷和 CRL 檢查和檢索。  <br/> |
|存取/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |任何  <br/> |透過 TCP 的 DNS 查詢。  <br/> |
|存取/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |任何  <br/> |透過 UDP 的 DNS 查詢。  <br/> |
|Access/SIP (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |外部使用者存取的用戶端對伺服器 SIP 流量。  <br/> |
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |適用于使用 SIP 的同盟與公用 IM 連線。  <br/> |
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |任何  <br/> |適用于使用 SIP 的同盟與公用 IM 連線。  <br/> |
|Web 會議/PSOM (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Web 會議 Edge service <br/> **公用 IP：** Edge Server Web 會議 Edge service 公用 IP 位址 <br/> |Web 會議媒體。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |任何  <br/> |這是用於中繼媒體流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |任何  <br/> |這是用於中繼媒體流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |任何  <br/> |3478輸出是：  <br/> •用於商務用 Skype Server 以判斷其所與其通訊之 Edge Server 的版本。  <br/> •用於 Edge Server 之間的媒體流量。  <br/> •與 Lync Server 2010 的同盟所需。  <br/> •在您的組織中部署多個 Edge 集區時需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |在埠3478上 STUN/TURN 以 UDP 協商的候選人。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |STUN/TURN 在埠443上透過 TCP 協商的候選人。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |任何  <br/> |STUN/TURN 在埠443上透過 TCP 協商的候選人。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>內部埠防火牆摘要表格

|**Protocol** (通訊協定)|**TCP 或 UDP**|**Port**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |任何執行 XMPP 閘道服務的下列專案：  <br/> •前端伺服器  <br/> •前端集區  <br/> |Edge Server 內部介面  <br/> |您的前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量。  <br/> **附注：** XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |任何：  <br/> • Director  <br/> • Director 集區  <br/> •前端伺服器  <br/> •前端集區  <br/> |Edge Server 內部介面  <br/> |從 Director、Director 集區、前端伺服器或前端集區到 Edge Server 內部介面的輸出 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Edge Server 內部介面  <br/> |任何：  <br/> • Director  <br/> • Director 集區  <br/> •前端伺服器  <br/> •前端集區  <br/> |從 Edge Server 內部介面到 Director、Director 集區、前端伺服器或前端集區的輸入 SIP 流量。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任何：  <br/> •前端伺服器  <br/> •每一部前端伺服器  <br/>  在前端集區中 <br/> |Edge Server 內部介面  <br/> |前端伺服器或每一部前端伺服器的 Web 會議流量 (若您的 Edge Server 內部介面) 有前端集區。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任何：  <br/> •前端伺服器  <br/> •前端集區  <br/> •任何使用此 Edge Server 的 Survivable 分支裝置  <br/> •任何使用此 Edge Server 的 Survivable 分支伺服器  <br/> |Edge Server 內部介面  <br/> |使用 Edge Server 從您的前端伺服器或前端集區，或 Survivable 分支裝置或 Survivable Branch 伺服器驗證 A/V 使用者。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |您的內部及外部使用者與 Survivable 分支裝置或 Survivable Branch 伺服器之間 A/V 媒體傳輸的慣用路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |您的內部及外部使用者與 Survivable Branch 裝置或 Survivable Branch 伺服器之間的 A/V 媒體傳輸的回退路徑（如果 UDP 通訊無法運作）。 然後，使用 TCP 進行檔案傳輸和桌面共用。  <br/> |
|HTTPS:  <br/> |TCP  <br/> |4443  <br/> |任何：  <br/> •具有中央管理存放區的前端伺服器  <br/> •具有中央管理存放區的前端集區  <br/> |Edge Server 內部介面  <br/> |從中央管理存放區對 Edge Server 所做的變更複寫。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Edge 埠表的硬體負載平衡器

我們會提供硬體負載平衡器 (HLBs) 和 Edge 埠各自的區段，因為其他硬體的情況有點複雜。 請參閱下表，以取得此特定案例的指導方針：
  
#### <a name="external-port-firewall-summary-table"></a>外部埠防火牆摘要表格

來源 IP 位址和目的地 IP 位址會包含使用 NAT 的私人 IP 位址的使用者，以及使用公用 IP 位址的人員資訊。 這將涵蓋[商務用 Skype Server 區段中的 Edge Server 案例](scenarios.md)中的所有排列。
  
|**角色或通訊協定**|**TCP 或 UDP**|**目的地埠或埠範圍**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Edge Server Access Edge service 公用 IP 位址  <br/> |任何  <br/> |憑證吊銷和 CRL 檢查和檢索。  <br/> |
|存取/DNS  <br/> |TCP  <br/> |53  <br/> |Edge Server Access Edge service 公用 IP 位址  <br/> |任何  <br/> |透過 TCP 的 DNS 查詢。  <br/> |
|存取/DNS  <br/> |UDP  <br/> |53  <br/> |Edge Server Access Edge service 公用 IP 位址  <br/> |任何  <br/> |透過 UDP 的 DNS 查詢。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edge Server A/V Edge service IP 位址  <br/> |任何  <br/> |這是用於中繼媒體流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge Server A/V Edge service 公用 IP 位址  <br/> |任何  <br/> |這是用於中繼媒體流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge Server A/V Edge service 公用 IP 位址  <br/> |任何  <br/> |3478輸出是：  <br/> •用於商務用 Skype Server 以判斷其所與其通訊之 Edge Server 的版本。  <br/> •用於 Edge Server 之間的媒體流量。  <br/> •同盟所需。  <br/> •在您的組織中部署多個 Edge 集區時需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |Edge Server A/V Edge service 公用 IP 位址  <br/> |在埠3478上 STUN/TURN 以 UDP 協商的候選人。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |Edge Server A/V Edge service 公用 IP 位址  <br/> |STUN/TURN 在埠443上透過 TCP 協商的候選人。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge Server A/V Edge service 公用 IP 位址  <br/> |任何  <br/> |STUN/TURN 在埠443上透過 TCP 協商的候選人。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>內部埠防火牆摘要表格

|**Protocol** (通訊協定)|**TCP 或 UDP**|**Port**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |任何執行 XMPP 閘道服務的下列專案：  <br/> •前端伺服器  <br/> •前端集區 VIP 位址正在執行 XMPP 閘道服務  <br/> |Edge Server 內部介面  <br/> |您的前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量。  <br/><br/> **附注：** XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。 |
|HTTPS:  <br/> |TCP  <br/> |4443  <br/> |任何：  <br/> •具有中央管理存放區的前端伺服器  <br/> •具有中央管理存放區的前端集區  <br/> |Edge Server 內部介面  <br/> |從中央管理存放區對 Edge Server 所做的變更複寫。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任何：  <br/> •前端伺服器  <br/> •前端集區中的每一部前端伺服器  <br/> |Edge Server 內部介面  <br/> |前端伺服器或每一部前端伺服器的 Web 會議流量 (若您的 Edge Server 內部介面) 有前端集區。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何：  <br/> •前端伺服器  <br/> •前端集區中的每一部前端伺服器  <br/> |Edge Server 內部介面  <br/> |您的內部及外部使用者與 Survivable 分支裝置或 Survivable Branch 伺服器之間 A/V 媒體傳輸的慣用路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任何：  <br/> •前端伺服器  <br/> •集區中的每一部前端伺服器  <br/> |Edge Server 內部介面  <br/> |您的內部及外部使用者與 Survivable Branch 裝置或 Survivable Branch 伺服器之間的 A/V 媒體傳輸的回退路徑（如果 UDP 通訊無法運作）。 然後，使用 TCP 進行檔案傳輸和桌面共用。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |集中式記錄服務控制器使用商務用 Skype Server 管理命令介面和集中式記錄服務指令程式，ClsController 命令列 (ClsController.exe) 或 agent (ClsAgent.exe) 命令和記錄檔集合。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部介面虛擬 Ip

|**角色或通訊協定**|**TCP 或 UDP**|**目的地埠或埠範圍**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Businesss Server 2019 不支援 Skype |TCP  <br/> |5269  <br/> |任何  <br/> |XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址)   <br/> |XMPP Proxy 服務接受定義之 XMPP 同盟中 XMPP 連絡人的流量。  <br/> |
|XMPP  <br/>Businesss Server 2019 不支援 Skype |TCP  <br/> |5269  <br/> |XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址)   <br/> |任何  <br/> |XMPP Proxy 服務會從已定義 XMPP 同盟中的 XMPP 連絡人傳送流量。  <br/> |
|Access/SIP (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |外部使用者存取的用戶端對伺服器 SIP 流量。  <br/> |
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |適用于使用 SIP 的同盟與公用 IM 連線。  <br/> |
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的私人 IP：** Edge Server Access Edge service <br/> **公用 IP：** Edge Server Access Edge service 公用 IP 位址 <br/> |任何  <br/> |適用于使用 SIP 的同盟與公用 IM 連線。  <br/> |
|Web 會議/PSOM (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server Web 會議 Edge service <br/> **公用 IP：** Edge Server Web 會議 Edge service 公用 IP 位址 <br/> |Web 會議媒體。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |在埠3478上 STUN/TURN 以 UDP 協商的候選人。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的私人 IP：** Edge Server A/V Edge service <br/> **公用 IP：** Edge Server A/V Edge service 公用 IP 位址 <br/> |STUN/TURN 在埠443上透過 TCP 協商的候選人。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>內部介面虛擬 Ip

我們的指導只是有點不同。 在實際 HLB 情況下，我們現在建議您在下列情況下，只會透過內部 VIP 進行路由傳送：
  
- 如果您使用 Exchange 2007 或 Exchange 2010 整合通訊 (UM) 。
    
- 如果您有使用 Edge 的舊版用戶端。
    
下表提供這些案例的指導方針，否則，您應該可以依靠中央管理存放區 (CMS) 將流量路由傳送至個別 Edge Server，但這 (項服務卻知道，該 CMS 必須在 Edge Server 資訊中保持最新狀態，當然) 。
  
|**Protocol** (通訊協定)|**TCP 或 UDP**|**Port**|**來源 IP 位址**|**目的地 IP 位址**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |任何：  <br/> • Director  <br/> • Director 集區 VIP 位址  <br/> •前端伺服器  <br/> •前端集區 VIP 位址  <br/> |Edge Server 內部介面  <br/> |從 Director、Director 集區 VIP 位址、前端伺服器或前端集區 VIP 位址到 Edge Server 內部介面的輸出 SIP 流量。  <br/> |
|Access/SIP (MTLS)   <br/> |TCP  <br/> |5061  <br/> |Edge Server 內部 VIP 介面  <br/> |任何：  <br/> • Director  <br/> • Director 集區 VIP 位址  <br/> •前端伺服器  <br/> •前端集區 VIP 位址  <br/> |從 Edge Server 內部介面到 Director、Director 集區 VIP 位址、前端伺服器或前端集區 VIP 位址的輸入 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任何：  <br/> •前端伺服器的 IP 位址  <br/> •前端集區 IP 位址  <br/> •任何使用此 Edge Server 的 Survivable 分支裝置  <br/> •任何使用此 Edge Server 的 Survivable 分支伺服器  <br/> |Edge Server 內部介面  <br/> |使用 Edge Server 從您的前端伺服器或前端集區，或 Survivable 分支裝置或 Survivable Branch 伺服器驗證 A/V 使用者。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |Edge Server 內部介面  <br/> |您的內部與外部使用者之間 A/V 媒體傳輸的慣用路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |Edge Server 內部 VIP 介面  <br/> |在您的內部與外部使用者之間，如果 UDP 通訊無法運作，則為 A/V 媒體傳輸的回退路徑。 然後，使用 TCP 進行檔案傳輸和桌面共用。  <br/> |