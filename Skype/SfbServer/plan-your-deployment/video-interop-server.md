---
title: 在商務用 Skype Server 中規劃影片互通性伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在規劃將商務用 Skype 伺服器與協力廠商 teleconferencing 裝置進行整合時，請複習本主題。
ms.openlocfilehash: af7618efa0b5f13419be216b37a4f1e7d4065e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815561"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃影片互通性伺服器
 
**摘要：** 在規劃將商務用 Skype 伺服器與協力廠商 teleconferencing 裝置進行整合時，請複習本主題。
  
商務用 Skype Server 現可讓您與特定的協力廠商 VTC （Video Teleconferencing 系統）解決方案整合。 啟用此視訊會議互通性的新伺服器角色是影片互通性伺服器（VIS），目前是以獨立伺服器角色的方式實現，只有內部部署安裝才能使用。 VIS 充當協力廠商電話會議系統和商務用 Skype Server 部署之間的媒介。 在這個版本中，VIS 的重點是使用 Cisco/Tandberg 視頻系統進行互通性。 請參閱這篇文章，以判斷是否要在商務用 Skype Server 安裝中使用這項功能。
  
## <a name="device-interoperability"></a>裝置互通性

在使用 cisco 整合通訊管理員（CallManager 或 CUCM）版本10.5 和 TCP SIP trunks 在 CUCM 和 VIS 之間進行 VTCs 註冊，即可測試並支援互通性。
  
目前支援的 VTCs 為：
  
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
>  在這些系統上需要 Cisco 軟體發行 TC 7.0.0 或更新版本，以便與商務用 Skype 伺服器整合，以如期運作。
  
## <a name="sip-trunks"></a>SIP trunks

影片交互操作伺服器在 SIP 幹線模式中起作用，VTCs 會繼續向現有的 Cisco 基礎結構註冊，例如 Cisco 通話管理員（CUCM）。 在 CUCM 和 VIS 之間定義了一個影片 SIP 主幹，讓通話可以在兩個系統間路由。 僅支援透過 SIP 主幹從 VTC 到 VIS 的呼叫。 因此，VTCs 可以撥入商務用 Skype 會議（透過撥打與來電自動助理相關的電話號碼），但無法將其拖曳並放入會議中。
  
![SfB 中的 VIS 圖表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Features

此伺服器角色提供：
  
- 協力廠商視頻系統和商務用 Skype Server 部署所使用的 .H 格式之間的轉換。
    
- 從 VTC 以給定解析度將單一視頻資料流程轉換成多個不同解析度的 simulcast 資料流程，以便在商務用 Skype Server 部署中使用。 這些資料流程可以傳送到 AVMCU，然後傳送到商務用 Skype Server 端點及其他已要求不同解析度的視頻系統。 在商務用 Skype A/V 電話會議中參與協力廠商影片系統時，也會使用這項轉換。 在特定的 VIS 伺服器中達到轉碼限制之後，針對不同解析度的任何下列要求將只會接收最低解析度的資料流程。 
    
- 支援 CUCM 閘道與商務用 Skype Server 視頻交互操作伺服器之間的視頻 SIP 幹線;VTCs [繼續使用 Cisco 閘道註冊]，然後透過閘道啟動對商務用 Skype 部署的呼叫。 通話是透過視頻 SIP 主幹從閘道傳送到商務用 Skype 的視頻交互操作伺服器。
    
- 支援會議室中的使用者，以及支援的影片系統，可從該系統撥打電話給開啟或關閉的會議。 此呼叫將遍歷 [視頻 SIP 主幹]。
    
- 支援在會議室中使用支援的視頻系統呼叫商務用 Skype 用戶端的使用者。 通話會遍歷 SIP 主幹。
    
- 支援從商務用 Skype 伺服器端或從支援的 VTC 系統，到兩個點對點和 multipoint 通話，包括將音訊靜音/取消靜音、暫停/繼續播放影片、鎖定影片，以及按住/取消暫留通話。
    
## <a name="known-limitations"></a>已知限制

此伺服器角色具有下列限制：
  
- 不支援透過視頻 SIP 幹線，從商務用 Skype 部署到 VTCs 的新通話。 . 這表示只有從 VTCs 到商務用 Skype 部署的新呼叫受到支援，才能透過視頻 SIP 主幹進行。 支援的視頻系統的目前狀態將無法在視頻 SIP 主幹上提供給 VIS。 
    
- 只有獨立的 VIS 池才支援視頻 SIP 幹線模式。
    
-  TLS + SRTP 或 TCP + RTP 將支援在 VTC 與 VIS 之間的通訊，以進行視頻 SIP 幹線。
    
- 不支援應用程式共用。 會議室中的商務用 Skype 使用者需要加入商務用 Skype 會議（例如透過膝上型電腦），並在會議室中的其中一個免費顯示器上顯示應用程式共用畫面，而不與 VTC 相關聯。
    
- VTC 透過 VIS 加入同盟會議的能力不受支援。
    
- VTC 透過 VIS 加入線上會議的功能不受支援。
    
- 不支援透過 VIS 從 VTC 到 PSTN 的呼叫。
    
- 不支援從 PSTN 至 VTC via VIS 的呼叫。
    
## <a name="resiliency-mechanisms"></a>復原機制
<a name="resiliency"> </a>

VIS 支援來自透過視頻 SIP 幹線傳送的 CUCM 中的來電。 可能會失去上游或下游的連線，因此為了提供強健的復原，請考慮兩種可能性：
  
1. **VIS 池容錯移轉**如果視頻閘道所指向的主 VIS 池已關閉，則可以在視頻閘道已定義 trunks 至兩個（或更多） VIS 池的情況下進行恢復。 如果視頻閘道判斷它無法呼叫主要 VIS 池，只需將呼叫路由到副 VIS pool。
    
     ![VIS 池容錯移轉的圖表](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定的 VIS 池可以將 trunks 設為多個閘道，但通常特定閘道不能 trunks 至多個 VIS 池，所以需要完成一項動作，才能支援此容錯移轉：在 DNS 中定義2個 FDQNs，解析為與視頻閘道相同的 IP 位址。 在拓撲檔中，將每個 FQDN 表示為一個獨立的視頻閘道，其中每個視頻閘道都有一個不同 VIS 池的主幹，而且現在可以進行恢復。 （如果使用 TLS，多個名稱將必須位於視頻閘道憑證的 SAN 中。）
    
    > [!NOTE]
    > VIS 只允許在拓撲檔中設定的閘道撥入來電。 
  
2. **前端容錯移轉**如果 VIS 池收到來自 CUCM 的呼叫，但無法到達其主要的下一中繼站註冊機構或前端池，則會將呼叫路由至備份前端池。
    
     ![前端容錯移轉的圖表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 將會追蹤其主要前端池與其備份前端池的狀態（在 [拓撲] 檔中，在 [註冊機構服務] 的 [備份] 設定中找到此設定）。 它會將選項輪詢一分鐘傳送一次到兩個池，而且如果有五個連續失敗，VIS 會假設某個特定的前端池已關閉。 如果主要前端池已標示為 down，且有可用的已設定備份，VIS 會將來自閘道的新呼叫傳送至備份前端池。 主前端池回到之後，VIS 將會繼續使用主要前端池來進行新的呼叫。
    
    VIS 也會針對來自視頻 SIP 幹線的呼叫執行10秒計時器。 如果主要的下一中繼站前臺端池是用來進行來自視頻 SIP 幹線的呼叫，而主要的下一個躍點前端池卻沒有回應在這個計時器值中傳送給它的邀請函（包括100嘗試），則是呼叫 s 的備份下一個躍點 proxy。如果已設定，請嘗試 hould。 
    
    > [!NOTE]
    > 如果先嘗試使用 [備份] 下一個躍點，則不會在下一次嘗試此程式。 
  
    系統管理員也可以使用 Windows PowerShell 容錯移轉命令，強制 VIS 使用備份前端池（例如，必須在主要前端池中執行維護）。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>在同一個閘道對等中存在語音與視頻 Trunks 的共存
<a name="resiliency"> </a>

商務用 Skype 伺服器支援讓語音及視頻 SIP trunks 使用相同的閘道對等。 因此，相同的 CUCM 部署可能會有語音 SIP trunks 到中繼伺服器與視頻 SIP trunks 至 VIS。
  
- PSTN 閘道必須在 [語音 SIP trunks] 的 [拓撲] 檔中使用特定的 FQDN 加以定義。
    
- 對等的 PSTN 閘道將是轉送伺服器。
    
- 如有需要，可將多個語音 trunks 定義從 PSTN 閘道到多個轉送伺服器池。
    
- 您必須在視頻 SIP 幹線的 [拓撲] 檔中，使用與 PSTN 閘道相同的 FQDN 來定義視頻閘道。
    
- 對等的視頻閘道將會 VIS。
    
- 您可以從視頻閘道定義單一的視頻幹線至特定的 VIS 池。
    
- CUCM 將需要設定為正確路由來自語音幹線與視頻幹線的通話。 例如，從 VTC 撥號時，可以使用特殊的撥號首碼;CUCM 可能會將這個撥號前置詞與 VIS 的呼叫關聯，而適當的翻譯規則會將此前置詞從 SIP 邀請中去除至 VIS。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>在商務用 Skype 發行中與舊版 Lync VIS 中共存
<a name="resiliency"> </a>

VIS 只能在商務用 Skype 部署中部署。 它可以與屬於現有部署的 Lync 2013 會議與用戶端進行互動;在這些情況下，VIS 池必須是商務用 Skype 部署的一部分，其中包含的註冊機構/FE 池是 VIS 池的下一躍點。
  
VIS 不支援 RTV 與 .H 之間的轉碼。 在會議中，Lync 2013 用戶端與 VTC 參與者之間沒有任何視頻互通性。
  
在會議中擁有 Lync 2013 用戶端，將會導致行動用戶端使用 RTV 傳送，當行動用戶端變成主要喇叭時，就會收到沒有影片的 VTCs。
  
為了讓 Lync 2013 能正確搭配商務用 Skype 部署中的 VIS 正常運作，Lync 2013 需要套用適當的 CU 來升級 Lync 2013 用戶端、CAA 和 AVMCU，才能與 VIS 搭配使用。
  
VIS 與 Lync 2013 和商務用 Skype 桌面用戶端的互通性已經過測試且受到支援。
  
VIS 與非桌面（Android、Ipad、Iphone、Windows Phone、LMX 等）的互通性。VIS 發行時，適用的應用程式商店提供的商務用 Skype 用戶端已經過測試且受到支援。
  
## <a name="recovery-from-packet-loss-via-fec"></a>透過 FEC 從資料包遺失中復原
<a name="resiliency"> </a>

FEC 可以開啟，以協助從資料包遺失中復原。 如果開啟50，將會在 VIS 中使用更多的影片頻寬，以 VTC 方向。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 調整大小與轉碼成本
<a name="resiliency"> </a>

將 Cisco VTC 中的單一視頻資料流程轉換成多個 simulcast 資料流程使用 CPU 容量。 大約 16 VTCs 可以有其影片 irandomaccessstream （假設每個 VTC 的720p 影片串流都 irandomaccessstream 成3個獨立的 simulcast 資料流程，在720p、360p 和180p）的單一 VIS 中，以 Lync 2013 建議的 FE 平臺執行。 如果 [轉碼] 是關閉的，這將會儲存在 VIS 的 CPU 上。 不過，VIS 從 VTC 要求的影片影像會是最低的一般解析度，以符合商務用 Skype 端的所有接收器。 請注意，即使是關閉轉碼，在商務用 Skype 用戶端要求 VTCs 無法傳送的特定低解析度時，也可能會啟用轉碼。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>從 [視頻] 閘道呼叫配送至 VIS
<a name="resiliency"> </a>

您可以透過下列其中一個 CUCM 傳播機制來完成分配：
  
- 動態使用 DNS。
    
- 在 CUCM 端，您可以定義個別的 trunks，其中每個幹線都會在 VIS 池中的不同伺服器上終止。 CUCM 會在不同的 trunks 中傳送呼叫路線。
    
## <a name="no-hybrid-interoperability"></a>無混合式互通性
<a name="resiliency"> </a>

VTCs 透過內部部署 VIS 加入線上會議的支援不是商務用 Skype 的一部分。
  
## <a name="no-federation-support"></a>無同盟支援
<a name="resiliency"> </a>

VTCs 透過 VIS 加入同盟會議的支援不是商務用 Skype 的一部分。
  
## <a name="see-also"></a>另請參閱
<a name="resiliency"> </a>

[在商務用 Skype Server 中部署視頻交互操作伺服器](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
