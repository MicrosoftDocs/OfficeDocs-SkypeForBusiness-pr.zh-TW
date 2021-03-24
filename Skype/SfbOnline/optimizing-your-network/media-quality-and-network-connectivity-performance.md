---
title: 媒體品質和網路連線效能
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 本主題定義一組商務用 Skype Online 服務的網路績效需求，以及如何選擇使用網際網路或 ExpressRoute 來建立網路與商務用 Skype Online 之間的連線能力，以評估網路連線性。 如果您決定將 Azure ExpressRoute 部署為 Microsoft 365 或 Office 365 的專用連線，本檔也會提供如何在不同商務用 Skype Online 部署情境中規劃 ExpressRoute 連線的指南。
ms.openlocfilehash: 4ac879c1e2e7b625a45f5d5f399d7438d038595f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100709"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>商務用 Skype Online 中的媒體質量和網路連線能力

本主題定義商務用 Skype Online 服務的網路績效需求集，以及您根據網路連線性評估，選擇使用網際網路或 ExpressRoute 在您的網路與商務用 Skype Online 之間連線。 如果您決定將 Azure ExpressRoute 部署為 Microsoft 365 或 Office 365 的專用連線，本檔也會提供如何在不同商務用 Skype Online 部署情境中規劃 ExpressRoute 連線的指南。
  
IP Real-Time媒體 (音訊、視) 應用程式共用的品質受到端對端網路連接品質的嚴重影響。 為了獲得最佳商務用 Skype Online 媒體質量，請務必確定公司網路與商務用 Skype Online 之間有高品質的連線。 最好的方法就是根據網路容量設定內部網路和雲端連線，以容納商務用 Skype Online 所有連線的尖峰流量。
  
Microsoft 365 和包括商務用 Skype Online 在內的 Office 365 服務不需要 Azure ExpressRoute。 不過，Azure ExpressRoute 是可用的部署選項之一，可協助確保 Microsoft 365 或 Office 365 的連線能力符合商務用 Skype 網路績效需求，並確保最佳的商務用 Skype Online 媒體質量體驗。
  
> [!TIP]
> 雖然本主題提供您整體網路績效指引，但網路評定的完整指南並超出本檔的範圍。 若要尋找可協助進行完整網路評估之網路績效測量之商務用 Skype Online 合作夥伴清單，請流覽商務用 [Skype 合作夥伴解決方案](http://partnersolutions.skypeforbusiness.com/)。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>商務用 Skype Online 的網路連線需求

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>影響商務用 Skype Online 媒體質量的因素

商務用 Skype Online Real-Time 媒體 (音訊、視視及應用程式共用品質) 包括所使用的裝置、環境和網路連線能力，有許多不同因素。 
  
#### <a name="devices"></a>裝置

在Real-Time會話中，所有參與者使用的媒體捕獲和呈現裝置 ，例如耳機和 Web 相機，對整體音訊和視音訊品質有很大的影響。 品質較低的裝置或裝置如果驅動程式不正確，則會降低音訊的整體音效品質，以及降低視音訊的影像品質。 另一方面，經過認證的裝置或品質良好的裝置可協助消除回音、雜訊篩選、視像解析度並減少延遲。
  
雖然不需要經過認證的音訊和視視媒體裝置，但強烈建議使用經商務用 Skype 認證的裝置，以獲得最佳媒體體驗。 有關所有商務用 Skype 認證裝置的清單，請參閱商務用 Skype 的電話 [和裝置](../../SfbPartnerCertification/certification/devices-ip-phones.md)。 您可以使用商務用 [Skype Online](/microsoftteams/turning-on-and-using-call-quality-dashboard)通話品質儀表板 ，位於商務用 **Skype** 系統管理中心，以驗證使用中的裝置是否正常，並監控音訊和視音訊媒體質量。
  
> [!TIP]
> **需要經過認證的裝置，才能獲得最佳商務用 Skype 媒體質量體驗**。
  
請記得，任何媒體裝置、商務用 Skype 用戶端和商務用 Skype 伺服器，Real-Time媒體流程時，會引入一些延遲。 裝置和軟體處理延遲，以及網路延遲，對端對端整體延遲和使用者體驗有極大的影響，並有助於其影響。
  
#### <a name="environment"></a>環境

使用者開會及使用音訊和視像裝置的環境及周圍區域是音訊和視音訊品質的另一大因素。 從吵雜環境通話的使用者會聽到回音、雜亂且不清楚的音訊。 在深色或低亮度環境中，使用者將無法為視片產生明亮、清楚的影像品質。 在會議室設定中，麥克風和視像裝置的位置會對參與者收到的音效和影像品質有直接的影響。
  
若要更清楚地瞭解使用者的音訊和視音訊體驗，請使用商務用 Skype 應用程式工具選項 音訊裝置或視像裝置，對使用中的裝置進行變更，並自訂  >    >  其設定。 

#### <a name="network"></a>網路

IP 網路Real-Time媒體的品質會受到網路連接品質的嚴重影響，尤其是受到以下數量的影響：
  
- **延遲** 這是從 A 點到網路 B 點取得 IP 封包所花的時間。 此網路傳播延遲基本上與兩點之間的實際距離和光速有關，包括介於兩者之間的各種路由器所增加的額外負荷。 延遲是以 RTT 或 RTT 的單向或往返時間 (測量) 。
    
- **封包遺失** 這通常定義為在給定時段內遺失的封包百分比。 封包遺失會直接影響音訊品質，包括小型、個別遺失的封包幾乎沒有影響，以及造成音訊完全中斷的背對背斷流損失。
    
- **封包間到達的抖動或只是抖動** 這是連續封包之間延遲的平均變化。 大部分的新式 VoIP 軟體 ，包括商務用 Skype，都可以透過緩衝來適應某些層級的抖動。 只有當抖動超過緩衝時，參與者才能注意到抖動的影響。
    
> [!NOTE]
>  針對抖動進行緩衝會增加端對端延遲。
  
有許多同時處理商務用 Skype Online Real-Time 媒體會話，以及其他 Microsoft 365 或 Office 365 服務及其他商務應用程式產生的網路流量，確保將您的網路連線至商務用 Skype Online 服務的整個網路路徑有足夠的頻寬，對於避免網路塞塞和確保媒體 Real-Time 媒體 (音訊、視像和應用程式共用品質) 至關重要。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>跨塞網路 (QoS) 服務品質

此外，整個網路的流量塞塞會嚴重影響媒體質量。 若要讓音訊和視訊封包能更快速地流覽網路，並優先處理擁擠網路的其他網路流量，可以使用服務品質 (QoS) ，協助為音訊和視訊通訊提供最佳的使用者體驗。
  
QoS 提供一種方法，您可以為包含音訊或視像資料的網路封包指派較高的優先順序。 將較高優先順序指派給這些封包後，音訊和視訊通訊可能會比涉及檔案傳輸、網頁流覽或資料庫備份等內容的網路會話更快速地在網路間傳輸，且干擾較少。 這是因為根據預設，用於檔案傳輸或資料庫備份的網路封包會獲派「最大努力」做為優先順序，而網路擠塞也不會有太大的影響。 如果您沒有將較高的優先順序指派給媒體 (音訊、視視及應用程式共用) 封包，並將這些封包指派為「盡力」，這些封包也會連同所有其他網路流量一起處理。 視網路塞塞量而不同，這可能會導致使用者的整體音訊和視音訊品質體驗降低。
  
強烈建議您于網路上執行 QoS，以確保網路內的網路塞塞不會受到影響。 不過，若要達到最大影響，所有網路端點都必須支援 QoS，這表示所有端點都必須遵守 QoS 標記和封包優先順序。 商務用 Skype Online 服務會遵守 Microsoft 網路內的 QoS 標記和優先順序。 不過，從貴公司網路路由到 Microsoft 網路等公用連接的流量，不會保留 QoS 標記和封包優先順序。 使用 Azure [ExpressRoute](https://azure.microsoft.com/services/expressroute/) 從網路到 Microsoft 365 或 Office 365 的私人連結提供可保留 QoS 標記和封包優先順序的部署解決方案，進而提升使用者的整體音訊和視訊品質。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>連線到商務用 Skype Online 的網路績效需求
<a name="bkNetworkPerf"> </a>

商務用 Skype Real-Time媒體會透過許多不同的裝置、用戶端應用程式、伺服器軟體，以及跨不同的網路進行。 媒體的端對端延遲Real-Time是跨所有元件和網路區段所引入的總延遲量。 端對端網路連接的品質取決於品質最差的網路區段。 此區段會成為此網路流量的瓶頸。
  
下圖說明會議中的單向音訊流程，從一個商務用 Skype 參與者到另一個參與者。
  
![ExpressRoute 通話流程。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
在此會議情境中，媒體路徑會橫跨下列網路區段：
  
1. **從使用者 1 到 Microsoft 網路邊緣的連接** 這通常包括網路連接 ，例如 WiFi 或乙太網路、從使用者 1 到網際網路出口點的 WAN 連接 (您的網路 Edge 裝置) ，以及從網路 Edge 到 Microsoft 網路 Edge 的網際網路連接。
    
2. **Microsoft 網路內的連接** 這是在 Microsoft Edge 到商務用 Skype Online 資料中心之間，使用 A/V 會議伺服器。
    
3. **Microsoft Network 內的連接** 這是在商務用 Skype Online 資料中心和 Microsoft 網路 Edge 之間。
    
4. **從 Microsoft 網路邊緣連接到使用者 2** 這包括從網路 Edge 到 Microsoft 網路 Edge 的網際網路連接、從使用者 2 到網際網路出口點的 WAN 連接 (您的網路 Edge) ，以及網路連接 ，例如 WiFi 或乙太網路。
    
下圖顯示商務用 Skype Online PSTN 通話的元件和網路區段明細：
  
![ExpressRoute PSTN 電信公司通話流程。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 通話情境中，媒體路徑會跨越下列網路區段：
  
1. **從商務用 Skype 用戶端來電者到 Microsoft 網路邊緣的連絡** 這通常包括網路連接 ，例如 WiFi 或乙太網路、從商務用 Skype 用戶端來電者到網際網路出口點的 WAN 連接 (您的網路邊緣裝置) ，以及從網路 Edge 到 Microsoft 網路 Edge 的網際網路連接。
    
2. **Microsoft 網路內的連接** 這是在 Microsoft Edge 到商務用 Skype Online 資料中心之間，使用中繼伺服器。
    
3. **Microsoft Network 內的連接** 這是在商務用 Skype Online 資料中心和 Microsoft 網路 Edge 之間。
    
4. **Microsoft Network 與 PSTN 服務提供者合作夥伴之間的連接** 這是從 Microsoft 網路外部的商務用 Skype 用戶端撥打 PSTN 通話所存在的連接。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>從商務用 Skype 用戶端到 Microsoft 網路 Edge 的網路績效需求
<a name="bkSfBClienttoEdge"></a>

為了獲得最佳商務用 Skype 媒體質量，從公司網路連接到 Microsoft 網路 Edge 時，需要下列網路績效度量目標或臨界值。 此網路區段包含您的內部網路，這包括所有 WiFi 和乙太網路連接、任何公司網站對網站流量的 WAN 連接，例如 Multiprotocol 標籤交換 (MPLS) ，以及網際網路或 ExpressRoute 合作夥伴到 Microsoft 網路 Edge 的連絡。
  
> [!CAUTION]
> **貴公司網路上商務用 Skype 用戶端與 Microsoft 365 或 Office 365 服務之間的連接必須符合下列網路績效需求和閾值。**
  
|||
|:-----|:-----|
|**度量** <br/> |**目標** <br/> |
|單向 (延遲)   <br/> |< 50 毫秒  <br/> |
|RTT (往返時間延遲)   <br/> |< 100 毫秒  <br/> |
|突發封包遺失  <br/> |<200 毫秒間隔期間增加 10%  <br/> |
|封包遺失  <br/> |<15 個間隔期間增加 1%  <br/> |
|封包間延遲  <br/> |<15 個間隔內，<30 毫秒  <br/> |
|封包重新排序  <br/> |<0.05% 的無序封包  <br/> |
   
 **其他績效目標需求：**
  
- Microsoft 網路在全球有 160 多個 Edge 位置。 我們透過這些 Edge 網站 (網際網路服務提供者) ISP。 延遲度量目標假設您的公司網站或網站與 Microsoft Edges 位於同一洲。
    
- 貴公司網站或 Microsoft 網路 Edge 連接的網站包含第一躍點網路存取，可以是 WiFi 或其他無線技術。 
    
- 網路績效目標會假設適當的頻寬和/或服務規劃品質。 換句話說，當網路負載最大時，這Real-Time商務用 Skype 或媒體流量。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>從網路 Edge 到 Microsoft 網路 Edge 的網路績效需求
<a name="bkYourNetworkEdge"> </a>

以下是網路 Edge 與 Microsoft 網路 Edge 之間連接所需的網路績效目標或臨界值。 此網路區段排除客戶的內部網路或 WAN，且用於測試透過網際網路或透過 ExpressRoute 合作夥伴網路所送出網路流量時，以及可用來與 ExpressRoute 提供者進行績效服務等級協定 (SLA) 的通訊。
  
> [!CAUTION]
> **貴公司網路 Edge 與 Microsoft 網路邊緣之間的連接必須符合下列網路績效需求和閾值。**
  
|||
|:-----|:-----|
|**度量** <br/> |**目標** <br/> |
|單向 (延遲)   <br/> |< 30 毫秒  <br/> |
|RTT (延遲)   <br/> |< 60 毫秒  <br/> |
|突發封包遺失  <br/> |<200 毫秒間隔期間增加 1%。  <br/> |
|封包遺失  <br/> |<15 個間隔期間，0.1%  <br/> |
|封包間延遲  <br/> |<15 個間隔內，超過 15 毫秒  <br/> |
|封包重新排序  <br/> |<0.01% 的無序封包  <br/> |
   
 **其他績效目標需求：**
  
- 績效目標需要貴公司的任何網路 Edge 與最接近的 Microsoft 網路 Edge 之間的連接，以在同一洲上。
    
- 網路績效目標會假設適當的頻寬和/或服務規劃品質。 當網路連接負載最大時Real-Time商務用 Skype 或媒體流量也適用。 如需適當的頻寬和 QoS 規劃，請參閱商務用 Skype Online 中的[ExpressRoute 和 QoS。](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>測量網路績效
<a name="bkNetworkPerf"> </a>

若要測量從任何公司網路網站到網路 Edge 的實際網路績效，尤其是延遲和封包遺失，您可以使用 ping 等工具，針對一組從 Microsoft Edge 和資料中心網站執行之商務用 Skype 媒體轉送服務進行測試。 

>[!NOTE]
> 透過 ping 或 ICMP (測量網路) 無法有效。 基於這個原因，下列任何廣播 IP 公開將會停止回應 ICMP 要求，從 2020 年 1 月開始。 為了有效測量網路執行，Microsoft 建議使用 [網路 Assesment 工具](https://www.microsoft.com/download/details.aspx?id=53885)。
  
若要測試 Microsoft 網路的網際網路連接，建議您針對下列商務用 Skype 媒體轉場的 VIP 進行測試。 *Anycast 的VIP* 會解析為最接近測試位置的 Microsoft 網路 Edge 網站中媒體轉場的 IP 位址。
  
||||
|:-----|:-----|:-----|
|**IP 位址** <br/> |**類型** <br/> |**位置** <br/> |
|13.107.8.2  <br/> |貴賓  <br/> |World Wide Anycast IP  <br/> |
   
 **以下是評估網路績效時要遵循的一些高層級建議：**
  
- 您應該評估內部網路，以及 Microsoft 365 或 Office 365 的關聯。
    
- 您應評估並收集您所有網路在很長一段時間的資料。 我們建議您至少執行一周的網路績效測試，以便查看所有工作天和小時的使用模式。 這會顯示高峰時間。
    
- 您應該採取多個網路績效度量的範例。 我們建議您在收集資料的整個期間，每隔 10 分鐘從公司網站進行測量。 為了比較商務用 Skype Online 網路績效需求，請從此範例資料集中取第 90 個百分位數度量值。 
    
- 您應該持續評估網路的表現。 由於使用模式變更、使用大量頻寬的新企業型應用程式，以及組織或實體公司位置的變更，網路使用量會隨著時間而改變。 請務必根據這些網路性能需求和目標/閾值持續監控網路績效，並及時進行調整，以確保媒體質量Real-Time最佳狀態。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>使用 Azure VM 測量網路績效
<a name="bkNetworkPerf"> </a>

除了針對 Microsoft 網路 Edge 網站進行測試，還有來自商務用 Skype 客戶和合作夥伴的網路評定解決方案，可運用 Microsoft Azure 雲端服務的測試設定。 在這些解決方案中，網路評估工具會針對在 Azure 雲端中設定為服務的自訂端點測試延遲、封包遺失和抖動。 因此，測試網路流量會經過一個額外的網路區段，即網路邊緣與託管網路評定服務的 Azure 資料中心之間的 Microsoft 網路內連接。
  
針對那些以 Azure 託管測試服務為基礎的網路評定解決方案。 我們建議您在國與/或地區內執行網路評估。 例如，針對美國東部的客戶網站，應針對 Azure 美國東部資料中心地區的測試服務實例執行評定。 
  
以下是 Azure 服務型網路 (評估) RTT 的延遲時間。 單向延遲目標為對應 RTT 目標的一半。 封包遺失和抖動目標與 Skype Media Relay 測試定義的目標相同。
  
|||||
|:-----|:-----|:-----|:-----|
|**用戶端區域** <br/> |**Azure 區域** <br/> |**您的網路 Edge - Azure 往返時間 (RTT)** <br/> |**您的網站 - Azure 往返時間 (RTT)** <br/> |
|美國中部  <br/> |美國中部  <br/> |99  <br/> |139  <br/> |
|美國東部  <br/> |美國東部  <br/> |86  <br/> |126  <br/> |
|美國中北部  <br/> |美國中北部  <br/> |97  <br/> |137  <br/> |
|美國中南部  <br/> |美國中南部  <br/> |94  <br/> |134  <br/> |
|美國西部  <br/> |美國西部  <br/> |94  <br/> |134  <br/> |
|美國夏威夷  <br/> |美國西部  <br/> |116  <br/> |156  <br/> |
|加拿大中部  <br/> |加拿大中部  <br/> |138  <br/> |178  <br/> |
|加拿大東部  <br/> |加拿大東部  <br/> |131  <br/> |171  <br/> |
|北歐  <br/> |北歐  <br/> |99  <br/> |139  <br/> |
|西歐  <br/> |西歐  <br/> |95  <br/> |135  <br/> |
|東亞  <br/> |東亞  <br/> |118  <br/> |158  <br/> |
|東南亞  <br/> |東南亞  <br/> |97  <br/> |137  <br/> |
|日本東部  <br/> |日本東部  <br/> |111  <br/> |151  <br/> |
|日本西部  <br/> |日本西部  <br/> |118  <br/> |158  <br/> |
|巴西南部  <br/> |巴西南部  <br/> |70  <br/> |110  <br/> |
|澳洲東部  <br/> |澳洲東部  <br/> |124  <br/> |164  <br/> |
|澳洲東南部  <br/> |澳洲東南部  <br/> |124  <br/> |164  <br/> |
|印度中部  <br/> |印度中部  <br/> |103  <br/> |143  <br/> |
|南印度  <br/> |南印度  <br/> |103  <br/> |143  <br/> |
|西印度  <br/> |西印度  <br/> |103  <br/> |143  <br/> |
|中國東部  <br/> |中國東部  <br/> |120  <br/> |160  <br/> |
|中國北部  <br/> |中國北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>媒體質量和 ExpressRoute
<a name="bkNetworkPerf"> </a>

Microsoft 365 或 Office 365 的 Azure ExpressRoute 是一種專用網路連接，可連接到 Microsoft 365 或 Office 365。 它讓客戶能夠控制其網路流量的路徑。 他們不再需要擔心網際網路上發生無法預測的路由，因為不明的電信公司、提供者和 ISP 會傳送資料。 透過 ExpressRoute 所送出的網路流量會直接透過 ExpressRoute 合作夥伴的網路送往 Microsoft 網路。 這可讓客戶將 Microsoft 365 或 Office 365 視為位於自己的非現場資料中心，並擁有專用連線。
  
Azure ExpressRoute 適用于所有 Microsoft 365 和 Office 365 授權方案。 不過，Microsoft 365 和 Office 365 需要 Azure ExpressRoute Premium 附加元件才能啟用全域路由。 擁有至少 500 個使用 ExpressRoute 的客戶可以取得所需的 *ExpressRoute Premium* 附加元件，而不需要支付額外費用。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>需要 ExpressRoute 才能確保良好的媒體質量嗎？

Azure ExpressRoute 並非獲得最佳商務用 Skype Online 媒體質量的需求。 不過，這是其中一個部署選項，可協助確保您的雲端連接子合商務用 Skype 網路績效目標或臨界值。
  
Microsoft 365 和 Office 365 是使用網際網路的高品質且安全的服務。 我們會持續投資新的安全性功能和地區邊緣節點，以持續改善安全性與績效。 Microsoft 365 或包括商務用 Skype Online 在內的 Office 365 服務不需要 Azure ExpressRoute。 Azure ExpressRoute 是可用的部署選項之一，可協助確保 Microsoft 365 或 Office 365 的連線能力符合商務用 Skype 網路績效需求，並確保最佳的商務用 Skype Online 媒體質量體驗。
  
針對商務用 Skype Online 媒體質量，公司網站與 Microsoft 網路 Edge 之間的連線必須符合從商務用 Skype 用戶端到 [Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) 網路 Edge 之網路績效需求中的績效目標，而且網路 Edge 和 Microsoft 網路邊緣之間的連線必須符合網路 Edge 到 [Microsoft](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)網路 Edge 之網路績效需求中的績效目標。  
  
此外，您公司實體網路連接 ，包括您的內部網路和雲端連接容量，也一樣必須能容納媒體流量的高峰。 Azure ExpressRoute 是可協助客戶確保其商務用 Skype Online 雲端連線符合所有這些性能需求的眾多方法之一。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Voice 品質 SLA 需要 ExpressRoute 嗎？

否，商務用 Skype Online 語音品質 SLA 不需要 ExpressRoute。 商務 [用 Skype Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) 語音品質 SLA 適用于任何商務用 Skype Online 語音服務使用者在正確的授權和訂閱內撥打的任何合格通話，讓使用者可以撥打任何類型的 VoIP 或 PSTN 通話。 語音品質 SLA 應包含解決下列所有條件：
  
- 來自 Microsoft 認證的 IP 電話通話。
    
- 有線乙太網路連接。
    
- Microsoft 網路問題導致語音品質問題。
    
> [!NOTE]
> 語音品質 SLA 會排除非 Microsoft 網路 ，包括 ExpressRoute 合作夥伴和其他網路的問題導致通話品質低的通話。 
  
### <a name="internet-or-azure-expressroute"></a>網際網路或 Azure ExpressRoute？

在決定商務用 Skype Online 的網路連線選項之前，客戶必須先根據網路績效需求中所述的網路績效需求來評估其網路和目前的網際網路連線能力，才能連線到商務用[Skype Online。](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
如果目前網際網路連線的網路績效設定為在尖峰時段內有足夠的容量，而且符合從網站到 Microsoft 網路 Edges 以及從網路 Edges 到 Microsoft 網路 Edges 的網路績效需求，您可以繼續使用現有的網際網路連線到商務用 Skype Online。
  
針對網路績效需求未達的公司網站，我們強烈建議您先與現有的網路服務提供者合作，以改善整體網路績效。 不過，如果仍無法符合需求，使用 Azure ExpressRoute 可協助確保您的商務用 Skype Online 雲端連線能力可協助您符合網路績效需求。
  
Azure ExpressRoute 提供下列額外權益：
  
- 服務等級協定 (SLA) 網路與 Microsoft 網路之間是否可用。 ExpressRoute 的保證可用性 SLA 為 99.9%。
    
- Microsoft 365 和 Office 365 服務所需的已規劃且保證頻寬。 您只要使用 ExpressRoute 傳送 Microsoft 365、Office 365 或商務用 Skype 流量，然後讓所有其他網際網路流量經過您網路的其他網際網路出口/進入點，就可以達成此目的。
    
- ExpressRoute 是專為保留您的網路與 Microsoft 網路之間的 DSCP QoS 標記所設計。
    
如需 ExpressRoute QoS 和容量規劃的資訊，請參閱商務用 Skype Online 中的[ExpressRoute 和 QoS。](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>我可以設定商務用 Skype Online 版 Azure ExpressRoute 嗎？

可以，您可以設定 Azure ExpressRoute，以確保從公司網路到商務用 Skype Online 的網路連線能力良好。 這會為使用者提供最佳Real-Time媒體質量，但您可以繼續網際網路上的其他 Microsoft 365 或 Office 365 服務。
  
BGP (閘道通訊) 是網際網路上的路由通訊協定，用來路由網際網路上的網路流量。 它專為在網際網路上找到的自動 (AS) 之間交換路由資訊。 BGP 社群值是可適用于傳入或外發路由的屬性標記。 BGP 社群通常用來根據地理位置、服務類型或其他準則，向接收的 AS 發出要用來到達指定目的地之輸出連結的訊號。
  
有了 BGP 社群支援，Microsoft 會根據 BGP 社群所屬的服務，以適當的 BGP 社群值標記首碼和路由。 Microsoft 會以適當的 BGP 社群值標記透過公用對等和 Microsoft 對等互連所宣告的首碼，指出首碼所託管的區域。 您可以仰賴社群值來做出適當的路由決策，以提供最佳路由。 您可以使用商務用 Skype Online BGP 社群值來設定僅適用于商務用 Skype Online 的 ExpressRoute 連線。 您可以瞭解[ExpressRoute 路由需求。](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>商務用 Skype Online 的 ExpressRoute 連線案例
<a name="bkNetworkPerf"> </a>

如果您根據上述建議決定 ExpressRoute 是適合您的，以下是您應該取得哪一個 ExpressRoute 連結和多少個 ExpressRoute 連接的建議。
  
### <a name="online-only-deployment---single-site"></a>僅線上部署 - 單一網站

如果您的所有使用者都使用商務用 Skype Online 服務，如果您的辦公室集中在單一實體位置，而您決定部署 Azure ExpressRoute，您應該在公司網站之間設定單一 ExpressRoute 連線，以最接近 [的 ExpressRoute](/azure/expressroute/expressroute-locations)對等位置。
  
下圖顯示此類型的部署範例。 在此範例中，Contoso 是一所位於美國佛羅里達州的大學。 Contoso 有 10，000 位教職員成員和學生。 從位置到 Microsoft Edge 網站的網際網路測試顯示，在尖峰時段期間，封包遺失超過 5%。 他們決定使用 ExpressRoute 與過度佈設頻寬，取得 Microsoft 365 或 Office 365 的專用連線，以避免 Microsoft 365 或 Office 365 的網路塞塞，尤其是商務用 Skype Online Real-Time 流量。 他們透過位於佐治亞州、GA MeetMe 網站的 ExpressRoute 來連接到 Microsoft 雲端。
  
![ExpressRoute 單一網站。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>僅線上部署 - 同一洲上的多個網站

如果您的公司使用同一地區或洲中多個辦公室的商務用 Skype Online 服務，而您選擇執行 Azure ExpressRoute，建議您透過 ExpressRoute 連線主網站，然後選擇性地為不符合建議網路績效目標的其他位置新增額外的 ExpressRoute 對等。
  
在下列範例中，Contoso 是一家美國旅遊服務公司，總部位於紐約，但在美國有其他辦公室。 他們的辦公室會透過 WAN 進行相互連結，該 WAN 會使用 MPLS 連接到 Microsoft 365 或 Office 365。 他們最初從他們在紐澤西州Hoboken的網際網路路由器設定 ExpressRoute 連接至紐約 MeetMe 網站。 
  
有了這項設定，從大部分網站到 Microsoft Network (紐約 Edge 網站) 的網路流量，就可以符合商務用 Skype 用戶端到 [Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)網路 Edge 之網路績效需求中所述的商務用 Skype 用戶端連接網路績效目標。 不過，Contoso 西岸辦公室到紐約之間的延遲會單向超過 50 毫秒。 此外，Honolulu 是 Contoso 的第二大辦公室，從 Hono延遲到紐約，單向延遲超過 80ms。 為了確保這些辦公室的使用者有良好的媒體質量，Contoso 決定在聖約瑟網站與矽谷 ExpressRoute MeetMe 網站之間新增西岸 ExpressRoute 連接。
  
![同一洲上的 Express 路由器多網站。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>僅線上部署 - 不同洲的多個網站

如果您的所有使用者都使用商務用 Skype Online 服務，如果您的辦公室位於多個洲的多個實體位置，如果您決定部署 Azure ExpressRoute，您應該在每個洲的主要網站與最接近的 [ExpressRoute](/azure/expressroute/expressroute-locations)對等位置之間，針對每個洲設定至少一個 ExpressRoute 連線。 根據成本與收益，您可以選擇從未達網路績效目標的網站部署額外的 ExpressRoute 連接。
  
在下列範例中，Contoso 是一家大型企業律師事務所，其辦公室遍佈北美和歐洲的大城市。 根據網際網路連接及其內部網路績效評定，Contoso 決定在北美部署兩個 ExpressRoute 連接，並針對所有歐洲辦公室部署單一 ExpressRoute 回路。
  
![具有多個網站和洲的 ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>混合式部署

如果您有內部部署 Lync 或商務用 Skype 部署，並選擇實行混合式商務用 Skype Online 整合，我們建議您決定部署 Azure ExpressRoute，則每個內部部署 Lync 或商務用 Skype Edge 網站必須至少有一個 ExpressRoute 連線，且每個洲與辦公室之間至少要有一個 ExpressRoute 連線。 根據成本與效益，您可以選擇從未達網路績效目標的辦公室部署額外的 ExpressRoute 連接。
  
如果您有內部部署商務用 Skype，則必須遵循 [Edge Server 規劃與部署指南](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md)。 具體來說，Edge 伺服器必須從您的網路外部進行。 這通常是將可路由的公用 IP 位址指派給 Edge 伺服器，或是使用網路位址翻譯 (NAT) 。
  
在下列範例中，Contoso 有現有的內部部署商務用 Skype 企業語音部署。 他們想要將內部部署使用者遷移到 Microsoft 365 或 Office 365 線上服務。 他們也決定使用混合式部署，以便繼續針對所有內部部署和線上使用者使用現有的 PSTN 基礎結構。 Contoso 內部部署資料中心和商務用 Skype Edge 伺服器位於芝加哥。 針對他們的部署，Contoso 決定在芝加哥資料中心與芝加哥 ExpressRoute 之間設定一個 ExpressRoute 連接。 他們也新增了西岸的 ExpressRoute 連接，以更好的服務其 Honolulu 辦公室。
  
![ExpressRoute 混合式。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>使用雲端連接器版進行線上部署

商務用 Skype Online 雲端連接器版本是混合式方案，包含一組封裝的虛擬機器 (虛擬機器) 內部部署 PSTN 連線。 透過在虛擬化環境中部署最小的商務用 Skype Server 拓撲，您就能透過現有的內部部署 PSTN 語音基礎結構，使用有線電話和行動電話來傳送和接聽電話。
  
如果您決定部署 Azure ExpressRoute 和雲端連接器版本，我們建議您在每個洲的主要網站與最接近 [的 ExpressRoute](/azure/expressroute/expressroute-locations)對等位置之間，針對每個洲設定至少一個 Express Route 連接。 根據成本與效益，您可以選擇從未達網路績效目標的網站部署額外的 ExpressRoute 連接。
  
如果您有內部部署商務用 Skype 部署，則必須遵循商務用 [Skype 雲端](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)連接器版規劃指南。 具體來說，Access Edge 和 A/V Edge 服務應指派公用 IP 位址和可存取的 Microsoft 365 或 Office 365 資料中心。
  
在下列範例中，Contoso 是一家歐洲會計公司，在幾個主要的歐洲國家/地區與城市有業務。 當他們註冊商務用 Skype Online 以完成所有共同合作需求時，他們決定為各自擁有實體位置的每個國家/地區安裝雲端連接器，以繼續使用其 PSTN 基礎結構和已經存在的電信業者合約。 根據他們從所有網站和 Microsoft 網路 Edge 的測試，他們決定倫敦的單一 ExpressRoute 連接可協助符合商務用 Skype 用戶端到 [Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)網路 Edge 之網路績效需求中所述的商務用 Skype 用戶端連接網路績效目標。
  
![ExpressRoute Cloud Connector One。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
以下是 Contoso 的另一個部署選項。 在這種情況下，他們決定在部署雲端連接器的每個網站上設定 ExpressRoute 連接。 
  
![ExpressRoute Cloud Connector 2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>相關主題

[商務用 Skype Online 中的 ExpressRoute 與 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
