---
title: Lync Server 2013：診斷報告
description: Lync Server 2013：診斷報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576249"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="bdffb-103">Lync Server 2013 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="bdffb-103">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdffb-104">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="bdffb-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="bdffb-105">診斷報告可提供失敗會話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="bdffb-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="bdffb-106">此資訊包含會話失敗時所報告的診斷識別碼和診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="bdffb-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="bdffb-107">診斷 ID 是與 SIP 郵件相連的 ms diagnostics 標頭) 形式的唯一識別碼 (，而診斷標頭則提供診斷識別碼的附帶描述。</span><span class="sxs-lookup"><span data-stu-id="bdffb-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="bdffb-108">報告可能也包含報告元件所知道的有用疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bdffb-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="bdffb-109">例如：</span><span class="sxs-lookup"><span data-stu-id="bdffb-109">For example:</span></span>

  - <span data-ttu-id="bdffb-110">產生失敗之 PSTN 閘道所提供的原因碼。</span><span class="sxs-lookup"><span data-stu-id="bdffb-110">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="bdffb-111">PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="bdffb-111">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="bdffb-112">例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="bdffb-112">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="bdffb-113">連接失敗的對等 FQDN、埠和 Winsock 錯誤。</span><span class="sxs-lookup"><span data-stu-id="bdffb-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="bdffb-114">要尋找以進行 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="bdffb-114">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="bdffb-115">DNS 解析會在用戶端接觸名稱伺服器時進行，並要求對應至指定裝置名稱的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bdffb-115">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="bdffb-116">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="bdffb-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="bdffb-117">您可以在 Lync Server 2013 或會議詳細資料包告的 [ [Peer-to-Peer 會話詳細資料](lync-server-2013-peer-to-peer-session-detail-report.md) ] 報告中，按一下 [診斷報告] (詳細資料) 指標，即可存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="bdffb-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bdffb-118">篩選</span><span class="sxs-lookup"><span data-stu-id="bdffb-118">Filters</span></span>

<span data-ttu-id="bdffb-119">無。</span><span class="sxs-lookup"><span data-stu-id="bdffb-119">None.</span></span> <span data-ttu-id="bdffb-120">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="bdffb-120">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="bdffb-121">指標</span><span class="sxs-lookup"><span data-stu-id="bdffb-121">Metrics</span></span>

<span data-ttu-id="bdffb-122">下表列出每個會話的診斷報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bdffb-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="bdffb-123">診斷報告計量</span><span class="sxs-lookup"><span data-stu-id="bdffb-123">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdffb-124">姓名</span><span class="sxs-lookup"><span data-stu-id="bdffb-124">Name</span></span></th>
<th><span data-ttu-id="bdffb-125">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bdffb-125">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bdffb-126">描述</span><span class="sxs-lookup"><span data-stu-id="bdffb-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-127"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-127"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-128">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-128">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-129">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="bdffb-129">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-130"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-130"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-131">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-131">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-132">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="bdffb-132">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-133"><strong>要求類型</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-133"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-134">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-134">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-135">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="bdffb-135">SIP request type that failed.</span></span> <span data-ttu-id="bdffb-136">例如，邀請、再見或服務。</span><span class="sxs-lookup"><span data-stu-id="bdffb-136">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-137"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-137"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-138">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-138">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-139">錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="bdffb-139">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-140"><strong>從使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-140"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-141">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-141">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-142">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="bdffb-142">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-143"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-143"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-144">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-144">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-145">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="bdffb-145">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-146"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-146"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-147">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-147">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-148">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="bdffb-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-149"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-149"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-150">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-150">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-151">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="bdffb-151">Type of media content that failed.</span></span> <span data-ttu-id="bdffb-152">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="bdffb-152">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="bdffb-153">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="bdffb-153">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-154"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-154"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-155">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-155">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-156">錯誤所涉及的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bdffb-156">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-157"><strong>至使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-157"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-158">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-158">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-159">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="bdffb-159">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdffb-160">會議加入時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="bdffb-160">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="bdffb-161">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-161">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-162">使用者加入會議所需的時間（以毫秒為單位）)  (量。</span><span class="sxs-lookup"><span data-stu-id="bdffb-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdffb-163"><strong>診斷標頭</strong></span><span class="sxs-lookup"><span data-stu-id="bdffb-163"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="bdffb-164">否</span><span class="sxs-lookup"><span data-stu-id="bdffb-164">No</span></span></p></td>
<td><p><span data-ttu-id="bdffb-165">診斷識別碼描述。</span><span class="sxs-lookup"><span data-stu-id="bdffb-165">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bdffb-166">您可以在 [Ms Diagnostics 頁首頁面](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上找到診斷錯誤的清單。</span><span class="sxs-lookup"><span data-stu-id="bdffb-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

