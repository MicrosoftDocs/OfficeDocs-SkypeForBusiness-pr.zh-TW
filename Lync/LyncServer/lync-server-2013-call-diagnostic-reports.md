---
title: Lync Server 2013：呼叫診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="93a9e-102">在 Lync Server 2013 中呼叫診斷報告</span><span class="sxs-lookup"><span data-stu-id="93a9e-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93a9e-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="93a9e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="93a9e-104">通話診斷報告提供失敗的對等與會議會話的摘要資訊與診斷資料。</span><span class="sxs-lookup"><span data-stu-id="93a9e-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93a9e-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="93a9e-105">In This Section</span></span>

  - <span data-ttu-id="93a9e-106">[在 Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   中呼叫診斷摘要報告，提供失敗的點對點工作階段及會議會話的整體摘要。</span><span class="sxs-lookup"><span data-stu-id="93a9e-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="93a9e-107">點對點工作階段是只涉及兩個參與者的會話。</span><span class="sxs-lookup"><span data-stu-id="93a9e-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="93a9e-108">會議會話涉及三個或更多參與者。</span><span class="sxs-lookup"><span data-stu-id="93a9e-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="93a9e-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   的對等活動診斷報告提供失敗的點對點工作階段的整體趨勢視圖。</span><span class="sxs-lookup"><span data-stu-id="93a9e-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="93a9e-110">點對點工作階段只涉及兩個參與者。</span><span class="sxs-lookup"><span data-stu-id="93a9e-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="93a9e-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   中的 [會議診斷報告] 可為每個會議模式提供失敗會議會話和趨勢視圖的整體趨勢視圖。</span><span class="sxs-lookup"><span data-stu-id="93a9e-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="93a9e-112">會議會話至少包含三個參與者。</span><span class="sxs-lookup"><span data-stu-id="93a9e-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="93a9e-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)   中的 [熱門失敗] 報告，提供最常見的失敗及其趨勢的清單。</span><span class="sxs-lookup"><span data-stu-id="93a9e-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="93a9e-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)   中的 [失敗的發佈報告] 可分析失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="93a9e-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="93a9e-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)   中的 [失敗清單] 報告，提供關於失敗的會議中所涉及的個別參與者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="93a9e-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="93a9e-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)   中的 [診斷報告] 可為失敗的會話提供診斷和疑難排解資訊（包括 SIP 回應代碼及診斷標頭和識別碼）。</span><span class="sxs-lookup"><span data-stu-id="93a9e-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

