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
description: 直接路由通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 015b07f538ad33079bbe04649849d22bfebbfb081feb30cea154cb30f9f10fd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347169"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由 - 定義和 RFC 標準

本文將說明系統Microsoft 電話路由如何實現 RFC 標準通訊協定。 本文適用于負責在內部部署會話邊界控制器 (SBC) 與會話初始通訊協定 (SIP) Proxy 服務之間建立連接的語音系統管理員。

客戶 SBC 會與後端的下列Microsoft Teams介面： 

- **用於訊號的 SIP** Proxy。 這是直接路由的網際網路元件，可處理 SIP (TLS) SBCs 和直接路由之間的連接。

- **媒體的** 媒體處理器。 這是直接路由的網際網路元件，可處理媒體流量。 此元件使用 SRTP 和 SRTCP 通訊協定。


有關直接路由詳細資訊，請參閱電話系統[路由](direct-routing-landing-page.md)。

有關直接路由如何實現 SIP 通訊協定之詳細資訊，請參閱直接 [路由 - SIP 通訊協定](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 標準

直接路由符合 RFC 標準。  連結至直接路由的 SBC 也必須遵守下列 RFC (其後續) 。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>適用于支援非媒體旁路模式的裝置的標準 

下列標準適用于僅支援非媒體旁路模式的裝置：

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：會話初始通訊協定
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 受信任網路內已確認身分識別的會話初始通訊協定私人擴充功能-關於處理 P-確認-身分識別標頭的章節。 直接路由會傳送具有隱私權識別碼標頭的 P-Identity。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) SIP 的會話初始通訊協定 (擴展) 所需的歷程記錄資訊。 另請參閱：路由 SIP 通訊協定描述以瞭解更多資訊。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 會話初始通訊協定Referred-By機制
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP 中的會話初始 (") 取代」標頭 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 會話初始通訊 (SIP) 方案/Answer 模型的使用狀況。
  請參閱「RFC 的偏差」一節。
- [RFC 3711](https://tools.ietf.org/html/rfc3711) 和 [RFC 4771](https://tools.ietf.org/html/rfc4771)。 使用 SRTP 保護 RTP 流量。 SBC 必須能夠使用 SDES 建立金鑰。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) SDP 的會話描述通訊 (方案) RTP/RTCP 多工方案/解答說明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>適用于支援媒體旁路模式的裝置的標準

除了列為適用于非旁路模式的標準之外，媒體旁路模式也採用下列標準：

- [RFC 5245 互動式連接建立 (ICE) 媒體旁路。](https://tools.ietf.org/html/rfc5245)  SBC 必須支援下列專案：
  - ICE Lite - Teams是完整的 ICE 用戶端
  - [ICE 會重新開機](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 查看有關 ICE 重新開機使用案例和範例的更多資訊：媒體旁路通話轉接到不支援媒體旁路的端點   
- [RFC RFC 5589 會話初始通訊協定 (SIP) 呼叫控制 – 傳輸](https://tools.ietf.org/html/rfc5589)。 
- [在會話初始通訊協定 (SIP) 中，RFC 3960 ](https://tools.ietf.org/html/rfc3960)早期媒體和鈴聲產生，請參閱第 3.1 節、Forking 和 3.2 節 ，鈴聲產生 
- [RFC 5389 會話橫向公用程式適用于 NAT (STUN) ](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 在 NAT (TURN) 周圍使用轉接：將延伸模組轉用至 NAT (STUN) ](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>適用于支援將位置資訊傳達給 E911 提供者的標準

- [RFC 6442，會話初始通訊協定的位置傳輸](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>與 RFC 的偏差

下表列出 RFC 協定 (的) ，其中 Microsoft 的 SIP 或媒體堆疊的實現與標準有偏差：

| RFC 和節 | 描述 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，第 5.3 節媒體保留與履歷表](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 允許使用"a=非使用中"、"a=sendonly"、a=recvonly"來保留通話。 |SIP Proxy 僅支援「a=非使用中」，且不了解 SBC 是傳送「a=sendonly」或「a=revonly」。
| [RFC 6337，第 5.4 節「使用 c=0.0.0.0.0 接收 SDP 的行為](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理程式能夠接收連接位址為 0.0.0.0 的 SDP，在這種情況下，這表示不應將 RTP 或 RTCP 送往對等電腦。 | SIP Proxy 不支援此選項。 |

## <a name="operational-modes"></a>操作模式

直接路由有兩種操作模式：

- **沒有媒體旁** 路，所有 RTP 流量Teams用戶端、媒體處理器和 SBC 之間流動。  

- **當媒體旁** 路時，所有 RTP 媒體Teams端點和 SBC 之間流動。 

請注意，SIP 流量一直透過 SIP Proxy 流動。 

## <a name="dtmf"></a>Dtmf
媒體堆疊不支援帶內 DTMF。
