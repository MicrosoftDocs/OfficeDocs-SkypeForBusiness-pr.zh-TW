---
title: 商務用 Skype Server 中的邊緣伺服器環境需求
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: '摘要: 瞭解商務用 Skype Server 中 Edge 伺服器的環境需求。'
ms.openlocfilehash: 25584c10c8359cb4a3e695cee4838b80bc9643f5
ms.sourcegitcommit: bd50c6239cee414ea9933e9d569fa5a24bc05544
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2019
ms.locfileid: "36193973"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>商務用 Skype Server 中的邊緣伺服器環境需求
 
**摘要:** 瞭解商務用 Skype Server 中 Edge 伺服器的環境需求。
  
在商務用 Skype Server Edge 伺服器環境本身之外, 有許多規劃及準備工作需要進行。 在本文中, 我們將回顧在組織環境中需要進行的準備, 如以下清單所示:
  
- [拓撲規劃](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 規劃](edge-environmental-requirements.md#DNSPlan)
    
- [憑證規劃](edge-environmental-requirements.md#CertPlan)
    
- [埠和防火牆規劃](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓撲規劃
<a name="TopoPlan"> </a>

商務用 Skype Server Edge 伺服器拓撲結構可以使用:
  
- 可路由的公用 IP 位址。
    
- 如果使用**對稱**網路位址轉譯 (NAT), 則無法路由的私人 IP 位址。
    
> [!TIP]
> 您可以將 Edge 伺服器設定為在每個服務的單一 IP 位址中使用不同的埠, 或者可以針對每個服務使用不同的 IP 位址, 但使用相同的預設埠 (預設為 TCP 443)。 以下是 [IP 位址需求] 區段的詳細資訊。 
  
如果您選擇的是與 NAT 的非路由私人 IP 位址, 請記住下列幾點:
  
- 您需要在**所有三個**外部介面上使用可路由的私人 IP 位址。
    
- 您必須為內送與外寄通訊設定**對稱**NAT。 對稱 NAT 是唯一支援的 NAT, 您可以搭配商務用 Skype Server Edge 伺服器使用。
    
- 設定您的 NAT, 不會變更傳入的來源位址。 A/V Edge 服務必須能夠接收傳入的來源位址, 才能找出最佳的媒體路徑。
    
- 您的邊緣伺服器必須能夠從其公用 A/V 邊緣 IP 位址進行通訊。 您的防火牆需要允許這種流量。
    
- 如果您使用 DNS 負載平衡, NAT**只能**用於已縮放的合併邊緣伺服器。 如果您使用硬體負載平衡 (HLB), 則需要使用**不含**NAT 的可公開路由的 IP 位址。
    
如果您不是使用硬體負載平衡, 您就不會在路由器或防火牆背後針對單一和縮放的合併邊緣伺服器拓撲執行對稱 NAT (只要您不使用硬體負載平衡), 就不會發生任何問題。
  
### <a name="summary-of-edge-server-topology-options"></a>Edge 伺服器拓撲選項摘要

在商務用 Skype Server Edge 伺服器部署中, 我們有幾種拓撲選項可供使用:
  
- 含私人 IP 位址和 NAT 的單一合併邊緣
    
- 含公用 IP 位址的單一合併邊緣
    
- 使用私人 IP 位址和 NAT 調整合並後的邊緣
    
- 使用公用 IP 位址調整合並的邊緣
    
- 使用硬體負載平衡器調整合並後的邊緣
    
為了協助您選擇其中一個選項, 我們會提供下清單格, 其中摘要列出您針對每個拓撲所擁有的選項:
  
|**拓撲**|**高可用性**|**Edge 池中的外部邊緣伺服器需要其他 DNS 記錄嗎？**|**商務用 Skype Server 會話的邊緣容錯移轉**|**商務用 Skype Server 同盟會話的邊緣容錯移轉**|
|:-----|:-----|:-----|:-----|:-----|
|含私人 IP 位址和 NAT 的單一合併邊緣  <br/> |不  <br/> |不  <br/> |不  <br/> |不  <br/> |
|含公用 IP 位址的單一合併邊緣  <br/> |不  <br/> |不  <br/> |不  <br/> |不  <br/> |
|使用私人 IP 位址和 NAT 調整合並後的邊緣 (DNS 負載平衡)  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是&sup1;  <br/> |
|使用公用 IP 位址調整合並的邊緣 (DNS 負載平衡)  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是&sup1;  <br/> |
|使用硬體負載平衡器調整合並後的邊緣  <br/> |是的  <br/> |否 (每個 VIP 一個 DNS A 記錄)  <br/> |是的  <br/> |是的  <br/> |
   
&sup1;Exchange 整合通訊 (UM) 使用 DNS 負載平衡的遠端使用者容錯移轉需要 Exchange 2013 或更新版本。
  
### <a name="ip-address-requirements"></a>IP 位址需求

在基本層面上, 三個服務需要 IP 位址;存取邊緣服務、網路會議邊緣服務, 以及 A/V 邊緣服務。 您可以選擇使用三個 IP 位址 (適用于每個服務), 或者您可以使用其中一個服務, 並選擇將每個服務放在不同的埠上 (您可以查看[埠和防火牆規劃](edge-environmental-requirements.md#PortFirewallPlan)區段, 以取得更多相關資訊)。 針對單一整合的邊緣環境而言, 就這麼簡單。
  
> [!NOTE]
> 如上所述, 您可以選擇在所有三個服務中都有一個 IP 位址, 並在不同的埠上執行它們。 但請務必清楚, 我們不建議這麼做。 如果您的客戶無法存取您在這種情況下要使用的備用埠, 您也無法存取您的邊緣環境的完整功能。 
  
使用縮放式合併拓朴可能會稍微複雜一些, 所以讓我們來看看配置 IP 位址需求的一些表格, 請記住, 拓撲選擇的主要決策點是高可用性和負載平衡。 高可用性需求可能會影響您的負載平衡選項 (我們將在表格後面討論更多相關資訊)。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>已調整合並邊緣的 IP 位址需求 (每個角色的 IP 位址)

|**每個池的邊緣伺服器數**|**DNS 負載平衡所需 IP 位址的數目**|**硬體負載平衡所需 IP 位址的數目**|
|:-----|:-----|:-----|
|pplx-2  <br/> |6  <br/> |3 (每個 VIP 1) + 6  <br/> |
|3  <br/> |9  <br/> |3 (每個 VIP 1 個) + 9  <br/> |
|4  <br/> |之間  <br/> |3 (每個 VIP 1) + 12  <br/> |
|500  <br/> |工資  <br/> |3 (每個 VIP 1) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>針對規模合併邊緣 (所有角色的單一 IP 位址) 的 IP 位址需求

|**每個池的邊緣伺服器數**|**DNS 負載平衡所需 IP 位址的數目**|**硬體負載平衡所需 IP 位址的數目**|
|:-----|:-----|:-----|
|pplx-2  <br/> |pplx-2  <br/> |1 (每個 VIP 1 個) + 2  <br/> |
|3  <br/> |3  <br/> |1 (每個 VIP 1 個) + 3  <br/> |
|4  <br/> |4  <br/> |1 (每個 VIP 1 個) + 4  <br/> |
|500  <br/> |500  <br/> |1 (每個 VIP 1 個) + 5  <br/> |
   
讓我們來看看在規劃時要考慮的一些其他事項。
  
- **高可用性**: 如果您在部署中需要高可用性, 您應該在一個池中部署至少兩個 Edge 伺服器。 值得注意的是, 單一邊緣池最多可支援12台邊緣伺服器 (不過, 拓撲建立器可讓您新增最多20個未測試或不受支援的), 因此我們建議您不要這麼做。 如果您需要的邊緣伺服器超過12個, 您應該為它們建立其他邊緣池。
    
- **硬體負載平衡**: 我們建議在大多數情況下進行 DNS 負載平衡。 當然也支援硬體負載平衡, 但重要的是, 它是整個 DNS 負載平衡的單一案例所需的:
    
  - 外部存取 Exchange 2007 或 Exchange 2010 (沒有 SP) 整合通訊 (UM)。
    
- **Dns 負載平衡**: 針對 UM, EXCHANGE 2010 SP1 及更新版本可以受到 DNS 負載平衡支援。 請注意, 如果您需要與舊版 Exchange 的 DNS 負載平衡搭配使用, 它會正常運作, 但是所有的流量都會移至池中的第一個伺服器, 如果不提供, 該流量將會隨後失敗。
    
    如果您要與公司進行聯盟, 也建議使用 DNS 負載平衡:
- 商務用 Skype Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- 商務用 Skype Server 2019:
    - Lync Server 2013
    - 商務用 Skype Server 2015
    - Microsoft Office 365。
    
## <a name="dns-planning"></a>DNS 規劃
<a name="DNSPlan"> </a>

當您進入商務用 Skype Server Edge 伺服器部署時, 請務必正確地準備 DNS。 適當的記錄放在適當的情況下, 部署就會簡單得多。 但願您在上述區段中選擇了一個拓朴, 因為我們要做的是一個概況, 然後列出幾個表格, 以大綱顯示這些案例的 DNS 記錄。 如果您需要, 我們也會針對[商務用 Skype 伺服器進行一些高級邊緣伺服器 DNS 規劃](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md), 以進行更深入的閱讀。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>單一整合邊緣伺服器案例的 DNS 記錄

這些是您將需要用於單一邊緣伺服器的 DNS 記錄, 您可以使用公用 Ip 或使用 NAT 的專用 Ip。 因為這是範例資料, 所以我們會提供範例 IPs, 讓您可以更輕鬆地完成自己的專案:
  
- 內部網路介面卡: 172.25.33.10 (沒有指派預設閘道)
    
    > [!NOTE]
    > 請確定您的網路有一個路由, 該網路包含邊緣內部介面到任何網路, 且包含執行商務用 Skype Server 或 Lync Server 2013 用戶端的伺服器 (例如從172.25.33.0 到 192.168.10.0)。 
  
- 外部網路介面卡:
    
  - 公用 Ip:
    
  - Access Edge: 131.107.155.10 (這是主要, 將預設閘道設定為公用路由器, ex: 131.107.155.1)
    
  - 網路會議 Edge: 131.107.155.20 (第二)
    
  - A/V 邊緣: 131.107.155.30 (第二)
    
  網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
    
  - 私人 Ip:
    
  - 存取邊緣: 10.45.16.10 (這是主要, 將預設閘道設定為您的路由器, ex: 10.45.16.1)
    
  - 網路會議 Edge: 10.45.16.20 (第二)
    
  - A/V 邊緣: 10.45.16.30 (第二)
    
網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
  
> [!TIP]
>這裡有其他可能的設定:
  
- 您可以在外部網路介面卡上使用一個 IP 位址。 我們建議您不要這麼做, 因為您需要使用不同的埠 (您可以在商務用 Skype Server 中執行) 來區分三個服務, 但有些防火牆可能會封鎖備用埠。 如需更多相關資訊, 請參閱[埠和防火牆規劃](edge-environmental-requirements.md#PortFirewallPlan)一節。
    
- 您可以有三個外部網路介面卡 (而非一個), 並將其中一個服務 Ip 指派給每一個。 為什麼要這麼做？ 它會將服務分開, 如果發生錯誤, 這會讓您更容易進行疑難排解, 而且在您解決問題時, 可能會讓其他服務繼續運作。
    
|**位置**|**類型**|**通道**|**FQDN 或 DNS 記錄**|**IP 位址或 FQDN**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公用:** 131.107.155.10 <br/> **私人:** 10.45.16.10 <br/> |您存取邊緣服務的外部介面。 您需要有一個適用于商務用 Skype 使用者的每個 SIP 網域。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公用:** 131.107.155.20 <br/> **私人:** 10.45.16.20 <br/> |您的網路會議 Edge 服務的外部介面。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |av.contoso.com  <br/> |**公用:** 131.107.155.30 <br/> **私人:** 10.45.16.30 <br/> |A/V 邊緣服務的外部介面。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |443  <br/> |_sip _tls  <br/> |sip.contoso.com  <br/> |您存取邊緣服務的外部介面。 商務用 Skype Server、Lync Server 2013 和 Lync Server 2010 用戶端都需要此 SRV 記錄才能在外部作業。 您必須為每一個網域使用商務用 Skype 使用者。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |5061  <br/> |_sipfederationtls _tcp  <br/> |sip.contoso.com  <br/> |您存取邊緣服務的外部介面。 如果聯盟夥伴的自動 DNS 探索稱為 [允許的 SIP 網域], 則需要這個 SRV 記錄。 您必須為每一個網域使用商務用 Skype 使用者。  <br/> |
|內部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |您的合併邊緣的內部介面。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>針對規模 DNS 和硬體邊緣伺服器案例的 DNS 記錄

這些是您將需要用於單一邊緣伺服器的 DNS 記錄, 您可以使用公用 Ip 或使用 NAT 的專用 Ip。 因為這是範例資料, 所以我們會提供範例 IPs, 讓您可以更輕鬆地完成自己的專案:
  
- 內部網路介面卡:
    
  - 節點 1: 172.25.33.10 (沒有指派預設閘道)
    
  - 節點 2: 172.25.33.11 (沒有指派預設閘道)
    
    > [!NOTE]
    > 請確定您的網路有一個路由, 該網路包含邊緣內部介面到任何網路, 且包含執行商務用 Skype Server 或 Lync Server 2013 用戶端的伺服器 (例如從172.25.33.0 到 192.168.10.0)。 
  
- 外部網路介面卡:
    
  - 節點1
    
     - 公用 Ip:
    
        - Access Edge: 131.107.155.10 (這是主要, 將預設閘道設定為公用路由器, ex: 131.107.155.1)
    
        - 網路會議 Edge: 131.107.155.20 (第二)
    
        - A/V 邊緣: 131.107.155.30 (第二)
    
          網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
    
    - 私人 Ip:
    
         - 存取邊緣: 10.45.16.10 (這是主要, 將預設閘道設定為您的路由器, ex: 10.45.16.1)
    
         - 網路會議 Edge: 10.45.16.20 (第二)
    
         - A/V 邊緣: 10.45.16.30 (第二)
    
      網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
    
  - 節點2
    
    - 公用 Ip:
    
      - Access Edge: 131.107.155.11 (這是主要, 將預設閘道設定為公用路由器, ex: 131.107.155.1)
    
      - 網路會議 Edge: 131.107.155.21 (第二)
    
      - A/V 邊緣: 131.107.155.31 (第二)
    
      網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
    
  - 私人 Ip:
    
    - 存取邊緣: 10.45.16.11 (這是主要, 將預設閘道設定為您的路由器, ex: 10.45.16.1)
    
    - 網路會議 Edge: 10.45.16.21 (第二)
    
    - A/V 邊緣: 10.45.16.31 (第二)
    
      網路會議與 A/V 邊緣的公用 IP 位址是 [Internet 通訊協定版本 4 (TCP/IPv4)] 的 [高級] 區段中的其他 (次要) IP 位址, 以及本機區域連線屬性的網際網路通訊協定版本 6 (TCP/IPv6)Windows Server。
    
這裡有其他可能的設定:
  
- 您可以在外部網路介面卡上使用一個 IP 位址。 我們建議您不要這麼做, 因為您需要使用不同的埠 (您可以在商務用 Skype Server 中執行) 來區分三個服務, 但有些防火牆可能會封鎖備用埠。 如需更多相關資訊, 請參閱[埠和防火牆規劃](edge-environmental-requirements.md#PortFirewallPlan)一節。
    
- 您可以有三個外部網路介面卡 (而非一個), 並將其中一個服務 Ip 指派給每一個。 為什麼要這麼做？ 它會將服務分開, 如果發生錯誤, 這會讓您更容易進行疑難排解, 而且在您解決問題時, 可能會讓其他服務繼續運作。
    
|**位置**|**類型**|**通道**|**FQDN 或 DNS 記錄**|**IP 位址或 FQDN**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公用:** 131.107.155.10 和131.107.155.11 <br/> **私人:** 10.45.16.10 和10.45.16.11 <br/> |您存取邊緣服務的外部介面。 您需要有一個適用于商務用 Skype 使用者的每個 SIP 網域。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公用:** 131.107.155.20 和131.107.155.21 <br/> **私人:** 10.45.16.20 和10.45.16.21 <br/> |您的網路會議 Edge 服務的外部介面。  <br/> |
|外部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |av.contoso.com  <br/> |**公用:** 131.107.155.30 和131.107.155.31 <br/> **私人:** 10.45.16.30 和10.45.16.31 <br/> |A/V 邊緣服務的外部介面。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |443  <br/> |_sip _tls  <br/> |sip.contoso.com  <br/> |您存取邊緣服務的外部介面。 商務用 Skype Server、Lync Server 2013 和 Lync Server 2010 用戶端都需要此 SRV 記錄才能在外部作業。 您必須針對每一個網域使用商務用 Skype。  <br/> |
|外部 DNS  <br/> |SRV 記錄  <br/> |5061  <br/> |_sipfederationtls _tcp  <br/> |sip.contoso.com  <br/> |您存取邊緣服務的外部介面。 如果聯盟夥伴的自動 DNS 探索稱為 [允許的 SIP 網域], 則需要這個 SRV 記錄。 您必須針對每一個網域使用商務用 Skype。  <br/> |
|內部 DNS  <br/> |A 記錄  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和172.25.33.11  <br/> |您的合併邊緣的內部介面。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>同盟的 DNS 記錄 (所有案例)

|**位置**|**類型**|**通道**|**稱**|**FQDN 主機記錄**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |DNS-SRV  <br/> |5061  <br/> |_sipfederationtls_tcp  <br/> |sip.contoso.com  <br/> |自動 DNS 探索所需的 SIP 存取邊緣外部介面。 由您其他可能的同盟合作夥伴所使用。 它也稱為「允許 SIP 網域」。 您將需要使用商務用 Skype 使用者的每個 SIP 網域的其中一個專案。  <br/><br/> **注意:** 您需要行動與推播通知結算所需的此 SRV 記錄。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的 DNS 記錄

|**位置**|**類型**|**通道**|**稱**|**IP 位址或 FQDN 主機記錄**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |DNS-SRV  <br/> |5269  <br/> |_xmpp-server _tcp  <br/> |xmpp.contoso.com  <br/> |您存取邊緣服務或 Edge 池中的 XMPP proxy 介面。 您必須在已啟用商務用 Skype Server 使用者的情況下, 視需要為所有內部 SIP 網域重複此動作, 且允許與 XMPP 連絡人的連絡人:  <br/> •全域原則  <br/> •使用者已啟用的網站原則  <br/> •已套用至商務用 Skype Server 的使用者原則  <br/> 您也必須在 XMPP 聯盟使用者原則中設定允許的 XMPP 原則。  <br/> |
|外部 DNS  <br/> |DNS-SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Edge 伺服器或託管您 XMPP Proxy 服務的邊緣池中的 Access Edge 服務 IP 位址  <br/> |這會指向邊緣伺服器或邊緣池上託管 XMPP Proxy 服務的存取邊緣服務。 通常, 您所建立的 SRV 記錄會指向這個主機 (A 或 AAAA) 記錄。  <br/> |
   
> [!NOTE]
> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

## <a name="certificate-planning"></a>憑證規劃
<a name="CertPlan"> </a>

商務用 Skype Server 在伺服器之間及從伺服器到用戶端的安全、加密通訊都使用憑證。 正如您預期的, 您的憑證必須擁有伺服器的 DNS 記錄, 才能符合您憑證上的所有主旨名稱 (SN.EXE) 和 subject 替換名稱 (SAN)。 這將會立即在規劃階段進行, 以確保您在 DNS 中針對您的憑證輸入了正確的 Fqdn 和 SAN 專案。
  
我們將分別討論外部與內部憑證需求, 然後查看提供這兩個需求的表格。
  
### <a name="external-certificates"></a>外部憑證

在最低限度中, 指派給外部邊緣伺服器介面的憑證必須由公用憑證授權單位 (CA) 提供。 我們無法針對您推薦某個特定的 CA, 但我們確實有一個 Ca 清單、[整合通訊憑證合作夥伴](/SkypeForBusiness/certification/services-ssl), 您可以查看您的首選 CA 是否已列在其中。
  
您何時需要將申請提交給此公用憑證的 CA, 以及如何執行該操作？ 有幾種方法可以完成此動作:
  
- 您可以進行商務用 Skype Server 的安裝, 然後再進行 Edge 伺服器部署。 商務用 Skype Server 部署嚮導會有一個步驟來產生憑證要求, 然後您就可以將它傳送給您所選的 CA。
    
- 您也可以使用 Windows PowerShell 命令來產生此要求, 如果這與您的業務需求或部署策略更內嵌。
    
- 最後, 您的 CA 可能會有自己的提交程式, 也可能會涉及 Windows PowerShell 或其他方法。 在這種情況下, 除了此處提供的參考資訊之外, 您還必須依賴其檔。
    
取得證書之後, 您必須先將它指派給商務用 Skype Server 中的下列服務:
  
- 存取邊緣服務介面
    
- 網路會議 Edge 服務介面
    
- 音訊/視頻驗證服務 (請不要將它與 A/V 邊緣服務混淆, 因為這不會使用憑證來加密音訊與視頻資料流程)
    
> [!IMPORTANT]
> 所有邊緣伺服器 (如果它們屬於相同的邊緣伺服器), 都需要擁有與媒體轉送驗證服務擁有相同私密金鑰的完全相同的憑證。 
  
### <a name="internal-certificates"></a>內部憑證

針對內部邊緣伺服器介面, 您可以使用來自公用 CA 的公用憑證, 或從貴組織的內部 CA 頒發的憑證。 內部憑證要記住的一點是, 它會使用 SN 專案, 而不是 SAN 專案, 因此您不需要擔心內部證書上的 SAN。
  
### <a name="required-certificates-table"></a>[必要的憑證] 表格

我們有一個表格可協助您處理您的要求。 此處的 FQDN 專案僅適用于範例網域。 您將需要根據您自己的私人和公用網域提出要求, 但以下是我們使用的指南:
  
- contoso<span></span>.Com: 公用 FQDN
    
- fabrikam<span></span>: 第二個公用 FQDN (如果您有多個 SIP 網域, 就會將它新增為要要求的專案)
    
- Contoso<span></span>.Net: 內部網域
    
#### <a name="edge-certificate-table"></a>Edge 憑證資料表

無論您是要執行單一邊緣伺服器或邊緣池, 您的憑證都需要這麼做:
  
|**元件**|**消費者名稱 (SN)**|**Subject 替代名稱 (SAN)/order**|**筆記**|
|:-----|:-----|:-----|:-----|
|外部邊緣  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |這是您需要從公用 CA 要求的憑證。 需要將它指派給外部邊緣介面, 以進行下列作業:  <br/> •存取邊緣  <br/> •網路會議邊緣  <br/> •音訊/視頻驗證  <br/> <br/>好消息是 San 會自動新增到您的憑證要求, 因此您提交要求之後, 您的憑證會根據您在 [拓撲建立程式] 中為此部署所定義的內容而定。 您只需要為任何其他 SIP 網域或其他需要支援的專案新增 SAN 專案。 為什麼 sip.contoso.com 是在這個範例中進行複製？ 這也會自動發生, 且需要一切才能正常運作。  <br/><br/> **注意:** 這個憑證也可以用於公用立即訊息連線。 您不需要對其執行任何其他動作, 但在本檔的先前版本中, 它是以個別的資料表的方式列出, 而現在卻不是。 <br/> |
|內部邊緣  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |您可以從公用 CA 或內部 CA 取得此憑證。 它必須包含伺服器 EKU (增強型金鑰用法), 您會將它指派給內部邊緣介面。  <br/> |
   
如果您需要可擴展訊息和目前狀態通訊協定 (XMPP) 的憑證, 它看起來會與上述兩個額外的 SAN 專案相同:
  
- xmpp.<span> </span>contoso<span> </span>
    
- \*contoso<span></span>. .com
    
請記住, 目前 XMPP 只能在 Google 交談的商務用 Skype Server 中受到支援, 如果您想要或需要將它用於任何其他專案, 您必須確認涉及協力廠商廠商的功能。
  
## <a name="port-and-firewall-planning"></a>埠和防火牆規劃
<a name="PortFirewallPlan"> </a>

在商務用 Skype Server Edge 的埠和防火牆的規劃中, 您可以為伺服器部署節省幾天或幾周的疑難排解與壓力。 如此一來, 我們將列出幾個表格, 指出我們的通訊協定使用量, 以及在 NAT 和公用 IP 案例中需要有哪些埠都已開啟、入站和出站。 我們也會針對硬體負載平衡案例 (HLB), 以及一些有關該案例的進一步指導方針。 如需進一步閱讀, 我們也會[在商務用 Skype server 中有一些 Edge 伺服器案例](scenarios.md), 您可以查看您的特定部署問題。
  
### <a name="general-protocol-usage"></a>一般通訊協定用法

在查看外部與內部防火牆的摘要資料表之前, 我們也可以考慮下清單格:
  
|**音訊/視頻傳輸**|**用法**|
|:-----|:-----|
|UDP-IN  <br/> |音訊與影片的首選傳輸層通訊協定。  <br/> |
|TCP-OUT  <br/> |音訊與影片的回退傳輸層通訊協定。  <br/> 商務用 Skype Server、Lync Server 2013 和 Lync Server 2010 的應用程式共用所需的傳輸層通訊協定。  <br/> 傳送到商務用 Skype Server、Lync Server 2013 和 Lync Server 2010 所需的傳輸層通訊協定。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部埠防火牆摘要資料表

來源 IP 位址和目的地 IP 位址將包含與 NAT 一起使用私人 IP 位址的使用者, 以及使用公用 IP 位址的人員的資訊。 這會涵蓋在商務用 Skype Server 的 [商務用 Skype] 區段中, 我們的[邊緣伺服器案例](scenarios.md)中的所有排列。
  
|**角色或通訊協定**|**TCP 或 UDP**|**[目的地埠] 或 [埠範圍]**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 商務用 Skype Server 2019 不支援 |TCP-OUT  <br/> |5269  <br/> |每  <br/> |XMPP Proxy service (與存取邊緣服務共用 IP 位址  <br/> |XMPP Proxy 服務接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量。  <br/> |
|Access/HTTP  <br/> |TCP-OUT  <br/> |80  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |每  <br/> |憑證吊銷及 CRL 檢查與檢索。  <br/> |
|Access/DNS  <br/> |TCP-OUT  <br/> |53  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |每  <br/> |針對 TCP 的 DNS 查詢。  <br/> |
|Access/DNS  <br/> |UDP-IN  <br/> |53  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |每  <br/> |經由 UDP 的 DNS 查詢。  <br/> |
|Access/SIP (TLS)  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |供外部使用者存取的用戶端到伺服器 SIP 流量。  <br/> |
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |使用 SIP 進行聯盟及公用 IM 連線。  <br/> |
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |每  <br/> |使用 SIP 進行聯盟及公用 IM 連線。  <br/> |
|網路會議/PSOM (TLS)  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器網路會議 Edge 服務 <br/> **公用 IP:** Edge 伺服器網路會議 Edge 服務公用 IP 位址 <br/> |網路會議媒體。  <br/> |
|A/V/RTP  <br/> |TCP-OUT  <br/> |50000-59999  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |每  <br/> |這是用來中繼媒體流量。  <br/> |
|A/V/RTP  <br/> |UDP-IN  <br/> |50000-59999  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |每  <br/> |這是用來中繼媒體流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |每  <br/> |3478輸出為:  <br/> •使用商務用 Skype Server 來判斷與其通訊的邊緣伺服器版本。  <br/> •用於邊緣伺服器之間的媒體流量。  <br/> •使用 Lync Server 2010 進行聯盟所需。  <br/> •如果貴組織內部署了多個 Edge 池, 則需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |在埠3478上 STUN/開啟候選人對 UDP 的協商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |在埠443上 STUN/開啟候選人與 TCP 的協商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |每  <br/> |在埠443上 STUN/開啟候選人與 TCP 的協商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>內部埠防火牆摘要資料表

|**通訊協定**|**TCP 或 UDP**|**通道**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP-OUT  <br/> |23456  <br/> |執行 XMPP 閘道服務的下列任何一項作業:  <br/> •前端伺服器  <br/> •前端池  <br/> |Edge 伺服器內部介面  <br/> |從您的前端伺服器或前端池執行的 XMPP 閘道服務的輸出 XMPP 流量。  <br/> **注意:** XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。|
|SIP/MTLS  <br/> |TCP-OUT  <br/> |5061  <br/> |每  <br/> •主管  <br/> •主管池  <br/> •前端伺服器  <br/> •前端池  <br/> |Edge 伺服器內部介面  <br/> |從您的主管、主管池、前端伺服器或頂層池到 Edge 伺服器內部介面的輸出 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP-OUT  <br/> |5061  <br/> |Edge 伺服器內部介面  <br/> |每  <br/> •主管  <br/> •主管池  <br/> •前端伺服器  <br/> •前端池  <br/> |從邊緣伺服器內部介面到您的主管、主管池、前端伺服器或頂層端池的輸入 SIP 流量。  <br/> |
|PSOM/MTLS  <br/> |TCP-OUT  <br/> |8057  <br/> |每  <br/> •前端伺服器  <br/> •每個前端伺服器  <br/>  在您的前端池中 <br/> |Edge 伺服器內部介面  <br/> |從您的前端伺服器或每個前端伺服器 (如果您有一個前端伺服器池) 到邊緣伺服器內部介面的網路會議流量。  <br/> |
|SIP/MTLS  <br/> |TCP-OUT  <br/> |5062  <br/> |每  <br/> •前端伺服器  <br/> •前端池  <br/> •使用此 Edge 伺服器的任何 Survivable 分支裝置  <br/> •任何使用此 Edge 伺服器的 Survivable 分支伺服器  <br/> |Edge 伺服器內部介面  <br/> |使用您的 Edge 伺服器, 從您的前端伺服器或前端池或您的 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者。  <br/> |
|STUN/MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |在您的內部與外部使用者以及您的 Survivable 分支裝置或 Survivable 分支伺服器之間, 傳送/V 媒體的首選路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |您的內部與外部使用者以及您的 Survivable 分支裝置或 Survivable 分支伺服器之間的/V 媒體傳輸的回退路徑 (如果 UDP 通訊無法運作)。 然後將 TCP 用於檔案傳輸與桌面共用。  <br/> |
|IP-HTTPS  <br/> |TCP-OUT  <br/> |4443  <br/> |每  <br/> •前端伺服器擁有中央管理存放區  <br/> •擁有中央管理存儲的 [前端] 池  <br/> |Edge 伺服器內部介面  <br/> |從中央管理儲存區將變更複製到 Edge 伺服器。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50001  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50002  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50003  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Edge 埠資料表的硬體負載平衡器

我們會將硬體負載平衡器 (HLBs) 和邊緣埠提供給它自己的區段, 因為其他硬體會稍微複雜一些。 請參閱下表以取得此特定案例的相關指導方針:
  
#### <a name="external-port-firewall-summary-table"></a>外部埠防火牆摘要資料表

來源 IP 位址和目的地 IP 位址將包含與 NAT 一起使用私人 IP 位址的使用者, 以及使用公用 IP 位址的人員的資訊。 這會涵蓋在商務用 Skype Server 的 [商務用 Skype] 區段中, 我們的[邊緣伺服器案例](scenarios.md)中的所有排列。
  
|**角色或通訊協定**|**TCP 或 UDP**|**[目的地埠] 或 [埠範圍]**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP-OUT  <br/> |80  <br/> |Edge 伺服器存取邊緣服務公用 IP 位址  <br/> |每  <br/> |憑證吊銷及 CRL 檢查與檢索。  <br/> |
|Access/DNS  <br/> |TCP-OUT  <br/> |53  <br/> |Edge 伺服器存取邊緣服務公用 IP 位址  <br/> |每  <br/> |針對 TCP 的 DNS 查詢。  <br/> |
|Access/DNS  <br/> |UDP-IN  <br/> |53  <br/> |Edge 伺服器存取邊緣服務公用 IP 位址  <br/> |每  <br/> |經由 UDP 的 DNS 查詢。  <br/> |
|A/V/RTP  <br/> |TCP-OUT  <br/> |50000-59999  <br/> |Edge 伺服器 A/V 邊緣的服務 IP 位址  <br/> |每  <br/> |這是用來中繼媒體流量。  <br/> |
|A/V/RTP  <br/> |UDP-IN  <br/> |50000-59999  <br/> |Edge 伺服器 A/V 邊緣服務公用 IP 位址  <br/> |每  <br/> |這是用來中繼媒體流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |Edge 伺服器 A/V 邊緣服務公用 IP 位址  <br/> |每  <br/> |3478輸出為:  <br/> •使用商務用 Skype Server 來判斷與其通訊的邊緣伺服器版本。  <br/> •用於邊緣伺服器之間的媒體流量。  <br/> •對於同盟是必要的。  <br/> •如果貴組織內部署了多個 Edge 池, 則需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> |Edge 伺服器 A/V 邊緣服務公用 IP 位址  <br/> |在埠3478上 STUN/開啟候選人對 UDP 的協商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |Edge 伺服器 A/V 邊緣服務公用 IP 位址  <br/> |在埠443上 STUN/開啟候選人與 TCP 的協商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |Edge 伺服器 A/V 邊緣服務公用 IP 位址  <br/> |每  <br/> |在埠443上 STUN/開啟候選人與 TCP 的協商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>內部埠防火牆摘要資料表

|**通訊協定**|**TCP 或 UDP**|**通道**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP-OUT  <br/> |23456  <br/> |執行 XMPP 閘道服務的下列任何一項作業:  <br/> •前端伺服器  <br/> •前端池 VIP 位址執行 XMPP 閘道服務  <br/> |Edge 伺服器內部介面  <br/> |從您的前端伺服器或前端池執行的 XMPP 閘道服務的輸出 XMPP 流量。  <br/><br/> **注意:** XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 |
|IP-HTTPS  <br/> |TCP-OUT  <br/> |4443  <br/> |每  <br/> •前端伺服器擁有中央管理存放區  <br/> •擁有中央管理存儲的 [前端] 池  <br/> |Edge 伺服器內部介面  <br/> |從中央管理儲存區將變更複製到 Edge 伺服器。  <br/> |
|PSOM/MTLS  <br/> |TCP-OUT  <br/> |8057  <br/> |每  <br/> •前端伺服器  <br/> •前端池中的每個前端伺服器  <br/> |Edge 伺服器內部介面  <br/> |從您的前端伺服器或每個前端伺服器 (如果您有一個前端伺服器池) 到邊緣伺服器內部介面的網路會議流量。  <br/> |
|STUN/MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> •前端伺服器  <br/> •前端池中的每個前端伺服器  <br/> |Edge 伺服器內部介面  <br/> |在您的內部與外部使用者以及您的 Survivable 分支裝置或 Survivable 分支伺服器之間, 傳送/V 媒體的首選路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> •前端伺服器  <br/> •每個前端伺服器都在您的池中  <br/> |Edge 伺服器內部介面  <br/> |您的內部與外部使用者以及您的 Survivable 分支裝置或 Survivable 分支伺服器之間的/V 媒體傳輸的回退路徑 (如果 UDP 通訊無法運作)。 然後將 TCP 用於檔案傳輸與桌面共用。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50001  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50002  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
|MTLS  <br/> |TCP-OUT  <br/> |50003  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |使用商務用 Skype Server Management 命令介面與集中式記錄服務 Cmdlet、ClsController 命令列 (ClsController) 或 agent (ClsAgent .exe) 命令及記錄集合的集中式記錄服務控制器。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部介面虛擬 Ip

|**角色或通訊協定**|**TCP 或 UDP**|**[目的地埠] 或 [埠範圍]**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Businesss Server 2019 的 Skype 中不支援 |TCP-OUT  <br/> |5269  <br/> |每  <br/> |XMPP Proxy service (與存取邊緣服務共用 IP 位址)  <br/> |XMPP Proxy 服務接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量。  <br/> |
|XMPP  <br/>在 Businesss Server 2019 的 Skype 中不支援 |TCP-OUT  <br/> |5269  <br/> |XMPP Proxy service (與存取邊緣服務共用 IP 位址)  <br/> |每  <br/> |XMPP Proxy 服務會從已定義 XMPP 聯合體中的 XMPP 連絡人傳送流量。  <br/> |
|Access/SIP (TLS)  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |供外部使用者存取的用戶端到伺服器 SIP 流量。  <br/> |
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |使用 SIP 進行聯盟及公用 IM 連線。  <br/> |
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器存取邊緣服務 <br/> **公用 IP:** Edge 伺服器存取邊緣服務公用 IP 位址 <br/> |每  <br/> |使用 SIP 進行聯盟及公用 IM 連線。  <br/> |
|網路會議/PSOM (TLS)  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器網路會議 Edge 服務 <br/> **公用 IP:** Edge 伺服器網路會議 Edge 服務公用 IP 位址 <br/> |網路會議媒體。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |在埠3478上 STUN/開啟候選人對 UDP 的協商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |**使用 NAT 的專用 IP:** Edge 伺服器 A/V 邊緣服務 <br/> **公用 IP:** Edge 伺服器 A/V 邊緣服務公用 IP 位址 <br/> |在埠443上 STUN/開啟候選人與 TCP 的協商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>內部介面虛擬 Ip

我們的指導方針將會稍有不同。 實際上, 在 HLB 情況中, 我們建議您只在下列情況下, 透過內部的 VIP 進行路由:
  
- 如果您使用的是 Exchange 2007 或 Exchange 2010 整合通訊 (UM)。
    
- 如果您有使用 Edge 的舊版用戶端。
    
下表提供這些案例的指導方針, 否則您應該能夠視中央管理書店 (CMS) 來將流量路由傳送給其認識的個別邊緣伺服器 (這會要求 CMS 在 Edge 伺服器上保持在最新狀態)資訊 (當然)。
  
|**通訊協定**|**TCP 或 UDP**|**通道**|**來源 IP 位址**|**目的地 IP 位址**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |每  <br/> •主管  <br/> •控制器池 VIP 位址  <br/> •前端伺服器  <br/> •前部端池 VIP 位址  <br/> |Edge 伺服器內部介面  <br/> |從您的主管、控制器池 VIP 位址、前端伺服器或前部端池 VIP 位址到 Edge 伺服器內部介面的輸出 SIP 流量。  <br/> |
|Access/SIP (MTLS)  <br/> |TCP-OUT  <br/> |5061  <br/> |Edge 伺服器內部 VIP 介面  <br/> |每  <br/> •主管  <br/> •控制器池 VIP 位址  <br/> •前端伺服器  <br/> •前部端池 VIP 位址  <br/> |從邊緣伺服器內部介面到您的主管、控制器池 VIP 位址、前端伺服器或前端池 VIP 位址的入站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP-OUT  <br/> |5062  <br/> |每  <br/> •前端伺服器 IP 位址  <br/> •前端池 IP 位址  <br/> •使用此 Edge 伺服器的任何 Survivable 分支裝置  <br/> •任何使用此 Edge 伺服器的 Survivable 分支伺服器  <br/> |Edge 伺服器內部介面  <br/> |使用您的 Edge 伺服器, 從您的前端伺服器或前端池或您的 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者。  <br/> |
|STUN/MSTURN  <br/> |UDP-IN  <br/> |3478  <br/> |每  <br/> |Edge 伺服器內部介面  <br/> |您內部與外部使用者之間的 A/V 媒體傳輸的首選路徑。  <br/> |
|STUN/MSTURN  <br/> |TCP-OUT  <br/> |443  <br/> |每  <br/> |Edge 伺服器內部 VIP 介面  <br/> |如果 UDP 通訊無法運作, 則為內部與外部使用者之間的 A/V 媒體傳輸的回退路徑。 然後將 TCP 用於檔案傳輸與桌面共用。  <br/> |
