---
title: Skype for Business Server 的診斷報告
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
description: 摘要： 了解 skype for Business Server 診斷報告。
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041990"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="94a5b-103">Skype for Business Server 的診斷報告</span><span class="sxs-lookup"><span data-stu-id="94a5b-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="94a5b-104">**摘要：** 了解 skype for Business Server 診斷報告。</span><span class="sxs-lookup"><span data-stu-id="94a5b-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="94a5b-105">診斷報告提供失敗工作階段的診斷與疑難排解的資訊。</span><span class="sxs-lookup"><span data-stu-id="94a5b-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="94a5b-106">此資訊包括診斷識別碼及工作階段失敗時，所報告的診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="94a5b-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="94a5b-107">診斷識別碼是取得附加至 SIP 郵件，而診斷標頭提供隨附的說明診斷識別碼的唯一識別碼 （以毫秒診斷標頭的形式）</span><span class="sxs-lookup"><span data-stu-id="94a5b-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="94a5b-108">報告也可能包含重要已知的報告元件的疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="94a5b-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="94a5b-109">例如：</span><span class="sxs-lookup"><span data-stu-id="94a5b-109">For example:</span></span>
  
- <span data-ttu-id="94a5b-110">原因程式碼提供者產生失敗的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="94a5b-110">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="94a5b-111">PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="94a5b-111">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="94a5b-112">例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="94a5b-112">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="94a5b-113">對等 FQDN、 連接埠與 Winsock 錯誤的連線失敗。</span><span class="sxs-lookup"><span data-stu-id="94a5b-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="94a5b-114">正在進行查閱 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="94a5b-114">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="94a5b-115">DNS 解析任何用戶端的連絡人名稱伺服器的時間，並要求的 IP 位址會對應至指定的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="94a5b-115">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="94a5b-116">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="94a5b-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="94a5b-117">可以按一下[skype for Business 伺服器端對端工作階段詳細資料報表](peer-to-peer-session-detail-report.md)或會議詳細資料報表上的 [診斷報告 （詳細資料）] 計量來存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="94a5b-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="94a5b-118">篩選</span><span class="sxs-lookup"><span data-stu-id="94a5b-118">Filters</span></span>

<span data-ttu-id="94a5b-119">無。</span><span class="sxs-lookup"><span data-stu-id="94a5b-119">None.</span></span> <span data-ttu-id="94a5b-120">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="94a5b-120">You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="94a5b-121">計量</span><span class="sxs-lookup"><span data-stu-id="94a5b-121">Metrics</span></span>

<span data-ttu-id="94a5b-122">下表列出診斷報告針對每個工作階段所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="94a5b-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="94a5b-123">**診斷報告計量**</span><span class="sxs-lookup"><span data-stu-id="94a5b-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="94a5b-124">**名稱**</span><span class="sxs-lookup"><span data-stu-id="94a5b-124">**Name**</span></span>|<span data-ttu-id="94a5b-125">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="94a5b-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="94a5b-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="94a5b-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94a5b-127">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="94a5b-127">**Report time**</span></span> <br/> |<span data-ttu-id="94a5b-128">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-128">No</span></span>  <br/> |<span data-ttu-id="94a5b-129">日期和時間報告的記錄。</span><span class="sxs-lookup"><span data-stu-id="94a5b-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="94a5b-130">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="94a5b-130">**Response code**</span></span> <br/> |<span data-ttu-id="94a5b-131">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-131">No</span></span>  <br/> |<span data-ttu-id="94a5b-132">SIP 工作階段失敗時傳送的回應碼。</span><span class="sxs-lookup"><span data-stu-id="94a5b-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="94a5b-133">**要求類型**</span><span class="sxs-lookup"><span data-stu-id="94a5b-133">**Request type**</span></span> <br/> |<span data-ttu-id="94a5b-134">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-134">No</span></span>  <br/> |<span data-ttu-id="94a5b-135">SIP 失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="94a5b-135">SIP request type that failed.</span></span> <span data-ttu-id="94a5b-136">例如，邀請、 BYE 或服務。</span><span class="sxs-lookup"><span data-stu-id="94a5b-136">For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="94a5b-137">**Source**</span><span class="sxs-lookup"><span data-stu-id="94a5b-137">**Source**</span></span> <br/> |<span data-ttu-id="94a5b-138">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-138">No</span></span>  <br/> |<span data-ttu-id="94a5b-139">錯誤的來源。</span><span class="sxs-lookup"><span data-stu-id="94a5b-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="94a5b-140">**來源使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="94a5b-140">**From user URI**</span></span> <br/> |<span data-ttu-id="94a5b-141">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-141">No</span></span>  <br/> |<span data-ttu-id="94a5b-142">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="94a5b-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="94a5b-143">**來源使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="94a5b-143">**From user agent**</span></span> <br/> |<span data-ttu-id="94a5b-144">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-144">No</span></span>  <br/> |<span data-ttu-id="94a5b-145">起始工作階段之使用者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="94a5b-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="94a5b-146">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="94a5b-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="94a5b-147">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-147">No</span></span>  <br/> |<span data-ttu-id="94a5b-148">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="94a5b-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="94a5b-149">**內容類型**</span><span class="sxs-lookup"><span data-stu-id="94a5b-149">**Content type**</span></span> <br/> |<span data-ttu-id="94a5b-150">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-150">No</span></span>  <br/> |<span data-ttu-id="94a5b-151">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="94a5b-151">Type of media content that failed.</span></span> <span data-ttu-id="94a5b-152">例如，常見的內容類型是應用程式/sdp。</span><span class="sxs-lookup"><span data-stu-id="94a5b-152">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="94a5b-153">工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="94a5b-153">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="94a5b-154">**Application**</span><span class="sxs-lookup"><span data-stu-id="94a5b-154">**Application**</span></span> <br/> |<span data-ttu-id="94a5b-155">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-155">No</span></span>  <br/> |<span data-ttu-id="94a5b-156">應用程式發生錯誤的。</span><span class="sxs-lookup"><span data-stu-id="94a5b-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="94a5b-157">**目標使用者 URI**</span><span class="sxs-lookup"><span data-stu-id="94a5b-157">**To user URI**</span></span> <br/> |<span data-ttu-id="94a5b-158">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-158">No</span></span>  <br/> |<span data-ttu-id="94a5b-159">獲邀加入工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="94a5b-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="94a5b-160">**會議加入時間 （毫秒）**</span><span class="sxs-lookup"><span data-stu-id="94a5b-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="94a5b-161">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-161">No</span></span>  <br/> |<span data-ttu-id="94a5b-162">量花使用者加入會議的時間 （以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="94a5b-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="94a5b-163">**診斷標頭**</span><span class="sxs-lookup"><span data-stu-id="94a5b-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="94a5b-164">否</span><span class="sxs-lookup"><span data-stu-id="94a5b-164">No</span></span>  <br/> |<span data-ttu-id="94a5b-165">診斷識別碼的描述。</span><span class="sxs-lookup"><span data-stu-id="94a5b-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="94a5b-166">[Ms-diagnostics 標頭] 頁面](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx)上，可以找到診斷錯誤清單。</span><span class="sxs-lookup"><span data-stu-id="94a5b-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx).</span></span>
  

