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
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065623"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="2108b-103">直接路由定義與 RFC 標準</span><span class="sxs-lookup"><span data-stu-id="2108b-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="2108b-104">本文說明 Microsoft 手機系統直通路由如何實現 RFC 標準通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2108b-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="2108b-105">本文適用于負責設定內部部署會話邊界控制器（SBC）與會話初始通訊協定（SIP） proxy 服務之間的連線的語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2108b-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="2108b-106">客戶 SBC 介面與 Microsoft 團隊後端的下列元件：</span><span class="sxs-lookup"><span data-stu-id="2108b-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="2108b-107">用於發信號的**SIP proxy** 。</span><span class="sxs-lookup"><span data-stu-id="2108b-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="2108b-108">這是直接路由的網際網路式元件，可在 SBCs 與直接路由之間處理 SIP （TLS）連線。</span><span class="sxs-lookup"><span data-stu-id="2108b-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="2108b-109">媒體**的媒體處理器**。</span><span class="sxs-lookup"><span data-stu-id="2108b-109">**The media processors** for media.</span></span> <span data-ttu-id="2108b-110">這是用來處理媒體流量之直接路由的網際網路式元件。</span><span class="sxs-lookup"><span data-stu-id="2108b-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="2108b-111">此元件使用 SRTP 和 SRTCP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2108b-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="2108b-112">如需直接路由的詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2108b-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="2108b-113">如需直接路由如何實現 SIP 通訊協定的詳細資訊，請參閱[直接路由 SIP 通訊協定](direct-routing-protocols-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="2108b-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="2108b-114">RFC 標準</span><span class="sxs-lookup"><span data-stu-id="2108b-114">RFC standards</span></span>

<span data-ttu-id="2108b-115">直接路由符合 RFC 標準。</span><span class="sxs-lookup"><span data-stu-id="2108b-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="2108b-116">連接至直接路由的 SBC 也必須符合下列 Rfc （或其後續任務）。</span><span class="sxs-lookup"><span data-stu-id="2108b-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="2108b-117">適用于支援非媒體旁路模式之裝置的標準</span><span class="sxs-lookup"><span data-stu-id="2108b-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="2108b-118">下列標準適用于僅支援非媒體旁路模式的裝置：</span><span class="sxs-lookup"><span data-stu-id="2108b-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="2108b-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：會話初始通訊協定</span><span class="sxs-lookup"><span data-stu-id="2108b-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="2108b-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325)。</span><span class="sxs-lookup"><span data-stu-id="2108b-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="2108b-121">在受信任的網路中，針對斷言身分識別的會話初始通訊協定的專用延伸-有關處理 P 斷言身分識別標頭的章節。</span><span class="sxs-lookup"><span data-stu-id="2108b-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="2108b-122">直接路由會傳送 P 斷言身分識別與隱私權 ID 標頭。</span><span class="sxs-lookup"><span data-stu-id="2108b-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="2108b-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)針對所需歷程記錄資訊的會話初始通訊協定（SIP）延伸。</span><span class="sxs-lookup"><span data-stu-id="2108b-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="2108b-124">另請參閱：路由 SIP 通訊協定描述以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2108b-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="2108b-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)會話初始通訊協定（依機構所參照）</span><span class="sxs-lookup"><span data-stu-id="2108b-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="2108b-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)會話初始通訊協定（SIP）「取代」標頭</span><span class="sxs-lookup"><span data-stu-id="2108b-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="2108b-127">[RFC 6337](https://tools.ietf.org/html/rfc6337)優惠/答案模型的會話初始通訊協定（SIP）使用量。</span><span class="sxs-lookup"><span data-stu-id="2108b-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="2108b-128">請參閱「RFC 差異」一節。</span><span class="sxs-lookup"><span data-stu-id="2108b-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="2108b-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711)與[rfc 4771](https://tools.ietf.org/html/rfc4771)。</span><span class="sxs-lookup"><span data-stu-id="2108b-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="2108b-130">使用 SRTP 保護 RTP 流量。</span><span class="sxs-lookup"><span data-stu-id="2108b-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="2108b-131">SBC 必須能夠使用 SDES 建立金鑰。</span><span class="sxs-lookup"><span data-stu-id="2108b-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="2108b-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)RTP/RTCP 複用的會話描述通訊協定（SDP）提供/答案說明</span><span class="sxs-lookup"><span data-stu-id="2108b-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="2108b-133">適用于支援媒體旁路模式之裝置的標準</span><span class="sxs-lookup"><span data-stu-id="2108b-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="2108b-134">除了列為非旁路模式使用的標準之外，下列標準適用于媒體旁路模式：</span><span class="sxs-lookup"><span data-stu-id="2108b-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="2108b-135">[針對媒體旁路的 RFC 5245 互動式連接建立（ICE）](https://tools.ietf.org/html/rfc5245)。</span><span class="sxs-lookup"><span data-stu-id="2108b-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="2108b-136">SBC 必須支援下列各項：</span><span class="sxs-lookup"><span data-stu-id="2108b-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="2108b-137">冰 Lite-團隊用戶端是完全 ICE 用戶端</span><span class="sxs-lookup"><span data-stu-id="2108b-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="2108b-138">[ICE 重新開機](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。</span><span class="sxs-lookup"><span data-stu-id="2108b-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="2108b-139">在 ICE 重新開機時，請參閱使用案例與範例的詳細資訊：媒體旁路來電轉接到不支援媒體旁路的端點</span><span class="sxs-lookup"><span data-stu-id="2108b-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="2108b-140">[RFC rfc 5589 會話初始通訊協定（SIP）通話控制–轉移](https://tools.ietf.org/html/rfc5589)。</span><span class="sxs-lookup"><span data-stu-id="2108b-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="2108b-141">[RFC 3960 在會話初始通訊協定（SIP）中，以早期媒體與鈴聲產生的方式](https://tools.ietf.org/html/rfc3960)，請參閱3.1、分叉與3.2 區段，以及撥打音調產生的章節</span><span class="sxs-lookup"><span data-stu-id="2108b-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="2108b-142">適用于 NAT 的 RFC 5389 會話遍歷公用程式（STUN）</span><span class="sxs-lookup"><span data-stu-id="2108b-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="2108b-143">RFC 5766 使用 NAT 的中繼進行遍歷（TURN）：將延伸移至 NAT 的會話遍歷公用程式（STUN）</span><span class="sxs-lookup"><span data-stu-id="2108b-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="2108b-144">可支援將位置資訊傳達給 E911 提供者的標準</span><span class="sxs-lookup"><span data-stu-id="2108b-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="2108b-145">RFC 6442，會話初始通訊協定的位置 Conveyance</span><span class="sxs-lookup"><span data-stu-id="2108b-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="2108b-146">RFC 的差異</span><span class="sxs-lookup"><span data-stu-id="2108b-146">Deviations from the RFC's</span></span>

<span data-ttu-id="2108b-147">下表列出 Microsoft 在其中的 SIP 或媒體堆疊實現與標準偏離的 RFC 區段：</span><span class="sxs-lookup"><span data-stu-id="2108b-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="2108b-148">RFC 和章節</span><span class="sxs-lookup"><span data-stu-id="2108b-148">RFC and sections</span></span> | <span data-ttu-id="2108b-149">描述</span><span class="sxs-lookup"><span data-stu-id="2108b-149">Description</span></span> | <span data-ttu-id="2108b-150">差異</span><span class="sxs-lookup"><span data-stu-id="2108b-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="2108b-151">RFC 6337，區段5.3 保留並繼續媒體</span><span class="sxs-lookup"><span data-stu-id="2108b-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="2108b-152">RFC 可讓您使用 "a = 不活躍"，"a = sendonly"，a = recvonly "保留通話。</span><span class="sxs-lookup"><span data-stu-id="2108b-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="2108b-153">SIP proxy 只支援 "a = 非使用中"，而且不了解 SBC 是傳送 "a = sendonly" 或 "a = recvonly"。</span><span class="sxs-lookup"><span data-stu-id="2108b-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="2108b-154">在使用 c = 0.0.0.0 接收 SDP 時的 RFC 6337，區段5.4」行為</span><span class="sxs-lookup"><span data-stu-id="2108b-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="2108b-155">[RFC3264](https://tools.ietf.org/html/rfc3264)要求工程師能夠接收連接位址為0.0.0.0 的 SDP，在這種情況下，這表示 RTP 和 RTCP 都不應傳送給對等。</span><span class="sxs-lookup"><span data-stu-id="2108b-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="2108b-156">SIP proxy 不支援此選項。</span><span class="sxs-lookup"><span data-stu-id="2108b-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="2108b-157">操作模式</span><span class="sxs-lookup"><span data-stu-id="2108b-157">Operational modes</span></span>

<span data-ttu-id="2108b-158">直接路由有兩種操作模式：</span><span class="sxs-lookup"><span data-stu-id="2108b-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="2108b-159">在團隊用戶端、媒體處理器與 SBC 之間流動時，**不需要媒體旁路**。</span><span class="sxs-lookup"><span data-stu-id="2108b-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="2108b-160">在**媒體旁路**中，所有的 RTP 媒體都在團隊端點與 SBC 之間流動。</span><span class="sxs-lookup"><span data-stu-id="2108b-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="2108b-161">請注意，SIP 流量永遠流經 SIP proxy。</span><span class="sxs-lookup"><span data-stu-id="2108b-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
