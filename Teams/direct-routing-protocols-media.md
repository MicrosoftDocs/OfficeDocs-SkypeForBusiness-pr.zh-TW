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
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065663"
---
# <a name="overview"></a><span data-ttu-id="50dd2-103">概觀</span><span class="sxs-lookup"><span data-stu-id="50dd2-103">Overview</span></span>

<span data-ttu-id="50dd2-104">本文說明在[RFC 5245](https://tools.ietf.org/html/rfc5245)中說明的直接路由如何支援以「ICE」外的會話邊界控制器（SBC）啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="50dd2-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="50dd2-105">本文適用于負責設定內部部署 SBC 與 SIP proxy 服務之間的連線的語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="50dd2-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="50dd2-106">本文將說明互通性簡化案例的概況和需求。</span><span class="sxs-lookup"><span data-stu-id="50dd2-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="50dd2-107">本文將說明郵件格式及必要的狀態電腦轉換，以確保可靠的通話和媒體流程。</span><span class="sxs-lookup"><span data-stu-id="50dd2-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="50dd2-108">詞彙</span><span class="sxs-lookup"><span data-stu-id="50dd2-108">Terminology</span></span>

- <span data-ttu-id="50dd2-109">第一位 Hello-呼叫者和被叫方所朗讀的第一字。</span><span class="sxs-lookup"><span data-stu-id="50dd2-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="50dd2-110">務必要進行所有努力，以確保端點中的第一個資料包在大部分使用案例中都得到可靠的傳送。</span><span class="sxs-lookup"><span data-stu-id="50dd2-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="50dd2-111">[分叉]：如果被呼叫者可在多個裝置上使用，可能會將來電傳送到多個被叫方的端點（例如，小組使用者可能會登入 Windows 的小組和 Android 或 iPhone 的小組）。</span><span class="sxs-lookup"><span data-stu-id="50dd2-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="50dd2-112">臨時應答（183）-呼叫方點數以取得更快的通話設定，傳送具有候選和按鍵來建立媒體流程所需的答案。</span><span class="sxs-lookup"><span data-stu-id="50dd2-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="50dd2-113">這是為了預期使用者可能會從該特定的被叫方實例應答呼叫（200OK）。</span><span class="sxs-lookup"><span data-stu-id="50dd2-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="50dd2-114">有了分叉，來電者就應該準備好接收多個臨時答案。</span><span class="sxs-lookup"><span data-stu-id="50dd2-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="50dd2-115">重新邀請–提供由 ICE 控制端點所選取的最終候選項目。</span><span class="sxs-lookup"><span data-stu-id="50dd2-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="50dd2-116">這將會有 a = 遠端候選屬性來解決任何爭用情況，以處理多個叉。</span><span class="sxs-lookup"><span data-stu-id="50dd2-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="50dd2-117">團隊端點–這可能是伺服器（媒體處理器、傳輸中繼）或團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="50dd2-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="50dd2-118">郵件格式</span><span class="sxs-lookup"><span data-stu-id="50dd2-118">Message format</span></span>

<span data-ttu-id="50dd2-119">團隊基礎結構遵循 RFC 5245 來進行 ICE Lite。</span><span class="sxs-lookup"><span data-stu-id="50dd2-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="50dd2-120">這表示所有的 STUN 訊息都將符合[RFC 5389](https://tools.ietf.org/html/rfc5389)。</span><span class="sxs-lookup"><span data-stu-id="50dd2-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="50dd2-121">RFC 5389 所需的 SBCs 必須忽略其無法辨識的任何 STUN 屬性，並繼續處理具有已知屬性的訊息。</span><span class="sxs-lookup"><span data-stu-id="50dd2-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="50dd2-122">如果收到任何格式錯誤的資料包，則必須捨棄資料包，而不會影響媒體會話的建立。</span><span class="sxs-lookup"><span data-stu-id="50dd2-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="50dd2-123">冰精簡需求</span><span class="sxs-lookup"><span data-stu-id="50dd2-123">ICE Lite requirements</span></span>

<span data-ttu-id="50dd2-124">本節簡要簡單地捕獲 ICE Lite 的需求。</span><span class="sxs-lookup"><span data-stu-id="50dd2-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="50dd2-125">候選收集</span><span class="sxs-lookup"><span data-stu-id="50dd2-125">Candidate gathering</span></span>

<span data-ttu-id="50dd2-126">SBC 只能提供可公開存取的單一候選方案。</span><span class="sxs-lookup"><span data-stu-id="50dd2-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="50dd2-127">目前只支援 IPV4 候選人。</span><span class="sxs-lookup"><span data-stu-id="50dd2-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="50dd2-128">連通性檢查</span><span class="sxs-lookup"><span data-stu-id="50dd2-128">Connectivity checks</span></span>

<span data-ttu-id="50dd2-129">ICE Lite 實現必須回應收到的任何連線檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="50dd2-130">ICE Lite 端點不能傳送任何連通性檢查要求。</span><span class="sxs-lookup"><span data-stu-id="50dd2-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="50dd2-131">（如果連線檢查發生衝突，完整的實現就會回應，這可能會導致發現意外的對等派生候選，且可能導致呼叫失敗。）</span><span class="sxs-lookup"><span data-stu-id="50dd2-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="50dd2-132">Nominations</span><span class="sxs-lookup"><span data-stu-id="50dd2-132">Nominations</span></span>

<span data-ttu-id="50dd2-133">[ICE 完整實現] 端點會一直是 [控制] 端點，並遵循 [Regular] nominations 來選取要用於媒體流程的最終候選項目。</span><span class="sxs-lookup"><span data-stu-id="50dd2-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="50dd2-134">[ICE Lite] 端點可以使用 nominations 來結束媒體與完成通話建立所要使用的路徑。</span><span class="sxs-lookup"><span data-stu-id="50dd2-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="50dd2-135">注意：在與對等端點傳送183臨時答案的分叉情況下，SBC 必須準備好回應來自多個端點的檢查，如果 nominations 在200OK 之前發生，也可以從多個端點 nominations。</span><span class="sxs-lookup"><span data-stu-id="50dd2-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="50dd2-136">根據 [ICE 狀態] 電腦在最終路徑和使用者應答時間的收斂，nominations 可能會在200OK 之前或之後發生。</span><span class="sxs-lookup"><span data-stu-id="50dd2-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="50dd2-137">SBC 必須能夠處理這兩種情況。</span><span class="sxs-lookup"><span data-stu-id="50dd2-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="50dd2-138">用於分叉的彙聚</span><span class="sxs-lookup"><span data-stu-id="50dd2-138">Converging for forking</span></span>

<span data-ttu-id="50dd2-139">如果從 SBC 叉給多個團隊端點，小組端點可能會以臨時答案回應，並啟動連線檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="50dd2-140">SBC 必須準備好接收連線檢查，並回應來自多個對等端點的連線性檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="50dd2-141">例如，小組使用者可以同時登入桌面和手機。</span><span class="sxs-lookup"><span data-stu-id="50dd2-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="50dd2-142">這兩個裝置都會收到撥入通話的通知，並會嘗試與 SBC 進行連接檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="50dd2-143">最終只有其中一個端點會接聽來電（200OK）。</span><span class="sxs-lookup"><span data-stu-id="50dd2-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="50dd2-144">在收到200OK 之後，SBC 可以設定適當的內容來處理媒體包。</span><span class="sxs-lookup"><span data-stu-id="50dd2-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="50dd2-145">案例</span><span class="sxs-lookup"><span data-stu-id="50dd2-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="50dd2-146">來自 SBC 的撥入通話</span><span class="sxs-lookup"><span data-stu-id="50dd2-146">Inbound call from SBC</span></span>

<span data-ttu-id="50dd2-147">在這種情況下，SBC 必須處理幾個可能的對等端點：</span><span class="sxs-lookup"><span data-stu-id="50dd2-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="50dd2-148">伺服器端點通常會直接使用200OK 來回應。</span><span class="sxs-lookup"><span data-stu-id="50dd2-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="50dd2-149">這些是完整的 ICE 端點，通常包含在語音信箱、通話佇列和自動語音應答案例中。</span><span class="sxs-lookup"><span data-stu-id="50dd2-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="50dd2-150">用戶端端點可以傳送具有不同 [寄件者] 和 [至] 標記的多個臨時應答（183），接著是來自接聽來電之端點的200OK。</span><span class="sxs-lookup"><span data-stu-id="50dd2-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="50dd2-151">這些是完整的 ICE 端點，通常代表最終使用者用戶端。</span><span class="sxs-lookup"><span data-stu-id="50dd2-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="50dd2-152">其他 SBC 端點。</span><span class="sxs-lookup"><span data-stu-id="50dd2-152">Other SBC endpoints.</span></span> <span data-ttu-id="50dd2-153">這些是冰精簡端點，通常會在同時撥打用戶端端點和其他電話號碼的情況中參與。</span><span class="sxs-lookup"><span data-stu-id="50dd2-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="50dd2-154">SBC 必須回應從全冰端點收到的所有有效連接檢查要求。</span><span class="sxs-lookup"><span data-stu-id="50dd2-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="50dd2-155">根據 RFC，完整的 ICE 端點會變成控制端點。</span><span class="sxs-lookup"><span data-stu-id="50dd2-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="50dd2-156">小組（用戶端/伺服器）端點會執行「Regular」 nominations 來完成連接檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="50dd2-157">最終的200Ok 可以來自傳送早期媒體或來自不同端點的端點。</span><span class="sxs-lookup"><span data-stu-id="50dd2-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="50dd2-158">在收到200Ok 之後，SBC 必須針對媒體流程設定正確的內容。</span><span class="sxs-lookup"><span data-stu-id="50dd2-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="50dd2-159">早期媒體</span><span class="sxs-lookup"><span data-stu-id="50dd2-159">Early media</span></span>

<span data-ttu-id="50dd2-160">如果有較早的媒體流程，則 SBC 必須鎖住開始串流媒體的第一個端點;媒體流程可以在您的候選人命名之前開始。</span><span class="sxs-lookup"><span data-stu-id="50dd2-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="50dd2-161">在此階段，SBC 應該支援傳送 DTMF 來啟用 IVR/語音信箱案例。</span><span class="sxs-lookup"><span data-stu-id="50dd2-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="50dd2-162">如果 nominations 尚未完成，則 SBC 應該使用其收到檢查的最高優先順序路徑。</span><span class="sxs-lookup"><span data-stu-id="50dd2-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="50dd2-163">對 SBC 的輸出呼叫</span><span class="sxs-lookup"><span data-stu-id="50dd2-163">Outbound call to SBC</span></span>

<span data-ttu-id="50dd2-164">團隊端點是此案例的來電者，將會是控制端點。</span><span class="sxs-lookup"><span data-stu-id="50dd2-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="50dd2-165">在收到臨時答案（183）或最終答案（200OK）時，小組端點會啟動連線檢查並繼續執行 [Regular] nominations，以完成連線檢查。</span><span class="sxs-lookup"><span data-stu-id="50dd2-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="50dd2-166">注意：如果 SBC 傳送臨時應答（183），則 SBC 必須準備好接收連線檢查要求，並可能完成 nominations，然後才能由 SBC 傳送200OK。</span><span class="sxs-lookup"><span data-stu-id="50dd2-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="50dd2-167">如果在收到200OK 之前，檢查和/或 nominations 都已完成，則在收到200OK 之後，就不會再執行檢查和/或 nominations。</span><span class="sxs-lookup"><span data-stu-id="50dd2-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="50dd2-168">SBC 不能在183和200之間變更 ICE 候選人、密碼及 ufrag （username 片段）。</span><span class="sxs-lookup"><span data-stu-id="50dd2-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="50dd2-169">為了支援早期媒體，SBC 可能會開始將媒體資料流程傳送到對等冰候選人，且根據接收到的連線檢查，即使 nominations 是由團隊端點完成，也可以使用最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="50dd2-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="50dd2-170">在 nominations 完成之前，SBC 應該會期望小組中的團隊擁有任何候選媒體。</span><span class="sxs-lookup"><span data-stu-id="50dd2-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="50dd2-171">獲候選人之後，SBC 必須重設為適當的內容，才能傳送和接收媒體包。</span><span class="sxs-lookup"><span data-stu-id="50dd2-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="50dd2-172">SRTP 支援需求</span><span class="sxs-lookup"><span data-stu-id="50dd2-172">SRTP support requirements</span></span>

<span data-ttu-id="50dd2-173">SBC 必須支援 SRTP 加密密碼 AES_CM_128_HMAC_SHA1_80，以下列格式提供和回答：</span><span class="sxs-lookup"><span data-stu-id="50dd2-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="50dd2-174">以下是來自 SBC 的 SDP 提供中的 [加密] 屬性範例：</span><span class="sxs-lookup"><span data-stu-id="50dd2-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="50dd2-175">不需要 MKI 和 Length 參數。</span><span class="sxs-lookup"><span data-stu-id="50dd2-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="50dd2-176">如需詳細資訊，請參閱[RFC 4568 （區段6.1）](https://tools.ietf.org/html/rfc4568#section-6.1)。</span><span class="sxs-lookup"><span data-stu-id="50dd2-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="50dd2-177">SDES 支援需求</span><span class="sxs-lookup"><span data-stu-id="50dd2-177">SDES support requirements</span></span>

<span data-ttu-id="50dd2-178">裝置必須能夠以如下所述的格式提供 SDES。</span><span class="sxs-lookup"><span data-stu-id="50dd2-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="50dd2-179">Microsoft 媒體處理器總是優先使用 SDES。</span><span class="sxs-lookup"><span data-stu-id="50dd2-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="50dd2-180">在非媒體旁路的情況下，即使用戶端只支援 DTLS，媒體處理器也會轉換成 SDES。</span><span class="sxs-lookup"><span data-stu-id="50dd2-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="50dd2-181">透過媒體旁路，如果用戶端只是 DTLS （未來 Google Chrome 狀態），直接路由就會在路徑中插入 MP，將來自 [媒體旁路] 的呼叫轉換為 [非媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="50dd2-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="50dd2-182">在直接路由的 SBC 與媒體處理器元件之間，SDES 總是使用。</span><span class="sxs-lookup"><span data-stu-id="50dd2-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="50dd2-183">目前沒有僅提供 DTLS 的團隊用戶端;不過，Google 已宣佈，在某個時間點會停止支援 SDES。</span><span class="sxs-lookup"><span data-stu-id="50dd2-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="50dd2-184">在旁路模式下，從 SBC 提供的格式</span><span class="sxs-lookup"><span data-stu-id="50dd2-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="50dd2-185">[提議] 必須包含 SDES，且可以包含 DTLS 選用下列格式：</span><span class="sxs-lookup"><span data-stu-id="50dd2-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="50dd2-186">包含 SDES 至 SBC 之答案的格式</span><span class="sxs-lookup"><span data-stu-id="50dd2-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="50dd2-187">從團隊向 SBC 提供的格式</span><span class="sxs-lookup"><span data-stu-id="50dd2-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="50dd2-188">SDES 僅提供給 SBC 的格式</span><span class="sxs-lookup"><span data-stu-id="50dd2-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

