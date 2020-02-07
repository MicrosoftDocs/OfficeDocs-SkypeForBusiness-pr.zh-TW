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
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f21a4532a841a23f6bbb78a57e223616ae539fa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835133"
---
# <a name="overview"></a>概觀

本文說明在[RFC 5245](https://tools.ietf.org/html/rfc5245)中說明的直接路由如何支援以「ICE」外的會話邊界控制器（SBC）啟用媒體旁路。 本文適用于負責設定內部部署 SBC 與 SIP proxy 服務之間的連線的語音系統管理員。

本文將說明互通性簡化案例的概況和需求。 本文將說明郵件格式及必要的狀態電腦轉換，以確保可靠的通話和媒體流程。

## <a name="terminology"></a>詞彙

- 第一位 Hello-呼叫者和被叫方所朗讀的第一字。 務必要進行所有努力，以確保端點中的第一個資料包在大部分使用案例中都得到可靠的傳送。

- [分叉]：如果被呼叫者可在多個裝置上使用，可能會將來電傳送到多個被叫方的端點（例如，小組使用者可能會登入 Windows 的小組和 Android 或 iPhone 的小組）。

- 臨時應答（183）-呼叫方點數以取得更快的通話設定，傳送具有候選和按鍵來建立媒體流程所需的答案。 這是為了預期使用者可能會從該特定的被叫方實例應答呼叫（200OK）。 有了分叉，來電者就應該準備好接收多個臨時答案。

- 重新邀請–提供由 ICE 控制端點所選取的最終候選項目。 這將會有 a = 遠端候選屬性來解決任何爭用情況，以處理多個叉。

- 團隊端點–這可能是伺服器（媒體處理器、傳輸中繼）或團隊用戶端。

## <a name="message-format"></a>郵件格式

團隊基礎結構遵循 RFC 5245 來進行 ICE Lite。 這表示所有的 STUN 訊息都將符合[RFC 5389](https://tools.ietf.org/html/rfc5389)。

RFC 5389 所需的 SBCs 必須忽略其無法辨識的任何 STUN 屬性，並繼續處理具有已知屬性的訊息。 

如果收到任何格式錯誤的資料包，則必須捨棄資料包，而不會影響媒體會話的建立。

## <a name="ice-lite-requirements"></a>冰精簡需求

本節簡要簡單地捕獲 ICE Lite 的需求。

### <a name="candidate-gathering"></a>候選收集

SBC 只能提供可公開存取的單一候選方案。 目前只支援 IPV4 候選人。


#### <a name="connectivity-checks"></a>連通性檢查

ICE Lite 實現必須回應收到的任何連線檢查。 ICE Lite 端點不能傳送任何連通性檢查要求。 （如果連線檢查發生衝突，完整的實現就會回應，這可能會導致發現意外的對等派生候選，且可能導致呼叫失敗。）

#### <a name="nominations"></a>Nominations

[ICE 完整實現] 端點會一直是 [控制] 端點，並遵循 [Regular] nominations 來選取要用於媒體流程的最終候選項目。 [ICE Lite] 端點可以使用 nominations 來結束媒體與完成通話建立所要使用的路徑。

注意：在與對等端點傳送183臨時答案的分叉情況下，SBC 必須準備好回應來自多個端點的檢查，如果 nominations 在200OK 之前發生，也可以從多個端點 nominations。 根據 [ICE 狀態] 電腦在最終路徑和使用者應答時間的收斂，nominations 可能會在200OK 之前或之後發生。 SBC 必須能夠處理這兩種情況。

#### <a name="converging-for-forking"></a>用於分叉的彙聚

如果從 SBC 叉給多個團隊端點，小組端點可能會以臨時答案回應，並啟動連線檢查。 SBC 必須準備好接收連線檢查，並回應來自多個對等端點的連線性檢查。 例如，小組使用者可以同時登入桌面和手機。 這兩個裝置都會收到撥入通話的通知，並會嘗試與 SBC 進行連接檢查。

最終只有其中一個端點會接聽來電（200OK）。 在收到200OK 之後，SBC 可以設定適當的內容來處理媒體包。

## <a name="scenarios"></a>案例

###  <a name="inbound-call-from-sbc"></a>來自 SBC 的撥入通話

在這種情況下，SBC 必須處理幾個可能的對等端點：

- 伺服器端點通常會直接使用200OK 來回應。 這些是完整的 ICE 端點，通常包含在語音信箱、通話佇列和自動語音應答案例中。

- 用戶端端點可以傳送具有不同 [寄件者] 和 [至] 標記的多個臨時應答（183），接著是來自接聽來電之端點的200OK。 這些是完整的 ICE 端點，通常代表最終使用者用戶端。

- 其他 SBC 端點。 這些是冰精簡端點，通常會在同時撥打用戶端端點和其他電話號碼的情況中參與。

SBC 必須回應從全冰端點收到的所有有效連接檢查要求。 根據 RFC，完整的 ICE 端點會變成控制端點。 小組（用戶端/伺服器）端點會執行「Regular」 nominations 來完成連接檢查。 最終的200Ok 可以來自傳送早期媒體或來自不同端點的端點。 在收到200Ok 之後，SBC 必須針對媒體流程設定正確的內容。 

###  <a name="early-media"></a>早期媒體

如果有較早的媒體流程，則 SBC 必須鎖住開始串流媒體的第一個端點;媒體流程可以在您的候選人命名之前開始。 在此階段，SBC 應該支援傳送 DTMF 來啟用 IVR/語音信箱案例。 如果 nominations 尚未完成，則 SBC 應該使用其收到檢查的最高優先順序路徑。

### <a name="outbound-call-to-sbc"></a>對 SBC 的輸出呼叫

團隊端點是此案例的來電者，將會是控制端點。 在收到臨時答案（183）或最終答案（200OK）時，小組端點會啟動連線檢查並繼續執行 [Regular] nominations，以完成連線檢查。

注意：如果 SBC 傳送臨時應答（183），則 SBC 必須準備好接收連線檢查要求，並可能完成 nominations，然後才能由 SBC 傳送200OK。 如果在收到200OK 之前，檢查和/或 nominations 都已完成，則在收到200OK 之後，就不會再執行檢查和/或 nominations。 SBC 不能在183和200之間變更 ICE 候選人、密碼及 ufrag （username 片段）。

為了支援早期媒體，SBC 可能會開始將媒體資料流程傳送到對等冰候選人，且根據接收到的連線檢查，即使 nominations 是由團隊端點完成，也可以使用最高優先順序。 在 nominations 完成之前，SBC 應該會期望小組中的團隊擁有任何候選媒體。 獲候選人之後，SBC 必須重設為適當的內容，才能傳送和接收媒體包。

## <a name="srtp-support-requirements"></a>SRTP 支援需求

SBC 必須支援 SRTP 加密密碼 AES_CM_128_HMAC_SHA1_80，以下列格式提供和回答：

```
"inline:" <key||salt> ["|" lifetime]
```

以下是來自 SBC 的 SDP 提供中的 [加密] 屬性範例：

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

不需要 MKI 和 Length 參數。

如需詳細資訊，請參閱[RFC 4568 （區段6.1）](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支援需求

裝置必須能夠以如下所述的格式提供 SDES。 Microsoft 媒體處理器總是優先使用 SDES。

- 在非媒體旁路的情況下，即使用戶端只支援 DTLS，媒體處理器也會轉換成 SDES。

- 透過媒體旁路，如果用戶端只是 DTLS （未來 Google Chrome 狀態），直接路由就會在路徑中插入 MP，將來自 [媒體旁路] 的呼叫轉換為 [非媒體旁路]。 在直接路由的 SBC 與媒體處理器元件之間，SDES 總是使用。

目前沒有僅提供 DTLS 的團隊用戶端;不過，Google 已宣佈，在某個時間點會停止支援 SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>在旁路模式下，從 SBC 提供的格式 

[提議] 必須包含 SDES，且可以包含 DTLS 選用下列格式：

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>包含 SDES 至 SBC 之答案的格式

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>從團隊向 SBC 提供的格式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES 僅提供給 SBC 的格式

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

