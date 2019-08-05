---
title: 商務用 Skype Server 的加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商務用 Skype 伺服器使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或交叉對內部網路周邊, 所有伺服器對伺服器的流量都必須是 MTLS。 將商務用 Skype Server 連線至協力廠商 IPPBX 系統或 SIP trunks TLS 是選擇性的, 但強烈建議在中繼伺服器與媒體閘道之間進行。 如果在此連結上設定 TLS, 則需要 MTLS。 因此, 閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192945"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="936b9-107">商務用 Skype Server 的加密</span><span class="sxs-lookup"><span data-stu-id="936b9-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="936b9-108">商務用 Skype 伺服器使用 TLS 和 MTLS 來加密立即訊息。</span><span class="sxs-lookup"><span data-stu-id="936b9-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="936b9-109">不論流量是限制在內部網路或交叉對內部網路周邊, 所有伺服器對伺服器的流量都必須是 MTLS。</span><span class="sxs-lookup"><span data-stu-id="936b9-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="936b9-110">將商務用 Skype Server 連線至協力廠商 IPPBX 系統或 SIP trunks TLS 是選擇性的, 但強烈建議在中繼伺服器與媒體閘道之間進行。</span><span class="sxs-lookup"><span data-stu-id="936b9-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="936b9-111">如果在此連結上設定 TLS, 則需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="936b9-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="936b9-112">因此, 閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。</span><span class="sxs-lookup"><span data-stu-id="936b9-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="936b9-113">已在2014中發佈有關 SSL 3.0 的安全性通知。</span><span class="sxs-lookup"><span data-stu-id="936b9-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="936b9-114">在商務用 Skype Server 2015 中停用 SSL 3.0 是受支援的選項。</span><span class="sxs-lookup"><span data-stu-id="936b9-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="936b9-115">若要深入瞭解安全性建議, 請參閱[在 Lync server 2013 和商務用 Skype server 2015 中停用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。</span><span class="sxs-lookup"><span data-stu-id="936b9-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="936b9-116">**安全性注意事項:** 為了確保使用最強的加密通訊協定, 商務用 Skype Server 2015 將以下列順序向用戶端提供 TLS 加密通訊協定: **tls 1.2、tls 1.1、TLS 1.0**。</span><span class="sxs-lookup"><span data-stu-id="936b9-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="936b9-117">TLS 是商務用 Skype Server 2015 的一個重要層面, 因此需要維持支援的環境。</span><span class="sxs-lookup"><span data-stu-id="936b9-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="936b9-118">**安全性注意事項:** 為了確保使用最強的加密通訊協定, 商務用 Skype Server 2019 將以下列順序向用戶端提供 TLS 加密通訊協定: **tls 1.3、tls 1.2**。</span><span class="sxs-lookup"><span data-stu-id="936b9-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="936b9-119">TLS 是商務用 Skype Server 2019 的一個重要層面, 因此需要維持支援的環境。</span><span class="sxs-lookup"><span data-stu-id="936b9-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="936b9-120">下表摘要列出每種通信量類型的通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="936b9-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="936b9-121">**交通防護**</span><span class="sxs-lookup"><span data-stu-id="936b9-121">**Traffic Protection**</span></span>

|<span data-ttu-id="936b9-122">**流量類型**</span><span class="sxs-lookup"><span data-stu-id="936b9-122">**Traffic type**</span></span>|<span data-ttu-id="936b9-123">**受**</span><span class="sxs-lookup"><span data-stu-id="936b9-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="936b9-124">伺服器與伺服器</span><span class="sxs-lookup"><span data-stu-id="936b9-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="936b9-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="936b9-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="936b9-126">用戶端到伺服器</span><span class="sxs-lookup"><span data-stu-id="936b9-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="936b9-127">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="936b9-127">TLS</span></span>  <br/> |
|<span data-ttu-id="936b9-128">立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="936b9-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="936b9-129">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="936b9-129">TLS</span></span>  <br/> |
|<span data-ttu-id="936b9-130">媒體的音訊和影片與桌面共用</span><span class="sxs-lookup"><span data-stu-id="936b9-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="936b9-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="936b9-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="936b9-132">桌面共用 (信號)</span><span class="sxs-lookup"><span data-stu-id="936b9-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="936b9-133">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="936b9-133">TLS</span></span>  <br/> |
|<span data-ttu-id="936b9-134">網路會議</span><span class="sxs-lookup"><span data-stu-id="936b9-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="936b9-135">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="936b9-135">TLS</span></span>  <br/> |
|<span data-ttu-id="936b9-136">會議內容下載、通訊錄下載、通訊群組延伸</span><span class="sxs-lookup"><span data-stu-id="936b9-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="936b9-137">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="936b9-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="936b9-138">媒體加密</span><span class="sxs-lookup"><span data-stu-id="936b9-138">Media Encryption</span></span>

<span data-ttu-id="936b9-139">媒體流量是使用安全的 RTP (SRTP) 來加密, 這是一種即時傳輸通訊協定 (RTP) 設定檔, 可為 RTP 流量提供保密性、驗證及重放攻擊保護。</span><span class="sxs-lookup"><span data-stu-id="936b9-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="936b9-140">此外, 在中繼伺服器與其內部下一個躍點之間的兩個方向上, 媒體也會使用 SRTP 來加密。</span><span class="sxs-lookup"><span data-stu-id="936b9-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="936b9-141">在中繼伺服器與媒體閘道之間的兩個方向上, 媒體的流動方式都有選擇性地加密及建議。</span><span class="sxs-lookup"><span data-stu-id="936b9-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="936b9-142">中繼伺服器可以支援對媒體閘道進行加密, 但閘道必須支援 MTLS 和儲存憑證。</span><span class="sxs-lookup"><span data-stu-id="936b9-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="936b9-143">如需設定混合式混合式的詳細資訊, 請參閱[規劃混合式連線性](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="936b9-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="936b9-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="936b9-144">FIPS</span></span>

<span data-ttu-id="936b9-145">商務用 Skype Server 和 Microsoft Exchange Server 2016 的運作方式支援聯邦資訊處理標準 (FIPS) 140-2 演算法 (如果 Windows 伺服器作業系統已設定為使用 FIPS 140-2 演算法進行系統加密).</span><span class="sxs-lookup"><span data-stu-id="936b9-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="936b9-146">若要實現 FIPS 支援, 您必須設定執行商務用 Skype Server 的每個伺服器以支援它。</span><span class="sxs-lookup"><span data-stu-id="936b9-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

