---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835023"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由定義與 RFC 標準

本文說明 Microsoft 手機系統直通路由如何實現 RFC 標準通訊協定。 本文適用于負責設定內部部署會話邊界控制器（SBC）與會話初始通訊協定（SIP） proxy 服務之間的連線的語音系統管理員。

客戶 SBC 介面與 Microsoft 團隊後端的下列元件： 

- 用於發信號的**SIP proxy** 。 這是直接路由的網際網路式元件，可在 SBCs 與直接路由之間處理 SIP （TLS）連線。

- 媒體**的媒體處理器**。 這是用來處理媒體流量之直接路由的網際網路式元件。 此元件使用 SRTP 和 SRTCP 通訊協定。


如需直接路由的詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。

如需直接路由如何實現 SIP 通訊協定的詳細資訊，請參閱[直接路由 SIP 通訊協定](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 標準

直接路由符合 RFC 標準。  連接至直接路由的 SBC 也必須符合下列 Rfc （或其後續任務）。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>適用于支援非媒體旁路模式之裝置的標準 

下列標準適用于僅支援非媒體旁路模式的裝置：

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：會話初始通訊協定
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 在受信任的網路中，針對斷言身分識別的會話初始通訊協定的專用延伸-有關處理 P 斷言身分識別標頭的章節。 直接路由會傳送 P 斷言身分識別與隱私權 ID 標頭。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)針對所需歷程記錄資訊的會話初始通訊協定（SIP）延伸。 另請參閱：路由 SIP 通訊協定描述以取得詳細資訊。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)會話初始通訊協定（依機構所參照）
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)會話初始通訊協定（SIP）「取代」標頭 
- [RFC 6337](https://tools.ietf.org/html/rfc6337)優惠/答案模型的會話初始通訊協定（SIP）使用量。
  請參閱「RFC 差異」一節。
- [Rfc 3711](https://tools.ietf.org/html/rfc3711)與[rfc 4771](https://tools.ietf.org/html/rfc4771)。 使用 SRTP 保護 RTP 流量。 SBC 必須能夠使用 SDES 建立金鑰。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)RTP/RTCP 複用的會話描述通訊協定（SDP）提供/答案說明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>適用于支援媒體旁路模式之裝置的標準

除了列為非旁路模式使用的標準之外，下列標準適用于媒體旁路模式：

- [針對媒體旁路的 RFC 5245 互動式連接建立（ICE）](https://tools.ietf.org/html/rfc5245)。  SBC 必須支援下列各項：
  - 冰 Lite-團隊用戶端是完全 ICE 用戶端
  - [ICE 重新開機](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 在 ICE 重新開機時，請參閱使用案例與範例的詳細資訊：媒體旁路來電轉接到不支援媒體旁路的端點   
- [RFC rfc 5589 會話初始通訊協定（SIP）通話控制–轉移](https://tools.ietf.org/html/rfc5589)。 
- [RFC 3960 在會話初始通訊協定（SIP）中，以早期媒體與鈴聲產生的方式](https://tools.ietf.org/html/rfc3960)，請參閱3.1、分叉與3.2 區段，以及撥打音調產生的章節 
- [適用于 NAT 的 RFC 5389 會話遍歷公用程式（STUN）](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 使用 NAT 的中繼進行遍歷（TURN）：將延伸移至 NAT 的會話遍歷公用程式（STUN）](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>可支援將位置資訊傳達給 E911 提供者的標準

- [RFC 6442，會話初始通訊協定的位置 Conveyance](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC 的差異

下表列出 Microsoft 在其中的 SIP 或媒體堆疊實現與標準偏離的 RFC 區段：

| RFC 和章節 | 說明 | 差異 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，區段5.3 保留並繼續媒體](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 可讓您使用 "a = 不活躍"，"a = sendonly"，a = recvonly "保留通話。 |SIP proxy 只支援 "a = 非使用中"，而且不了解 SBC 是傳送 "a = sendonly" 或 "a = recvonly"。
| [在使用 c = 0.0.0.0 接收 SDP 時的 RFC 6337，區段5.4」行為](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264)要求工程師能夠接收連接位址為0.0.0.0 的 SDP，在這種情況下，這表示 RTP 和 RTCP 都不應傳送給對等。 | SIP proxy 不支援此選項。 |

## <a name="operational-modes"></a>操作模式

直接路由有兩種操作模式：

- 在團隊用戶端、媒體處理器與 SBC 之間流動時，**不需要媒體旁路**。  

- 在**媒體旁路**中，所有的 RTP 媒體都在團隊端點與 SBC 之間流動。 

請注意，SIP 流量永遠流經 SIP proxy。   
