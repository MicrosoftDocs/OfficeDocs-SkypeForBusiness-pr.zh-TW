---
title: 商務用 Skype Server 中的診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 摘要：瞭解商務用 Skype 伺服器中的診斷報告。
ms.openlocfilehash: e8f89f1f5a013b40f7f5f105f49611542667a477
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817983"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="b682a-103">商務用 Skype Server 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="b682a-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="b682a-104">**摘要：** 瞭解商務用 Skype Server 中的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="b682a-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="b682a-105">診斷報告提供失敗會話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="b682a-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="b682a-106">此資訊包括在會話失敗時所報告的診斷 ID 和診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="b682a-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="b682a-107">診斷 ID 是附加至 SIP 訊息的唯一識別碼（以 ms 診斷標頭形式），而診斷標頭則提供診斷識別碼的隨附描述。</span><span class="sxs-lookup"><span data-stu-id="b682a-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="b682a-108">報告可能也包含報告元件已知的有用疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b682a-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="b682a-109">例如：</span><span class="sxs-lookup"><span data-stu-id="b682a-109">For example:</span></span>
  
- <span data-ttu-id="b682a-110">PSTN 閘道產生失敗時所提供的原因代碼。</span><span class="sxs-lookup"><span data-stu-id="b682a-110">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="b682a-111">PSTN 網路上的撥出電話失敗時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="b682a-111">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="b682a-112">例如，PSTN 閘道可能傳送原因碼 34，指出沒有電路或通道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="b682a-112">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="b682a-113">針對連接失敗的對等 FQDN、埠和 Winsock 錯誤。</span><span class="sxs-lookup"><span data-stu-id="b682a-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="b682a-114">尋找 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="b682a-114">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="b682a-115">只要用戶端與名稱伺服器聯絡，並要求對應至指定裝置名稱的 IP 位址，就會發生 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="b682a-115">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="b682a-116">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="b682a-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="b682a-117">按一下 [商務用 Skype 伺服器] 或 [會議詳細資料] 報表[中的點對點工作階段詳細資料包告](peer-to-peer-session-detail-report.md)上的 [診斷報告（詳細資料）] 度量，即可存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="b682a-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="b682a-118">濾鏡</span><span class="sxs-lookup"><span data-stu-id="b682a-118">Filters</span></span>

<span data-ttu-id="b682a-119">無。</span><span class="sxs-lookup"><span data-stu-id="b682a-119">None.</span></span> <span data-ttu-id="b682a-120">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="b682a-120">You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="b682a-121">指標</span><span class="sxs-lookup"><span data-stu-id="b682a-121">Metrics</span></span>

<span data-ttu-id="b682a-122">下表列出每個會話的診斷報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="b682a-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="b682a-123">**診斷報告度量單位**</span><span class="sxs-lookup"><span data-stu-id="b682a-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="b682a-124">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b682a-124">**Name**</span></span>|<span data-ttu-id="b682a-125">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="b682a-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="b682a-126">**說明**</span><span class="sxs-lookup"><span data-stu-id="b682a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b682a-127">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="b682a-127">**Report time**</span></span> <br/> |<span data-ttu-id="b682a-128">否</span><span class="sxs-lookup"><span data-stu-id="b682a-128">No</span></span>  <br/> |<span data-ttu-id="b682a-129">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b682a-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="b682a-130">**回應代碼**</span><span class="sxs-lookup"><span data-stu-id="b682a-130">**Response code**</span></span> <br/> |<span data-ttu-id="b682a-131">否</span><span class="sxs-lookup"><span data-stu-id="b682a-131">No</span></span>  <br/> |<span data-ttu-id="b682a-132">在會話失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="b682a-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="b682a-133">**要求類型**</span><span class="sxs-lookup"><span data-stu-id="b682a-133">**Request type**</span></span> <br/> |<span data-ttu-id="b682a-134">否</span><span class="sxs-lookup"><span data-stu-id="b682a-134">No</span></span>  <br/> |<span data-ttu-id="b682a-135">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="b682a-135">SIP request type that failed.</span></span> <span data-ttu-id="b682a-136">例如，[邀請]、[再見] 或 [服務]。</span><span class="sxs-lookup"><span data-stu-id="b682a-136">For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="b682a-137">**從源**</span><span class="sxs-lookup"><span data-stu-id="b682a-137">**Source**</span></span> <br/> |<span data-ttu-id="b682a-138">否</span><span class="sxs-lookup"><span data-stu-id="b682a-138">No</span></span>  <br/> |<span data-ttu-id="b682a-139">錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="b682a-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="b682a-140">**從使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="b682a-140">**From user URI**</span></span> <br/> |<span data-ttu-id="b682a-141">否</span><span class="sxs-lookup"><span data-stu-id="b682a-141">No</span></span>  <br/> |<span data-ttu-id="b682a-142">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b682a-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="b682a-143">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="b682a-143">**From user agent**</span></span> <br/> |<span data-ttu-id="b682a-144">否</span><span class="sxs-lookup"><span data-stu-id="b682a-144">No</span></span>  <br/> |<span data-ttu-id="b682a-145">啟動會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="b682a-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="b682a-146">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="b682a-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="b682a-147">否</span><span class="sxs-lookup"><span data-stu-id="b682a-147">No</span></span>  <br/> |<span data-ttu-id="b682a-148">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="b682a-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="b682a-149">**內容類型**</span><span class="sxs-lookup"><span data-stu-id="b682a-149">**Content type**</span></span> <br/> |<span data-ttu-id="b682a-150">否</span><span class="sxs-lookup"><span data-stu-id="b682a-150">No</span></span>  <br/> |<span data-ttu-id="b682a-151">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="b682a-151">Type of media content that failed.</span></span> <span data-ttu-id="b682a-152">例如，常見的內容類型是 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="b682a-152">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="b682a-153">會話描述通訊協定（SDP）是一種標準的網際網路通訊協定，用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</span><span class="sxs-lookup"><span data-stu-id="b682a-153">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="b682a-154">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="b682a-154">**Application**</span></span> <br/> |<span data-ttu-id="b682a-155">否</span><span class="sxs-lookup"><span data-stu-id="b682a-155">No</span></span>  <br/> |<span data-ttu-id="b682a-156">錯誤中涉及的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b682a-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="b682a-157">**使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="b682a-157">**To user URI**</span></span> <br/> |<span data-ttu-id="b682a-158">否</span><span class="sxs-lookup"><span data-stu-id="b682a-158">No</span></span>  <br/> |<span data-ttu-id="b682a-159">受邀者加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b682a-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="b682a-160">**會議加入時間（毫秒）**</span><span class="sxs-lookup"><span data-stu-id="b682a-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="b682a-161">否</span><span class="sxs-lookup"><span data-stu-id="b682a-161">No</span></span>  <br/> |<span data-ttu-id="b682a-162">使用者加入會議所需的時間量（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="b682a-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="b682a-163">**診斷標頭**</span><span class="sxs-lookup"><span data-stu-id="b682a-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="b682a-164">否</span><span class="sxs-lookup"><span data-stu-id="b682a-164">No</span></span>  <br/> |<span data-ttu-id="b682a-165">診斷識別碼描述。</span><span class="sxs-lookup"><span data-stu-id="b682a-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="b682a-166">您可以在[Ms Diagnostics 頁首頁面](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)找到診斷錯誤清單。</span><span class="sxs-lookup"><span data-stu-id="b682a-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).</span></span>
  

