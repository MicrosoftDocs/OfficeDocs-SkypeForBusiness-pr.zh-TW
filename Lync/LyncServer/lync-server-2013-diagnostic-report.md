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
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="5f5a7-102">Lync Server 2013 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="5f5a7-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f5a7-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="5f5a7-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="5f5a7-104">診斷報告提供失敗會話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="5f5a7-105">此資訊包括在會話失敗時所報告的診斷 ID 和診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="5f5a7-106">診斷 ID 是附加至 SIP 訊息的唯一識別碼（以 ms 診斷標頭形式），而診斷標頭則提供診斷識別碼的隨附描述。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="5f5a7-107">報告可能也包含報告元件已知的有用疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="5f5a7-108">例如：</span><span class="sxs-lookup"><span data-stu-id="5f5a7-108">For example:</span></span>

  - <span data-ttu-id="5f5a7-109">PSTN 閘道產生失敗時所提供的原因代碼。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="5f5a7-110">PSTN 網路上的撥出電話失敗時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="5f5a7-111">例如，PSTN 閘道可能傳送原因碼 34，指出沒有電路或通道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="5f5a7-112">針對連接失敗的對等 FQDN、埠和 Winsock 錯誤。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="5f5a7-113">尋找 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="5f5a7-114">只要用戶端與名稱伺服器聯絡，並要求對應至指定裝置名稱的 IP 位址，就會發生 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="5f5a7-115">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="5f5a7-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="5f5a7-116">您可以透過在 Lync Server 2013 或會議詳細資料包表中，按一下[點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)上的診斷報告（詳細資料）度量來存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5f5a7-117">濾鏡</span><span class="sxs-lookup"><span data-stu-id="5f5a7-117">Filters</span></span>

<span data-ttu-id="5f5a7-118">無。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-118">None.</span></span> <span data-ttu-id="5f5a7-119">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5f5a7-120">指標</span><span class="sxs-lookup"><span data-stu-id="5f5a7-120">Metrics</span></span>

<span data-ttu-id="5f5a7-121">下表列出每個會話的診斷報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="5f5a7-122">診斷報告度量單位</span><span class="sxs-lookup"><span data-stu-id="5f5a7-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f5a7-123">名稱</span><span class="sxs-lookup"><span data-stu-id="5f5a7-123">Name</span></span></th>
<th><span data-ttu-id="5f5a7-124">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="5f5a7-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5f5a7-125">說明</span><span class="sxs-lookup"><span data-stu-id="5f5a7-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-126"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-127">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-127">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-128">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-129"><strong>回應代碼</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-130">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-130">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-131">在會話失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-132"><strong>要求類型</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-133">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-133">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-134">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-134">SIP request type that failed.</span></span> <span data-ttu-id="5f5a7-135">例如，[邀請]、[再見] 或 [服務]。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-136"><strong>從源</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-137">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-137">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-138">錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-139"><strong>從使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-140">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-140">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-141">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-142"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-143">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-143">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-144">啟動會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-145"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-146">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-146">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-147">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-148"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-149">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-149">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-150">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-150">Type of media content that failed.</span></span> <span data-ttu-id="5f5a7-151">例如，常見的內容類型是 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="5f5a7-152">會話描述通訊協定（SDP）是一種標準的網際網路通訊協定，用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-153"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-154">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-154">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-155">錯誤中涉及的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-156"><strong>使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-157">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-157">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-158">受邀者加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5a7-159">會議加入時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="5f5a7-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-160">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-160">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-161">使用者加入會議所需的時間量（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5a7-162"><strong>診斷標頭</strong></span><span class="sxs-lookup"><span data-stu-id="5f5a7-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5a7-163">否</span><span class="sxs-lookup"><span data-stu-id="5f5a7-163">No</span></span></p></td>
<td><p><span data-ttu-id="5f5a7-164">診斷識別碼描述。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f5a7-165">您可以在[Ms Diagnostics 頁首頁面](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)找到診斷錯誤清單。</span><span class="sxs-lookup"><span data-stu-id="5f5a7-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

