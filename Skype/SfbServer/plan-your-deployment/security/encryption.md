---
title: 商務用 Skype Server 的加密
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商務用 Skype Server 使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。 將商務用 Skype 伺服器連接到協力廠商 IPPBX 系統或 SIP 主幹 TLS 是選用的，但強烈建議在轉送伺服器和媒體閘道之間進行。 如果在此連結上設定 TLS，則需要 MTLS。 因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。
ms.openlocfilehash: 269a5394f5438802c68dabed17081c71a353a2b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104229"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="df100-107">商務用 Skype Server 的加密</span><span class="sxs-lookup"><span data-stu-id="df100-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="df100-108">商務用 Skype Server 使用 TLS 和 MTLS 來加密立即訊息。</span><span class="sxs-lookup"><span data-stu-id="df100-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="df100-109">不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="df100-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="df100-110">將商務用 Skype 伺服器連接至協力廠商 IPPBX 系統或 SIP 主幹 TLS 是選用的，但強烈建議在轉送伺服器和媒體閘道之間進行。</span><span class="sxs-lookup"><span data-stu-id="df100-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="df100-111">如果在此連結上設定 TLS，則需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="df100-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="df100-112">因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。</span><span class="sxs-lookup"><span data-stu-id="df100-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df100-113">有關 SSL 3.0 的安全性通報已在2014中發佈。</span><span class="sxs-lookup"><span data-stu-id="df100-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="df100-114">在商務用 Skype Server 2015 中停用 SSL 3.0 是支援的選項。</span><span class="sxs-lookup"><span data-stu-id="df100-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="df100-115">若要深入瞭解安全性通報，請參閱 [在 Lync server 2013 和商務用 Skype server 2015 中停用 SSL 3.0](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="df100-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013).</span></span><br/>
<span data-ttu-id="df100-116">**安全性附注：** 為了確保使用最強的加密通訊協定，商務用 Skype Server 2015 會依照下列順序為用戶端提供 TLS 加密通訊協定： **tls 1.2，tls 1.1，tls 1.0**。</span><span class="sxs-lookup"><span data-stu-id="df100-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="df100-117">TLS 是商務用 Skype Server 2015 的重要層面，因此必須用來維護支援的環境。</span><span class="sxs-lookup"><span data-stu-id="df100-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="df100-118">**安全性附注：** 為了確保使用最強的加密通訊協定，商務用 Skype Server 2019 會依照下列順序為用戶端提供 TLS 加密通訊協定： **tls 1.3，tls 1.2**。</span><span class="sxs-lookup"><span data-stu-id="df100-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="df100-119">TLS 是商務用 Skype Server 2019 的重要層面，因此必須用來維護支援的環境。</span><span class="sxs-lookup"><span data-stu-id="df100-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="df100-120">下表摘要說明每一種流量類型的通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="df100-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="df100-121">**流量保護**</span><span class="sxs-lookup"><span data-stu-id="df100-121">**Traffic Protection**</span></span>

|<span data-ttu-id="df100-122">**流量類型**</span><span class="sxs-lookup"><span data-stu-id="df100-122">**Traffic type**</span></span>|<span data-ttu-id="df100-123">**提供保護的通訊協定**</span><span class="sxs-lookup"><span data-stu-id="df100-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df100-124">伺服器對伺服器</span><span class="sxs-lookup"><span data-stu-id="df100-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="df100-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="df100-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="df100-126">用戶端對伺服器</span><span class="sxs-lookup"><span data-stu-id="df100-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="df100-127">TLS</span><span class="sxs-lookup"><span data-stu-id="df100-127">TLS</span></span>  <br/> |
|<span data-ttu-id="df100-128">立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="df100-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="df100-129">TLS</span><span class="sxs-lookup"><span data-stu-id="df100-129">TLS</span></span>  <br/> |
|<span data-ttu-id="df100-130">音訊和視訊及媒體的桌面共用</span><span class="sxs-lookup"><span data-stu-id="df100-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="df100-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="df100-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="df100-132">桌面共用 (訊號)</span><span class="sxs-lookup"><span data-stu-id="df100-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="df100-133">TLS</span><span class="sxs-lookup"><span data-stu-id="df100-133">TLS</span></span>  <br/> |
|<span data-ttu-id="df100-134">Web 會議</span><span class="sxs-lookup"><span data-stu-id="df100-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="df100-135">TLS</span><span class="sxs-lookup"><span data-stu-id="df100-135">TLS</span></span>  <br/> |
|<span data-ttu-id="df100-136">會議內容下載、通訊錄下載、通訊群組擴充</span><span class="sxs-lookup"><span data-stu-id="df100-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="df100-137">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="df100-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="df100-138">媒體加密</span><span class="sxs-lookup"><span data-stu-id="df100-138">Media Encryption</span></span>

<span data-ttu-id="df100-139">媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。</span><span class="sxs-lookup"><span data-stu-id="df100-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="df100-140">此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。</span><span class="sxs-lookup"><span data-stu-id="df100-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="df100-141">轉送伺服器和媒體閘道之間的兩種方向的媒體都是可選擇性地加密及建議的。</span><span class="sxs-lookup"><span data-stu-id="df100-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="df100-142">中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。</span><span class="sxs-lookup"><span data-stu-id="df100-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df100-143">如需設定混合式的詳細資訊，請參閱 [規劃混合](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)式連線。</span><span class="sxs-lookup"><span data-stu-id="df100-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="df100-144">Fips</span><span class="sxs-lookup"><span data-stu-id="df100-144">FIPS</span></span>

<span data-ttu-id="df100-145">商務用 Skype Server 和 Microsoft Exchange Server 2016 的運作方式支援聯邦資訊處理標準 (FIPS) 140-2 演算法（如果 Windows Server 作業系統設定為使用 FIPS 140-2 演算法進行系統加密）。</span><span class="sxs-lookup"><span data-stu-id="df100-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="df100-146">若要實施 FIPS 支援，您必須設定每台執行商務用 Skype Server 的伺服器，以支援。</span><span class="sxs-lookup"><span data-stu-id="df100-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
