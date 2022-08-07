---
title: Teams 手機系統直接路由：定義和 RFC 標準
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Phone System Direct Routing 如何實作 RFC 標準通訊協定。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271238"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由 - 定義和 RFC 標準

本文說明 Microsoft Phone System Direct Routing 如何實作 RFC 標準通訊協定。 本文適用于負責設定內部部署會話框線控制器 (SBC) 與 SIP) Proxy 服務 (會話初始通訊協定之間的連線的語音系統管理員。

Microsoft Teams 後端中包含下列元件的客戶 SBC 介面： 

- 訊號的 **SIP Proxy**。 這是直接路由的網際網路元件，可處理 SIP (TLS，) SB 和直接路由之間的連線。

- **媒體的媒體處理器** 。 這是處理媒體流量之直接路由的網際網路元件。 此元件使用 SRTP 和 SRTCP 通訊協定。


如需直接路由的詳細資訊，請參閱 [電話系統直接路由](direct-routing-landing-page.md)。

如需直接路由如何實作 SIP 通訊協定的詳細資訊，請參閱 [直接路由 - SIP 通訊協定](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 標準

直接路由符合 RFC 標準。  連線至直接路由的 SBC 也必須遵守下列 RFC (或其後續) 。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>適用于支援非媒體略過模式之裝置的標準 

下列標準適用于僅支援非媒體略過模式的裝置：

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：會話初始通訊協定
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 在信任的網路內針對已驗證身分識別的會話初始通訊協定專用的專用擴充功能 --關於處理 P-名片識別標頭的章節。 直接路由會傳送具有隱私權識別碼標頭的 P-維護身分識別。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 會話初始通訊協定的擴充功能 (SIP) 必要歷程記錄資訊。 另請參閱：路由 SIP 通訊協定描述以取得詳細資訊。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 會話初始通訊協定Referred-By機制
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP (會話初始通訊協定) 「取代」標頭 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 會話初始通訊協定 (SIP) 優惠/Answer 模型的使用方式。
  See the “Deviations from RFC” section.
- [RFC 3711](https://tools.ietf.org/html/rfc3711) 和 [RFC 4771](https://tools.ietf.org/html/rfc4771)。 使用 SRTP 保護 RTP 流量。 SBC 必須能夠使用 SDES 建立金鑰。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 會話描述通訊協定 (SDP) RTP/RTCP Multiplexing 的優惠/解答說明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>適用于支援媒體略過模式之裝置的標準

除了列出適用于非略過模式的標準之外，下列標準也適用于媒體略過模式：

- [RFC 5245 互動式連線因媒體略過而 (ICE) ](https://tools.ietf.org/html/rfc5245)。  SBC 必須支援下列專案：
  - ICE Lite - Teams 用戶端是完整的 ICE 用戶端
  - [ICE 隨即重新開機](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 如需更多有關 ICE 重新開機使用案例的詳細資訊，請參閱 ICE 重新開機中的案例和範例：媒體略過來電轉接至不支援媒體略過的端點   
- [RFC RFC 5589 會話初始通訊協定 (SIP) 通話控制 – 傳輸](https://tools.ietf.org/html/rfc5589)。 
- [SIP)  (會話初始通訊協定中的 RFC 3960 早期媒體和 ](https://tools.ietf.org/html/rfc3960)鈴聲產生音調，請參閱 3.1、Forking 和 3.2 節的鈴聲產生 
- [RFC 5389 SESSION Traversal Utilities for NAT (STUN) ](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 在 NAT 周圍使用轉送功能 (轉) ：將擴充功能轉送到 NAT (STUN) ](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>適用于支援向 E911 提供者傳達位置資訊的標準

- [RFC 6442，會話初始通訊協定的位置傳輸](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>與 RFC 的偏差

下表列出 RFC () 區段，其中 Microsoft 的 SIP 或媒體堆疊實作與標準不同：

| RFC 和節 | 描述 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，區段 5.3 保留和繼續媒體](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 允許使用 「a=inactive」， 「a=sendonly」， a=recvonly「 來保留通話。 |SIP Proxy 僅支援 「a=inactive」，且不了解 SBC 是否傳送 「a=sendonly」 或 「a=recvonly」。
| [RFC 6337，區段 5.4「使用 c=0.0.0.0 接收 SDP 時的行為](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理程式能夠接收連線位址為 0.0.0.0 的 SDP，在這種情況下，這表示不應將 RTP 或 RTCP 傳送給同儕。 | SIP Proxy 不支援此選項。 |

## <a name="operational-modes"></a>操作模式

直接路由有兩種操作模式：

- **不需要媒體略過** ，所有 RTP 流量會流經 Teams 用戶端、媒體處理器和 SBC。  

- **在媒體略過** 時，所有 RTP 媒體會在 Teams 端點和 SBC 之間延伸。 

請注意，SIP 流量一律會透過 SIP Proxy 流經。 

## <a name="dtmf"></a>Dtmf
媒體堆疊不支援頻內 DTMF。
