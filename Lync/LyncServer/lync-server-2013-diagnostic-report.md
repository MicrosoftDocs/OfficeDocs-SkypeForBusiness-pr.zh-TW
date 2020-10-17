---
title: Lync Server 2013：診斷報告
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
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514490"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="58a12-102">Lync Server 2013 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="58a12-102">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58a12-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="58a12-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="58a12-104">診斷報告可提供失敗會話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="58a12-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="58a12-105">此資訊包含會話失敗時所報告的診斷識別碼和診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="58a12-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="58a12-106">診斷 ID 是與 SIP 郵件相連的 ms diagnostics 標頭) 形式的唯一識別碼 (，而診斷標頭則提供診斷識別碼的附帶描述。</span><span class="sxs-lookup"><span data-stu-id="58a12-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="58a12-107">報告可能也包含報告元件所知道的有用疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="58a12-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="58a12-108">例如：</span><span class="sxs-lookup"><span data-stu-id="58a12-108">For example:</span></span>

  - <span data-ttu-id="58a12-109">產生失敗之 PSTN 閘道所提供的原因碼。</span><span class="sxs-lookup"><span data-stu-id="58a12-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="58a12-110">PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="58a12-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="58a12-111">例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="58a12-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="58a12-112">連接失敗的對等 FQDN、埠和 Winsock 錯誤。</span><span class="sxs-lookup"><span data-stu-id="58a12-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="58a12-113">要尋找以進行 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="58a12-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="58a12-114">DNS 解析會在用戶端接觸名稱伺服器時進行，並要求對應至指定裝置名稱的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58a12-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="58a12-115">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="58a12-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="58a12-116">您可以在 Lync Server 2013 或會議詳細資料包告的 [ [Peer-to-Peer 會話詳細資料](lync-server-2013-peer-to-peer-session-detail-report.md) ] 報告中，按一下 [診斷報告] (詳細資料) 指標，即可存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="58a12-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="58a12-117">篩選</span><span class="sxs-lookup"><span data-stu-id="58a12-117">Filters</span></span>

<span data-ttu-id="58a12-118">無。</span><span class="sxs-lookup"><span data-stu-id="58a12-118">None.</span></span> <span data-ttu-id="58a12-119">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="58a12-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="58a12-120">指標</span><span class="sxs-lookup"><span data-stu-id="58a12-120">Metrics</span></span>

<span data-ttu-id="58a12-121">下表列出每個會話的診斷報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="58a12-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="58a12-122">診斷報告計量</span><span class="sxs-lookup"><span data-stu-id="58a12-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58a12-123">姓名</span><span class="sxs-lookup"><span data-stu-id="58a12-123">Name</span></span></th>
<th><span data-ttu-id="58a12-124">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="58a12-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="58a12-125">描述</span><span class="sxs-lookup"><span data-stu-id="58a12-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58a12-126"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-127">否</span><span class="sxs-lookup"><span data-stu-id="58a12-127">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-128">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="58a12-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-129"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-130">否</span><span class="sxs-lookup"><span data-stu-id="58a12-130">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-131">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="58a12-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a12-132"><strong>要求類型</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-133">否</span><span class="sxs-lookup"><span data-stu-id="58a12-133">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-134">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="58a12-134">SIP request type that failed.</span></span> <span data-ttu-id="58a12-135">例如，邀請、再見或服務。</span><span class="sxs-lookup"><span data-stu-id="58a12-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-137">否</span><span class="sxs-lookup"><span data-stu-id="58a12-137">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-138">錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="58a12-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a12-139"><strong>從使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-140">否</span><span class="sxs-lookup"><span data-stu-id="58a12-140">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-141">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="58a12-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-142"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-143">否</span><span class="sxs-lookup"><span data-stu-id="58a12-143">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-144">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="58a12-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a12-145"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-146">否</span><span class="sxs-lookup"><span data-stu-id="58a12-146">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-147">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="58a12-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-148"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-149">否</span><span class="sxs-lookup"><span data-stu-id="58a12-149">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-150">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="58a12-150">Type of media content that failed.</span></span> <span data-ttu-id="58a12-151">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="58a12-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="58a12-152">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="58a12-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a12-153"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-154">否</span><span class="sxs-lookup"><span data-stu-id="58a12-154">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-155">錯誤所涉及的應用程式。</span><span class="sxs-lookup"><span data-stu-id="58a12-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-156"><strong>至使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-157">否</span><span class="sxs-lookup"><span data-stu-id="58a12-157">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-158">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="58a12-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a12-159">會議加入時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="58a12-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="58a12-160">否</span><span class="sxs-lookup"><span data-stu-id="58a12-160">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-161">使用者加入會議所需的時間（以毫秒為單位）)  (量。</span><span class="sxs-lookup"><span data-stu-id="58a12-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a12-162"><strong>診斷標頭</strong></span><span class="sxs-lookup"><span data-stu-id="58a12-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="58a12-163">否</span><span class="sxs-lookup"><span data-stu-id="58a12-163">No</span></span></p></td>
<td><p><span data-ttu-id="58a12-164">診斷識別碼描述。</span><span class="sxs-lookup"><span data-stu-id="58a12-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58a12-165">您可以在 [Ms Diagnostics 頁首頁面](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上找到診斷錯誤的清單。</span><span class="sxs-lookup"><span data-stu-id="58a12-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

