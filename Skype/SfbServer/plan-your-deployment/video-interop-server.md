---
title: 在商務用 Skype Server 中規劃影片互通性伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在規劃將商務用 Skype 伺服器與協力廠商 teleconferencing 裝置進行整合時，請複習本主題。
ms.openlocfilehash: 5531fd60cc2aa28202903fcc4392fe7830bcdfa0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684186"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="f31a7-103">在商務用 Skype Server 中規劃影片互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="f31a7-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f31a7-104">**摘要：** 在規劃將商務用 Skype 伺服器與協力廠商 teleconferencing 裝置進行整合時，請複習本主題。</span><span class="sxs-lookup"><span data-stu-id="f31a7-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="f31a7-105">商務用 Skype Server 現可讓您與特定的協力廠商 VTC （Video Teleconferencing 系統）解決方案整合。</span><span class="sxs-lookup"><span data-stu-id="f31a7-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="f31a7-106">啟用此視訊會議互通性的新伺服器角色是影片互通性伺服器（VIS），目前是以獨立伺服器角色的方式實現，只有內部部署安裝才能使用。</span><span class="sxs-lookup"><span data-stu-id="f31a7-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="f31a7-107">VIS 充當協力廠商電話會議系統和商務用 Skype Server 部署之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="f31a7-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="f31a7-108">在這個版本中，VIS 的重點是使用 Cisco/Tandberg 視頻系統進行互通性。</span><span class="sxs-lookup"><span data-stu-id="f31a7-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="f31a7-109">請參閱這篇文章，以判斷是否要在商務用 Skype Server 安裝中使用這項功能。</span><span class="sxs-lookup"><span data-stu-id="f31a7-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="f31a7-110">裝置互通性</span><span class="sxs-lookup"><span data-stu-id="f31a7-110">Device interoperability</span></span>

<span data-ttu-id="f31a7-111">在使用 cisco 整合通訊管理員（CallManager 或 CUCM）版本10.5 和 TCP SIP trunks 在 CUCM 和 VIS 之間進行 VTCs 註冊，即可測試並支援互通性。</span><span class="sxs-lookup"><span data-stu-id="f31a7-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="f31a7-112">目前支援的 VTCs 為：</span><span class="sxs-lookup"><span data-stu-id="f31a7-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="f31a7-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="f31a7-113">Cisco C40</span></span>
    
- <span data-ttu-id="f31a7-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="f31a7-114">Cisco C60</span></span>
    
- <span data-ttu-id="f31a7-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="f31a7-115">Cisco C90</span></span>
    
- <span data-ttu-id="f31a7-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="f31a7-116">Cisco MX200</span></span>
    
- <span data-ttu-id="f31a7-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="f31a7-117">Cisco MX300</span></span>
    
- <span data-ttu-id="f31a7-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="f31a7-118">Cisco DX80</span></span>
    
- <span data-ttu-id="f31a7-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="f31a7-119">Cisco EX60</span></span>
    
- <span data-ttu-id="f31a7-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="f31a7-120">Cisco EX90</span></span>
    
- <span data-ttu-id="f31a7-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="f31a7-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="f31a7-122">在這些系統上需要 Cisco 軟體發行 TC 7.0.0 或更新版本，以便與商務用 Skype 伺服器整合，以如期運作。</span><span class="sxs-lookup"><span data-stu-id="f31a7-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="f31a7-123">SIP trunks</span><span class="sxs-lookup"><span data-stu-id="f31a7-123">SIP trunks</span></span>

<span data-ttu-id="f31a7-124">影片交互操作伺服器在 SIP 幹線模式中起作用，VTCs 會繼續向現有的 Cisco 基礎結構註冊，例如 Cisco 通話管理員（CUCM）。</span><span class="sxs-lookup"><span data-stu-id="f31a7-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="f31a7-125">在 CUCM 和 VIS 之間定義了一個影片 SIP 主幹，讓通話可以在兩個系統間路由。</span><span class="sxs-lookup"><span data-stu-id="f31a7-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="f31a7-126">僅支援透過 SIP 主幹從 VTC 到 VIS 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f31a7-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="f31a7-127">因此，VTCs 可以撥入商務用 Skype 會議（透過撥打與來電自動助理相關的電話號碼），但無法將其拖曳並放入會議中。</span><span class="sxs-lookup"><span data-stu-id="f31a7-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB 中的 VIS 圖表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="f31a7-129">Features</span><span class="sxs-lookup"><span data-stu-id="f31a7-129">Features</span></span>

<span data-ttu-id="f31a7-130">此伺服器角色提供：</span><span class="sxs-lookup"><span data-stu-id="f31a7-130">This server role provides:</span></span>
  
- <span data-ttu-id="f31a7-131">協力廠商視頻系統和商務用 Skype Server 部署所使用的 .H 格式之間的轉換。</span><span class="sxs-lookup"><span data-stu-id="f31a7-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="f31a7-132">從 VTC 以給定解析度將單一視頻資料流程轉換成多個不同解析度的 simulcast 資料流程，以便在商務用 Skype Server 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="f31a7-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="f31a7-133">這些資料流程可以傳送到 AVMCU，然後傳送到商務用 Skype Server 端點及其他已要求不同解析度的視頻系統。</span><span class="sxs-lookup"><span data-stu-id="f31a7-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="f31a7-134">在商務用 Skype A/V 電話會議中參與協力廠商影片系統時，也會使用這項轉換。</span><span class="sxs-lookup"><span data-stu-id="f31a7-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="f31a7-135">在特定的 VIS 伺服器中達到轉碼限制之後，針對不同解析度的任何下列要求將只會接收最低解析度的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f31a7-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="f31a7-136">支援 CUCM 閘道與商務用 Skype Server 視頻交互操作伺服器之間的視頻 SIP 幹線;VTCs [繼續使用 Cisco 閘道註冊]，然後透過閘道啟動對商務用 Skype 部署的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f31a7-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="f31a7-137">通話是透過視頻 SIP 主幹從閘道傳送到商務用 Skype 的視頻交互操作伺服器。</span><span class="sxs-lookup"><span data-stu-id="f31a7-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="f31a7-138">支援會議室中的使用者，以及支援的影片系統，可從該系統撥打電話給開啟或關閉的會議。</span><span class="sxs-lookup"><span data-stu-id="f31a7-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="f31a7-139">此呼叫將遍歷 [視頻 SIP 主幹]。</span><span class="sxs-lookup"><span data-stu-id="f31a7-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="f31a7-140">支援在會議室中使用支援的視頻系統呼叫商務用 Skype 用戶端的使用者。</span><span class="sxs-lookup"><span data-stu-id="f31a7-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="f31a7-141">通話會遍歷 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="f31a7-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="f31a7-142">支援從商務用 Skype 伺服器端或從支援的 VTC 系統，到兩個點對點和 multipoint 通話，包括將音訊靜音/取消靜音、暫停/繼續播放影片、鎖定影片，以及按住/取消暫留通話。</span><span class="sxs-lookup"><span data-stu-id="f31a7-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="f31a7-143">已知限制</span><span class="sxs-lookup"><span data-stu-id="f31a7-143">Known limitations</span></span>

<span data-ttu-id="f31a7-144">此伺服器角色具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="f31a7-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="f31a7-145">不支援透過視頻 SIP 幹線，從商務用 Skype 部署到 VTCs 的新通話。</span><span class="sxs-lookup"><span data-stu-id="f31a7-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="f31a7-146">.</span><span class="sxs-lookup"><span data-stu-id="f31a7-146">.</span></span> <span data-ttu-id="f31a7-147">這表示只有從 VTCs 到商務用 Skype 部署的新呼叫受到支援，才能透過視頻 SIP 主幹進行。</span><span class="sxs-lookup"><span data-stu-id="f31a7-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="f31a7-148">支援的視頻系統的目前狀態將無法在視頻 SIP 主幹上提供給 VIS。</span><span class="sxs-lookup"><span data-stu-id="f31a7-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="f31a7-149">只有獨立的 VIS 池才支援視頻 SIP 幹線模式。</span><span class="sxs-lookup"><span data-stu-id="f31a7-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="f31a7-150">TLS + SRTP 或 TCP + RTP 將支援在 VTC 與 VIS 之間的通訊，以進行視頻 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="f31a7-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="f31a7-151">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="f31a7-151">Application sharing is not supported.</span></span> <span data-ttu-id="f31a7-152">會議室中的商務用 Skype 使用者需要加入商務用 Skype 會議（例如透過膝上型電腦），並在會議室中的其中一個免費顯示器上顯示應用程式共用畫面，而不與 VTC 相關聯。</span><span class="sxs-lookup"><span data-stu-id="f31a7-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="f31a7-153">VTC 透過 VIS 加入同盟會議的能力不受支援。</span><span class="sxs-lookup"><span data-stu-id="f31a7-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="f31a7-154">VTC 透過 VIS 加入線上會議的功能不受支援。</span><span class="sxs-lookup"><span data-stu-id="f31a7-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="f31a7-155">不支援透過 VIS 從 VTC 到 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f31a7-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="f31a7-156">不支援從 PSTN 至 VTC via VIS 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f31a7-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="f31a7-157">復原機制</span><span class="sxs-lookup"><span data-stu-id="f31a7-157">Resiliency mechanisms</span></span>
<span data-ttu-id="f31a7-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-159">VIS 支援來自透過視頻 SIP 幹線傳送的 CUCM 中的來電。</span><span class="sxs-lookup"><span data-stu-id="f31a7-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="f31a7-160">可能會失去上游或下游的連線，因此為了提供強健的復原，請考慮兩種可能性：</span><span class="sxs-lookup"><span data-stu-id="f31a7-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="f31a7-161">**VIS 池容錯移轉**如果視頻閘道所指向的主 VIS 池已關閉，則可以在視頻閘道已定義 trunks 至兩個（或更多） VIS 池的情況下進行恢復。</span><span class="sxs-lookup"><span data-stu-id="f31a7-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="f31a7-162">如果視頻閘道判斷它無法呼叫主要 VIS 池，只需將呼叫路由到副 VIS pool。</span><span class="sxs-lookup"><span data-stu-id="f31a7-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 池容錯移轉的圖表](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="f31a7-164">特定的 VIS 池可以將 trunks 設為多個閘道，但通常特定閘道不能 trunks 至多個 VIS 池，所以需要完成一項動作，才能支援此容錯移轉：在 DNS 中定義2個 FDQNs，解析為與視頻閘道相同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f31a7-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="f31a7-165">在拓撲檔中，將每個 FQDN 表示為一個獨立的視頻閘道，其中每個視頻閘道都有一個不同 VIS 池的主幹，而且現在可以進行恢復。</span><span class="sxs-lookup"><span data-stu-id="f31a7-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="f31a7-166">（如果使用 TLS，多個名稱將必須位於視頻閘道憑證的 SAN 中。）</span><span class="sxs-lookup"><span data-stu-id="f31a7-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f31a7-167">VIS 只允許在拓撲檔中設定的閘道撥入來電。</span><span class="sxs-lookup"><span data-stu-id="f31a7-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="f31a7-168">**前端容錯移轉**如果 VIS 池收到來自 CUCM 的呼叫，但無法到達其主要的下一中繼站註冊機構或前端池，則會將呼叫路由至備份前端池。</span><span class="sxs-lookup"><span data-stu-id="f31a7-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![前端容錯移轉的圖表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="f31a7-170">VIS 將會追蹤其主要前端池與其備份前端池的狀態（在 [拓撲] 檔中，在 [註冊機構服務] 的 [備份] 設定中找到此設定）。</span><span class="sxs-lookup"><span data-stu-id="f31a7-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="f31a7-171">它會將選項輪詢一分鐘傳送一次到兩個池，而且如果有五個連續失敗，VIS 會假設某個特定的前端池已關閉。</span><span class="sxs-lookup"><span data-stu-id="f31a7-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="f31a7-172">如果主要前端池已標示為 down，且有可用的已設定備份，VIS 會將來自閘道的新呼叫傳送至備份前端池。</span><span class="sxs-lookup"><span data-stu-id="f31a7-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="f31a7-173">主前端池回到之後，VIS 將會繼續使用主要前端池來進行新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f31a7-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="f31a7-174">VIS 也會針對來自視頻 SIP 幹線的呼叫執行10秒計時器。</span><span class="sxs-lookup"><span data-stu-id="f31a7-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="f31a7-175">如果主要的下一中繼站前臺端池是用來進行來自視頻 SIP 幹線的呼叫，而主要的下一個躍點前端池卻沒有回應在這個計時器值中傳送給它的邀請函（包括100嘗試），則是呼叫 s 的備份下一個躍點 proxy。如果已設定，請嘗試 hould。</span><span class="sxs-lookup"><span data-stu-id="f31a7-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f31a7-176">如果先嘗試使用 [備份] 下一個躍點，則不會在下一次嘗試此程式。</span><span class="sxs-lookup"><span data-stu-id="f31a7-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="f31a7-177">系統管理員也可以使用 Windows PowerShell 容錯移轉命令，強制 VIS 使用備份前端池（例如，必須在主要前端池中執行維護）。</span><span class="sxs-lookup"><span data-stu-id="f31a7-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="f31a7-178">在同一個閘道對等中存在語音與視頻 Trunks 的共存</span><span class="sxs-lookup"><span data-stu-id="f31a7-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="f31a7-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-180">商務用 Skype 伺服器支援讓語音及視頻 SIP trunks 使用相同的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="f31a7-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="f31a7-181">因此，相同的 CUCM 部署可能會有語音 SIP trunks 到中繼伺服器與視頻 SIP trunks 至 VIS。</span><span class="sxs-lookup"><span data-stu-id="f31a7-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="f31a7-182">PSTN 閘道必須在 [語音 SIP trunks] 的 [拓撲] 檔中使用特定的 FQDN 加以定義。</span><span class="sxs-lookup"><span data-stu-id="f31a7-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="f31a7-183">對等的 PSTN 閘道將是轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="f31a7-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="f31a7-184">如有需要，可將多個語音 trunks 定義從 PSTN 閘道到多個轉送伺服器池。</span><span class="sxs-lookup"><span data-stu-id="f31a7-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="f31a7-185">您必須在視頻 SIP 幹線的 [拓撲] 檔中，使用與 PSTN 閘道相同的 FQDN 來定義視頻閘道。</span><span class="sxs-lookup"><span data-stu-id="f31a7-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="f31a7-186">對等的視頻閘道將會 VIS。</span><span class="sxs-lookup"><span data-stu-id="f31a7-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="f31a7-187">您可以從視頻閘道定義單一的視頻幹線至特定的 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="f31a7-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="f31a7-188">CUCM 將需要設定為正確路由來自語音幹線與視頻幹線的通話。</span><span class="sxs-lookup"><span data-stu-id="f31a7-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="f31a7-189">例如，從 VTC 撥號時，可以使用特殊的撥號首碼;CUCM 可能會將這個撥號前置詞與 VIS 的呼叫關聯，而適當的翻譯規則會將此前置詞從 SIP 邀請中去除至 VIS。</span><span class="sxs-lookup"><span data-stu-id="f31a7-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="f31a7-190">在商務用 Skype 發行中與舊版 Lync VIS 中共存</span><span class="sxs-lookup"><span data-stu-id="f31a7-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="f31a7-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-192">VIS 只能在商務用 Skype 部署中部署。</span><span class="sxs-lookup"><span data-stu-id="f31a7-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="f31a7-193">它可以與屬於現有部署的 Lync 2013 會議與用戶端進行互動;在這些情況下，VIS 池必須是商務用 Skype 部署的一部分，其中包含的註冊機構/FE 池是 VIS 池的下一躍點。</span><span class="sxs-lookup"><span data-stu-id="f31a7-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="f31a7-194">VIS 不支援 RTV 與 .H 之間的轉碼。</span><span class="sxs-lookup"><span data-stu-id="f31a7-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="f31a7-195">在會議中，Lync 2013 用戶端與 VTC 參與者之間沒有任何視頻互通性。</span><span class="sxs-lookup"><span data-stu-id="f31a7-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="f31a7-196">在會議中擁有 Lync 2013 用戶端，將會導致行動用戶端使用 RTV 傳送，當行動用戶端變成主要喇叭時，就會收到沒有影片的 VTCs。</span><span class="sxs-lookup"><span data-stu-id="f31a7-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="f31a7-197">為了讓 Lync 2013 能正確搭配商務用 Skype 部署中的 VIS 正常運作，Lync 2013 需要套用適當的 CU 來升級 Lync 2013 用戶端、CAA 和 AVMCU，才能與 VIS 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f31a7-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="f31a7-198">VIS 與 Lync 2013 和商務用 Skype 桌面用戶端的互通性已經過測試且受到支援。</span><span class="sxs-lookup"><span data-stu-id="f31a7-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="f31a7-199">VIS 與非桌面（Android、Ipad、Iphone、Windows Phone、LMX 等）的互通性。VIS 發行時，適用的應用程式商店提供的商務用 Skype 用戶端已經過測試且受到支援。</span><span class="sxs-lookup"><span data-stu-id="f31a7-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="f31a7-200">透過 FEC 從資料包遺失中復原</span><span class="sxs-lookup"><span data-stu-id="f31a7-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="f31a7-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-202">FEC 可以開啟，以協助從資料包遺失中復原。</span><span class="sxs-lookup"><span data-stu-id="f31a7-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="f31a7-203">如果開啟50，將會在 VIS 中使用更多的影片頻寬，以 VTC 方向。</span><span class="sxs-lookup"><span data-stu-id="f31a7-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="f31a7-204">VIS 調整大小與轉碼成本</span><span class="sxs-lookup"><span data-stu-id="f31a7-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="f31a7-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-206">將 Cisco VTC 中的單一視頻資料流程轉換成多個 simulcast 資料流程使用 CPU 容量。</span><span class="sxs-lookup"><span data-stu-id="f31a7-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="f31a7-207">大約 16 VTCs 可以有其影片 irandomaccessstream （假設每個 VTC 的720p 影片串流都 irandomaccessstream 成3個獨立的 simulcast 資料流程，在720p、360p 和180p）的單一 VIS 中，以 Lync 2013 建議的 FE 平臺執行。</span><span class="sxs-lookup"><span data-stu-id="f31a7-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="f31a7-208">如果 [轉碼] 是關閉的，這將會儲存在 VIS 的 CPU 上。</span><span class="sxs-lookup"><span data-stu-id="f31a7-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="f31a7-209">不過，VIS 從 VTC 要求的影片影像會是最低的一般解析度，以符合商務用 Skype 端的所有接收器。</span><span class="sxs-lookup"><span data-stu-id="f31a7-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="f31a7-210">請注意，即使是關閉轉碼，在商務用 Skype 用戶端要求 VTCs 無法傳送的特定低解析度時，也可能會啟用轉碼。</span><span class="sxs-lookup"><span data-stu-id="f31a7-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="f31a7-211">從 [視頻] 閘道呼叫配送至 VIS</span><span class="sxs-lookup"><span data-stu-id="f31a7-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="f31a7-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-213">您可以透過下列其中一個 CUCM 傳播機制來完成分配：</span><span class="sxs-lookup"><span data-stu-id="f31a7-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="f31a7-214">動態使用 DNS。</span><span class="sxs-lookup"><span data-stu-id="f31a7-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="f31a7-215">在 CUCM 端，您可以定義個別的 trunks，其中每個幹線都會在 VIS 池中的不同伺服器上終止。</span><span class="sxs-lookup"><span data-stu-id="f31a7-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="f31a7-216">CUCM 會在不同的 trunks 中傳送呼叫路線。</span><span class="sxs-lookup"><span data-stu-id="f31a7-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="f31a7-217">無混合式互通性</span><span class="sxs-lookup"><span data-stu-id="f31a7-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="f31a7-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-219">VTCs 透過內部部署 VIS 加入線上會議的支援不是商務用 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f31a7-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="f31a7-220">無同盟支援</span><span class="sxs-lookup"><span data-stu-id="f31a7-220">No Federation Support</span></span>
<span data-ttu-id="f31a7-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="f31a7-222">VTCs 透過 VIS 加入同盟會議的支援不是商務用 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f31a7-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f31a7-223">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f31a7-223">See also</span></span>
<span data-ttu-id="f31a7-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="f31a7-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="f31a7-225">在商務用 Skype Server 中部署視頻交互操作伺服器</span><span class="sxs-lookup"><span data-stu-id="f31a7-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
