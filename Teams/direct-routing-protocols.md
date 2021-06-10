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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569201"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="adbb8-103">直接路由 - 定義和 RFC 標準</span><span class="sxs-lookup"><span data-stu-id="adbb8-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="adbb8-104">本文將說明系統Microsoft 電話路由如何實現 RFC 標準通訊協定。</span><span class="sxs-lookup"><span data-stu-id="adbb8-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="adbb8-105">本文適用于負責在內部部署會話邊界控制器 (SBC) 與會話初始通訊協定 (SIP) Proxy 服務之間建立連接的語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="adbb8-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="adbb8-106">客戶 SBC 會與後端的下列Microsoft Teams介面：</span><span class="sxs-lookup"><span data-stu-id="adbb8-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="adbb8-107">**用於訊號的 SIP** Proxy。</span><span class="sxs-lookup"><span data-stu-id="adbb8-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="adbb8-108">這是直接路由的網際網路元件，可處理 SIP (TLS) SBC 和直接路由之間的連接。</span><span class="sxs-lookup"><span data-stu-id="adbb8-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="adbb8-109">**媒體的** 媒體處理器。</span><span class="sxs-lookup"><span data-stu-id="adbb8-109">**The media processors** for media.</span></span> <span data-ttu-id="adbb8-110">這是直接路由的網際網路元件，可處理媒體流量。</span><span class="sxs-lookup"><span data-stu-id="adbb8-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="adbb8-111">此元件使用 SRTP 和 SRTCP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="adbb8-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="adbb8-112">有關直接路由的資訊，請參閱電話系統[路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="adbb8-113">有關直接路由如何實現 SIP 通訊協定之詳細資訊，請參閱直接 [路由 - SIP 通訊協定](direct-routing-protocols-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="adbb8-114">RFC 標準</span><span class="sxs-lookup"><span data-stu-id="adbb8-114">RFC standards</span></span>

<span data-ttu-id="adbb8-115">直接路由符合 RFC 標準。</span><span class="sxs-lookup"><span data-stu-id="adbb8-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="adbb8-116">連結至直接路由的 SBC 也必須遵守下列 RFC (其後續) 。</span><span class="sxs-lookup"><span data-stu-id="adbb8-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="adbb8-117">適用于支援非媒體旁路模式的裝置的標準</span><span class="sxs-lookup"><span data-stu-id="adbb8-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="adbb8-118">下列標準適用于僅支援非媒體旁路模式的裝置：</span><span class="sxs-lookup"><span data-stu-id="adbb8-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="adbb8-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：會話初始通訊協定</span><span class="sxs-lookup"><span data-stu-id="adbb8-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="adbb8-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="adbb8-121">受信任網路內已確認身分識別的會話初始通訊協定私人擴充功能-關於處理 P-確認-身分識別標頭的章節。</span><span class="sxs-lookup"><span data-stu-id="adbb8-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="adbb8-122">直接路由會傳送具有隱私權識別碼標頭的 P-Identity。</span><span class="sxs-lookup"><span data-stu-id="adbb8-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="adbb8-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) SIP 的會話初始通訊協定 (擴展) 所需的歷程記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="adbb8-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="adbb8-124">另請參閱：路由 SIP 通訊協定描述以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="adbb8-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="adbb8-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 會話初始通訊協定Referred-By機制</span><span class="sxs-lookup"><span data-stu-id="adbb8-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="adbb8-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP 中的會話初始 (「) 取代」標頭</span><span class="sxs-lookup"><span data-stu-id="adbb8-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="adbb8-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) 會話初始通訊 (SIP) /Answer 模型的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="adbb8-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="adbb8-128">請參閱「RFC 的偏差」一節。</span><span class="sxs-lookup"><span data-stu-id="adbb8-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="adbb8-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) 和 [RFC 4771](https://tools.ietf.org/html/rfc4771)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="adbb8-130">使用 SRTP 保護 RTP 流量。</span><span class="sxs-lookup"><span data-stu-id="adbb8-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="adbb8-131">SBC 必須能夠使用 SDES 建立金鑰。</span><span class="sxs-lookup"><span data-stu-id="adbb8-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="adbb8-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 會話描述通訊協定 (SDP) 提供/回答 RTP/RTCP 多重處理的說明</span><span class="sxs-lookup"><span data-stu-id="adbb8-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="adbb8-133">適用于支援媒體旁路模式的裝置的標準</span><span class="sxs-lookup"><span data-stu-id="adbb8-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="adbb8-134">除了列為適用于非旁路模式的標準之外，媒體旁路模式也採用下列標準：</span><span class="sxs-lookup"><span data-stu-id="adbb8-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="adbb8-135">[RFC 5245 互動式連接建立 (ICE) 媒體旁路。](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="adbb8-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="adbb8-136">SBC 必須支援下列專案：</span><span class="sxs-lookup"><span data-stu-id="adbb8-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="adbb8-137">ICE Lite - Teams是完整的 ICE 用戶端</span><span class="sxs-lookup"><span data-stu-id="adbb8-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="adbb8-138">[ICE 會重新開機](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="adbb8-139">在 ICE 重新開機中查看更多有關 ICE 重新開機使用案例和範例：媒體旁路通話轉接到不支援媒體旁路的端點</span><span class="sxs-lookup"><span data-stu-id="adbb8-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="adbb8-140">[RFC RFC 5589 會話初始通訊協定 (SIP) 呼叫控制 – 傳輸](https://tools.ietf.org/html/rfc5589)。</span><span class="sxs-lookup"><span data-stu-id="adbb8-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="adbb8-141">[在會話初始通訊協定 (SIP) 中，RFC 3960 ](https://tools.ietf.org/html/rfc3960)早期媒體和鈴聲產生，請參閱第 3.1 節、Forking 和 3.2 節 ，鈴聲產生</span><span class="sxs-lookup"><span data-stu-id="adbb8-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="adbb8-142">RFC 5389 會話橫向公用程式適用于 NAT (STUN) </span><span class="sxs-lookup"><span data-stu-id="adbb8-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="adbb8-143">RFC 5766 在 NAT 周圍使用轉 (轉) ：將延伸模組轉傳至 NAT (STUN) </span><span class="sxs-lookup"><span data-stu-id="adbb8-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="adbb8-144">適用于支援將位置資訊傳達給 E911 提供者的標準</span><span class="sxs-lookup"><span data-stu-id="adbb8-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="adbb8-145">RFC 6442，會話初始通訊協定的位置傳輸</span><span class="sxs-lookup"><span data-stu-id="adbb8-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="adbb8-146">與 RFC 的偏差</span><span class="sxs-lookup"><span data-stu-id="adbb8-146">Deviations from the RFC's</span></span>

<span data-ttu-id="adbb8-147">下表列出 RFC 協定 (區段) 其中 Microsoft 的 SIP 或媒體堆疊的實現與標準有偏差：</span><span class="sxs-lookup"><span data-stu-id="adbb8-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="adbb8-148">RFC 和節</span><span class="sxs-lookup"><span data-stu-id="adbb8-148">RFC and sections</span></span> | <span data-ttu-id="adbb8-149">描述</span><span class="sxs-lookup"><span data-stu-id="adbb8-149">Description</span></span> | <span data-ttu-id="adbb8-150">偏差</span><span class="sxs-lookup"><span data-stu-id="adbb8-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="adbb8-151">RFC 6337，第 5.3 節媒體保留與履歷表</span><span class="sxs-lookup"><span data-stu-id="adbb8-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="adbb8-152">RFC 允許使用"a=非使用中"、"a=sendonly"、a=recvonly"來保留通話。</span><span class="sxs-lookup"><span data-stu-id="adbb8-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="adbb8-153">SIP Proxy 僅支援「a=非使用中」，且不了解 SBC 是傳送「a=sendonly」或「a=revonly」。</span><span class="sxs-lookup"><span data-stu-id="adbb8-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="adbb8-154">RFC 6337，第 5.4 節「使用 c=0.0.0.0.0 接收 SDP 的行為</span><span class="sxs-lookup"><span data-stu-id="adbb8-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="adbb8-155">[RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理程式能夠接收具有 0.0.0.0.0 之連接位址的 SDP，在這種情況下，這表示不應將 RTP 或 RTCP 送往對等電腦。</span><span class="sxs-lookup"><span data-stu-id="adbb8-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="adbb8-156">SIP Proxy 不支援此選項。</span><span class="sxs-lookup"><span data-stu-id="adbb8-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="adbb8-157">操作模式</span><span class="sxs-lookup"><span data-stu-id="adbb8-157">Operational modes</span></span>

<span data-ttu-id="adbb8-158">直接路由有兩種操作模式：</span><span class="sxs-lookup"><span data-stu-id="adbb8-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="adbb8-159">**沒有媒體旁** 路，所有 RTP 流量Teams用戶端、媒體處理器和 SBC 之間流動。</span><span class="sxs-lookup"><span data-stu-id="adbb8-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="adbb8-160">**當媒體旁** 路時，所有 RTP 媒體Teams端點和 SBC 之間流動。</span><span class="sxs-lookup"><span data-stu-id="adbb8-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="adbb8-161">請注意，SIP 流量一直透過 SIP Proxy 流動。</span><span class="sxs-lookup"><span data-stu-id="adbb8-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="adbb8-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="adbb8-162">DTMF</span></span>
<span data-ttu-id="adbb8-163">媒體堆疊不支援帶內 DTMF。</span><span class="sxs-lookup"><span data-stu-id="adbb8-163">In-band DTMF is not supported by media stack.</span></span>
