---
title: 在商務用 Skype Server 中規劃影片 Interop 伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在規劃整合商務用 Skype Server 與協力廠商電話會議裝置時，請參閱本主題。
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831943"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="5daad-103">在商務用 Skype Server 中規劃影片 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="5daad-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="5daad-104">**摘要：** 在規劃整合商務用 Skype Server 與協力廠商電話會議裝置時，請參閱本主題。</span><span class="sxs-lookup"><span data-stu-id="5daad-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="5daad-105">商務用 Skype Server 現在可讓您與特定協力廠商 VTC (Video 電話會議 System) 解決方案進行整合。</span><span class="sxs-lookup"><span data-stu-id="5daad-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="5daad-106">新的伺服器角色可讓這種影片成為 VIS 互通性，這是一種影片 Interop 伺服器 () ，目前是以獨立伺服器角色的形式來執行，只供內部部署安裝使用。</span><span class="sxs-lookup"><span data-stu-id="5daad-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="5daad-107">VIS 充當協力廠商電話會議系統和商務用 Skype Server 部署之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="5daad-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="5daad-108">在此版本中，VIS 著重于與 Cisco/Tandberg 影片系統的互通性。</span><span class="sxs-lookup"><span data-stu-id="5daad-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="5daad-109">請參閱這篇文章，以決定是否要在商務用 Skype Server 安裝中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5daad-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="5daad-110">裝置互通性</span><span class="sxs-lookup"><span data-stu-id="5daad-110">Device interoperability</span></span>

<span data-ttu-id="5daad-111">在 cisco 整合通訊管理員 (CallManager 或 CUCM) 版本10.5 和 TCP SIP 主幹設定 CUCM 與 VIS 之間測試及支援互通性。</span><span class="sxs-lookup"><span data-stu-id="5daad-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="5daad-112">目前支援的 VTCs 包括：</span><span class="sxs-lookup"><span data-stu-id="5daad-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="5daad-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="5daad-113">Cisco C40</span></span>
    
- <span data-ttu-id="5daad-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="5daad-114">Cisco C60</span></span>
    
- <span data-ttu-id="5daad-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="5daad-115">Cisco C90</span></span>
    
- <span data-ttu-id="5daad-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="5daad-116">Cisco MX200</span></span>
    
- <span data-ttu-id="5daad-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="5daad-117">Cisco MX300</span></span>
    
- <span data-ttu-id="5daad-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="5daad-118">Cisco DX80</span></span>
    
- <span data-ttu-id="5daad-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="5daad-119">Cisco EX60</span></span>
    
- <span data-ttu-id="5daad-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="5daad-120">Cisco EX90</span></span>
    
- <span data-ttu-id="5daad-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="5daad-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="5daad-122">為了與商務用 Skype Server 整合，您需要 Cisco 軟體版本 TC 7.0.0 或以上版本，以如期運作。</span><span class="sxs-lookup"><span data-stu-id="5daad-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="5daad-123">SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="5daad-123">SIP trunks</span></span>

<span data-ttu-id="5daad-124">影片 Interop 伺服器的運作 SIP 主幹模式，VTCs 會繼續向現有的 Cisco 基礎結構註冊，例如，Cisco 通話管理員 (CUCM) 。</span><span class="sxs-lookup"><span data-stu-id="5daad-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="5daad-125">影片的 SIP 主幹會定義在 CUCM 和 VIS 之間，以便通話可以在兩個系統間路由傳送。</span><span class="sxs-lookup"><span data-stu-id="5daad-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="5daad-126">只支援從 VTC 到 VIS 的 SIP 主幹呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="5daad-127">因此，VTCs 可以撥入商務用 Skype 會議 (，方法是撥打與自動語音應答) 相關聯的電話號碼，但無法將其拖放到會議中。</span><span class="sxs-lookup"><span data-stu-id="5daad-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB 中的 VIS 圖表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="5daad-129">功能</span><span class="sxs-lookup"><span data-stu-id="5daad-129">Features</span></span>

<span data-ttu-id="5daad-130">此伺服器角色提供：</span><span class="sxs-lookup"><span data-stu-id="5daad-130">This server role provides:</span></span>
  
- <span data-ttu-id="5daad-131">協力廠商影片和商務用 Skype Server 部署所使用的 H-p 格式之間的轉換。</span><span class="sxs-lookup"><span data-stu-id="5daad-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="5daad-132">從 VTC 以指定解析度將單一影片資料流程轉換成多個 simulcast 資料流程，以供商務用 Skype Server 部署使用。</span><span class="sxs-lookup"><span data-stu-id="5daad-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="5daad-133">這些資料流程可以傳送至 AVMCU，然後傳送至商務用 Skype 伺服器端點和其他已要求不同解決方案的視頻系統。</span><span class="sxs-lookup"><span data-stu-id="5daad-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="5daad-134">在商務用 Skype A/V 電話會議中參與協力廠商影片系統時，也會使用此轉換。</span><span class="sxs-lookup"><span data-stu-id="5daad-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="5daad-135">在特定 VIS 伺服器中達到轉碼限制之後，任何針對不同解決方法的要求都只會接收最低解析度的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5daad-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="5daad-136">支援 CUCM 閘道和商務用 Skype Server Video Interop 伺服器之間的影片 SIP 主幹;VTCs 繼續向 Cisco 閘道註冊，並透過閘道啟動對商務用 Skype 部署的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="5daad-137">呼叫是透過透過視頻 SIP 主幹傳送從閘道到商務用 Skype Video Interop 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5daad-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="5daad-138">支援具有支援的影片的會議室中的使用者，以便從該系統撥號加入開啟或關閉的會議。</span><span class="sxs-lookup"><span data-stu-id="5daad-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="5daad-139">此呼叫會跨越影片 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="5daad-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="5daad-140">支援具有支援的影片的會議室中的使用者，可呼叫商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="5daad-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="5daad-141">呼叫會遍歷 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="5daad-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="5daad-142">支援從商務用 Skype 伺服器端或從支援的 VTC 系統進行 mid 電話控制，以實現兩個點對點和 multipoint 通話（包括靜音/取消靜音音訊、暫停/繼續播放影片、鎖定影片及保留/取消通話）。</span><span class="sxs-lookup"><span data-stu-id="5daad-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="5daad-143">已知限制</span><span class="sxs-lookup"><span data-stu-id="5daad-143">Known limitations</span></span>

<span data-ttu-id="5daad-144">此伺服器角色具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="5daad-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="5daad-145">不支援透過視頻 SIP 主幹從商務用 Skype 部署至 VTCs 的新呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="5daad-146">.</span><span class="sxs-lookup"><span data-stu-id="5daad-146">.</span></span> <span data-ttu-id="5daad-147">這表示只有透過 VTCs 進入商務用 Skype 部署的新呼叫才能透過影片 SIP 主幹獲得支援。</span><span class="sxs-lookup"><span data-stu-id="5daad-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="5daad-148">支援的影片的目前狀態將無法透過影片 SIP 主幹 VIS。</span><span class="sxs-lookup"><span data-stu-id="5daad-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="5daad-149">影片 SIP 主幹模式只支援獨立 VIS 集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="5daad-150">TLS + SRTP 或 TCP + RTP 可支援 VTC 和 VIS 透過視頻 SIP 主幹之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="5daad-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="5daad-151">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="5daad-151">Application sharing is not supported.</span></span> <span data-ttu-id="5daad-152">會議室中的商務用 Skype 使用者必須透過膝上型電腦加入商務用 Skype 會議 (例如) ，並在會議室的其中一個空閒監視器上顯示應用程式共用畫面，而不是與 VTC 相關聯。</span><span class="sxs-lookup"><span data-stu-id="5daad-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="5daad-153">不支援 VTC 透過 VIS 加入同盟會議的功能。</span><span class="sxs-lookup"><span data-stu-id="5daad-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="5daad-154">不支援 VTC 透過 VIS 加入線上會議的功能。</span><span class="sxs-lookup"><span data-stu-id="5daad-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="5daad-155">不支援透過 VIS 從 VTC 到 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="5daad-156">從 PSTN 到透過 VIS 的 VTC 的呼叫都不受支援。</span><span class="sxs-lookup"><span data-stu-id="5daad-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="5daad-157">恢復機制</span><span class="sxs-lookup"><span data-stu-id="5daad-157">Resiliency mechanisms</span></span>
<span data-ttu-id="5daad-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-159">VIS 支援來自透過影片 SIP 主幹的 CUCM 傳入的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="5daad-160">可能會遺失上游或下游的連線，因此，可靠的復原會考慮這兩種可能性：</span><span class="sxs-lookup"><span data-stu-id="5daad-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="5daad-161">**VIS 集區容錯移轉** 如果影片閘道指向的主 VIS 集區已停機，當影片閘道已定義主幹至兩個 (或更多) VIS 集區時，可能會復原。</span><span class="sxs-lookup"><span data-stu-id="5daad-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="5daad-162">如果影片閘道決定它無法呼叫主要 VIS 集區，它只會將通話路由傳送至次要 VIS 集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 集區容錯移轉圖表](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="5daad-164">特定的 VIS 集區可以有主幹多個閘道，但通常特定閘道不能有主幹至多個 VIS 集區，因此必須執行一項技巧，以支援此容錯移轉：在 DNS 中定義2個 FDQNs，以解析為一個視頻閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5daad-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="5daad-165">將每個 FQDN 都表示為拓撲檔中的個別影片閘道，其中每個影片閘道都具有不同 VIS 集區的主幹，而且現在可以進行復原。</span><span class="sxs-lookup"><span data-stu-id="5daad-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="5daad-166"> (如果使用 TLS，多個名稱將需要位於視頻閘道憑證的 SAN 中。 ) </span><span class="sxs-lookup"><span data-stu-id="5daad-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5daad-167">VIS 只允許來自拓撲檔中設定之閘道上的來電。</span><span class="sxs-lookup"><span data-stu-id="5daad-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="5daad-168">**前端容錯移轉** 如果 VIS 集區接收到來自 CUCM 的呼叫，但無法抵達其主要的下一個躍點註冊機構或前端集區，則會將通話路由傳送至備份前端集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![前端容錯移轉圖表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="5daad-170">VIS 將追蹤其主要前端集區和其備份前端集區的狀態 (此設定會在 [拓撲檔) 中的註冊機服務備份設定中找到。</span><span class="sxs-lookup"><span data-stu-id="5daad-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="5daad-171">這兩個集區的每一分鐘都會傳送一次選項，而且如果有五個連續的失敗，VIS 會認為特定前端集區已停機。</span><span class="sxs-lookup"><span data-stu-id="5daad-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="5daad-172">如果主要前端集區標示為 [停機]，且有可用的已設定備份，VIS 會將新呼叫從閘道傳送至備份前端集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="5daad-173">當主要前端集區回到後，VIS 將會繼續使用主要前端集區進行新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5daad-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="5daad-174">VIS 也會針對來自視頻 SIP 主幹的呼叫，執行10秒的計時器。</span><span class="sxs-lookup"><span data-stu-id="5daad-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="5daad-175">如果主要下一個躍點前端集區是用於來自視頻 SIP 主幹的呼叫，而且主要的下一個躍點前端集區並未以某些 SIP (郵件（包括100嘗試) 在此計時器值中傳送給它的情況下）進行應答，則應嘗試針對呼叫使用備份下一個躍點 proxy （如果已設定）。</span><span class="sxs-lookup"><span data-stu-id="5daad-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5daad-176">如果先嘗試備份下一個躍點，將不會再嘗試一個主備份。</span><span class="sxs-lookup"><span data-stu-id="5daad-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="5daad-177">系統管理員也可以使用 Windows PowerShell 容錯移轉命令，強制 VIS 使用備份前端集區，例如，在主要前端集區上進行維護時。</span><span class="sxs-lookup"><span data-stu-id="5daad-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="5daad-178">在相同的閘道對等中共存語音和影片主幹</span><span class="sxs-lookup"><span data-stu-id="5daad-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="5daad-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-180">商務用 Skype 伺服器支援語音和視頻 SIP 主幹使用相同的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="5daad-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="5daad-181">因此，相同的 CUCM 部署可能會具有語音 SIP 主幹至轉送伺服器及視頻 SIP 主幹到 VIS。</span><span class="sxs-lookup"><span data-stu-id="5daad-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="5daad-182">在語音 SIP 主幹的拓撲檔中，必須使用特定的 FQDN 來定義 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="5daad-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="5daad-183">對等的 PSTN 閘道將會是轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="5daad-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="5daad-184">如有必要，可將多個 voice 主幹定義從 PSTN 閘道到多個轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="5daad-185">在與 PSTN 閘道具有相同 FQDN 的視頻 SIP 主幹的拓撲檔中，將需要定義影片閘道。</span><span class="sxs-lookup"><span data-stu-id="5daad-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="5daad-186">對等的視頻閘道將會是 VIS。</span><span class="sxs-lookup"><span data-stu-id="5daad-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="5daad-187">單一的影片主幹可以從影片閘道定義為特定 VIS 集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="5daad-188">CUCM 將需要設定為透過語音主幹和影片主幹正確路由通話。</span><span class="sxs-lookup"><span data-stu-id="5daad-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="5daad-189">例如，當您從 VTC 撥號時，可以使用特殊的撥號首碼;CUCM 可將此撥號首碼與 VIS 的呼叫關聯，而且適當的轉譯規則會將此前置詞從 SIP 邀請中去掉到 VIS。</span><span class="sxs-lookup"><span data-stu-id="5daad-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="5daad-190">與舊版 Lync 搭配商務用 Skype 版本中的 VIS 共同存在</span><span class="sxs-lookup"><span data-stu-id="5daad-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="5daad-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-192">VIS 只能部署為商務用 Skype 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="5daad-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="5daad-193">它可以與屬於現有部署一部分的 Lync 2013 會議和用戶端進行交互操作;在這種情況下，VIS 集區必須是商務用 Skype 部署的一部分，其中包含 VIS 集區的下一個躍點的註冊人員/FE 集區。</span><span class="sxs-lookup"><span data-stu-id="5daad-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="5daad-194">VIS 不支援 RTV 和 H-p 間的轉碼。</span><span class="sxs-lookup"><span data-stu-id="5daad-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="5daad-195">在會議中，Lync 2013 用戶端與 VTC 參與者之間沒有任何影片的互用性。</span><span class="sxs-lookup"><span data-stu-id="5daad-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="5daad-196">在會議中具有 Lync 2013 用戶端，將會造成行動用戶端使用 RTV 傳送，導致行動用戶端成為主要喇叭時，VTCs 不會收到任何影片。</span><span class="sxs-lookup"><span data-stu-id="5daad-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="5daad-197">為了讓 Lync 2013 能夠與 VIS （商務用 Skype 部署的一部分）正確運作，Lync 2013 需要套用適當的 CU，以升級 Lync 2013 用戶端、CAA 和 AVMCU，以與 VIS 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5daad-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="5daad-198">VIS 與 Lync 2013 和商務用 Skype 桌面用戶端的互通性已經過測試，且受到支援。</span><span class="sxs-lookup"><span data-stu-id="5daad-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="5daad-199">VIS 與非桌面的互通性 (Android、Ipad、Iphone、Windows Phone、LMX 等等。 ) VIS 發行時，適用的應用程式存放區中可用的商務用 Skype 用戶端，都已經過測試，且受支援。</span><span class="sxs-lookup"><span data-stu-id="5daad-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="5daad-200">透過 FEC 恢復封包遺失</span><span class="sxs-lookup"><span data-stu-id="5daad-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="5daad-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-202">您可以開啟 FEC，以協助從封包遺失中復原。</span><span class="sxs-lookup"><span data-stu-id="5daad-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="5daad-203">開啟時50，VIS 會使用更多的影片頻寬以 VTC 方向。</span><span class="sxs-lookup"><span data-stu-id="5daad-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="5daad-204">VIS 大小和轉碼成本</span><span class="sxs-lookup"><span data-stu-id="5daad-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="5daad-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-206">將 Cisco VTC 中的單一影片資料流程轉換成多個 simulcast 資料流程使用 CPU 容量。</span><span class="sxs-lookup"><span data-stu-id="5daad-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="5daad-207">大約 16 VTCs 可以有其影片 transcoded (假設每個 VTC 的720p 影片資料流程會 transcoded 成3個不同的 simulcast 資料流程，在720p、360p 和 180p) 中，在建議的中文平臺2013上執行的單一 VIS 中。</span><span class="sxs-lookup"><span data-stu-id="5daad-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="5daad-208">如果將轉碼關閉，這將會儲存在 VIS CPU 上。</span><span class="sxs-lookup"><span data-stu-id="5daad-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="5daad-209">不過，VIS 從 VTC 所要求的影片影像將是符合商務用 Skype 一方所有接收器的最低一般解析度。</span><span class="sxs-lookup"><span data-stu-id="5daad-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="5daad-210">請注意，即使是關閉轉碼功能，當商務用 Skype 用戶端要求某些低解析度 VTCs 無法傳送時，可能會啟用轉碼。</span><span class="sxs-lookup"><span data-stu-id="5daad-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="5daad-211">從影片閘道到 VIS 的呼叫分配</span><span class="sxs-lookup"><span data-stu-id="5daad-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="5daad-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-213">分配是透過其中一個 CUCM 發佈機制來完成：</span><span class="sxs-lookup"><span data-stu-id="5daad-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="5daad-214">使用 DNS 動態地使用。</span><span class="sxs-lookup"><span data-stu-id="5daad-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="5daad-215">在 CUCM 端，您可以定義個別的主幹，其中每個主幹會在 VIS 集區中的不同伺服器上終止。</span><span class="sxs-lookup"><span data-stu-id="5daad-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="5daad-216">CUCM 會將通話路由傳送到不同的主幹。</span><span class="sxs-lookup"><span data-stu-id="5daad-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="5daad-217">無混合互通性</span><span class="sxs-lookup"><span data-stu-id="5daad-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="5daad-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-219">VTCs 透過內部部署 VIS 加入線上會議的支援不是商務用 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5daad-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="5daad-220">無同盟支援</span><span class="sxs-lookup"><span data-stu-id="5daad-220">No Federation Support</span></span>
<span data-ttu-id="5daad-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="5daad-222">VTCs 通過 VIS 加入同盟會議的支援不是商務用 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5daad-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5daad-223">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5daad-223">See also</span></span>
<span data-ttu-id="5daad-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="5daad-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="5daad-225">在商務用 Skype Server 中部署影片 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="5daad-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
