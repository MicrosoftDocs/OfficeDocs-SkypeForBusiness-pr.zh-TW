---
title: Lync Server 2013： 診斷報告
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
ms.openlocfilehash: 3e95d746d323e803bf7dbc37e8cdaebcdd1d655c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="4dc5f-102">Lync Server 2013 中的診斷報告</span><span class="sxs-lookup"><span data-stu-id="4dc5f-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc5f-103">_**上次修改主題：** 2014年-02-07_</span><span class="sxs-lookup"><span data-stu-id="4dc5f-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="4dc5f-104">診斷報告提供失敗工作階段的診斷與疑難排解的資訊。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="4dc5f-105">此資訊包括診斷識別碼及工作階段失敗時，所報告的診斷標頭。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="4dc5f-106">診斷識別碼是取得附加至 SIP 郵件，而診斷標頭提供隨附的說明診斷識別碼的唯一識別碼 （以毫秒診斷標頭的形式）</span><span class="sxs-lookup"><span data-stu-id="4dc5f-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="4dc5f-107">報告也可能包含重要已知的報告元件的疑難排解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="4dc5f-108">例如：</span><span class="sxs-lookup"><span data-stu-id="4dc5f-108">For example:</span></span>

  - <span data-ttu-id="4dc5f-109">原因程式碼提供者產生失敗的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="4dc5f-110">PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="4dc5f-111">例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="4dc5f-112">對等 FQDN、 連接埠與 Winsock 錯誤的連線失敗。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="4dc5f-113">正在進行查閱 DNS 解析失敗的名稱。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="4dc5f-114">DNS 解析任何用戶端的連絡人名稱伺服器的時間，並要求的 IP 位址會對應至指定的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="4dc5f-115">存取診斷報告</span><span class="sxs-lookup"><span data-stu-id="4dc5f-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="4dc5f-116">可以按一下 [ [Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)] 或 [會議詳細資料報表上的 [診斷報告 （詳細資料）] 計量來存取診斷報告。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4dc5f-117">篩選</span><span class="sxs-lookup"><span data-stu-id="4dc5f-117">Filters</span></span>

<span data-ttu-id="4dc5f-118">無。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-118">None.</span></span> <span data-ttu-id="4dc5f-119">您無法篩選診斷報告。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4dc5f-120">計量</span><span class="sxs-lookup"><span data-stu-id="4dc5f-120">Metrics</span></span>

<span data-ttu-id="4dc5f-121">下表列出診斷報告針對每個工作階段所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="4dc5f-122">診斷報告計量</span><span class="sxs-lookup"><span data-stu-id="4dc5f-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dc5f-123">名稱</span><span class="sxs-lookup"><span data-stu-id="4dc5f-123">Name</span></span></th>
<th><span data-ttu-id="4dc5f-124">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="4dc5f-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4dc5f-125">說明</span><span class="sxs-lookup"><span data-stu-id="4dc5f-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-126"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-127">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-127">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-128">日期和時間報告的記錄。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-129"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-130">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-130">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-131">SIP 工作階段失敗時傳送的回應碼。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-132"><strong>要求類型</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-133">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-133">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-134">SIP 失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-134">SIP request type that failed.</span></span> <span data-ttu-id="4dc5f-135">例如，邀請、 BYE 或服務。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-137">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-137">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-138">錯誤的來源。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-139"><strong>來源使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-140">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-140">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-141">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-142"><strong>來源使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-143">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-143">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-144">起始工作階段之使用者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-145"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-146">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-146">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-147">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-148"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-149">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-149">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-150">失敗的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-150">Type of media content that failed.</span></span> <span data-ttu-id="4dc5f-151">例如，常見的內容類型是應用程式/sdp。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="4dc5f-152">工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-153"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-154">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-154">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-155">應用程式發生錯誤的。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-156"><strong>目標使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-157">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-157">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-158">獲邀加入工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc5f-159">會議加入時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="4dc5f-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-160">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-160">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-161">量花使用者加入會議的時間 （以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc5f-162"><strong>診斷標頭</strong></span><span class="sxs-lookup"><span data-stu-id="4dc5f-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc5f-163">否</span><span class="sxs-lookup"><span data-stu-id="4dc5f-163">No</span></span></p></td>
<td><p><span data-ttu-id="4dc5f-164">診斷識別碼的描述。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4dc5f-165">[Ms-diagnostics 標頭] 頁面](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上，可以找到診斷錯誤清單。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

