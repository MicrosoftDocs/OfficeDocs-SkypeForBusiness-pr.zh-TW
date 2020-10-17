---
title: Lync Server 2013：通話診斷報告
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
ms.openlocfilehash: 46073c5540b0b4cd48f6c5a13c17d4a4d3f12a46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526330"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="5d7e6-102">在 Lync Server 2013 中呼叫診斷報告</span><span class="sxs-lookup"><span data-stu-id="5d7e6-102">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d7e6-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5d7e6-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5d7e6-104">通話診斷報告可提供失敗的對等和會議會話的摘要資訊和診斷資料。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d7e6-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5d7e6-105">In This Section</span></span>

  - <span data-ttu-id="5d7e6-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     中的通話診斷摘要報告提供失敗的點對點工作階段和會議會話的整體摘要。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="5d7e6-107">點對點工作階段是只涉及兩位參與者的會話。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="5d7e6-108">會議會話包含三個或多位參與者。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="5d7e6-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     中的 Peer-to-Peer 活動診斷報告提供失敗的點對點工作階段的整體趨勢視圖。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="5d7e6-110">點對點工作階段只涉及兩位參與者。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="5d7e6-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     中的會議診斷報告針對每個會議形式提供失敗會議會話和趨勢視圖的整體趨勢視圖。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="5d7e6-112">會議會話至少包含三個參與者。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="5d7e6-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)     的最大失敗報告提供最常見失敗及其隨時間變化的趨勢清單。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="5d7e6-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)     的失敗散佈報告提供失敗會話的分析。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="5d7e6-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)     的失敗清單報告提供有關失敗的會議中所涉及的個別參與者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="5d7e6-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)     中的診斷報告提供診斷及疑難排解資訊 (包括 SIP 回應碼和診斷標頭，以及失敗會話的 IDs) 。</span><span class="sxs-lookup"><span data-stu-id="5d7e6-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

