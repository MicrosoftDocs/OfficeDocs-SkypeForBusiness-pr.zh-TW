---
title: 最佳化您的網路
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 下列需求對於確保您為組織所設定之所有線上功能商務用 Skype健康狀態和成功非常重要。 我們知道有些人很技術，這份檔是適合您的，但有些則不是。 如果您需要協助設定線上商務用 Skype，您應該閱讀這份檔，以熟悉您需要考慮的內容。 當您與 Microsoft FastTrack 中心、您的 Microsoft Services 和帳戶小組合作，或與 Microsoft 合作夥伴合作時，或與 Microsoft 合作夥伴合作，瞭解如何符合這些需求時，它也提供您討論的問題。
ms.openlocfilehash: a32e7864a15945fc9bad64c12466aa376cb924f9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240223"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a><span data-ttu-id="16478-106">優化您的網路以商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="16478-106">Optimizing your network for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="16478-107">下列需求對於確保您為組織所設定之所有線上功能商務用 Skype健康狀態和成功非常重要。</span><span class="sxs-lookup"><span data-stu-id="16478-107">The following requirements are really important to ensure the long-term health and success for all Skype for Business Online features you are setting up for your organization.</span></span> <span data-ttu-id="16478-108">我們知道有些人很技術，這份檔是適合您的，但有些則不是。</span><span class="sxs-lookup"><span data-stu-id="16478-108">We know some of you are very technical - this document is for you, but there are some of you that aren't.</span></span> <span data-ttu-id="16478-109">如果您需要協助設定線上商務用 Skype，您應該閱讀這份檔，以熟悉您需要考慮的內容。</span><span class="sxs-lookup"><span data-stu-id="16478-109">If you need help setting up Skype for Business Online, you should read this document to become familiar with the things you need to consider.</span></span> <span data-ttu-id="16478-110">當您與 [Microsoft FastTrack](https://fasttrack.microsoft.com/office)中心、您的 Microsoft Services 和帳戶小組合作，或與 Microsoft 合作夥伴合作時，或與 [Microsoft](https://partnercenter.microsoft.com/pcv/search) 合作夥伴合作時，也會提供您一些可以討論的問題。</span><span class="sxs-lookup"><span data-stu-id="16478-110">It will also give you things to talk about when you are working with the [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), your Microsoft Services and account teams, or with [Microsoft partners](https://partnercenter.microsoft.com/pcv/search) to figure out how you can meet these requirements.</span></span>

## <a name="a-quick-overview"></a><span data-ttu-id="16478-111">快速概觀</span><span class="sxs-lookup"><span data-stu-id="16478-111">A quick overview</span></span>

<span data-ttu-id="16478-112">商務用 Skype可讓您與公司或世界各地的同事或商務合作夥伴聯繫。</span><span class="sxs-lookup"><span data-stu-id="16478-112">Skype for Business lets you connect with co-workers or business partners in your company or around the world.</span></span>

<span data-ttu-id="16478-113">使用 商務用 Skype，您可以：</span><span class="sxs-lookup"><span data-stu-id="16478-113">With Skype for Business, you can:</span></span>

- <span data-ttu-id="16478-114">使用 IM、語音或視音訊通話開始交談。</span><span class="sxs-lookup"><span data-stu-id="16478-114">Start conversations with IM, voice, or video calls.</span></span>

- <span data-ttu-id="16478-115">查看您的連絡人何時可在線上、會議或進行展示。</span><span class="sxs-lookup"><span data-stu-id="16478-115">See when your contacts are available online, in a meeting, or presenting.</span></span>

- <span data-ttu-id="16478-116">設定會議的產業強度安全性。</span><span class="sxs-lookup"><span data-stu-id="16478-116">Set industrial-strength security for meetings.</span></span>

- <span data-ttu-id="16478-117">線上廣播給大量觀眾。</span><span class="sxs-lookup"><span data-stu-id="16478-117">Broadcast online to a large audience.</span></span>

- <span data-ttu-id="16478-118">在會議期間展示您的螢幕畫面，或將控制權授予其他人。</span><span class="sxs-lookup"><span data-stu-id="16478-118">Present your screen during meetings or give control to others.</span></span>

- <span data-ttu-id="16478-119">在商務用 Skype程式中Office聊天、通話或加入會議。</span><span class="sxs-lookup"><span data-stu-id="16478-119">Use Skype for Business in other Office programs to chat, call, or join a meeting with a click.</span></span>

## <a name="why-is-this-all-so-important"></a><span data-ttu-id="16478-120">為什麼這一切這麼重要？</span><span class="sxs-lookup"><span data-stu-id="16478-120">Why is this all so important?</span></span>

<span data-ttu-id="16478-121">即時媒體的品質 (IP 上) 音訊、視視及應用程式共用的品質受到端對端網路連接品質的嚴重影響。</span><span class="sxs-lookup"><span data-stu-id="16478-121">The quality of real-time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="16478-122">若要商務用 Skype線上媒體質量，請務必確定公司網路與線上媒體之間商務用 Skype連線。</span><span class="sxs-lookup"><span data-stu-id="16478-122">For optimal Skype for Business Online media quality, it is important for you to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="16478-123">最好的方法就是根據網路容量來設定內部網路和雲端連線，以容納所有連線中 商務用 Skype Online 的尖峰流量。</span><span class="sxs-lookup"><span data-stu-id="16478-123">The best way to accomplish this is to set up your internal network and cloud connectivity based on the capacity of your network to accommodate for peak traffic volume for Skype for Business Online across all connections.</span></span>

<span data-ttu-id="16478-124">您可以與[Microsoft](https://partnercenter.microsoft.com/pcv/search)合作夥伴合作，將各種 Microsoft 365 或 Office 365 應用程式 ，包括雲端中的 商務用 Skype Online 連線到您的網路，而 商務用 Skype 即時語音和視訊通訊功能則要求網路服務必須特別配置，以支援這些 Microsoft 365 和 Office 365 即時工作負載。</span><span class="sxs-lookup"><span data-stu-id="16478-124">Working with a [Microsoft partner](https://partnercenter.microsoft.com/pcv/search), you can connect a variety of Microsoft 365 or Office 365 applications including Skype for Business Online in the cloud to your network and real-time voice and video communications capabilities for Skype for Business require network services must be specifically configured to support these Microsoft 365 and Office 365 real-time workloads.</span></span> <span data-ttu-id="16478-125">這包括頻寬足以承載所需流量的網路，且能夠支援服務品質 (QoS) ，為使用者供應商務課程體驗。</span><span class="sxs-lookup"><span data-stu-id="16478-125">This includes a network that has sufficient bandwidth to carry the required volume of traffic and be capable of supporting Quality of Service (QoS) to deliver a business class experience for your users.</span></span>

<span data-ttu-id="16478-126">除了此處的資訊，還有其他資源可協助您成功規劃及部署商務用 Skype線上服務和功能，並確保您的網路服務符合這些要求：</span><span class="sxs-lookup"><span data-stu-id="16478-126">Along with the information here, there are other resources that can help you successfully plan and deploy Skype for Business Online services and features and to ensure that your network services meet those requirements:</span></span>

- [<span data-ttu-id="16478-127">使用 ExpressRoute 的通話流程</span><span class="sxs-lookup"><span data-stu-id="16478-127">Call flow using ExpressRoute</span></span>](call-flow-using-expressroute.md)

- [<span data-ttu-id="16478-128">商務用 Skype Online 中的 ExpressRoute 與 QoS</span><span class="sxs-lookup"><span data-stu-id="16478-128">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)

- [<span data-ttu-id="16478-129">線上媒體質量與網路連線商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="16478-129">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a><span data-ttu-id="16478-130">針對服務 (QoS) 服務品質商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="16478-130">Implement Quality of Service (QoS) for Skype for Business</span></span>

<span data-ttu-id="16478-131">在移商務用 Skype Online 之前，您應該先看看您的網路處理音訊、視視和共用會話流量的能力。</span><span class="sxs-lookup"><span data-stu-id="16478-131">Before moving to Skype for Business Online, you should take a look at your network's capacity to handle audio, video and sharing session traffic.</span></span> <span data-ttu-id="16478-132">與其他Microsoft 365 Office 365服務一樣，Microsoft 也提供下載[商務用 Skype](https://www.microsoft.com/download/details.aspx?id=19011)頻寬計算機，用來判斷每個公司網站所需的網路流量。</span><span class="sxs-lookup"><span data-stu-id="16478-132">As with other Microsoft 365 and Office 365 services, Microsoft has available for download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011) that's used to determine the required network traffic for each of your company sites.</span></span> <span data-ttu-id="16478-133">您應該執行使用方式模型，包括建立即時通訊流量媒體流量模型，以及每個公司位置的 商務用 Skype 流量量、計算流量，以及分析流量如何影響整體網路。</span><span class="sxs-lookup"><span data-stu-id="16478-133">You should perform usage modeling, including modeling real-time communication traffic media flows and the amount of Skype for Business traffic per company location, calculating traffic volume, and analyzing how that traffic impacts your overall network.</span></span> <span data-ttu-id="16478-134">完成之後，分析此資料應提供網路需要改善的位置建議，並建議佇列大小，以提供絕佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="16478-134">After you've done that, analysis of this data should provide recommendations of where your network needs to be improved and recommend queue sizes in order to provide an excellent end user experience.</span></span>

<span data-ttu-id="16478-135">商務用 Skype流量對封包遺失、延遲和抖動十分敏感，這些在塞塞網路中經常發生。</span><span class="sxs-lookup"><span data-stu-id="16478-135">Skype for Business real-time traffic is sensitive to packet loss, delay and jitter, which occur frequently in congested networks.</span></span> <span data-ttu-id="16478-136">服務品質 (QoS) 也稱為服務類別 -也必須部署在受管理的外部 WAN、受管理的內部 LANs 和企業型 WiFi 網路上。</span><span class="sxs-lookup"><span data-stu-id="16478-136">Quality of Service (QoS) - sometimes called Class of Service - must also be deployed on managed external WANs, managed internal LANs, and enterprise-based WiFi networks.</span></span> <span data-ttu-id="16478-137">這可協助正確商務用 Skype即時流量的優先順序，例如音訊和視音訊，而超過本地網路和 WAN 的其他非即時流量，為使用者創造更好的體驗。</span><span class="sxs-lookup"><span data-stu-id="16478-137">This will help to properly prioritize Skype for Business real-time traffic such as audio and video over other non-real time traffic on local networks and over WAN, creating a better experience for end users.</span></span>

<span data-ttu-id="16478-138">商務用 Skype音訊必須部署在 EF (快速轉轉 - DSCP 46) 佇列和 商務用 Skype 影片中必須部署在 AF41 (保證轉轉 - DSCP 34) 佇列中。</span><span class="sxs-lookup"><span data-stu-id="16478-138">Skype for Business audio must be deployed in the EF (Expedited Forwarding - DSCP 46) queue and Skype for Business video must be deployed in the AF41 (Assured Forwarding - DSCP 34) queue.</span></span> <span data-ttu-id="16478-139">即使對等和會議流量也是如此，無論 電話系統 或 Microsoft 365 Office 365 或其他電話功能是否部署。</span><span class="sxs-lookup"><span data-stu-id="16478-139">This is true even for peer-to-peer and conferencing traffic, regardless of whether Phone System in Microsoft 365 or Office 365 or other telephony features are being deployed.</span></span>

<span data-ttu-id="16478-140">雖然其他 IP 電話產品的 LAN 和 WAN 中可能已經有現有的 QoS 政策，商務用 Skype 可讓使用者在使用服務時行動，以及從位置移至不同位置。</span><span class="sxs-lookup"><span data-stu-id="16478-140">While existing QoS policies might be in place already on the LAN and WAN for other IP telephony products, Skype for Business allows users to be mobile and to move from location to location while using the service.</span></span> <span data-ttu-id="16478-141">因此，QoS 策略必須在 LAN、WAN 和無線網路上標示，以確保所有流量商務用 Skype管理網路優先處理。</span><span class="sxs-lookup"><span data-stu-id="16478-141">Because of this, QoS policies must be marked on the LAN, WAN and wireless networks in order to be sure that all Skype for Business traffic is being prioritized across managed networks.</span></span>

<span data-ttu-id="16478-142">若要協助調整網路大小，請下載 商務用 Skype[計算機](https://www.microsoft.com/download/details.aspx?id=19011)。</span><span class="sxs-lookup"><span data-stu-id="16478-142">To help you will sizing your network, download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011).</span></span>

<span data-ttu-id="16478-143">有關媒體質量和 QoS 的更多資訊，請參閱 商務用 Skype [Online 中的媒體質量和網路連線商務用 Skype。](media-quality-and-network-connectivity-performance.md)</span><span class="sxs-lookup"><span data-stu-id="16478-143">For more about media quality and QoS, see [Media Quality and Network Connectivity Performance in Skype for Business Online](media-quality-and-network-connectivity-performance.md).</span></span>

<span data-ttu-id="16478-144">有關設定及管理 QoS 的更多資訊，請參閱 [管理服務品質](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16478-144">For more about setting up and managing QoS, see [Managing Quality of Service](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md).</span></span>

## <a name="bypass-proxies-and-wan-optimization-devices"></a><span data-ttu-id="16478-145">忽略代理和 WAN 優化裝置</span><span class="sxs-lookup"><span data-stu-id="16478-145">Bypass proxies and WAN optimization devices</span></span>

<span data-ttu-id="16478-146">所有Microsoft 365或Office 365線上商務用 Skype加密，通常無法由 Proxy 裝置檢查。</span><span class="sxs-lookup"><span data-stu-id="16478-146">All Microsoft 365 or Office 365 including Skype for Business Online is encrypted and is typically not able to be inspected by proxy devices.</span></span> <span data-ttu-id="16478-147">基於這些原因，我們建議您忽略所有 Microsoft 365 和 Office 365 的 Proxy 裝置，定義為使用者與 Office 365 URL 和 IP 位址[範圍之間的連結](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="16478-147">For these reasons we recommend bypassing proxy devices for all Microsoft 365 and Office 365 network traffic as defined as connections your users make to [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> <span data-ttu-id="16478-148">由於 Proxy 裝置可能會延遲即時商務用 Skype線上媒體流，我們強烈建議您至少忽略該流量的 Proxy 裝置。</span><span class="sxs-lookup"><span data-stu-id="16478-148">Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.</span></span>

<span data-ttu-id="16478-149">Microsoft 建議排除Microsoft 365 Office 365使用 PAC 檔案傳送Microsoft 365 Office 365流量到防火牆的 URL。</span><span class="sxs-lookup"><span data-stu-id="16478-149">Microsoft recommends excluding Microsoft 365 and Office 365 URLs using PAC files to send Microsoft 365 and Office 365 traffic to a firewall.</span></span>

<span data-ttu-id="16478-150">以下是一些可協助的可用資源：</span><span class="sxs-lookup"><span data-stu-id="16478-150">Here are some available resources that can help too:</span></span>

- [<span data-ttu-id="16478-151">Microsoft 365比較Office 365比較基準與績效歷程記錄來調整或調整績效</span><span class="sxs-lookup"><span data-stu-id="16478-151">Microsoft 365 or Office 365 performance tuning using baselines and performance history</span></span>](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [<span data-ttu-id="16478-152">適用于或移Microsoft 365的網路Office 365</span><span class="sxs-lookup"><span data-stu-id="16478-152">Network and migration planning for Microsoft 365 or Office 365</span></span>](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [<span data-ttu-id="16478-153">Office 365Proxy Pac 產生器</span><span class="sxs-lookup"><span data-stu-id="16478-153">Office 365 Proxy Pac generator</span></span>](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [<span data-ttu-id="16478-154">使用 WAN 優化控制器或流量/檢查裝置Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="16478-154">Using WAN Optimization Controller or Traffic/Inspection devices with Microsoft 365 or Office 365</span></span>](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [<span data-ttu-id="16478-155">使用 ExpressRoute 路由Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="16478-155">Routing with ExpressRoute for Microsoft 365 or Office 365</span></span>](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a><span data-ttu-id="16478-156">忽略雙加密</span><span class="sxs-lookup"><span data-stu-id="16478-156">Bypass double encryption</span></span>

<span data-ttu-id="16478-157">若要為使用者提供最佳的音訊和視視體驗，您必須執行解決方案，防止 商務用 Skype 媒體 (音訊和視) 穿過虛擬私人網路絡 (VPN) 管道。</span><span class="sxs-lookup"><span data-stu-id="16478-157">To provide users the best possible audio and video experience, you must implement a solution that prevents Skype for Business media (audio and video) from traversing a Virtual Private Network (VPN) tunnel.</span></span> <span data-ttu-id="16478-158">所有商務用 Skype流量都是使用傳輸層安全性 (TLS) 加密，而媒體工作負載會使用安全即時通訊協定 (SRTP) 。</span><span class="sxs-lookup"><span data-stu-id="16478-158">All Skype for Business traffic is encrypted with Transport Layer Security (TLS) and the media workloads are encrypted with Secure Real Time Protocol (SRTP).</span></span> <span data-ttu-id="16478-159">訊號會使用 TLS 加密，而媒體工作負載會以 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="16478-159">Signaling is encrypted with TLS and the media workloads are encrypted with SRTP.</span></span> <span data-ttu-id="16478-160">在 VPN 管道傳送此流量會增加額外的加密層，以及用戶端與 Microsoft 365 或 Office 365 之間的額外網路躍點，這兩者都可能會導致會話降級，因為這會增加抖動、封包遺失和延遲。</span><span class="sxs-lookup"><span data-stu-id="16478-160">Sending this traffic over the VPN tunnel adds an extra layer of encryption, and additional network hops between the client and Microsoft 365 or Office 365, both of which can result in a degraded session because it increases jitter, packet loss and latency.</span></span>

<span data-ttu-id="16478-161">防止流量商務用 Skype VPN 管道的其中一個選項是分割管道。</span><span class="sxs-lookup"><span data-stu-id="16478-161">One option to prevent Skype for Business traffic from traversing the VPN tunnel is Split Tunneling.</span></span> <span data-ttu-id="16478-162">若要執行分割-分流，客戶應諮詢其 VPN 廠商如何在其軟體中執行此操作的具體資料。</span><span class="sxs-lookup"><span data-stu-id="16478-162">To implement split-tunneling, customers should consult with their VPN vendor on the specifics of how to do this in their software.</span></span>

> [!NOTE]
> <span data-ttu-id="16478-163">這僅適用于商務用 Skype工作負載，不適用於其他Microsoft 365或Office 365服務。</span><span class="sxs-lookup"><span data-stu-id="16478-163">This is only required for the Skype for Business media workloads and isn't applicable to other Microsoft 365 or Office 365 services.</span></span>

<span data-ttu-id="16478-164">其他資源：</span><span class="sxs-lookup"><span data-stu-id="16478-164">Additional resources:</span></span>

- [<span data-ttu-id="16478-165">啟用 Lync Media 以忽略 VPN Tunnel</span><span class="sxs-lookup"><span data-stu-id="16478-165">Enabling Lync Media to Bypass a VPN Tunnel</span></span>](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [<span data-ttu-id="16478-166">更多有關直接存取、分割管道和強制管道</span><span class="sxs-lookup"><span data-stu-id="16478-166">More on Direct Access, Split Tunneling and Force Tunneling</span></span>](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- <span data-ttu-id="16478-167">[啟用直接存取](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="16478-167">[Enable Direct Access](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))</span></span>

## <a name="ensure-the-right-ports-and-protocols-are-open"></a><span data-ttu-id="16478-168">確保已開啟正確的埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="16478-168">Ensure the right ports and protocols are open</span></span>

<span data-ttu-id="16478-169">客戶必須確保服務或服務所需的 URL 和 IP 位址Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="16478-169">Customers must ensure reachability of the URLs and IP addresses that are required for the Microsoft 365 or Office 365 service.</span></span> <span data-ttu-id="16478-170">有關線上版的所有 IP 位址和 URL 的完整商務用 Skype，請參閱OFFICE 365 URL 和[IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="16478-170">For a complete listing of all IP addresses and URLs for Skype for Business Online, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

<span data-ttu-id="16478-171">商務用 Skype用戶端會使用各種埠和通訊協定。</span><span class="sxs-lookup"><span data-stu-id="16478-171">Skype for Business clients use a variety of ports and protocols.</span></span> <span data-ttu-id="16478-172">商務用 Skype 會話的網路流量方向和流程會因互動類型 (對等與多方) 以及內容共用和語音/視像的使用而有所差異。</span><span class="sxs-lookup"><span data-stu-id="16478-172">The direction and flow of network traffic for a Skype for Business session will vary depending on the type of interactions (peer-to-peer vs multiparty) and depending on the use of content sharing and voice/video.</span></span> <span data-ttu-id="16478-173">您必須檢查並開啟埠和通訊協定清單，並特別注意來源和目的地埠。</span><span class="sxs-lookup"><span data-stu-id="16478-173">You must review and open the list of ports and protocols, paying special attention to the source and destination ports.</span></span> <span data-ttu-id="16478-174">例如，音訊流量在用戶端只使用 20 個埠 (50000-50019 TCP/UDP) ，但目的地埠可能位於 10K 埠範圍 (50000-59999 TCP/UDP) 服務端的任何位置。</span><span class="sxs-lookup"><span data-stu-id="16478-174">For example, audio traffic uses just 20 ports (50000-50019 TCP/UDP) at the client side, but the destination port could be anywhere in a 10K port range (50000-59999 TCP/UDP) at the service side.</span></span> <span data-ttu-id="16478-175">這也包括在防火牆上開啟 TCP 443 和 UDP 3478。</span><span class="sxs-lookup"><span data-stu-id="16478-175">This also includes opening TCP 443 and UDP 3478 on the firewall.</span></span>

<span data-ttu-id="16478-176">可能需要其他網路組組才能支援 商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="16478-176">Additional network configuration might also be required to support Skype for Business Online.</span></span>


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a><span data-ttu-id="16478-177">使用針對手機和裝置優化商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="16478-177">Use Phones and Devices Optimized for Skype for Business</span></span>

<span data-ttu-id="16478-178">在即時媒體會話中，所有參與者使用的媒體裝置 ，例如耳機和網路相機，對整體音訊和視音訊品質有很大的影響。</span><span class="sxs-lookup"><span data-stu-id="16478-178">In a real-time media session, media devices that are used by all participants such as headsets and web cams have a great impact on the overall audio and video quality.</span></span> <span data-ttu-id="16478-179">品質較低的裝置或裝置，如果裝置磁碟機不正確，則會產生較低的音訊整體音效品質，以及較低的視像品質。</span><span class="sxs-lookup"><span data-stu-id="16478-179">Lower-quality devices or devices with incorrect device drivers will produce lower overall sound quality for audio and lower image quality for video.</span></span> <span data-ttu-id="16478-180">另一方面，經過認證的裝置或品質良好的裝置可協助消除回音、雜訊篩選、視像解析度並減少延遲。</span><span class="sxs-lookup"><span data-stu-id="16478-180">Certified devices or good quality devices, on the other hand, help with echo cancellation, noise filtering, video resolution and reduce latency.</span></span>

<span data-ttu-id="16478-181">手機和裝置對於使用者的音訊和視音訊品質有極大的影響。</span><span class="sxs-lookup"><span data-stu-id="16478-181">Phones and devices make a huge difference in the quality of audio and video for end users.</span></span> <span data-ttu-id="16478-182">商務用 Skype認證計畫是「Lync 相容」計畫的演進，並驗證裝置是否符合 Microsoft 的音訊和視音訊標準。</span><span class="sxs-lookup"><span data-stu-id="16478-182">The Skype for Business certification program is an evolution of the "Lync Compatible" program and validates that the device meets Microsoft standards for audio and video.</span></span> <span data-ttu-id="16478-183">Microsoft 已測試並認證許多 IP 電話、USB 音訊和視像裝置、電腦和會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="16478-183">There are a number of IP Phones, USB audio and video devices, PCs and meeting room devices that have been tested and qualified by Microsoft.</span></span> <span data-ttu-id="16478-184">您應該查看針對 商務用 Skype 優化的裝置清單，並努力提供不同的裝置，以滿足貴組織中使用者的各種需求和個人喜好設定。</span><span class="sxs-lookup"><span data-stu-id="16478-184">You should review the list of devices that are optimized for Skype for Business, and work to provide different devices in order to meet the various needs and personal preferences of your end users in your organization.</span></span>

<span data-ttu-id="16478-185">請參閱下列內容，以進一步瞭解支援與認證裝置的資訊：</span><span class="sxs-lookup"><span data-stu-id="16478-185">See the following for more information on supported and certified devices:</span></span>  

- [<span data-ttu-id="16478-186">取得商務用 Skype Online 的電話</span><span class="sxs-lookup"><span data-stu-id="16478-186">Getting phones for Skype for Business Online</span></span>](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [<span data-ttu-id="16478-187">手機和裝置商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="16478-187">Phones and Devices for Skype for Business</span></span>](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [<span data-ttu-id="16478-188">個人周邊設備解決方案目錄</span><span class="sxs-lookup"><span data-stu-id="16478-188">Solutions Catalog for Personal Peripherals</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [<span data-ttu-id="16478-189">符合 Microsoft Lync 資格的電話和裝置</span><span class="sxs-lookup"><span data-stu-id="16478-189">Phones and devices qualified for Microsoft Lync</span></span>](../../SfbPartnerCertification/lync-cert/ip-phones.md)

<span data-ttu-id="16478-190">使用者開會及使用音訊和視像裝置的環境及周圍區域是音訊和視音訊品質的另一大因素。</span><span class="sxs-lookup"><span data-stu-id="16478-190">The environment and surrounding area where users are meeting and using audio and video devices is another big factor for audio and video quality.</span></span> <span data-ttu-id="16478-191">從吵雜環境通話的使用者會聽到回音、雜亂且不清楚的音訊。</span><span class="sxs-lookup"><span data-stu-id="16478-191">Users calling from a noisy environment will have echoed, muffled and unclear audio.</span></span> <span data-ttu-id="16478-192">在深色或低亮度環境中，使用者將無法為視片產生明亮、清楚的影像品質。</span><span class="sxs-lookup"><span data-stu-id="16478-192">Users in a dark or low light environment won't be able to produce bright, clear image quality for video.</span></span> <span data-ttu-id="16478-193">在會議室設定中，麥克風和視像裝置的位置會對參與者收到的音效和影像品質有直接的影響。</span><span class="sxs-lookup"><span data-stu-id="16478-193">In a conference room setting, the location of the microphone and video device have a direct impact on the sound and image quality that participants will receive.</span></span>

<span data-ttu-id="16478-194">若要更清楚地瞭解使用者的音訊和視音訊體驗，請使用 商務用 Skype **App** 工具選項 音訊裝置或視像裝置來變更使用中的裝置，並自訂其  >    >  設定。 </span><span class="sxs-lookup"><span data-stu-id="16478-194">To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings.</span></span> <span data-ttu-id="16478-195">您也可以按一下檢查通話品質來檢查通話 **的音訊品質**。</span><span class="sxs-lookup"><span data-stu-id="16478-195">You can also check the audio quality of a call by clicking **Check Call Quality**.</span></span> <span data-ttu-id="16478-196">如果他們按一下 **[檢查通話品質**，然後可以報告測試通話的品質與問題。</span><span class="sxs-lookup"><span data-stu-id="16478-196">If they click **Check Call Quality**, they can then report the quality and issues found with the test call.</span></span>

![在用戶端中商務用 Skype音訊。](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a><span data-ttu-id="16478-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="16478-198">Related topics</span></span>

[<span data-ttu-id="16478-199">商務用 Skype Online 中的 ExpressRoute 與 QoS</span><span class="sxs-lookup"><span data-stu-id="16478-199">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
