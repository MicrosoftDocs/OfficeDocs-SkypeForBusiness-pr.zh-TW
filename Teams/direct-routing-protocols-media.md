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
# <a name="overview"></a><span data-ttu-id="b897b-103">概觀</span><span class="sxs-lookup"><span data-stu-id="b897b-103">Overview</span></span>

<span data-ttu-id="b897b-104">本文將說明直接路由如何支援使用會話邊界控制器 (SBC) 啟用 ICE Lite 的媒體旁路，如 [RFC 5245](https://tools.ietf.org/html/rfc5245)中所述。</span><span class="sxs-lookup"><span data-stu-id="b897b-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="b897b-105">本文適用于負責在內部部署 SBC 與 SIP Proxy 服務之間建立連接之語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b897b-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="b897b-106">本文提供 ICE Lite 案例與互通性需求概觀。</span><span class="sxs-lookup"><span data-stu-id="b897b-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="b897b-107">本文將說明訊息格式，以及確保可靠的通話和媒體流程所需的狀態機轉場。</span><span class="sxs-lookup"><span data-stu-id="b897b-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="b897b-108">術語</span><span class="sxs-lookup"><span data-stu-id="b897b-108">Terminology</span></span>

- <span data-ttu-id="b897b-109">First Hello – 來電者與受話者所說出的第一個字。</span><span class="sxs-lookup"><span data-stu-id="b897b-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="b897b-110">必須做出一切努力，確保從端點傳送的第一個封包在大部分使用方式下都能夠可靠地傳遞。</span><span class="sxs-lookup"><span data-stu-id="b897b-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="b897b-111">Forking - 如果受叫者在多個裝置上可用，則來電者所提供的優惠可能會傳送到多個受叫者端點 (例如，Teams 使用者可能會針對 Windows 和 Teams for Android 或 iPhone) Teams 進行登錄。</span><span class="sxs-lookup"><span data-stu-id="b897b-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="b897b-112">暫 (183) – 呼叫者端點可傳送答案，以加快通話設定速度，並傳送要建立媒體流程所需的候選項和按鍵。</span><span class="sxs-lookup"><span data-stu-id="b897b-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="b897b-113">這是在預期使用者可能從該特定受叫者實例 (200OK) 來電時所完成。</span><span class="sxs-lookup"><span data-stu-id="b897b-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="b897b-114">使用點名時，來電者應該可以接收多個暫發性答案。</span><span class="sxs-lookup"><span data-stu-id="b897b-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="b897b-115">Re-Invite – 由 ICE 控制端點選取最終候選人的優惠。</span><span class="sxs-lookup"><span data-stu-id="b897b-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="b897b-116">這會有 a=remote-candidate 屬性，以解決處理多個分叉時的任何競賽條件。</span><span class="sxs-lookup"><span data-stu-id="b897b-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="b897b-117">Teams端點 – 這可能是媒體處理器 (傳輸轉) 伺服器Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="b897b-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="b897b-118">郵件格式</span><span class="sxs-lookup"><span data-stu-id="b897b-118">Message format</span></span>

<span data-ttu-id="b897b-119">此Teams遵循 ICE-Lite 的 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="b897b-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="b897b-120">這表示所有 STUN 郵件都會符合[RFC 5389。](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="b897b-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="b897b-121">RFC 5389 要求的 SBCs 必須忽略他們無法識別的任何 STUN 屬性，並繼續處理具有已知屬性的郵件。</span><span class="sxs-lookup"><span data-stu-id="b897b-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="b897b-122">如果收到任何格式錯誤的封包，則必須捨棄封包，而不會影響媒體會話的建立。</span><span class="sxs-lookup"><span data-stu-id="b897b-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="b897b-123">ICE Lite 需求</span><span class="sxs-lookup"><span data-stu-id="b897b-123">ICE Lite requirements</span></span>

<span data-ttu-id="b897b-124">本節簡要說明 ICE Lite 的需求。</span><span class="sxs-lookup"><span data-stu-id="b897b-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="b897b-125">候選人聚會</span><span class="sxs-lookup"><span data-stu-id="b897b-125">Candidate gathering</span></span>

<span data-ttu-id="b897b-126">SBC 只能提供一個可公開聯繫的候選者。</span><span class="sxs-lookup"><span data-stu-id="b897b-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="b897b-127">目前僅支援 IPV4 候選項。</span><span class="sxs-lookup"><span data-stu-id="b897b-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="b897b-128">連接檢查</span><span class="sxs-lookup"><span data-stu-id="b897b-128">Connectivity checks</span></span>

<span data-ttu-id="b897b-129">ICE Lite 的實現必須回應收到的任何連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="b897b-130">ICE Lite 端點不得傳送任何連接檢查要求。</span><span class="sxs-lookup"><span data-stu-id="b897b-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="b897b-131"> (如果中斷連接檢查，則完整實現會回應，這可能會導致發現非預期的對等衍生候選者，並可能導致通話失敗。) </span><span class="sxs-lookup"><span data-stu-id="b897b-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="b897b-132">提名</span><span class="sxs-lookup"><span data-stu-id="b897b-132">Nominations</span></span>

<span data-ttu-id="b897b-133">ICE 完整實現端點一直是控制端點，並遵循 「一般」的提名，以選取媒體流程使用的最終候選項目。</span><span class="sxs-lookup"><span data-stu-id="b897b-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="b897b-134">ICE Lite 端點可以使用提名來結束媒體和完整的通話建立路徑。</span><span class="sxs-lookup"><span data-stu-id="b897b-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="b897b-135">注意：若是使用對等端點進行點選，傳送 183 個暫定答案，SBC 必須準備好回應來自多個端點的檢查，以及多個端點的提名，如果 200OK 之前發生。</span><span class="sxs-lookup"><span data-stu-id="b897b-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="b897b-136">根據 ICE 狀態機在使用者回答的最後路徑和時間上的趨同，200OK 之前或之後可能會進行提名。</span><span class="sxs-lookup"><span data-stu-id="b897b-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="b897b-137">SBC 必須能夠處理這兩種情況。</span><span class="sxs-lookup"><span data-stu-id="b897b-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="b897b-138">針對點點進行匯合</span><span class="sxs-lookup"><span data-stu-id="b897b-138">Converging for forking</span></span>

<span data-ttu-id="b897b-139">如果從 SBC 分叉到多個Teams，Teams端點可能會以暫時答案回應，並啟動連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="b897b-140">SBC 必須準備好接收連接檢查，並回應來自多個對等端點的連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="b897b-141">例如，Teams使用者可以同時在桌面和行動電話上登錄。</span><span class="sxs-lookup"><span data-stu-id="b897b-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="b897b-142">這兩個裝置都會收到來電通知，並嘗試與 SBC 進行連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="b897b-143">最終只有其中一個端點會接聽 (200OK) 。</span><span class="sxs-lookup"><span data-stu-id="b897b-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="b897b-144">收到 200OK 後，SBC 可以設定處理媒體封包的合適上下文。</span><span class="sxs-lookup"><span data-stu-id="b897b-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b897b-145">案例</span><span class="sxs-lookup"><span data-stu-id="b897b-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="b897b-146">來自 SBC 的來電</span><span class="sxs-lookup"><span data-stu-id="b897b-146">Inbound call from SBC</span></span>

<span data-ttu-id="b897b-147">針對此案例，SBC 必須處理數個可能的對等端點：</span><span class="sxs-lookup"><span data-stu-id="b897b-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="b897b-148">伺服器端點通常會以 200OK 直接回應。</span><span class="sxs-lookup"><span data-stu-id="b897b-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="b897b-149">這些是完整 ICE 端點，通常涉及語音信箱、通話佇列和自動語音信箱案例。</span><span class="sxs-lookup"><span data-stu-id="b897b-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="b897b-150">用戶端端點可以傳送多個臨時答案，並使用不同的 From/To 標籤 (183) 後面接著接聽來電端點的 200OK。</span><span class="sxs-lookup"><span data-stu-id="b897b-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="b897b-151">這些是完整 ICE 端點，通常代表使用者用戶端。</span><span class="sxs-lookup"><span data-stu-id="b897b-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="b897b-152">其他 SBC 端點。</span><span class="sxs-lookup"><span data-stu-id="b897b-152">Other SBC endpoints.</span></span> <span data-ttu-id="b897b-153">這些是 ICE Lite 端點，通常涉及同時撥打用戶端端點和另一個電話號碼 () 。</span><span class="sxs-lookup"><span data-stu-id="b897b-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="b897b-154">SBC 必須回應從完整 ICE 端點收到的所有有效連接檢查要求。</span><span class="sxs-lookup"><span data-stu-id="b897b-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="b897b-155">根據 RFC，完整的 ICE 端點會變成控制端點。</span><span class="sxs-lookup"><span data-stu-id="b897b-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="b897b-156">用戶端/Teams (端點) 會執行「一般」的推薦，以完成連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="b897b-157">最終的 200Ok 可以來自早期媒體的端點，也可以來自不同的端點。</span><span class="sxs-lookup"><span data-stu-id="b897b-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="b897b-158">在收到 200Ok 時，SBC 必須為媒體流程設定正確的內容。</span><span class="sxs-lookup"><span data-stu-id="b897b-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="b897b-159">早期媒體</span><span class="sxs-lookup"><span data-stu-id="b897b-159">Early media</span></span>

<span data-ttu-id="b897b-160">如果有早期媒體流程，SBC 必須鎖定至第一個啟動串流媒體的端點;媒體流程可以在候選人被提名前開始。</span><span class="sxs-lookup"><span data-stu-id="b897b-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="b897b-161">SBC 應支援在此階段期間傳送 DTMF，以啟用 IVR/語音信箱案例。</span><span class="sxs-lookup"><span data-stu-id="b897b-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="b897b-162">如果尚未完成提名，SBC 應該會使用收到檢查的最高優先順序路徑。</span><span class="sxs-lookup"><span data-stu-id="b897b-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="b897b-163">到 SBC 的外發通話</span><span class="sxs-lookup"><span data-stu-id="b897b-163">Outbound call to SBC</span></span>

<span data-ttu-id="b897b-164">Teams端點是此案例的來電者，且會為控制端點。</span><span class="sxs-lookup"><span data-stu-id="b897b-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="b897b-165">收到暫定答案 (183) 或最終答案 (200OK) 時，Teams 端點會開始進行連接檢查，然後繼續進行「一般」的提名，以完成連接檢查。</span><span class="sxs-lookup"><span data-stu-id="b897b-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="b897b-166">注意：如果 SBC 傳送暫定答案 (183) ，SBC 必須準備好接收連接檢查要求，並有可能完成提名，再由 SBC 傳送 200OK。</span><span class="sxs-lookup"><span data-stu-id="b897b-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="b897b-167">如果在收到 200OK 之前已完成檢查和/或提名，則收到 200OK 之後，將不會再次執行檢查和/或提名。</span><span class="sxs-lookup"><span data-stu-id="b897b-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="b897b-168">SBC 不得變更 ICE 候選者、密碼和 ufrag (使用者) 介於 183 和 200 之間。</span><span class="sxs-lookup"><span data-stu-id="b897b-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="b897b-169">為了支援早期媒體，SBC 可能會開始將媒體串流至對等 ICE 候選者，而最高優先順序會依據收到的連接檢查，甚至在由 Teams 端點完成Teams為止。</span><span class="sxs-lookup"><span data-stu-id="b897b-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="b897b-170">SBC 應預期媒體Teams任何候選人，直到完成提名為止。</span><span class="sxs-lookup"><span data-stu-id="b897b-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="b897b-171">一旦候選人被提名，SBC 必須重設至正確的上下文，以傳送和接收媒體封包。</span><span class="sxs-lookup"><span data-stu-id="b897b-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="b897b-172">SRTP 支援需求</span><span class="sxs-lookup"><span data-stu-id="b897b-172">SRTP support requirements</span></span>

<span data-ttu-id="b897b-173">SBC 必須支援 SRTP 加密密碼AES_CM_128_HMAC_SHA1_80以下列格式提供和接聽：</span><span class="sxs-lookup"><span data-stu-id="b897b-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="b897b-174">以下是 SBC SDP 優惠中加密屬性的範例：</span><span class="sxs-lookup"><span data-stu-id="b897b-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="b897b-175">MKI 和 Length 參數是不需要的。</span><span class="sxs-lookup"><span data-stu-id="b897b-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="b897b-176">詳細資訊，請參閱 [RFC 4568，第 6.1 節](https://tools.ietf.org/html/rfc4568#section-6.1)。</span><span class="sxs-lookup"><span data-stu-id="b897b-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="b897b-177">SDES 支援需求</span><span class="sxs-lookup"><span data-stu-id="b897b-177">SDES support requirements</span></span>

<span data-ttu-id="b897b-178">裝置必須能夠以下列格式提供 SDES。</span><span class="sxs-lookup"><span data-stu-id="b897b-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="b897b-179">Microsoft Media 處理器一向偏好 SDES。</span><span class="sxs-lookup"><span data-stu-id="b897b-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="b897b-180">如果忽略非媒體，即使用戶端僅支援 DTLS，媒體處理器也會轉換成 SDES。</span><span class="sxs-lookup"><span data-stu-id="b897b-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="b897b-181">如果媒體旁路，如果用戶端是 DTLS (未來的 Google Chrome 狀態) ，直接路由就會在路徑中插入 MP，將媒體旁路的通話轉換成非媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b897b-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="b897b-182">在直接路由的 SBC 和媒體處理器元件之間，一直使用 SDES。</span><span class="sxs-lookup"><span data-stu-id="b897b-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="b897b-183">目前，沒有任何用戶端Teams只提供 DTLS;不過，Google 已宣佈在一段時間停止支援 SDES。</span><span class="sxs-lookup"><span data-stu-id="b897b-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="b897b-184">在旁路模式中提供 SBC 優惠的格式</span><span class="sxs-lookup"><span data-stu-id="b897b-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="b897b-185">優惠必須包含 SDES，且可以包含下列格式的 DTLS 選擇性：</span><span class="sxs-lookup"><span data-stu-id="b897b-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="b897b-186">包含 SDES 到 SBC 之答案的格式</span><span class="sxs-lookup"><span data-stu-id="b897b-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="b897b-187">優惠格式從 Teams 到 SBC</span><span class="sxs-lookup"><span data-stu-id="b897b-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="b897b-188">SDES 格式僅適用于 SBC</span><span class="sxs-lookup"><span data-stu-id="b897b-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

