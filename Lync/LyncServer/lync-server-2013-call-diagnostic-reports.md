---
title: Lync Server 2013： 通話診斷報告
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
ms.openlocfilehash: 692c3e3baa564b2276be678b48e67b5f2a4abd56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="095d6-102">Lync Server 2013 中的通話診斷報告</span><span class="sxs-lookup"><span data-stu-id="095d6-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="095d6-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="095d6-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="095d6-104">通話診斷報告提供摘要資訊與診斷資料失敗-對等和會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="095d6-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="095d6-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="095d6-105">In This Section</span></span>

  - <span data-ttu-id="095d6-106">[Lync Server 2013 中通話診斷摘要報告](lync-server-2013-call-diagnostic-summary-report.md)   提供失敗對等工作階段和會議工作階段的整體摘要。</span><span class="sxs-lookup"><span data-stu-id="095d6-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="095d6-107">端對端工作階段所涉及僅由兩個參與者的工作階段。</span><span class="sxs-lookup"><span data-stu-id="095d6-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="095d6-108">會議工作階段涉及三個或更多位參與者。</span><span class="sxs-lookup"><span data-stu-id="095d6-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="095d6-109">[Lync Server 2013 中的對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   提供失敗對等工作階段的整體趨勢檢視。</span><span class="sxs-lookup"><span data-stu-id="095d6-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="095d6-110">端對端工作階段包括僅由兩個參與者。</span><span class="sxs-lookup"><span data-stu-id="095d6-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="095d6-111">[Lync Server 2013 中的會議診斷報告](lync-server-2013-conference-diagnostic-report.md)   提供每個會議形式區分的失敗的會議工作階段的整體趨勢檢視和趨勢檢視。</span><span class="sxs-lookup"><span data-stu-id="095d6-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="095d6-112">會議工作階段涉及三個以上的參與者。</span><span class="sxs-lookup"><span data-stu-id="095d6-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="095d6-113">[最大失敗報告在 Lync Server 2013 中](lync-server-2013-top-failures-report.md)   經過一段時間提供最常見的失敗和其趨勢的清單。</span><span class="sxs-lookup"><span data-stu-id="095d6-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="095d6-114">[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)   提供失敗工作階段的分析。</span><span class="sxs-lookup"><span data-stu-id="095d6-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="095d6-115">[Lync Server 2013 中的失敗清單報告](lync-server-2013-failure-list-report.md)   提供關於失敗會議中個別參與者的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="095d6-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="095d6-116">[Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)   ： 提供診斷和疑難排解資訊 （包括 SIP 回應碼和診斷標頭及識別碼） 的失敗工作階段。</span><span class="sxs-lookup"><span data-stu-id="095d6-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

