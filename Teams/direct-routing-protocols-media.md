---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888572"
---
# <a name="overview"></a>概觀

本文將說明直接路由如何支援使用會話邊界控制器 (SBC) 啟用 ICE Lite 的媒體旁路，如 [RFC 5245](https://tools.ietf.org/html/rfc5245)中所述。 本文適用于負責在內部部署 SBC 與 SIP Proxy 服務之間建立連接之語音系統管理員。

本文提供 ICE Lite 案例與互通性需求概觀。 本文將說明訊息格式，以及確保可靠的通話和媒體流程所需的狀態機轉場。

## <a name="terminology"></a>術語

- First Hello – 來電者與受話者所說出的第一個字。 必須做出一切努力，確保從端點傳送的第一個封包在大部分使用方式下都能夠可靠地傳遞。

- Forking - 如果受叫者在多個裝置上可用，則來電者所提供的優惠可能會傳送到多個受叫者端點 (例如，Teams 使用者可能會針對 Windows 和 Teams for Android 或 iPhone) Teams 進行登錄。

- 暫 (183) – 呼叫者端點可傳送答案，以加快通話設定速度，並傳送要建立媒體流程所需的候選項和按鍵。 這是在預期使用者可能從該特定受叫者實例 (200OK) 來電時所完成。 使用點名時，來電者應該可以接收多個暫發性答案。

- Re-Invite – 由 ICE 控制端點選取最終候選人的優惠。 這會有 a=remote-candidate 屬性，以解決處理多個分叉時的任何競賽條件。

- Teams端點 – 這可能是媒體處理器 (傳輸轉) 伺服器Teams用戶端。

## <a name="message-format"></a>郵件格式

此Teams遵循 ICE-Lite 的 RFC 5245。 這表示所有 STUN 郵件都會符合[RFC 5389。](https://tools.ietf.org/html/rfc5389)

RFC 5389 要求的 SBCs 必須忽略他們無法識別的任何 STUN 屬性，並繼續處理具有已知屬性的郵件。 

如果收到任何格式錯誤的封包，則必須捨棄封包，而不會影響媒體會話的建立。

## <a name="ice-lite-requirements"></a>ICE Lite 需求

本節簡要說明 ICE Lite 的需求。

### <a name="candidate-gathering"></a>候選人聚會

SBC 只能提供一個可公開聯繫的候選者。 目前僅支援 IPV4 候選項。


#### <a name="connectivity-checks"></a>連接檢查

ICE Lite 的實現必須回應收到的任何連接檢查。 ICE Lite 端點不得傳送任何連接檢查要求。  (如果中斷連接檢查，則完整實現會回應，這可能會導致發現非預期的對等衍生候選者，並可能導致通話失敗。) 

#### <a name="nominations"></a>提名

ICE 完整實現端點一直是控制端點，並遵循 「一般」的提名，以選取媒體流程使用的最終候選項目。 ICE Lite 端點可以使用提名來結束媒體和完整的通話建立路徑。

注意：若是使用對等端點進行點選，傳送 183 個暫定答案，SBC 必須準備好回應來自多個端點的檢查，以及多個端點的提名，如果 200OK 之前發生。 根據 ICE 狀態機在使用者回答的最後路徑和時間上的趨同，200OK 之前或之後可能會進行提名。 SBC 必須能夠處理這兩種情況。

#### <a name="converging-for-forking"></a>針對點點進行匯合

如果從 SBC 分叉到多個Teams，Teams端點可能會以暫時答案回應，並啟動連接檢查。 SBC 必須準備好接收連接檢查，並回應來自多個對等端點的連接檢查。 例如，Teams使用者可以同時在桌面和行動電話上登錄。 這兩個裝置都會收到來電通知，並嘗試與 SBC 進行連接檢查。

最終只有其中一個端點會接聽 (200OK) 。 收到 200OK 後，SBC 可以設定處理媒體封包的合適上下文。

## <a name="scenarios"></a>案例

###  <a name="inbound-call-from-sbc"></a>來自 SBC 的來電

針對此案例，SBC 必須處理數個可能的對等端點：

- 伺服器端點通常會以 200OK 直接回應。 這些是完整 ICE 端點，通常涉及語音信箱、通話佇列和自動語音信箱案例。

- 用戶端端點可以傳送多個臨時答案，並使用不同的 From/To 標籤 (183) 後面接著接聽來電端點的 200OK。 這些是完整 ICE 端點，通常代表使用者用戶端。

- 其他 SBC 端點。 這些是 ICE Lite 端點，通常涉及同時撥打用戶端端點和另一個電話號碼 () 。

SBC 必須回應從完整 ICE 端點收到的所有有效連接檢查要求。 根據 RFC，完整的 ICE 端點會變成控制端點。 用戶端/Teams (端點) 會執行「一般」的推薦，以完成連接檢查。 最終的 200Ok 可以來自早期媒體的端點，也可以來自不同的端點。 在收到 200Ok 時，SBC 必須為媒體流程設定正確的內容。 

###  <a name="early-media"></a>早期媒體

如果有早期媒體流程，SBC 必須鎖定至第一個啟動串流媒體的端點;媒體流程可以在候選人被提名前開始。 SBC 應支援在此階段期間傳送 DTMF，以啟用 IVR/語音信箱案例。 如果尚未完成提名，SBC 應該會使用收到檢查的最高優先順序路徑。

### <a name="outbound-call-to-sbc"></a>到 SBC 的外發通話

Teams端點是此案例的來電者，且會為控制端點。 收到暫定答案 (183) 或最終答案 (200OK) 時，Teams 端點會開始進行連接檢查，然後繼續進行「一般」的提名，以完成連接檢查。

注意：如果 SBC 傳送暫定答案 (183) ，SBC 必須準備好接收連接檢查要求，並有可能完成提名，再由 SBC 傳送 200OK。 如果在收到 200OK 之前已完成檢查和/或提名，則收到 200OK 之後，將不會再次執行檢查和/或提名。 SBC 不得變更 ICE 候選者、密碼和 ufrag (使用者) 介於 183 和 200 之間。

為了支援早期媒體，SBC 可能會開始將媒體串流至對等 ICE 候選者，而最高優先順序會依據收到的連接檢查，甚至在由 Teams 端點完成Teams為止。 SBC 應預期媒體Teams任何候選人，直到完成提名為止。 一旦候選人被提名，SBC 必須重設至正確的上下文，以傳送和接收媒體封包。

## <a name="srtp-support-requirements"></a>SRTP 支援需求

SBC 必須支援 SRTP 加密密碼AES_CM_128_HMAC_SHA1_80以下列格式提供和接聽：

```console
"inline:" <key||salt> ["|" lifetime]
```

以下是 SBC SDP 優惠中加密屬性的範例：

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 和 Length 參數是不需要的。

詳細資訊，請參閱 [RFC 4568，第 6.1 節](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支援需求

裝置必須能夠以下列格式提供 SDES。 Microsoft Media 處理器一向偏好 SDES。

- 如果忽略非媒體，即使用戶端僅支援 DTLS，媒體處理器也會轉換成 SDES。

- 如果媒體旁路，如果用戶端是 DTLS (未來的 Google Chrome 狀態) ，直接路由就會在路徑中插入 MP，將媒體旁路的通話轉換成非媒體旁路。 在直接路由的 SBC 和媒體處理器元件之間，一直使用 SDES。

目前，沒有任何用戶端Teams只提供 DTLS;不過，Google 已宣佈在一段時間停止支援 SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>在旁路模式中提供 SBC 優惠的格式 

優惠必須包含 SDES，且可以包含下列格式的 DTLS 選擇性：

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>包含 SDES 到 SBC 之答案的格式

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>優惠格式從 Teams 到 SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES 格式僅適用于 SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

