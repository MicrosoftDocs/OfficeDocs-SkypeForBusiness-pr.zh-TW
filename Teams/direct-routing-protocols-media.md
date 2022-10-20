---
title: 電話系統直接路由概觀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw 直接路由支援已啟用 ICE Lite 的會話框線控制器的媒體略過。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f9715ee410116a66c572522a910cd16ef27154
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614416"
---
# <a name="overview"></a>概觀

本文說明直接路由如何支援使用會話框線控制器略過媒體 (SBC) 啟用 ICE Lite，如 [RFC 5245](https://tools.ietf.org/html/rfc5245)中所述。 本文適用于負責設定內部部署 SBC 與 SIP Proxy 服務之間連線的語音系統管理員。

本文提供 ICE 精簡版案例的概觀，以及互通性的需求。 本文將說明訊息格式和必要的狀態機器轉換，以確保可靠的通話和媒體流程。

## <a name="terminology"></a>術語

- First Hello – 來電者和來電者說出的第一個字。 請務必全力確保端點的第一個封包在大多數使用案例中都能可靠地傳遞。

- 手寫筆跡 – 舉例來說，如果來電者可在多個裝置上使用，則來電者提供的優惠可能會傳送到多個來電者端點 (例如，Teams 使用者可能已登入 Windows 版 Teams 以及 Android 版或 iPhone 版 Teams) 。

- 定義答案 (183) – 快速通話設定的來電端點會傳送具有建立媒體流程所需的候選字和按鍵的答案。 這會在使用者可能接聽該特定來電實例 (200OK) 接聽來電時完成。 使用手寫筆跡時，來電者應該可以接聽多個解答。

- Re-Invite – 提供由 ICE 控制端點選取的最終候選字。 這將具有 a=remote-candidate 屬性，以解決處理多個墨水的任何競賽條件。

- Teams 端點 - 這可能是伺服器 (媒體處理器、傳輸轉送) 或 Teams 用戶端。

## <a name="message-format"></a>郵件格式

Teams 基礎結構遵循 RFC 5245 for ICE-Lite。 這表示所有 STUN 訊息都符合 [RFC 5389](https://tools.ietf.org/html/rfc5389)。

RFC 5389 要求的 SBC 必須忽略他們無法辨識的任何 STUN 屬性，並繼續使用已知屬性處理郵件。 

如果收到任何惡意的封包，則必須捨棄封包，而不會影響媒體會話。

## <a name="ice-lite-requirements"></a>ICE 精簡版需求

本節簡要擷取 ICE Lite 的需求。

### <a name="candidate-gathering"></a>候選人聚會

SBC 只能提供一個候選項目。 目前僅支援 IPV4 候選字。


#### <a name="connectivity-checks"></a>連線檢查

ICE Lite 實作必須回應收到的任何連線檢查。 ICE Lite 端點不能傳送任何連線檢查要求。  (如果違反連線能力檢查傳送，則完整實作會回應，這可能會導致發現非預期的對等衍生候選字，並可能導致通話失敗。) 

#### <a name="nominations"></a>提名

ICE 完整實作端點一律會是控制端點，並遵循「一般」程式，選取要用於媒體流程的最終候選字。 ICE 精簡版端點可以使用定位來結束要用於媒體和完整通話的路徑。

注意：如果使用對等端點傳送 183 個解答的筆跡功能，SBC 必須準備好回應多個端點的檢查，如果在 200OK 之前發生傳送摘要資訊，則必須從多個端點進行摘要處理。 根據 ICE 狀態電腦在使用者解答最終路徑和時間上的合併，結果可能會發生在 200OK 之前或之後。 SBC 必須能夠處理這兩個案例。

#### <a name="converging-for-forking"></a>集中換換筆跡

如果從 SBC forks 到多個 Teams 端點的優惠，Teams 端點可能會以快速解答來回應，並開始連線檢查。 SBC 必須準備好接收連線檢查，並從多個對等端點回應連線檢查。 例如，Teams 使用者可以同時登入桌面和行動電話。 這兩個裝置都會收到輸入通話的通知，並嘗試使用 SBC 進行連線檢查。

最後只有其中一個端點會 (200OK) 接聽來電。 在收到 200OK 時，SBC 可以設定處理媒體封包的正確內容。

## <a name="scenarios"></a>案例

###  <a name="inbound-call-from-sbc"></a>來自 SBC 的撥入通話

針對此案例，SBC 必須處理幾個可能的對等端點：

- 伺服器端點通常會以 200OK 直接回應。 這些是完整的 ICE 端點，通常包含在語音信箱、通話佇列和自動語音應答案例中。

- 用戶端點可以傳送多個不同寄件者/收件者標籤的解答 (183) 後接接來電端點的 200OK。 這些是完整的 ICE 端點，通常代表使用者用戶端。

- 其他 SBC 端點。 這些是 ICE Lite 端點，通常包含在同時響鈴用戶端端點和另一個電話號碼 () 的情況下。

SBC 必須回應所有從完整 ICE 端點收到的有效連線檢查要求。 根據 RFC，完整的 ICE 端點會變成控制端點。 Teams (用戶端/伺服器) 端點會執行「一般」傳送，以完成連線檢查。 最後的 200Ok 可以是從傳送早期媒體的端點，也可以從不同的端點。 在收到 200Ok 時，SBC 必須為媒體流程設定正確的內容。 

###  <a name="early-media"></a>早期媒體

如果有早期的媒體流程，SBC 必須與啟動串流媒體的第一個端點不符;媒體流程可以在候選字進入候選字之前開始。 SBC 應該支援在此階段期間傳送 DTMF，以啟用 IVR/語音信箱案例。 SBC 應該使用最高優先順序路徑，如果尚未完成檢查，SBC 會收到檢查。

### <a name="outbound-call-to-sbc"></a>SBC 的撥出通話

Teams 端點是此案例的呼叫者，且會是控制端點。 在收到正式答案 (183) 或最終答案 (200OK) 時，Teams 端點將會開始連線檢查，並繼續進行「一般」附加專案以完成連線檢查。

注意：如果 SBC 在 183)  (傳送解答，則 SBC 必須準備好接收連線檢查要求，並有可能在 SBC 傳送 200OK 之前完成確認。 如果在收到 200OK 之前已完成檢查和/或修訂，則在收到 200OK 之後，將不會再次執行檢查和/或修訂。 SBC 不得變更 ICE 候選字、密碼和 ufrag (183 到 200 之間的使用者名稱片段) 。

若要支援早期媒體，SBC 可能會開始串流媒體至對等 ICE 候選字，並根據收到的連線檢查獲得最高優先順序，甚至在 Teams 端點完成簡報之前。 SBC 應該會預期任何候選字上的 Teams 媒體，直到完成簡報為止。 候選字通過後，SBC 必須重設為正確的內容，才能傳送和接收媒體封包。

## <a name="srtp-support-requirements"></a>SRTP 支援需求

SBC 必須支援 SRTP 加密密碼AES_CM_128_HMAC_SHA1_80，以提供並以下列格式回答：

```console
"inline:" <key||salt> ["|" lifetime]
```

以下是 SBC SDP 優惠中的加密屬性範例：

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

不需要 MKI 和 Length 參數。

如需詳細資訊，請參閱 [RFC 4568 一節 6.1](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支援需求

裝置必須能夠提供 SDES 格式，如下所述。 Microsoft Media 處理器一律偏好 SDES。

- 在非媒體略過的情況下，即使用戶端只支援 DTLS，媒體處理器也會轉換成 SDES。

- 在媒體略過的情況下，如果用戶端是 DTLS， (未來的 Google Chrome 狀態) ，直接路由會在路徑中插入 MP，將呼叫從媒體略過轉換為非媒體略過。 在直接路由的 SBC 和媒體處理器元件之間，一律會使用 SDES。

目前沒有僅提供 DTLS 的 Teams 用戶端;不過，Google 已宣佈在某個時間點停止支援 SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>從 SBC 略過模式提供優惠的格式 

優惠必須包含 SDES，且可以包含下列格式的 DTLS 選擇性：

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>包含 SDES 轉 SBC 之答案的格式

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>從 Teams 到 SBC 的優惠格式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES 格式僅提供 SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

