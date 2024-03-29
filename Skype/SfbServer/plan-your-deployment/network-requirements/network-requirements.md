---
title: 規劃商務用 Skype 的網路需求
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 摘要：在實施商務用 Skype Server 之前，請先複查下列網路元件考慮。
---

# <a name="plan-network-requirements-for-skype-for-business"></a>規劃商務用 Skype 的網路需求

**總結：** 在實施商務用 Skype Server 之前，請先複查下列網路元件考慮。

這些主題中的資訊也會在 [Lync Server 的白皮書網路規劃、監控及疑難排解](https://www.microsoft.com/download/details.aspx?id=39084) 中討論，以及其他詳細資料與深度。 雖然內容明確表示 lync 2010 和 Lync 2013，但商務用 Skype Server 的考慮不會改變。

同樣地，如果您的網路包括 wi-fi 和有線存取，則透過[Wi-Fi 傳送 Lync 2013 Real-Time 通訊](https://www.microsoft.com/download/details.aspx?id=36494)的白皮書是很好的參考，而且同樣適用于商務用 Skype Server。

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>伺服器硬體
<a name="S_hard"> </a>

商務用 Skype Server 拓撲中每一部伺服器的網路介面卡都必須支援至少1十億位元/秒 (Gbps) 。 一般說來，您應該使用低延遲和高頻寬區域網路 (LAN) ，在商務用 Skype Server 拓撲中連線所有伺服器角色。 LAN 的大小取決於拓撲大小：

- 在 Standard Edition 拓撲中，伺服器應位於支援 1 Gbps 乙太網或對等的網路上。

- 在 Enterprise Edition 拓朴中，大部分的伺服器應位於支援 1 Gbps 以上的網路中，尤其是支援音訊/視頻 (A/V) 會議和應用程式共用。

針對公用交換電話網路 (PSTN) 整合，您可以使用 T1/E1 線路或 SIP 主幹來整合。

## <a name="audiovideo-network-requirements"></a>Audio/Video 網路需求
<a name="AV_req"> </a>

商務用 Skype Server 部署中的音訊/視頻 (A/V) 的網路需求如下：

- 若要使用 DNS 負載平衡部署單一 Edge Server 或 Edge 集區，您可以設定  _外部_ 防火牆，以執行網路位址轉譯 (NAT) 。 您無法設定 _內部_ 防火牆來執行 NAT。 如需詳細資訊，請參閱 [埠及防火牆規劃](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)。

    > [!IMPORTANT]
    > 如果您有 Edge 集區而且使用硬體負載平衡器，則必須使用 Edge Server 上的公用 IP 位址，而且無法在具有 NAT (功能之裝置的伺服器或集區上使用 NAT，例如，防火牆裝置或 LAN 參數。 如需詳細資訊，請參閱[商務用 Skype Server 中的 Edge Server 案例](../edge-server-deployments/scenarios.md)。

- 如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。

- 如果您使用網際網路通訊協定安全性 (IPsec)，建議您針對 A/V 流量所使用的連接埠範圍停用 IPsec。 如需詳細資訊，請參閱 [IPsec 例外](#ipsec-exceptions)狀況。

若要提供最佳的媒體質量，請執行下列操作：

- 布建網路連結，以支援每秒 65 kb 的輸送量 (Kbps 500) 每個影片資料流程，如果已啟用，則會在尖峰時間內使用。 雙向音訊或影片會話會使用兩個數據流，所以簡單的音訊/電話連線將需要130Kbps 來涵蓋每個資料流程。 另外，影片也會使用 1000 Kbps，以傳送上游和下游連線。

- 為了處理流量中的意外峰值，以及隨著時間增加的使用量，商務用 Skype Server 媒體端點可以調整不同的網路狀況，並支援三倍的音訊和影片輸送量，但仍然維持可接受的品質。 請勿假設這種適應性會在網路已布建的情況下掩蓋問題。 在未布建的網路中，商務用 Skype Server 媒體端點可動態處理不同網路狀況的功能 (例如，暫時的高封包遺失) 已降低。

- 針對布建成本極高且困難的網路連結，您可能必須考慮為較低的流量量進行布建。 在此案例中，請讓商務用 Skype Server 媒體端點的彈性吸收流量量與流量峰值流量層級之間的差異，以降低語音品質的成本。 此外，預留空間也會減少，但仍可用於吸收流量突然的高峰。

- 對於無法在短期內正確布建的連結 (例如，使用極差的 WAN 連結的網站) ，請考慮針對特定使用者停用影片。

- 布建網路以保證最長的端對端延遲 (延隔時間) 150 毫秒 (毫秒) 低於峰值負載。 延遲是指商務用 Skype Server 媒體元件無法降低的網路障礙，所以尋找並消除薄弱點很重要。

- 若為執行防毒軟體的伺服器，請在例外狀況清單中包含執行商務用 Skype Server 的所有伺服器，以提供最佳效能及音訊品質。

## <a name="ipsec-exceptions"></a>IPsec 例外狀況

對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。

下表說明建議採用的 IPSec 例外設定。

**建議的 IPsec 例外**

|規則名稱 |來源 IP |目的地 IP |Protocol (通訊協定) |來源連接埠 |目的地連接埠 |驗證需求 |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V Edge Server (輸入的內部流量)|任何  |A/V Edge Server (內部流量)|UDP 和 TCP|任何 |任何 |不要驗證|
|A/V Edge Server (輸入的外部流量)|任何  |A/V Edge Server (外部流量)|UDP 和 TCP|任何 |任何 |不要驗證|
|A/V Edge Server (輸出的內部流量)|A/V Edge Server (內部流量)  |A/V Edge Server (外部流量) |UDP 和 TCP|任何 |任何 |不要驗證|
|A/V Edge Server (輸出的外部流量)|A/V Edge Server (外部流量) |任何 |UDP 和 TCP|任何 |任何 |不要驗證|
|中繼伺服器 (輸入流量)|任何  |轉送伺服器 (s)  |UDP 和 TCP|任何 |任何 |不要驗證|
|中繼伺服器 (輸出流量)|轉送伺服器 (s)   |任何|UDP 和 TCP|任何 |任何 |不要驗證|
|會議服務員 (輸入流量)|任何  |執行會議服務員的前端伺服器 |UDP 和 TCP|任何 |任何 |不要驗證|
|會議服務員 (輸出流量)|執行會議服務員的前端伺服器  |任何|UDP 和 TCP|任何 |任何 |不要驗證|
|A/V 會議 (輸入流量)|任何|前端伺服器|UDP 和 TCP|任何 |任何 |不要驗證|
|A/V 會議 (輸出流量)|前端伺服器|任何|UDP 和 TCP|任何 |任何 |不要驗證|
|Exchange (輸入流量)|任何|Exchange Unified Messaging|UDP 和 TCP|任何 |任何 |不要驗證|
|應用程式共用伺服器輸入|任何|應用程式共用伺服器|UDP 和 TCP|任何 |任何 |不要驗證|
|應用程式共用伺服器輸出|應用程式共用伺服器| 任何 |UDP 和 TCP|任何 |任何 |不要驗證|
|Exchange (輸出流量)|Exchange Unified Messaging|任何|UDP 和 TCP|任何 |任何 |不要驗證|
|用戶端| 任何  |任何|UDP 和 TCP|任何 |任何 |不要驗證|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>會議網路需求
<a name="Conf_req"> </a>

從 IIS) 伺服器 (的 Internet Information Services 下載會議內容所用的頻寬，取決於內容的大小。 您可以選擇監視實際使用狀況，並據此調整頻寬規劃。

## <a name="network-bandwidth-requirements-for-media-traffic"></a>媒體流量的網路頻寬需求
<a name="Conf_req"> </a>

網路規劃的重要部分是確保您的網路可以處理商務用 Skype Server 所產生的媒體流量。 本節將協助您規劃這類媒體流量。

### <a name="media-traffic-network-usage"></a>媒體流量網路使用量
<a name="Net_req"> </a>

由於不同變數 (例如轉碼器使用率、解析度和活動層級) 的數目，計算媒體流量頻寬使用率將是一項挑戰。 頻寬使用量是使用的編解碼器功能和 stream 的活動，其可能會隨案例而有所不同。 下表列出商務用 Skype Server 案例中一般使用的音訊編解碼器。

**音訊編解碼器頻寬**

|**音訊編解碼器**|**案例**|**音訊負載位元速率 (KBPS)**|**僅頻寬音訊承載和 IP 標頭 (Kbps)**|**頻寬音訊承載、IP 標頭、UDP、RTP 和 SRTP (Kbps)**|**頻寬音訊承載、IP 標頭、UDP、RTP、SRTP 和正向錯誤更正 (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio 寬頻  <br/> |對等  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio 窄頻  <br/> |對等 PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G. g.722  <br/> |會議  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 立體聲  <br/> |對等會議  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G. g.711  <br/> |PSTN、會議  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|警笛  <br/> |會議  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|絞絲寬頻  <br/> |對等  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|絞絲寬頻  <br/> |對等  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|絞絲寬頻  <br/> |對等  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|絞絲寬頻/窄頻  <br/> |對等  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> 來自商務用 Skype 用戶端的 PSTN 通話通常會使用 g.711 編解碼器，這需要高頻寬。 如果該編解碼器沒有足夠的頻寬可供使用，則通話會失敗，並顯示類似于媒體記錄檔中下列的錯誤： **必須啟用至少一個編解碼器，hr： c0042004**。 媒體記錄 () 加密，而且只能由 Microsoft 支援人員解碼。

上表中的頻寬數位是以20毫秒 packetization 為基礎，每秒)  (50 封包，而 Siren 和 G 編碼解碼器包含其他安全即時傳輸通訊協定 (SRTP) 來自會議案例的額外負荷，並假設資料流程是100% 的使用中。 轉寄錯誤修正 (FEC) 會在連結上的封包遺失時以動態方式使用，以協助維護音訊資料流程的品質。

G.722 編解碼器的立體版本是由以 Lync 會議室系統為基礎的系統所使用，它會使用單一立體麥克風或一對 mono 麥克風，讓監聽器能夠更好地區別會議室中的多個揚聲器。

**視訊解析度頻寬**

|**視訊轉碼器**|**解析度和外觀比例**|**最大影片負載位元速率 (Kbps)**|**最小影片負載位元速率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H-p  <br/> |320x180 (16:9)   <br/> 212x160 (4:3)   <br/> |250  <br/> |15   <br/> |
|上的 264/RTVideo  <br/> |424x240 (16:9)   <br/> 320x240 (4:3)   <br/> |350  <br/> |100  <br/> |
|H-p  <br/> |480x270 (16:9)   <br/> 424x320 (4:3)   <br/> |450  <br/> |200  <br/> |
|上的 264/RTVideo  <br/> |640x360 (16:9)   <br/> 640x480 (4:3)   <br/> |800  <br/> |300  <br/> |
|H-p  <br/> |848x480 (16:9)   <br/> |1500  <br/> |400  <br/> |
|H-p  <br/> |960x540 (16:9)   <br/> |2000  <br/> |500  <br/> |
|上的 264/RTVideo  <br/> |1280x720 (16:9)   <br/> |2500  <br/> |700  <br/> |
|H-p  <br/> |1920x1080 (16:9)   <br/> |4000  <br/> |1500  <br/> |
|上的 264/RTVideo  <br/> |960x144 (20:3)   <br/> |500  <br/> |15   <br/> |
|H-p  <br/> |1280x192 (20:3)   <br/> |1000  <br/> |250  <br/> |
|H-p  <br/> |1920x288 (20:3)   <br/> |2000  <br/> |500  <br/> |

影片的預設編解碼器是《 264/MPEG-4 第10部分先進的視頻編碼標準，以及其可擴充的影片編碼擴充的時態可伸縮性。 為了維護與舊版用戶端的互通性，RTVideo 編解碼器仍用於商務用 Skype Server 和舊版用戶端之間的對等通話。 在具有商務用 Skype Server 和舊版用戶端的會議會話中，商務用 Skype Server 端點可能會使用影片編碼解碼器來編碼影片，並傳送 bitstream 至商務用 Skype Server 用戶端和 RTVideo bitstream 至舊版用戶端。

需要的頻寬取決於解析度、品質、相框速率，以及圖片中的動作數量和變化量。 針對每個解決方法，有兩個相關的位元速率：

- **有效負載位元速率上限** 這是端點將用於解析度的位元速率，最大畫面播放速率。 這是允許最高影片和音質品質的值。

- **最小負載位元速率** 這是商務用 Skype Server 端點會切換到下一個較低解析度的位元速率。 為了保證特定的解決方式，可用的影片負載位元速率不得低於該解析度的最低位元速率。 這個值可協助您瞭解當最大位元速率不可用或不切實際時可能的最低值。 對某些使用者而言，低位元速率影片可能會提供無法接受的影片體驗，所以請謹慎使用這些最低的影片 bitrates。 請注意，針對靜態、變化的影片場景，實際的位元速率可能會暫時低於最小位元速率。

商務用 Skype Server 支援許多解決方案。 這可讓商務用 Skype Server 調整為不同的網路頻寬和接收用戶端功能。 商務用 Skype Server 的預設長寬比為16:9。 在網路攝像頭上仍支援舊版4:3 寬高比，但不允許在16:9 長寬比例內俘獲。

當使用影片時，影片 FEC 一定會包含在影片有效負載位元速率中，使影片 FEC 和不含影片 FEC 不會有不同的值。

端點不會持續對音訊或視訊封包進行資料流處理。依據不同的案例，有不同層級的資料流活動來指示為資料流傳送封包的頻率。資料流的活動依媒體和案例而定，而不是取決於使用的轉碼器。在對等案例中：

- 端點只會在使用者講話時傳送音訊資料流程。

- 這兩個參與者都會接收音訊資料流。

- 如果使用影片，這兩個端點都會在通話期間傳送和接收影片資料流程。

- 針對靜態影片場景，實際位元速率可能暫時很低，因為影片編解碼器會略過影片的編碼區域，而不會在先前的範例後進行變更。

在會議案例中：

- 端點只在使用者說話時傳送音訊資料流。

- 所有參與者都會接收音訊資料流。

- 如果使用視訊，所有參與者都能夠接收多達五個接收視訊資料流和一個全景 (例如，外觀比例 20:3) 視訊資料流。 根據預設，五個接收視訊資料流以目前發言者記錄為依據，但是使用者也可手動選取要接收視訊資料流的參與者。 如果啟用多個影片，則每個影片資料流程的解析度及頻寬需求都會較低。

- 每個開啟使用者傳送影片資料流程的參與者都會傳送一或多個影片資料流程。 商務用 Skype Server 能夠傳送最多五個影片資料流程，以優化所有接收用戶端的影片品質。 傳送的視訊資料流實際數目由傳送者依據 CPU 能力、可用上行連結頻寬和要求特定視訊串流的接收用戶端數目所決定。 最常見的情況是，舊版用戶端加入會議時，傳送一個 H.264 和一個 RTVideo 視訊資料流。 另一個常見的情況是，傳送多個 H.264 視訊資料流 (例如，不同視訊解析度的視訊資料流)，以配合不同的接收方要求。

除了音訊和視訊媒體的即時傳輸通訊協定 (RTP) 流量所需的頻寬，即時傳輸控制通訊協定 (RTCP) 也需要頻寬。 RTCP 用於報告統計資料和頻外控制 RTP 資料流。 為了規畫，將下表中的頻寬數字用於 RTCP 流量。 這些值代表用於 RTCP 的最大頻寬，而且因控制項資料差異而不同于音訊和影片資料流程。

**RTCP 頻寬**

|**媒體**|**RTCP 最大頻寬 (Kbps)**|
|:-----|:-----|
|音訊  <br/> |5  <br/> |
|視訊 (僅傳送/接收 H.264 或 RTVideo)  <br/> |10   <br/> |
|視訊 (傳送/接收 H.264 或 RTVideo)  <br/> |15   <br/> |

若要進行容量規劃，請注意下列兩個統計資料：

- **不含 FEC 的最大頻寬** Stream 會消耗的最大頻寬。 這包括資料流程的一般活動，以及在沒有 FEC 的情況下使用的一般編解碼器。 當資料流程為100% 活動時，此為頻寬，且沒有封包遺失觸發使用 FEC。 這可用於計算必須分配多少頻寬以允許在特定案例中使用編解碼器。 FEC 不應該是受管理網路上的需求。

- **使用 FEC 的最大頻寬** Stream 使用的最大頻寬。 這包括資料流程的一般活動，以及與 FEC 案例中使用的一般編解碼器。 當資料流程為100% 活動時，這就是頻寬，而且會發生封包遺失，觸發使用 FEC 以提升品質。 這可用於計算必須分配多少頻寬以允許在特定案例中使用編解碼器，以及允許使用 FEC，以在封包遺失的情況下保留品質。

下表還列出其他頻寬值 **一般頻寬**。 這是 stream 消耗的平均頻寬。 這包括資料流程的一般活動，以及案例中使用的一般編解碼器。 此頻寬可用於 polyline 特定時間的媒體流量所耗用的頻寬量，但不應用於容量規劃，因為當活動層級大於平均值時，個別呼叫會超出此值。 下表中的一般影片頻寬是根據衡量的客戶資料中所觀測的不同影片解析度混合而成，較小的安裝可能會有不同于資料表資料的實際數位。 例如，在點對點工作階段中，大部分使用者會使用預設的 [影片轉譯] 視窗，而某些部分的使用者會增加或最大化商務用 Skype Server 的應用程式，以允許更好的影片解析度。

下表提供各種案例的值。

**對等工作階段的音訊/視訊容量規劃**

|**媒體**|**轉碼器**|**一般資料流頻寬 (Kbps)**|**沒有 FEC 的最大資料流頻寬**|**具有 FEC 的最大資料流頻寬**|
|:-----|:-----|:-----|:-----|:-----|
|音訊  <br/> |RTAudio 寬頻  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|音訊  <br/> |RTAudio 窄頻  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|音訊  <br/> |絞絲寬頻  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|呼叫商務用 Skype Server 端點時的主要影片  <br/> |H-p  <br/> |460  <br/> |4010 (對於 1920x1080 的最大解析度)  <br/> |已包含  <br/> |
|呼叫 Lync 2010 或 Office Communicator 2007 R2 端點時的主要影片  <br/> |RTVideo  <br/> |460  <br/> |2510 (對於 1280x720 的最大解析度)  <br/> |已包含  <br/> |
|呼叫商務用 Skype Server 端點時的全景影片  <br/> |H-p  <br/> |190  <br/> |2010 (對於 1920x288 的最大解析度)  <br/> |已包含  <br/> |
|呼叫 Lync 2010 端點時的全景影片  <br/> |RTVideo  <br/> |190  <br/> |510 (對於 960x144 的最大解析度)  <br/> |已包含  <br/> |

**會議的音訊/視訊容量規劃**

|**媒體**|**一般轉碼器**|**一般資料流頻寬 (Kbps)**|**沒有 FEC 的最大資料流頻寬**|**具有 FEC 的最大資料流頻寬**|
|:-----|:-----|:-----|:-----|:-----|
|音訊  <br/> |G. g.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|音訊  <br/> |警笛  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|主要視訊接收  <br/> |上的264和 RTVideo ¹  <br/> |260  <br/> |8015  <br/> |無  <br/> |
|主要視訊傳送  <br/> |上的264和 RTVideo  <br/> |270  <br/> |8015  <br/> |無  <br/> |
|全景視訊接收  <br/> |上的264和 RTVideo  <br/> |190  <br/> |2010 (對於 1920x288 的最大解析度)  <br/> |無  <br/> |
|全景視訊傳送  <br/> |上的264和 RTVideo  <br/> |190  <br/> |2515²  <br/> |不適用  <br/> |

1. 當 Lync 2010 用戶端連線至會議時，除了-264 之外，還會傳送 RT 影片。

2. 如果有多個資料流程，它們會動態共用已分配的頻寬。

針對主要影片，一般的資料流程頻寬是透過所有接收的影片所積累的頻寬，而最大的資料流程是所有傳送影片資料流程的頻寬。 即使使用多個影片資料流程，一般的影片頻寬也比對等案例小，因為許多影片會議都使用內容共用來產生更小的影片視窗，因此可顯示較小的影片解析度。 受支援的匯總影片的最大值為 8000 Kbps （ (例如，如果有兩個傳入1920x1080p 影片資料流程) ，就會使用該傳送和接收資料流程）。 在實際的實施中，最大值只是很少看到。

當組建使用圖庫 view 功能的多方會議時，頻寬使用量會隨著參與者的加入而逐漸增加，然後在降低解析度以符合最大值時降低。

||**2參與者**|**3參與者**|**4參與者**|**5參與者**|**6位參與者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**收到的最大解析度** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**平均平均位元速率** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**最大位元速率總數** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

全景影片的一般資料流程頻寬是以僅資料流程為960x144 全景影片的裝置為基礎。 當使用具有1920x288 全景影片的裝置時，預計一般的資料流程頻寬會增加。

**PSTN 的音訊容量規劃**

|**媒體**|**一般轉碼器**|**一般資料流頻寬 (Kbps)**|**沒有 FEC 的最大資料流頻寬**|**具有 FEC 的最大資料流頻寬**|
|:-----|:-----|:-----|:-----|:-----|
|音訊  <br/> |G. g.711 (這包括會議中的 PSTN 參與者)   <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|音訊  <br/> |RTAudio 窄頻  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

這些表中的網路頻寬數字僅表示單向流量，包括每個資料流的 5 Kbps RTCP 流量負荷。

## <a name="managing-quality-of-service"></a>管理服務品質
<a name="man_QOS"> </a>

服務品質 (QoS) 是一種網路技術，可供一些組織用來協助為音訊和影片通訊提供最佳的使用者體驗。 QoS 最常用於頻寬有限的網路上：有大量的網路資料包會爭用極少量的可用頻寬，QoS 可讓系統管理員將更高優先順序指派給攜帶音訊或視頻資料的資料包。 透過提供這些封包的優先順序較高，音訊和影片通訊的速度可能會更快，且中斷較少，但會與涉及檔案傳輸、網頁流覽或資料庫備份等網路會話的情況少。 這是因為用於進行檔案傳輸或資料庫備份的網路封包是以「最大努力」優先順序指派。

> [!NOTE]
> 一般來說，QoS 只適用于內部網路上的通訊會話。 當您執行 QoS 時，您可以設定您的伺服器和路由器，以支援封包標記，其可能在網際網路或其他網路上可能不支援的特定方式。 即使其他網路支援服務品質，也無法保證 QoS 的設定方式與您設定服務的方式完全相同。 如果您使用 MPLS，您必須與 MPLS 提供者搭配運作。

商務用 Skype Server 不需要 QoS，但是強烈建議您這麼做。 如果您在網路上遇到封包遺失問題，您可用的解決方案就是增加更多頻寬或執行 QoS。 如果無法新增更多的頻寬，則實施 QoS 可能是您唯一可以解決問題的收費。

商務用 Skype Server 提供 QoS 的完整支援：這表示已使用 QoS 的組織可以輕鬆地將商務用 Skype Server 整合至現有的網路基礎結構。 若要這麼做，您必須遵循下列步驟：

- [為不是以 Windows 為基礎的裝置啟用商務用 Skype Server 中的 QoS](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，系統會停用電腦及其他裝置的 QoS，例如執行其他作業系統的 Iphone) 等 (。 雖然您可以使用商務用 Skype Server 來啟用及停用裝置的服務品質，但通常無法使用產品修改這些裝置所使用的 DSCP 碼。

- [針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須為不同的封包類型（如音訊和影片）預約一組獨特的埠。 使用商務用 Skype Server 您不需要將屬性值設定為 True 或 False 來啟用或停用 QoS。 相反地，您可以設定埠範圍，然後建立及套用群組原則來啟用 QoS。 如果您稍後決定不使用 QoS 可以移除適當的群組原則物件，以「停用」 QoS。

- 設定[Edge server 的埠範圍及服務品質原則](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md)。 您可以將 Edge server 設定成使用與其他伺服器相同的埠範圍，但這不是必要的。 僅對 Edge server 的內部端執行 QoS 原則的設定。 這是因為 QoS 是設計供內部網路使用，而不是在網際網路上使用。

- [在商務用 Skype Server 中為用戶端設定埠範圍和服務品質原則](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md)。 這些埠範圍只適用于用戶端電腦，通常與伺服器上設定的埠範圍不同。 請注意，商務用 Skype Server 不支援 Windows 10 以外的 Windows 作業系統 QoS。


> [!NOTE]
> 如果您使用 Windows Server 2012 或 Windows Server 2012 R2，您可能會對可用來在該平臺上管理 QoS 的一組新 Windows PowerShell Cmdlet 感興趣。 如需詳細資訊，請參閱[Windows PowerShell Cmdlet for 網路](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj717268(v=ws.11))。

您也會在使用 Lync Server 的詳細資訊與深度疑難排解的白皮書 [網路規劃、監控及疑難排解](https://www.microsoft.com/download/details.aspx?id=39084) 中討論 QoS。 雖然內容明確表示 lync 2010 和 Lync 2013，但商務用 Skype Server 的考慮不會改變。

## <a name="see-also"></a>另請參閱
<a name="man_QOS"> </a>

[規劃商務用 Skype 中的 IPv6](ipv6.md)

[商務用 Skype 的負載平衡需求](load-balancing.md)

[商務用 Skype Server 的 DNS 需求](dns.md)
