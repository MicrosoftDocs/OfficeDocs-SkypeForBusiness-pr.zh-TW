---
title: 在商務用 Skype Server 中規劃視頻 Interop 伺服器
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在規劃將商務用 Skype Server 與協力廠商電話會議裝置進行整合時，複查這個主題。
ms.openlocfilehash: 34afa051513ea2ebef60213fbc8c1a650bfec199
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749912"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃視頻 Interop 伺服器
 
**摘要：** 在規劃將商務用 Skype Server 與協力廠商電話會議裝置整合時，請複查這個主題。
  
商務用 Skype Server 現在可讓您與特定協力廠商 VTC (Video 電話會議 System) 方案進行整合。 新的伺服器角色可讓這種影片成為 VIS 互通性，這是一種影片 Interop 伺服器 () ，目前是以獨立伺服器角色的形式來執行，只供內部部署安裝使用。 VIS 是以協力廠商電話會議系統和商務用 Skype Server 部署為媒介。 在此版本中，VIS 著重于與 Cisco/Tandberg 影片系統的互通性。 請參閱這篇文章，以決定在商務用 Skype Server 安裝中是否使用此功能。
  
## <a name="device-interoperability"></a>裝置互通性

在 cisco 整合通訊管理員 (CallManager 或 CUCM) 版本10.5 和 TCP SIP 主幹設定 CUCM 與 VIS 之間測試及支援互通性。
  
目前支援的 VTCs 包括：
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  在這些系統上，需要 Cisco 軟體版本 tc 7.0.0 或以上版本，以便與商務用 Skype Server 整合，以如期運作。
  
## <a name="sip-trunks"></a>SIP 主幹

影片 Interop 伺服器的運作 SIP 主幹模式，VTCs 會繼續向現有的 Cisco 基礎結構註冊，例如，Cisco 通話管理員 (CUCM) 。 影片的 SIP 主幹會定義在 CUCM 和 VIS 之間，以便通話可以在兩個系統間路由傳送。 只支援從 VTC 到 VIS 的 SIP 主幹呼叫。 因此，VTCs 可以撥打與自動語音應答) 相關聯的電話號碼，但無法將其拖曳及放入會議中，可以撥打商務用 Skype 會議 (。
  
![SfB 中的 VIS 圖表。](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>功能

此伺服器角色提供：
  
- 協力廠商影片和商務用 Skype Server 部署所使用的 h-p 格式之間的轉換。
    
- 從 VTC 以指定解析度將單一影片資料流程轉換成多個不同解決方案的 simulcast 資料流程，以用於商務用 Skype Server 部署。 這些資料流程可以傳送至 AVMCU，然後商務用 Skype Server 端點和其他已要求不同解析度的視頻系統。 當協力廠商影片系統參與商務用 Skype A/V 電話會議時，也會使用此轉換。 在特定 VIS 伺服器中達到轉碼限制之後，任何針對不同解決方法的要求都只會接收最低解析度的資料流程。 
    
- 支援 CUCM 閘道和商務用 Skype Server video Interop 伺服器之間的影片 SIP 主幹;VTCs 繼續向 Cisco 閘道註冊，並透過閘道初始化對商務用 Skype 部署的呼叫。 呼叫是透過透過視頻 SIP 主幹傳送至商務用 Skype 的視頻 Interop 伺服器的閘道。
    
- 支援具有支援的影片的會議室中的使用者，以便從該系統撥號加入開啟或關閉的會議。 此呼叫會跨越影片 SIP 主幹。
    
- 支援具有支援的視頻系統的會議室中的使用者，可呼叫商務用 Skype 用戶端。 呼叫會遍歷 SIP 主幹。
    
- 支援從商務用 Skype Server 端或從支援的 VTC 系統進行 mid 通話控制，以實現點對點和 multipoint 通話（包括靜音/取消靜音音訊、暫停/繼續播放影片、鎖定影片及保留/取消通話）。
    
## <a name="known-limitations"></a>已知限制

此伺服器角色具有下列限制：
  
- 不支援透過 VTCs 部署到透過視頻 SIP 主幹的商務用 Skype 部署的新呼叫。 . 這表示只有商務用 Skype VTCs 中的新呼叫會透過影片 SIP 主幹進行支援。 支援的影片的目前狀態將無法透過影片 SIP 主幹 VIS。 
    
- 影片 SIP 主幹模式只支援獨立 VIS 集區。
    
-  TLS + SRTP 或 TCP + RTP 可支援 VTC 和 VIS 透過視頻 SIP 主幹之間的通訊。
    
- 不支援應用程式共用。 會議室中的商務用 Skype 使用者必須透過膝上型電腦加入商務用 Skype 會議 (例如) ，並在會議室的其中一個空閒監視器上顯示應用程式共用畫面，而不與 VTC 關聯。
    
- 不支援 VTC 透過 VIS 加入同盟會議的功能。
    
- 不支援 VTC 透過 VIS 加入線上會議的功能。
    
- 不支援透過 VIS 從 VTC 到 PSTN 的呼叫。
    
- 從 PSTN 到透過 VIS 的 VTC 的呼叫都不受支援。
    
## <a name="resiliency-mechanisms"></a>恢復機制
<a name="resiliency"> </a>

VIS 支援來自透過影片 SIP 主幹的 CUCM 傳入的呼叫。 可能會遺失上游或下游的連線，因此，可靠的復原會考慮這兩種可能性：
  
1. **VIS 集區容錯移轉** 如果影片閘道指向的主 VIS 集區已停機，當影片閘道已定義主幹至兩個 (或更多) VIS 集區時，可能會復原。 如果影片閘道決定它無法呼叫主要 VIS 集區，它只會將通話路由傳送至次要 VIS 集區。
    
     ![VIS 集區容錯移轉圖表。](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定的 VIS 集區可以有主幹多個閘道，但通常特定閘道不能有主幹至多個 VIS 集區，因此必須執行一項技巧，以支援此容錯移轉：在 DNS 中定義2個 FDQNs，以解析為一個視頻閘道的 IP 位址。 將每個 FQDN 都表示為拓撲檔中的個別影片閘道，其中每個影片閘道都具有不同 VIS 集區的主幹，而且現在可以進行復原。  (如果使用 TLS，多個名稱將需要位於視頻閘道憑證的 SAN 中。 ) 
    
    > [!NOTE]
    > VIS 只允許來自拓撲檔中設定之閘道上的來電。 
  
2. **前端容錯移轉** 如果 VIS 集區接收到來自 CUCM 的呼叫，但無法抵達其主要的下一個躍點註冊機構或前端集區，則會將通話路由傳送至備份前端集區。
    
     ![前端容錯移轉圖表。](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 將追蹤其主要前端集區和其備份前端集區的狀態 (此設定會在 [拓撲檔) 中的註冊機服務備份設定中找到。 這兩個集區的每一分鐘都會傳送一次選項，而且如果有五個連續的失敗，VIS 會認為特定前端集區已停機。 如果主要前端集區標示為 [停機]，且有可用的已設定備份，VIS 會將新呼叫從閘道傳送至備份前端集區。 當主要前端集區回到後，VIS 將會繼續使用主要前端集區進行新的呼叫。
    
    VIS 也會針對來自視頻 SIP 主幹的呼叫，執行10秒的計時器。 如果主要下一個躍點前端集區是用於來自視頻 SIP 主幹的呼叫，而且主要的下一個躍點前端集區並未以某些 SIP (郵件（包括100嘗試) 在此計時器值中傳送給它的情況下）進行應答，則應嘗試針對呼叫使用備份下一個躍點 proxy （如果已設定）。 
    
    > [!NOTE]
    > 如果先嘗試備份下一個躍點，將不會再嘗試一個主備份。 
  
    系統管理員也可以使用 Windows PowerShell 容錯移轉命令，強制 VIS 使用備份前端集區，例如，在主要前端集區上進行維護時。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>在相同的閘道對等中共存語音和影片主幹
<a name="resiliency"> </a>

商務用 Skype Server 支援讓語音和視頻 SIP 主幹使用相同的閘道對等。 因此，相同的 CUCM 部署可能會具有語音 SIP 主幹至轉送伺服器及視頻 SIP 主幹到 VIS。
  
- 在語音 SIP 主幹的拓撲檔中，必須使用特定的 FQDN 來定義 PSTN 閘道。
    
- 對等的 PSTN 閘道將會是轉送伺服器。
    
- 如有必要，可將多個 voice 主幹定義從 PSTN 閘道到多個轉送伺服器集區。
    
- 在與 PSTN 閘道具有相同 FQDN 的視頻 SIP 主幹的拓撲檔中，將需要定義影片閘道。
    
- 對等的視頻閘道將會是 VIS。
    
- 單一的影片主幹可以從影片閘道定義為特定 VIS 集區。
    
- CUCM 將需要設定為透過語音主幹和影片主幹正確路由通話。 例如，當您從 VTC 撥號時，可以使用特殊的撥號首碼;CUCM 可將此撥號首碼與 VIS 的呼叫關聯，而且適當的轉譯規則會將此前置詞從 SIP 邀請中去掉到 VIS。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>在商務用 Skype 隨舊版 Lync 發行的版本中共存 VIS
<a name="resiliency"> </a>

VIS 只可在商務用 Skype 部署中部署。 它可以與屬於現有部署一部分的 Lync 2013 會議和用戶端進行交互操作;在這種情況下，VIS 集區必須是商務用 Skype 部署的一部分，其中包含了 VIS 集區的下一個躍點的註冊系/FE 集區。
  
VIS 不支援 RTV 和 H-p 間的轉碼。 在會議中，Lync 2013 用戶端與 VTC 參與者之間沒有任何影片的互用性。
  
在會議中具有 Lync 2013 用戶端，將會造成行動用戶端使用 RTV 傳送，導致行動用戶端成為主要喇叭時，VTCs 不會收到任何影片。
  
為了讓 lync 2013 能夠搭配屬於商務用 Skype 部署的 VIS 正常運作，lync 2013 需要套用適當的 CU，以升級 Lync 2013 用戶端、CAA 和 AVMCU，以與 VIS 搭配使用。
  
VIS 與 Lync 2013 及商務用 Skype 桌面用戶端的互通性已經過測試，且受到支援。
  
VIS 與非桌面的互通性 (Android、Ipad、Iphone、Windows Phone、LMX 等 ) 商務用 Skype 發行時可從適用的應用程式存放區取得用戶端，都已經過測試且受支援。
  
## <a name="recovery-from-packet-loss-via-fec"></a>透過 FEC 恢復封包遺失
<a name="resiliency"> </a>

您可以開啟 FEC，以協助從封包遺失中復原。 開啟時50，VIS 會使用更多的影片頻寬以 VTC 方向。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 大小和轉碼成本
<a name="resiliency"> </a>

將 Cisco VTC 中的單一影片資料流程轉換成多個 simulcast 資料流程使用 CPU 容量。 大約 16 VTCs 可以有其影片 transcoded (假設每個 VTC 的720p 影片資料流程會 transcoded 成3個不同的 simulcast 資料流程，在720p、360p 和 180p) 中，在建議的中文平臺2013上執行的單一 VIS 中。 如果將轉碼關閉，這將會儲存在 VIS CPU 上。 不過，VIS 從 VTC 所要求的影片影像將是在商務用 Skype 端滿足所有接收器的最低一般解析度。 請注意，即使是關閉轉碼，當商務用 Skype 用戶端要求某些 VTCs 無法傳送的低解析度時，可能會啟用轉碼。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>從影片閘道到 VIS 的呼叫分配
<a name="resiliency"> </a>

分配是透過其中一個 CUCM 發佈機制來完成：
  
- 使用 DNS 動態地使用。
    
- 在 CUCM 端，您可以定義個別的主幹，其中每個主幹會在 VIS 集區中的不同伺服器上終止。 CUCM 會將通話路由傳送到不同的主幹。
    
## <a name="no-hybrid-interoperability"></a>無混合互通性
<a name="resiliency"> </a>

VTCs 透過內部部署 VIS 加入線上會議的支援不屬於商務用 Skype。
  
## <a name="no-federation-support"></a>無同盟支援
<a name="resiliency"> </a>

VTCs 透過 VIS 加入同盟會議的支援不屬於商務用 Skype。
  
## <a name="see-also"></a>另請參閱
<a name="resiliency"> </a>

[在商務用 Skype Server 中部署視頻 Interop 伺服器](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
