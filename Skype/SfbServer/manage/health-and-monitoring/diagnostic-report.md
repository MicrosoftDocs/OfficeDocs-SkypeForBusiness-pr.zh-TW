---
title: 商務用 Skype Server 中的診斷報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 摘要：瞭解商務用 Skype Server 中的診斷報告。
ms.openlocfilehash: b7739214cf176336e47a5d2e11b36b52ea87eca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095237"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="6fe61-103">商務用 Skype Server 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="6fe61-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="6fe61-104">**摘要：** 深入瞭解商務用 Skype Server 中的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="6fe61-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="6fe61-105">診斷報告可提供失敗會話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="6fe61-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="6fe61-106">此資訊包含會話失敗時所報告的診斷識別碼和診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="6fe61-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="6fe61-107">診斷 ID 是與 SIP 郵件相連的 ms diagnostics 標頭) 形式的唯一識別碼 (，而診斷標頭則提供診斷識別碼的附帶描述。</span><span class="sxs-lookup"><span data-stu-id="6fe61-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="6fe61-108">報告可能也包含報告元件所知道的有用疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6fe61-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="6fe61-109">例如：</span><span class="sxs-lookup"><span data-stu-id="6fe61-109">For example:</span></span>
  
- <span data-ttu-id="6fe61-110">產生失敗之 PSTN 閘道所提供的原因碼。</span><span class="sxs-lookup"><span data-stu-id="6fe61-110">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="6fe61-111">PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="6fe61-111">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="6fe61-112">例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="6fe61-112">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="6fe61-113">連接失敗的對等 FQDN、埠和 Winsock 錯誤。</span><span class="sxs-lookup"><span data-stu-id="6fe61-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="6fe61-114">要尋找以進行 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="6fe61-114">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="6fe61-115">DNS 解析會在用戶端接觸名稱伺服器時進行，並要求對應至指定裝置名稱的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6fe61-115">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="6fe61-116">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="6fe61-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="6fe61-117">您可以在 [商務用 Skype 伺服器] 或 [會議詳細資料] 報告中，按一下 [ [Peer-to-Peer 會話詳細資料](peer-to-peer-session-detail-report.md) ] 報告上的 [診斷報告] (詳細資料) 指標，即可存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="6fe61-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="6fe61-118">篩選</span><span class="sxs-lookup"><span data-stu-id="6fe61-118">Filters</span></span>

<span data-ttu-id="6fe61-119">無。</span><span class="sxs-lookup"><span data-stu-id="6fe61-119">None.</span></span> <span data-ttu-id="6fe61-120">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="6fe61-120">You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="6fe61-121">度量</span><span class="sxs-lookup"><span data-stu-id="6fe61-121">Metrics</span></span>

<span data-ttu-id="6fe61-122">下表列出每個會話的診斷報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6fe61-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="6fe61-123">**診斷報告計量**</span><span class="sxs-lookup"><span data-stu-id="6fe61-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="6fe61-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="6fe61-124">**Name**</span></span>|<span data-ttu-id="6fe61-125">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="6fe61-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="6fe61-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="6fe61-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6fe61-127">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="6fe61-127">**Report time**</span></span> <br/> |<span data-ttu-id="6fe61-128">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-128">No</span></span>  <br/> |<span data-ttu-id="6fe61-129">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="6fe61-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="6fe61-130">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="6fe61-130">**Response code**</span></span> <br/> |<span data-ttu-id="6fe61-131">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-131">No</span></span>  <br/> |<span data-ttu-id="6fe61-132">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="6fe61-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="6fe61-133">**要求類型**</span><span class="sxs-lookup"><span data-stu-id="6fe61-133">**Request type**</span></span> <br/> |<span data-ttu-id="6fe61-134">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-134">No</span></span>  <br/> |<span data-ttu-id="6fe61-135">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="6fe61-135">SIP request type that failed.</span></span> <span data-ttu-id="6fe61-136">例如，邀請、再見或服務。</span><span class="sxs-lookup"><span data-stu-id="6fe61-136">For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="6fe61-137">**Source**</span><span class="sxs-lookup"><span data-stu-id="6fe61-137">**Source**</span></span> <br/> |<span data-ttu-id="6fe61-138">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-138">No</span></span>  <br/> |<span data-ttu-id="6fe61-139">錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="6fe61-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="6fe61-140">**從使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="6fe61-140">**From user URI**</span></span> <br/> |<span data-ttu-id="6fe61-141">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-141">No</span></span>  <br/> |<span data-ttu-id="6fe61-142">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="6fe61-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="6fe61-143">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="6fe61-143">**From user agent**</span></span> <br/> |<span data-ttu-id="6fe61-144">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-144">No</span></span>  <br/> |<span data-ttu-id="6fe61-145">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="6fe61-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="6fe61-146">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="6fe61-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="6fe61-147">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-147">No</span></span>  <br/> |<span data-ttu-id="6fe61-148">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="6fe61-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="6fe61-149">**內容類型**</span><span class="sxs-lookup"><span data-stu-id="6fe61-149">**Content type**</span></span> <br/> |<span data-ttu-id="6fe61-150">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-150">No</span></span>  <br/> |<span data-ttu-id="6fe61-151">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="6fe61-151">Type of media content that failed.</span></span> <span data-ttu-id="6fe61-152">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="6fe61-152">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="6fe61-153">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="6fe61-153">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="6fe61-154">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="6fe61-154">**Application**</span></span> <br/> |<span data-ttu-id="6fe61-155">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-155">No</span></span>  <br/> |<span data-ttu-id="6fe61-156">錯誤所涉及的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6fe61-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="6fe61-157">**至使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="6fe61-157">**To user URI**</span></span> <br/> |<span data-ttu-id="6fe61-158">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-158">No</span></span>  <br/> |<span data-ttu-id="6fe61-159">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="6fe61-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="6fe61-160">**會議加入時間 (毫秒)**</span><span class="sxs-lookup"><span data-stu-id="6fe61-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="6fe61-161">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-161">No</span></span>  <br/> |<span data-ttu-id="6fe61-162">使用者加入會議所需的時間（以毫秒為單位）)  (量。</span><span class="sxs-lookup"><span data-stu-id="6fe61-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="6fe61-163">**診斷標頭**</span><span class="sxs-lookup"><span data-stu-id="6fe61-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="6fe61-164">否</span><span class="sxs-lookup"><span data-stu-id="6fe61-164">No</span></span>  <br/> |<span data-ttu-id="6fe61-165">診斷識別碼描述。</span><span class="sxs-lookup"><span data-stu-id="6fe61-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="6fe61-166">您可以在 [Ms Diagnostics 頁首頁面](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)上找到診斷錯誤的清單。</span><span class="sxs-lookup"><span data-stu-id="6fe61-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3).</span></span>
